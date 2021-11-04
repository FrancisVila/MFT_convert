{
    "title": "Transfers and message type",
    "linkTitle": "Transfers and message type",
    "weight": "340"
}To run the TARGET2 module in simulation mode, a SWIFT loop configuration must be possible in which you send messages/files to yourself. Users must have access to a SWIFT InterAct service and a SWIFT identity that allows them to send InterAct to themselves.

The file sent to the simulation (InitialRequest.xml in the example) can have any content. The only requirements are:

-   The file must be embedded:
    -   File content must be contained between the tags <span class="code">&lt;SwInt:RequestPayload></span> and <span class="code">&lt;/SwInt:RequestPayload></span>
    -   File content must not conflict with XML parsing
-   The file must be an XML file. For example, you could use the <span class="code">InitialRequest.xml</span> file provided in the QT2 directory

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
