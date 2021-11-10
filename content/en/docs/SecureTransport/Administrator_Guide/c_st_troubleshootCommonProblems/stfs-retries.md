{
    "title": " Troubleshooting I/O problems ",
    "linkTitle": "Troubleshoot I/O problems",
    "weight": "310"
}**Problem summary:** An I/O error may occur when a large number of write or read operations are happening simultaneously. As a result, SecureTransport may fail to retrieve file attributes or decrypt repository encrypted files when sending them outbound, for example. The issue is observed mainly in cluster environments with GlusterFS.

 

**Possible cause:** Read/write operations may require more time.

 

**Solution:** In this case, retrying failed read/write operations more times or/and for longer intervals may solve the issue. SecureTransport uses an exponential backoff algorithm for retries: it increases the waiting time between the consecutive retries after each retry failure following the logic:

The first retry is after 1 x `retryTime`, the second retry is after 2 x `retryTime`, the third after 3 x `retryTime` and so on until the configured number of `retries` is reached.  
where

-   `retries` is the maximum number of retry attempts for failed read/write operations configured in the `com.axway.st.server.fs.attributes.read.retries` parameter (10 by default).
-   `retryTime` is the delay of the first retry and the growth rate between attempts configured in the `com.axway.st.server.fs.attributes.read.retryTime` parameter. (100 ms by default).

With the default values, SecureTransport retries 10 times: the first retry happens in 100 ms, the second after 200, the third after 300, and so on. This sets a deadline of 5.5 seconds for SecureTransport to retry a failed read/write operation.  
For example, if the number of retries is limited to 20, and the delay is set to 200 ms, the retries happen in 200, 400, 600, 800,...., 4000 ms. So, the total amount of time for retrying is 42 seconds.  
The benefits of changing these parameters are dependent on the shared storage type and its performance

To customize the read/write retry logic, add the following in the `<FILEDRIVEHOME>/bin/start_tm_console` file and edit the values to fit your needs:

`JAVA_OPTS="-Dcom.axway.st.server.fs.attributes.read.retries=10 $JAVA_OPTS"`

`JAVA_OPTS="-Dcom.axway.st.server.fs.attributes.read.retryTime=100 $JAVA_OPTS"`
