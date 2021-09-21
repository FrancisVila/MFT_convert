{
    "title": "Connect and configure PostgreSQL",
    "linkTitle": "Connect and configure PostgreSQL",
    "weight": "110"
}Follow these instructions if you will be using PostgreSQL with your SecureTransport deployment. If you will be using Oracle DB, see [Connect and configure Oracle DB](../connect-oracle) .

## Connect to your PostgreSQL database

Connect to a PostgreSQL DB instance using pgAdmin

1.  Find the endpoint (DNS name) and port number for your DB Instance.
    1.  Open the RDS console and then choose Databases to display a list of your DB instances.
    2.  Choose the PostgreSQL DB instance name to display its details.
    3.  On the Connectivity & security tab, copy the endpoint. Also, note the port number. You need both the endpoint and the port number to connect to the DB instance.

      
    
    ![PostgreSQL endpoint](db-postgre-connection.png "PostgreSQL endpoint")
2.  Install [pgAdmin](http://www.pgadmin.org/). You can download and use pgAdmin without having a local instance of PostgreSQL on your client computer.
3.  Launch the pgAdmin application on your client computer.
4.  On the **Dashboard** tab, choose **Add New Server**.
5.  In the Create - Server dialog box, type a name on the General tab to identify the server in pgAdmin.
6.  On the Connection tab, type the following information from your DB instance:
7.  For **Host**, type the endpoint, for example mypostgresql.c6c8dntfzzhgv0.us-east-2.rds.amazonaws.com.
8.  For **Port**, type the assigned port.
9.  For **Username**, type the user name that you entered when you created the DB instance.
10. For **Password**, type the password that you entered when you created the DB instance.  
    
    ![PostgreSQL connection](db-postgre-connection.png "PostgreSQL connection ")
      
    **Note** The PostgreSQL user in AWS RDS does not have superuser rights.
11. Click **Save**.
12. To access a database in the pgAdmin browser, expand Servers, the DB instance, and Databases. Choose the DB instance's database name.
13. To open a panel where you can enter SQL commands, choose Tools, Query Tool.

### Connect to a PostgreSQL DB instance over SSL

1.  Download the certificate. For information about downloading certificates, see [Using SSL/TLS to encrypt a connection to a DB instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.SSL.html) in the AWS documentation.
2.  Import the certificate into your operating system. For sample scripts that import certificates, see [Sample script for importing certificates into your trust store](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.SSL-certificate-rotation.html#UsingWithRDS.SSL-certificate-rotation-sample-script) in the AWS documentation.
3.  Connect to your PostgreSQL DB instance over SSL.

## Create tables and set ownership of the PostgreSQL Database

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
      </tr>
   </tbody>
</table>

1.  Create "user/login":  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CREATE ROLE user/login WITH</p>
            <p>   LOGIN</p>
            <p>   NOSUPERUSER</p>
            <p>   NOCREATEDB</p>
            <p>   NOCREATEROLE</p>
            <p>   INHERIT</p>
            <p>   NOREPLICATION</p>
            <p>   CONNECTION LIMIT -1</p>
            <p>   PASSWORD 'xxxxxx';</p>
         </td>
      </tr>
   </tbody>
</table>

2.  Grant privileges to user:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>GRANT "user/login" TO postgres;         </td>
      </tr>
   </tbody>
</table>

3.  Create tablespaces the following tablespaces:

    -   st\_data

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>CREATE TABLESPACE st_data            <p>OWNER postgres</p>            <p>GRANT CREATE ON TABLESPACE st_data TO ‘user/login’;</p>         </td>      </tr>   </tbody></table>

    -   st\_filetracking

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>CREATE TABLESPACE st_filetracking</p>            <p>OWNER postgres</p>            <p>GRANT CREATE ON TABLESPACE st_filetracking TO ‘user/login’;</p>         </td>      </tr>   </tbody></table>

    -   st\_serverlog

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>CREATE TABLESPACE st_serverlog</p>            <p>OWNER postgres</p>            <p>GRANT CREATE ON TABLESPACE st_serverlog TO ‘user/login’;</p>         </td>      </tr>   </tbody></table>

4.  create database  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CREATE DATABASE 'dbname'</p>
            <p>   WITH</p>
            <p>   OWNER = 'user/login'</p>
            <p>   ENCODING = 'UTF8'</p>
            <p>   CONNECTION LIMIT = -1;</p>
         </td>
      </tr>
   </tbody>
</table>
