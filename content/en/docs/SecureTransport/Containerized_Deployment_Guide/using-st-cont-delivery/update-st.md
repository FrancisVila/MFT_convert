{
    "title": "Update the deployment",
    "linkTitle": "Update the deployment",
    "weight": "120"
}SecureTransport update in the context of Docker deployment means upgrade for the database only, since all the binaries are added to the respective SecureTransport image.

In case the update process does not complete successfully, a roll-back procedure is automatically executed in order to revert database changes.

## Docker update workflow

When starting the container, the docker-installer executes normal Docker installation procedures. When all of them are done, then the installer searches for update files. If this file exists, then the Docker installer proceeds with applying the update procedures.

### Docker update steps

> **Note:**
>
> Before you proceed, delete the Horizontal Pod Autoscaler if any is deployed.

1.  Scale down docker containers to 0 nodes or delete the deployment.  
      
2.  Back up your databases.  
      
3.  If performance tuning is applied and any of the following files are tuned: `hibernate-cache-config.xml, scheduler.properties, coherence-cache-config-tm.xml`, please make sure that your customized files are synchronized with the latest default files shipped with the new SecureTransport image.  
      
4.  Load the SecureTransport images containing the update in Docker engine on all machines.  
    **Note**: If you are changing the image of Edge
    -   from SecureTransport\_5.5-20210624\_DockerImage\_edge or previous  
    -   to SecureTransport\_5.5-20210729\_DockerImage\_edge or later

    please keep in mind that SecureTransport should operate with **MariaDB** as of SecureTransport\_5.5-20210729\_DockerImage\_edge onwards.  
    If this is **not** your case, please skip to **step 5**.  
    **If this is your case**,
    please follow the below procedure to migrate your data to MariaDB. Supported version is 10.4.19.
    1.  Export database from MySQL instance:  
        `mysqldump -u root -p`*&lt;databasePassword>* `--databases` *&lt;databaseName>* `>` *&lt;dump\_file\_path>*`/`*&lt;dump\_file\_name>*`.sql`

    2.  Create user and import database in the MariaDB instance:  
        `mariadb -u root -p`*&lt;databasePassword>* `--database` *&lt;databaseName>* `<` *&lt;dump\_file\_path>*`/`*&lt;dump\_file\_name>*`.sql`

    3.  Edit `db.conf `file to point to the new MariaDB service. The db.type property should be changed to 'internaldb'

    4.  Delete and recreate the kubernetes secret created in step 5f of in [Initial deployment](../initial-deployment) > Deploying SecureTransport Edge

    5.  Restart all the containers from the ST Edge statefulset  
          
5.  Modify the image tag in the Kubernetes configuration files. (`st-server-kubernetes.yml, st-edge-kubernetes.yml`)  
      
6.  Execute the following command for both Server and Edge: `kubectl apply -f <st-kubernetes-configuration-file>`  
      
7.  Check the logs for information.  
      
8.  After the successful deployment of the new image, scale up to needed number of nodes.

## Rollback procedure

In case the update process does not complete successfully, the rollback procedure is triggered. Its purpose is to revert all changes made in the database during the update attempt. The rollback logic is the same as the logic for removing an update.

**Important!** After applying an update, you can no longer revert to previous versions.

*next topic:* [Known limitations and deployment specifics](../../k8s-known-issues)
