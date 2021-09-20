{
    "title": "UI performance settings ",
    "linkTitle": "UI performance settings ",
    "weight": "140"
}The following code snippet shows the ST Web Client UI performance defaults:

    {

      ...

      "uiPerformance": {

        "refreshThrottleTime": 1000,

         "addressBook": {

        "minimumBatchSize": 100

        }

      }

      ...

    }

To change the UI performance default setting, in the custom configuration file, add a `"uiPerformance"` section and overwrite the desired property.

Listed below are all the accepted properties and what they affect.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Property</p>
            <p><em>(type)</em>
</p>
</th>
         <th>
            <p>Description</p>
            <p> </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>refreshThrottleTime </strong>
            <p><em>(integer)</em>
</p>
         </td>
         <td>
            <p>Determines the interval between the Uploads Monitor refreshes, in milliseconds.</p>
            <p>Default value: <code>1000</code></p>
         </td>
      </tr>
      <tr>
         <td><strong>addressBook</strong>
            <p><em>(object)</em>
</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td><b>minimumBatchSize</b>
         </td>
         <td>
            <p>Specifies the maximum number of records to include in a single  request to the address book API.</p>
            <p>Default value: <code>100</code></p>
         </td>
      </tr>
   </tbody>
</table>
