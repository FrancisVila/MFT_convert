{
    "title": "Launching tests from the Gateway GUI",
    "linkTitle": "Launching tests from the Gateway GUI",
    "weight": "310"
}To launch a test case from the Gateway GUI you complete the following *New Transfer Request* screens:

## General tab

<img src="/Images/Gateway/0300001E.png" class="maxWidth" />

In the **Model** field, enter the name of the model called by Gateway to execute the test case. For the current set of test cases you always use the Model FROM\_BO\_TO\_SSP.

## Attributes tab

<img src="/Images/Gateway/0300001F.png" class="maxWidth" />

In the **File component** field, enter the path to the <span class="code">InitialRequest.xml</span> file. By default, this file is located at: <span class="code">C:\\Axway\\qt2\\xml</span>

## Details tab

<img src="/Images/Gateway/03000020.png" class="maxWidth" />

In the **Param 1** field, enter the number of the test case you want to run. Select a test case from the table provided in [Pre-built test cases](../).

## SWIFTNet tab

<img src="/Images/Gateway/03000021.png" class="maxWidth" />

In the **Destination partner** and **Originator partner** fields, enter the names of the appropriate Remote Sites.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)