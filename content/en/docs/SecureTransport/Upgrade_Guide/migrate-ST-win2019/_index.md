{
    "title": "Migrate Windows Server 2012 R2 to a later OS version",
    "linkTitle": "Migrate Windows Server 2012 R2 to a later OS version",
    "weight": "120"
}This chapter provides detailed step-by step procedures on migrating SecureTransport 5.5 installed on Microsoft Windows Server 2012 R2 to a later Windows Server version: either 2016 or 2019. The following topics cover different SecureTransport 5.5 deployments.

-   [Standalone installation with embedded database](standalone-mysql)
-   [Standalone with External Database](standalone-ext-db)
-   [Standard Cluster environment with embedded database](standard-cluster-mysql)
-   [Enterprise Cluster environment with external database](lec-ext-db)
-   [Edge installation with Embedded Database](edge-mysql)
-   [Edge installation with Embedded Database when part of a synchronized cluster](edge-synced-mysql)

 

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The topics described will refer to your existing <span>SecureTransport</span> <span>5.5</span> on Windows Server 2012 R2 deployment as the <i>original</i> deployment. Your future <span>SecureTransport</span> <span>5.5</span> (on either Windows Server 2016 or Windows Server 2019) deployment is referred to as the <i>new</i> deployment.         </td>
      </tr>
</table>

Instructions in these topics pertain to SecureTransport 5.5 only. If you are using a previous version of SecureTransport, follow the upgrade procedures as provided in this guide.

In the listed topics, to avoid confusion, the following terminology is introduced:

-   The current SecureTransport deployment on Windows Server 2012 R2 is also referred to as the *original* deployment.
-   Similarly, your future deployment (Windows Server 2016 or Windows Server 2019) is also referred to as the *new* deployment.

 
