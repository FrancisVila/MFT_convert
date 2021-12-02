{
    "title": "Post-transfer file renaming",
    "linkTitle": "Post-transfer file renaming",
    "weight": "230"
}You can configure  post-transfer, file renaming on the receiver side of a flow. The file is renamed on transfer completion, in the post processing phase, and includes a configurable retry mechanism.

Limitation

-   When using a group of files in homogeneous mode, you cannot use post-transfer file renaming.

## How to configure

To enable the renaming option for a given flow (CFTRECV) set FACTION to RETRYRENAME.

**Example**

Use the following uconf parameters to customize the retry mechanism.


| Parameter  | Default  | Value  | Description  |
| --- | --- | --- | --- |
| cft.server.transfer.rrename.retry_delay  | 60 seconds  | 1-65535  |  Delay in seconds between two retries for renaming.<br/>If the file is not successfully renamed after the first retry_delay, the time is compounded so that the next retry occurs at the retry time added to the number of tries multiplied by the retry value.<br/>The time of the next retry = D + D * (R-1)<br/>Where:<br/> • D is the retry_delay<br/> • R is the number of retries<br/>For example, if the file is not renamed after 60 seconds (default value), the next retry occurs in 120 seconds, and the following one in 180 seconds, etc.  |
| cft.server.transfer.rrename.max_retries  | 10  | 1-65535  | Maximum number of retries.  |


### Monitoring

**Log**

Following a successful renaming, `CFTF33I `is displayed.

Once the maximum number of retries is reached, the transfer moves to the YK state, and displays a DIAGI=156, `DIAGP=RETRYRENAME`, a DIAGC=`RETRYRENAME MAX RETRIES REACHED` or = `RETRYRENAME WFNAME NOT FOUND`, and the log messages [CFTF32E](../../troubleshoot_intro/messages_and_error_codes_start_here/cftf_messages#CFTF32E) and [CFTF34E](../../troubleshoot_intro/messages_and_error_codes_start_here/cftf_messages#CFTF34E).

Catalog

Information in the catalog displays the number of retries performed.

## Work flow

The retry and rename (R) option falls between the (T) and (Y) phase.

![](/Images/TransferCFT/temp_retry_rename.png)

## Queuing

If you have several transfers with RETRYRENAME set for the same FNAME in a single flow, the transfers are queued based on their date/time of the end-of-transfer (DATEE, TIMEE).

## Example of spooling and renaming files

This example combines the use of the serialization with the rename/retry mechanism to ensure a spooling of file transfers without overwriting an un-consumed file at the destination.

-   Our user defines a transfer flow, for example `DailyReport,`based on a transfer state (acknowledgement) using the serialization option.
-   Several applications generate files that use the same flow, `DailyReport`; these file transfer requests are queued.
-   The source Transfer CFT for the flow executes the first file transfer request, `Report1`.  
-   The target Transfer CFT receives `Report1`.
-   Post-processing makes the file available to a target application, and immediately sends an acknowledgment to the source. This enables the next file transfer in the queue to be executed.
-   Upon receiving the acknowledgement, the source Transfer CFT executes the next transfer request. However:

> -   If the file no longer exists on the target (it was consumed by a target application), the cycle repeats as above.
>
> <!-- -->
>
> -   If the file still exists on the target Transfer CFT, then the next new file transfer (`Report2`) enters a retry cycle while it waits for the previous file to be deleted (moved/copied).

### Example configuration

#### Create models

Create a sender side model:

Create a receiver side model:

#### Define post-processing

Post-processing should include an acknowledgement so that the next queued transfer request is triggered. Additionally, your post-processing script can include, for example, a message to indicate that the file has been received and renamed, and is ready to be consumed by the target application.

#### Enter command to send files

#### Check output files

Sender side

Receiver side

## Troubleshooting

Error and information messages include the following:

-   [CFTF32E](../../troubleshoot_intro/messages_and_error_codes_start_here/cftf_messages#CFTF32E): PART=&part IDF=&idf IDT=&idt \_ Maximum number of rename retries reached
-   [CFTF34E](../../troubleshoot_intro/messages_and_error_codes_start_here/cftf_messages#CFTF34E): PART=&part IDF=&idf IDT=&idt \_ WFNAME=&wfname not found
-   [CFTF35W](../../troubleshoot_intro/messages_and_error_codes_start_here/cftf_messages#CFTF35W) PART=&part IDF=&idf IDT=&idt Rename to FNAME=&fname failed, will be retried at &datetime

Diagnostic code values related to RETRYRENAME include:

-   [diagi=156](../../troubleshoot_intro/messages_and_error_codes_start_here/diagi_diagnostic_codes) / diagc=RETRYRENAME
