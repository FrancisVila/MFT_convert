{
    "title": "Maintaining the Mailbox (kfmcp command)",
    "linkTitle": "Maintaining the Mailbox",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[KFM-based data files](#kfm_data_files)

[kfmcp command](#kfmcp_command)

[kfmcp command usage](#kfmcp_command_usage)

[Gateway KFM-based files](#gw_kfm_files)

[Resizing the Mailbox](#resizing_mailbox)

<span id="kfm_data_files"></span>

## KFM-based data files

Some Gateway data files use a proprietary structure that offers the following access features:

-   Fast record retrieval by key value
-   Fast insertion/deletion
-   Concurrent (reader/writer) access
-   Record locking
-   Integrity checking
-   File space pre-allocation
-   Free space reuse

The software that implements this file structure and the associated access method is called <span style="font-style: italic;">KFM (Key File Management)</span> software.

The metadata that allows fast retrieval by key value is based on the hashcoding technique.

<span id="kfmcp_command"></span>

## kfmcp command

The <span class="code" style="font-weight: bold;">kfmcp</span> utility supplied with the product enables you to manage KFM-based files.

Each KFM-based data file has the following set of attributes that define its structure:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Attribute</span></p>         </td>
         <td><p>Meaning</p>         </td>
      </tr>
      <tr>
         <td><p>-version</p>         </td>
         <td><p>A number that informs KFM about the version of the file structure.</p>
<p>Only version numbers 11 and 12 are used in the current version of Gateway. Most of the KFM-based files use version 11. KFM version 12 provides minor optimizations over version 11.</p>         </td>
      </tr>
      <tr>
         <td><p>-maxr</p>         </td>
         <td><p>Corresponds to the <span style="font-style: italic;">modulo</span> of the hashcode.</p>
<p>This is related to the maximum number of records without hash collisions. The maximum supported value is 262 144 (2^^18). The actual number of records in a KFM file is not limited to this value.</p>
<p>An average value of no more than 4 hash collisions should not significantly affect performance for direct accesses by key value.</p>         </td>
      </tr>
      <tr>
         <td><p>-alsz</p>         </td>
         <td>Initial file allocation table. The maximum value supported is 16 Gb. Any value greater than this limit is truncated to 16Gb.         </td>
      </tr>
      <tr>
         <td><p>-alsz2</p>         </td>
         <td><p>The size in bytes used for secondary allocations.</p>
<p>Each time KFM allocates more space for a file, it uses this value for the size of the allocation. This value must be distinguished with the initial file space allocation that can be achieved using the <span class="code" style="font-weight: bold;">kfmcp</span> command.</p>
<p>The maximum value supported is 256Mb. Any value greater than this limit is truncated to 256Mb.</p>         </td>
      </tr>
      <tr>
         <td><p>-hhint, hp1, hp2</p>         </td>
         <td><p>Hints used for hashcode optimization.</p>         </td>
      </tr>
   </tbody>
</table>

Additionally, some other hidden attributes are used for ciphered files.

<span id="kfmcp_command_usage"></span>

## kfmcp command usage

You can use the <span class="code" style="font-weight: bold;">kfmcp</span> command for various tasks:

### usage 1

kfmcp  -t  \[infile1  infile2  ...\]

Counts the total number of records of the files and prints the result.

### usage 2

kfmcp  -M  maxr  alsz\_kb  alsz2\_kb  \[infile1  infile2  ...\]  outfile

Creates a new file envelope in <span class="code">outfile</span> and copies all the records from <span class="code">infiles</span> to <span class="code">outfile</span>.

<span class="code">maxr</span> = number of hash classes:

-   Rounded down to the greatest power of 2 &lt;= <span class="code">maxr</span>
-   Maximum value 262 144=2^18

<span class="code">alsz\_kb</span>: primary (initial) file allocation in KB

<span class="code">alsz2\_kb</span>: secondary file space allocation in KB

Other attributes (<span class="code">version</span>, <span class="code">hhint</span>, <span class="code">hp0</span>, <span class="code">hp1</span>, cipher-related ones) are extracted from <span class="code">infile1</span> and applied to <span class="code">outfile</span>.

### usage 3

kfmcp  -X  version  maxr  alsz\_b  alsz2\_b  \[infile1  infile2  ...\]  outfile

Same as option <span class="code">-M</span> except that:

-   The version of <span class="code">outfile</span> can be changed
-   Allocation quantities are in bytes instead of kilobytes (KB) and limited to 2 Gigabytes.

### usage 4

kfmcp  -S  \[infile1  infile2  ...\]

Prints attributes of <span class="code">infiles</span> to the standard output. For example:

kfmcp  -S  xfer.dat

file=xfer.dat

version=11

maxr=262144

alsz2=100000

hhint=1

hp1=0

hp2=4

records=6

### usage 5

kfmcp  -d  \[infile1  infile2  ...\]

Dumps the internal structure of the file to the standard output. Can be used for low-level debugging.

### usage 6

kfmcp -R \[infile1 infile2 ...\] \[outfile\]

Creates a new file envelope in <span class="code">outfile</span> and copies the records from <span class="code">infiles ...</span> to <span class="code">outfile</span>, while validating each input record. Invalid records will be skipped. This command can be used as a means
to "repair" a mailbox file.
If only one file is specified in the parameter list, it will be considered an <span class="code">infile </span>and the command will verify its consistency.
Only a partial check is performed, enough to create a problem-free copy of the <span class="code">infiles</span>, but not to detect all possible consistency errors.

<span id="gw_kfm_files"></span>

## Gateway KFM-based files

On its first startup, Gateway creates the following KFM-based files:

<table>
         
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>File Name</p>         </td>
         <td><p>KFM version</p>         </td>
         <td><p>maxr</p>         </td>
         <td><p>alsz2_b</p>         </td>
         <td><p>alsz_b</p>         </td>
      </tr>
      <tr>
         <td><p>admin.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>agenda.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>cert.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>cgate.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>cgategroup.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>dlist.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>key.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>model.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>nprof.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>pmindex.dat</p>         </td>
         <td><p>12</p>         </td>
         <td><p>1024</p>         </td>
         <td><p>100 000</p>         </td>
         <td><p>100 000</p>         </td>
      </tr>
      <tr>
         <td><p>profile.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>proxy.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>5 000 000</p>         </td>
      </tr>
      <tr>
         <td><p>rules.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>5 000 000</p>         </td>
      </tr>
      <tr>
         <td><p>sgateb.dat</p>         </td>
         <td><p>12</p>         </td>
         <td><p>262 144</p>         </td>
         <td><p>5 000 000</p>         </td>
         <td><p>5 000 000</p>         </td>
      </tr>
      <tr>
         <td><p>sgate.dat</p>         </td>
         <td><p>12</p>         </td>
         <td><p>262 144</p>         </td>
         <td><p>5 000 000</p>         </td>
         <td><p>5 000 000</p>         </td>
      </tr>
      <tr>
         <td><p>sgategroupb.dat</p>         </td>
         <td><p>12</p>         </td>
         <td><p>16 384</p>         </td>
         <td><p>5 000 000</p>         </td>
         <td><p>5 000 000</p>         </td>
      </tr>
      <tr>
         <td><p>sgategroup.dat</p>         </td>
         <td><p>12</p>         </td>
         <td><p>16 384</p>         </td>
         <td><p>5 000 000</p>         </td>
         <td><p>5 000 000</p>         </td>
      </tr>
      <tr>
         <td><p>sprof.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>sshprof.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>trade.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>user.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>32 768</p>         </td>
         <td><p>500 000</p>         </td>
         <td><p>500 000</p>         </td>
      </tr>
      <tr>
         <td><p>vsite03.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>262 144</p>         </td>
         <td><p>2 000 000</p>         </td>
         <td><p>2 000 000</p>         </td>
      </tr>
      <tr>
         <td><p>xferb.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>262 144</p>         </td>
         <td><p>5 000 000</p>         </td>
         <td><p>5 000 000</p>         </td>
      </tr>
      <tr>
         <td><p>xfer.dat</p>         </td>
         <td><p>11</p>         </td>
         <td><p>262 144</p>         </td>
         <td><p>5 000 000</p>         </td>
         <td><p>5 000 000</p>         </td>
      </tr>
   </tbody>
</table>

### Mailbox files

Most of the Gateway KFM-based files contain configuration objects, such as Sites, CGates, Applications, Decision Rules, and so on. The <span class="code">xfer.dat</span> and <span class="code">xferb.dat</span> files contain transfer metadata items that are accessed very extensively by Gateway. These two files are collectively known as the <span style="font-style: italic;">Transfer Mailbox</span> or simply the <span style="font-style: italic;">Mailbox</span> in Gateway terminology.

<span id="resizing_mailbox"></span>

## Resizing the Mailbox

Although Gateway can allocate KFM file space when needed, allocating the whole Mailbox disk space needed for a given production workload can improve performance and protects against errors due to file allocation failures.

You can use the following guidelines to estimate the maximum size of the two Mailbox files:

-   The file <span class="code">xfer.dat</span> contains 1 fixed-size record for each Transfer Request. The size of each record is about 11 KB.
-   The file <span class="code">xferb.dat</span> also contains fixed size records. Each record is 3.5 KB. The use of an <span class="code">xferb.dat</span> record for a Transfer Request depends on the protocol. For example, PESIT and PEL protocols do not need a record in <span class="code">xferb.dat</span>. However, all EDI protocols require such a record for each transfer. As a general rule, used in the examples below, you can assume that the number of records in both <span class="code">xfer.dat</span> and <span class="code">xferb.dat</span> are the same.
-   For a large number of records, the space of KFM files that is not used for data records (mostly hash technique related structure) is very small (less than 5% of the total file space).

Given these simple rules, assuming that each record requires 12 KB in <span class="code">xfer.dat</span> and 4 KB in <span class="code">xferb.dat</span>, we can estimate the disk space for these files.

### Use case for 100 000 Transfer Requests

The preferred <span class="code" style="font-weight: bold;">kfmcp</span> command to use to resize the Mailbox is <span class="code" style="font-weight: bold;">kfmcp  -M  ...</span>

File space for <span class="code">xfer.dat</span>: 100 000 x 12 KB = 1 200 000 KB

File space for <span class="code">xferb.dat</span>: 100 000 x 4 KB = 400 000 KB

These values correspond to the <span class="code">alsz\_kb</span> argument of the <span class="code" style="font-weight: bold;">kfmcp  -M</span> command.

The secondary allocation <span class="code">alsz2\_kb</span> is only useful if new space has to be allocated on need. It is not used if the full needed space is pre-allocated. Nevertheless, it is not recommended to specify a very small value for <span class="code">alsz2\_kb</span>.

In the following examples, we use the greater value between 5000 KB and 1% of the total file space, with an absolute maximum of 50 000 KB.

#### Example 1

kfmcp  -M  131072  1200000  12000  xfer.dat  xfer\_new.dat

This example uses 131 072 hash classes for 100 000 transfers (reasonable).

#### Example 2

kfmcp  -M  262144  1200000  12000  xfer.dat  xfer\_new.dat

This example uses twice the number of needed classes (rather high).

#### Example 3

kfmcp  M  0  1200000  12000  xfer.dat  xfer\_new.dat

This example provides a value of 0 for <span class="code">maxr</span> which has the effect of reusing the value from <span class="code">xfer.dat</span> which is 262 144.

Given the low overhead of KFM space due to hashcoding related data, we recommend that you do not change the <span class="code">maxr</span> value (262 144), even in situations where this value may seem too large in theory.

The following tables provide suitable values for <span class="code">alsz\_kb</span> and <span class="code">alsz2\_kb</span> depending on the number of Transfer Requests.

#### Values to use for xfer.dat

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Number of transfers</p>         </td>
         <td><p>alsz_kb</p>         </td>
         <td><p>alsz2_kb</p>         </td>
      </tr>
      <tr>
         <td><p>100 000</p>         </td>
         <td><p>1 200 000</p>         </td>
         <td><p>12 000</p>         </td>
      </tr>
      <tr>
         <td><p>200 000</p>         </td>
         <td><p>2 400 000</p>         </td>
         <td><p>24 000</p>         </td>
      </tr>
      <tr>
         <td><p>300 000</p>         </td>
         <td><p>3 600 000</p>         </td>
         <td><p>36 000</p>         </td>
      </tr>
      <tr>
         <td><p>500 000</p>         </td>
         <td><p>6 000 000</p>         </td>
         <td><p>50 000</p>         </td>
      </tr>
      <tr>
         <td><p>1 000 000</p>         </td>
         <td><p>12 000 000</p>         </td>
         <td><p>50 000</p>         </td>
      </tr>
   </tbody>
</table>

#### Values to use for xferb.dat

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Number of transfers</p>         </td>
         <td><p>alsz_kb</p>         </td>
         <td><p>alsz2_kb</p>         </td>
      </tr>
      <tr>
         <td><p>100 000</p>         </td>
         <td><p>400 000</p>         </td>
         <td><p>5 000</p>         </td>
      </tr>
      <tr>
         <td><p>200 000</p>         </td>
         <td><p>800 000</p>         </td>
         <td><p>8 000</p>         </td>
      </tr>
      <tr>
         <td><p>300 000</p>         </td>
         <td><p>1 200 000</p>         </td>
         <td><p>12 000</p>         </td>
      </tr>
      <tr>
         <td><p>500 000</p>         </td>
         <td><p>2 000 000</p>         </td>
         <td><p>20 000</p>         </td>
      </tr>
      <tr>
         <td><p>1 000 000</p>         </td>
         <td><p>4 000 000</p>         </td>
         <td><p>40 000</p>         </td>
      </tr>
   </tbody>
</table>

### Use case for 300 000 Transfer Requests on a UNIX system

kfmcp  -M  0  3600000  36000  xfer.dat  xfer\_new.dat

kfmcp  -M  0  1200000  12000  xferb.dat  xferb\_new.dat

mv  xfer.dat  xfer\_old.dat

mv  xfer\_new.dat  xfer.dat

mv  xferb.dat  xferb\_old.dat

mv  xferb\_new.dat  xferb.dat

Related topics

[Managing the Mailbox (command line)](../managing_mailbox_cli)

[Upgrading the Mailbox](../../../../starting_and_stopping_server/migrating_mailbox)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
