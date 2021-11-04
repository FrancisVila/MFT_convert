{
    "title": "Customizing Gateway Decision Rules for TARGET2",
    "linkTitle": "Customizing Decision Rules",
    "weight": "350"
}After importing the TARGET2 object set, you must modify the configuration of the Decision Rule objects to correspond to your network environment.

After you import Decision Rules:

1.  In Gateway Navigator, right-click <span class="bold_in_para">Event Management\\Transfer Change State\\Default</span>.
2.  Click **Properties**.
3.  In the **General** tab:
    -   Select <span class="bold_in_para">Active</span>
    -   For Default execution type select <span class="bold_in_para">No action</span>
    -   Select <span class="bold_in_para">Link input and output transfers</span>
    -   For Log level select <span class="bold_in_para">Full</span>

      
    <img src="/Images/Gateway/0300001B.png" class="maxWidth" />
4.  In the **Linked rules** tab:
    -   Move Decision Rules from Available rules to Linked rules using the <span class="bold_in_para">Link</span> button.
    -   Click <span class="bold_in_para">OK</span>.

      
    <img src="/Images/Gateway/0300001C.png" class="maxWidth" />  
5.  Customize parameters according to your configuration requirements.  
     

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
