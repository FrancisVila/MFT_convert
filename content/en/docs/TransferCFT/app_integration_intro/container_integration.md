{
    "title": "Integrate a containerized application",
    "linkTitle": "Containerized application integration",
    "weight": "200"
}This page is intended to help you understand the various ways to use Transfer CFT and associated applications in a container environment, providing a high level overview of the possible integration architectures.

You may want to review the two methods  for installing and operating a containerized <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>, using either [Docker Compose or Kubernetes with Helm](../../cft_intro_install/install_container).

## Kubernetes concepts

Nodes

Kubernetes runs your workload by placing containers into Pods to run on Nodes. A node may be a virtual or physical machine, depending on the cluster. Each node contains the services necessary to run Pods, managed by the control plane.

Typically you have several nodes in a cluster; in a learning or resource-limited environment, you might have just one.

Pods

Pods are the smallest deployable units of computing that you can create and manage in Kubernetes.

A Pod is a group of one or more containers, with shared storage/network resources, and a specification for how to run the containers. A Pod's contents are always co-located and co-scheduled, and run in a shared context. A Pod models an application-specific "logical host": it contains one or more application containers that are relatively tightly coupled. In non-cloud contexts, applications executed on the same physical or virtual machine are analogous to cloud applications executed on the same logical host.

Definitions are provided by Kubernetes at: [https://kubernetes.io/docs/concepts](https://kubernetes.io/docs/concepts/)

## Producer/consumer application integration

Your producer/consumer application integration with Transfer CFT is based on:

-   File storage: Where and how files transferred by Transfer CFT are shared with the application
-   Transfer triggering: How the application triggers a transfer request
-   Post-processing: How Transfer CFT handles post-processing

### File storage

There are 3 possible file storage implementations when you have Transfer CFT as a container along with a producer/consumer application.

#### <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> is the application sidecar

The application and <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> run in the same pod but in different containers. Both the data produced/consumed by the application and <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> reside on a persistent volume attached to a node where the pod is running. The persistent volume supports ReadWriteOnce access mode and is a local volume (AWS ESB, GCEPersistentDisk, AzureDisk).

<span class="autonumber"></span>Sidecar architecture                     <img src="/Images/TransferCFT/pod1.png" class="maxWidth" />

#### <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> and the application run on different pods but on the same node

The application and <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> run on different pods on the same node. If using a local volume, both pods must run on the same node. Both the data produced and consumed by the application and <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> reside on a persistent volume attached to the node where the pods are running. The persistent volume supports ReadWriteOnce access mode, and is a local volume (AWS ESB, GCEPersistentDisk, AzureDisk).

<span class="autonumber"></span>Two pods one node architecture            <img src="/Images/TransferCFT/pod2.png" class="maxWidth" />

<span class="autonumber"></span> 

<span id="__RefHeading___Toc2647_2515630742"></span>

#### <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> and the application run on different nodes

The application and <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> run on different nodes both of which support the **ReadWriteMany** access mode, where:

-   The Transfer CFT data resides on a persistent volume that can be a shared volume (Ceph, GlusterFS, NFS, ...).
-   The data produced and consumed by the application resides on a persistent volume that can be a shared volume (Ceph, GlusterFS, NFS, ...) or cloud storage (AWS S3, GCS). In this implementation, you configure the cloud storage at the flow deployment level, not in the product deployment.

<span class="autonumber"></span>Two pods two nodes architecture                    <img src="/Images/TransferCFT/pod3.png" class="maxWidth" />

<span id="__RefHeading___Toc2649_2515630742"></span>

####  Architecture versus file storage summary

<table>
   <th>
      <tr>
<th><p>Architecture</p>         </th>
<th><p>Local volume</p>         </th>
<th><p>Shared volume</p>         </th>
<th><p>Cloud storage</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1. Same pod</p>         </td>
         <td><p>yes</p>         </td>
         <td><p>yes</p>         </td>
         <td><p>yes</p>         </td>
      </tr>
      <tr>
         <td><p>2. Two pods on the same node</p>         </td>
         <td><p>yes</p>         </td>
         <td><p>yes</p>         </td>
         <td><p>yes</p>         </td>
      </tr>
      <tr>
         <td><p>3. Two pods regardless of the running node</p>         </td>
         <td><p>no</p>         </td>
         <td><p>yes</p>         </td>
         <td><p>yes</p>         </td>
      </tr>
   </tbody>
</table>

### Transfer triggering

In a standard environment, on bare metal, or virtual machines, an application can trigger transfers using the following methods:

-   Batch mode (CFTUTIL)
-   REST API
-   Folder monitoring

When using a container environment however, you cannot use batch mode since Transfer CFT is isolated in a container. Available methods include:

-   REST API
-   Folder monitoring

Application invokes Transfer CFT REST APIs            <img src="/Images/TransferCFT/trigger_restapi.png" class="maxWidth" />

 

 

Folder monitoring              <img src="/Images/TransferCFT/foldermonitoring_trigger.png" class="maxWidth" />

 

### Post-processing

The application and Transfer CFT run in different containers. Therefore, for post-processing Transfer CFT can interact with the application by:

-   Invoking the application’s REST API using the cURL command in the post-processing script
-   Invoking a Kubernetes job using the Kubernetes API in the post-processing script
-   Storing a file in a directory monitored by the application

Transfer CFT notifies the application using REST API          <img src="/Images/TransferCFT/cft_container_app_post_processing.png" class="maxWidth" />

 

 

The application monitors a directory                  <img src="/Images/TransferCFT/foldermonitoring_container.png" class="maxWidth" />