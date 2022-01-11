


============================== table nb count(1) table converted to MD ========================================


| Resource | Description | Resource actions |
| --- | --- | --- |
| SERVICE:CATALOG | Manage the catalog file | PURGE |
| SERVICE:LOG | Manage the log file | SWITCH |
| SERVICE:ACCOUNT | Manage account files | SWITCH |
| SERVICE:CFTSRV | Manage the Transfer CFT server | STARTUP, SHUTDOWN, EDIT, VIEW |
| SERVICE:COM | Manage the COM file | DELETE, VIEW |
| COMMAND:EXTRACT | Extract Transfer CFT parameters | EXECUTE |
| COMMAND:MQUERY | Execute the Mquery command | EXECUTE |
| COMMAND:TURN | Execute the Turn command | EXECUTE |
| COMMAND:CFTSUPPORT | Allow the cft_support command | EXECUTE |



============================== table nb count(2) table converted to MD ========================================


| Parameter | Description | Type |
| --- | --- | --- |
| sentinel.xfb.enable | Enables the Sentinel connector. | Boolean: Yes | No |
| sentinel.xfb.transfer | Level of detail for Transfer Message content. | Enumeration: ALL SUMMARY ERROR NO |
| sentinel.xfb.audit  | Enables configuration change logging.  | Boolean: Yes | No  |



============================== table nb count(3) table converted to MD ========================================


| File | Description | Access for Transfer CFT<br/> Product and administrator | Access for others |
| --- | --- | --- | --- |
| cftuconf.dat | Configuration file | READ, WRITE | READ |
| cftparm | Configuration database | READ, WRITE | READ |
| crypkey  | Ciphering file  | READ, WRITE  | NONE  |
| crypsalt  | Salt file  | READ, WRITE  | NONE  |



============================== table nb count(4) table converted to MD ========================================


| File | Description | Access for Transfer CFT<br/> Product and administrator | Access for others |
| --- | --- | --- | --- |
| cftcom | Communication file | READ, WRITE | READ, WRITE (an application requires write authorization to create and manipulate new transfer requests) |
| cftcat | Catalog file | READ, WRITE | READ |
| CFTAM  | Access management's persistent cache  | READ, WRITE  | READ  |
