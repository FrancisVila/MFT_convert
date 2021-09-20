{
    "title": "Applications",
    "linkTitle": "Applications",
    "weight": "160"
}This section introduces Axway SecureTransport applications and describes how to use the Applications menu features of the SecureTransport Administration Tool.

## Application overview

In SecureTransport, *applications* are sets of workflow you can create to perform file processing, including the following:

-   Transform data
-   Schedule file transfers
-   Route files
-   Monitor shared folder monitoring across user accounts
-   Trigger sequential sets of actions

An application is defined as an instance of a set of workflow called an *application type*. Once you have defined an application, you create a connection between an application and one or more *accounts*. Such a connection is defined through a *subscription*.

SecureTransport ships with the following built-in application types:

-   **[Account Maintenance](applicationsaccountmaintenance)** – Automatically deletes, disables, or purges accounts based on their inactivity or age. You can configure account maintenance schedule and emails notifications, as well as email alerts for password and certificate expiration.
-   **[Advanced Routing](../c_st_advanced_routing)** – Provides options to create multiple automated flows for file transformations, routing and transfers between different participants, partner systems, and applications.
-   **[Archive Maintenance](applicationsarchivemaintenance)** – Automatically deletes archived files based on a schedule you define.  
-   **[Audit Log Maintenance](applicationsauditlogmaintenance)** – Automatically deletes Audit log records that are older than a specified number of days or months (6 months by default). You can schedule how often to run this application and configure it to optionally export these records prior to deletion.
-   **[Axway Sentinel Link Data Maintenance](applicationssentinellinkdatamaintenance)** – Removes all SentinelLinkData entries to files that do not exist anymore, based on a schedule you define.
-   **[Axway Transfer CFT](applicationstransfercft)** – Enables Axway Transfer CFT to push files to SecureTransport.
-   **[**Basic Application**](applicationsbasic)** – Processes server-initiated transfers and performs data transformations.  
-   **[File Maintenance](applicationsfilemaintenance)** – Automatically deletes files from account home folders based on a specified retention or expiration period. You can schedule how often to run this application and configure it to optionally send notification before or/and after file deletion.
-   **[File Transfer via File Services Interface](applicationstransferfileservicesinterface)** – Processes metadata files sent from another system for a protocol implemented using the file services interface.
-   **[**Human to System**](applicationsh2s)** – Provides a way to route H2S file transfers.
-   **[Log Entry Maintenance](applicationslogentrymaintenance)** – Automatically deletes Server log records that are older than a specified number of days, hours or minutes (1 day by default). You can schedule how often to run this application and configure it to optionally export these records prior to deletion.
-   **[Login Threshold Maintenance](applicationsloginthresholdmaintenance)** – Unlocks accounts locked according to the selected "Lock account after N successful logins" option in the *Account settings* and sends a report to specified email contacts.  
    See [Login Threshold Maintenance application](applicationsloginthresholdmaintenance).
-   **[**Package Retention Maintenance**](applicationspackageretentionmaintenance)** – Deletes expired file packages from ad hoc file transfers.
-   **[Shared Folder](applicationssharedfolder)** – Provides shared data storage between accounts.
-   **[**Site Mailbox**](applicationssitemailbox)** – Similar to Basic application, however with dedicated outbox and inbox folders for files transfers using a transfer site. This application is recommended for AS2 transfer sites.
-   **[Standard Router](applicationsstandardrouter)** – Provides basic options to automate flows for file transformations, routing and transfers between an account and internal systems.
-   **[Transfer Log Maintenance](applicationstransferlogmaintenance)** – Automatically deletes Transfer log records that are older than a specified number of days (30 days by default). You can schedule how often to run this application and configure it to optionally export these records prior to deletion.
-   **[**Unlicensed Accounts Maintenance**](applicationsunlicensedacctsmaintenance)** – Deletes inactive unlicensed user accounts older than a specified number of days (60 days by default). You can schedule how often to run this application.  
     

This subtopic provides instructions on how to access, edit, and delete applications.

## Access applications

Select **Application**.  
The *Applications* page is displayed. It lists all the applications available currently on the system. Use it to add, delete, view, and edit applications.

