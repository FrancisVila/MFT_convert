{
    "title": "Managing exits",
    "linkTitle": "Managing exits",
    "weight": "270"
}This section begins with this topic
which provides the information about:

-   [Exit
    task concepts](#exit_task_concepts)
-   [Exit
    task architecture](#exit_task_architecture)

A CFTEXIT object describes
the environment and activation of an exit
task. Each CFTEXIT object has an associated exit task. You can activate an exit task using:

-   [Command
    line operations](../../c_intro_userinterfaces/web_copilot_ui/conf_intro/cftexit) for the CFTEXIT object

### <span id="About_the_CFTEXIT_object"></span>About the CFTEXIT object

You can define as many CFTEXIT objects as needed.

There is an EXIT task for each
CFTEXIT object as described below:

-   File type: Performed
    at various stages in the transfer of a file
-   Directory type:
    Performed during the protocol connection phase
-   End-of-transfer:
    Performed at the end of a transfer
-   Beginning-of-transfer: Performed at the start of a transfer

The maximum number of EXIT tasks which are active simultaneously depends
on the operating system.

-   z/OS (MVS): 99
-   Windows: 128
-   UNIX: 15

## <span id="Exit_task_concepts"></span>Exit task concepts

Transfer CFT provides a programming interface, called an exit,
which allows user programs to take control during a transfer.

Transfer CFT handles:

The file EXIT task
which can take place at all the stages in a file transfer process

Beginning and end of transfer tasks, which are prior to or upon completion of a file transfer, respectively

The directory EXIT
task:

-   In
    server mode, it can replace the standard checks performed by Transfer
    CFT when a remote partner requests a session to be set up

<!-- -->

-   In
    requester mode, it can provide all the parameters required to set
    up a connection with a remote partner

Exit tasks are not mutually exclusive. Several types of exit tasks may
be initiated for a given transfer request.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For 
 information on transport security exits, see <a href="../../transport_security_start_here/configuring_transport_security_start_here">Configuring 
 Transport Security</a>.         </td>
      </tr>
</table>

### Exit list

The exit list is a file exit task that was written by Axway. It enables the following:

-   Remote partners
    to query the Transfer CFT catalog of a central site or server
-   The catalog to
    be queried

## <span id="Exit_task_architecture"></span>Exit task architecture

Transfer CFT can activate one or more EXIT tasks, such as calls, scheduling, and so on, which
are fully managed by the Transfer CFT.

![Displays Transfer CFT relationship to multiple Exits](cft_exits_2.png)

An EXIT task is generally activated, or loaded into memory,
as soon as Transfer CFT is started with the Directory EXIT
task, or else at the first transfer initiating an event to be checked.
After the event in question has been checked, the task is not de-activated
but stays loaded in memory. It remains active for a time that is defined
by the EXIT type, such as:

-   Throughout the
    Transfer CFT activity period for the Directory EXIT tasks
-   For an EXIT task
    maximum inactivity time, only for File and End-of-transfer exits

An EXIT task consists of:

-   An interface supplied
    with Transfer CFT, providing functions for communicating with the Transfer
    CFT
-   A user program,
    communicating with the interface

The interface communicates with the Transfer CFT through a semaphore. A semaphore is an entity
consisting of a structured stack of limited size. Each EXIT task has its
own semaphore.

The user program communicates with the interface through a communication
structure. This consists of one or more user functions and an initialization
function whose purpose is to indicate the address of the right user function
to call.

The following diagram shows an example
of a user program with two functions.

Communication structure

![Simplified view of a user program communicating with functions](cft_exits_2.png)