## View or edit an application

Use the following procedure to view or edit an application.

1.  Select **Application**.
2.  On the *Applications* page, click the name of the application you want to view or edit. The *Application Details* page of the application you selected is displayed.
3.  View or edit the information displayed.  
    The *Application Details* page varies for the different application types. It dynamically displays the attributes for the respective application type. You can edit all the standard settings of an application, except application type.
4.  If you edit the information, click **Save** to preserve the changes.

## Delete an application

Use the following procedure to delete an application.

1.  Select **Application**. The *Applications* page is displayed.
2.  Select the check box for the application you want to delete.
3.  Click **Delete**.
4.  When prompted, confirm that any subscription to this application will be lost.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When you delete an application, all subscriptions to this application are removed.         </td>
      </tr>
</table>

## <span id="ConfigureMaintSchedule"></span>Configure a schedule for a maintenance application

SecureTransport allows you to schedule maintenance events that will be executed once at a specified time in the future or at periodic intervals. You can access the scheduler page by creating or editing any maintenance application.

To schedule a maintenance event:

1.  Select **Application** and click **Add New** or select a maintenance application from the list.
2.  Scroll down to the *Schedule* pane and click **Configure**.   
    The *Configure Schedule* dialog box is displayed.
3.  Select the event's timing:  
    
    -   One-time event – the event is executed once at the specified date and time.
    -   Recurrent – the event is executed at the specified periodic intervals until it is deleted.
        1.  Specify *Recurrence* for the event by selecting one of the supported intervals: **Hourly**, **Daily**, **Weekly**, **Monthly**, or **Yearly**. If you select **CRON Expression**, enter your quartz cron expressions in the text box, each on a new line.
        2.  In the *Length of Recurrence* pane, select a specific start day and time, end day and time, both, or neither. By default, a recurring event's schedule begins as soon as it is created, and continues indefinitely, until it is disabled.  
4.  Choose whether the task should be performed if it falls on a day specified as a holiday in the [Holiday Schedule](../c_st_setup/t_st_holidayschedule). Note that the Holiday Schedule functionality does not allow for executing a scheduled task on the next working day if the specified date happens to be a holiday – when this occurs, the tasks are not executed.
5.  Click **OK** when finished setting the schedule.

Before queuing a new task, the server checks if a previous instance of same periodic task is still pending. If there is a pending instance of the same periodic scheduled task , the new task is not scheduled.

If the server goes down for some time and restarts, the scheduler does not execute any scheduled tasks missed during the server down time.

For information on scheduling file downloads, see [Scheduled downloads and tasks](../accounts/c_st_subscriptions/t_st_subscriptions).

## Create applications

Every application in SecureTransport must be based on an application type. Currently, SecureTransport supports multiple application types. Learn how to create applications of each application type:

-   [Archive Maintenance application](applicationsarchivemaintenance)
-   [Archive Maintenance application](applicationsarchivemaintenance)
-   [Audit Log Maintenance application](applicationsauditlogmaintenance)
-   [Axway Sentinel Link Data Maintenance application](applicationssentinellinkdatamaintenance)
-   [Axway Transfer CFT application](applicationstransfercft)
-   [Basic Application](applicationsbasic)
-   [File Transfer via File Services Interface application](applicationstransferfileservicesinterface)
-   [Human to System application](applicationsh2s)
-   [Log Entry Maintenance application](applicationslogentrymaintenance)
-   [Login Threshold Maintenance application](applicationsloginthresholdmaintenance)
-   [Package Retention Maintenance application](applicationspackageretentionmaintenance)
-   [Shared Folder application](applicationssharedfolder)
-   [Site Mailbox application](applicationssitemailbox)
-   [Standard Router application](applicationsstandardrouter)
-   [Transfer Log Maintenance application](applicationstransferlogmaintenance)
-   [Unlicensed Accounts Maintenance application](applicationsunlicensedacctsmaintenance)
-   [File Maintenance application](applicationsfilemaintenance)

For instructions on creating an Advanced Routing application, see [Create Advanced Routing application](../c_st_advanced_routing/c_st_configuration/t_st_create_advanced_routing_application).