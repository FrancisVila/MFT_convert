{
    "title": "Add applications to use in flows",
    "linkTitle": "Add applications to use in flows",
    "weight": "130"
}When you are working in <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> you create *applications* to use in flows. Therefore, if your products did not create applications upon registering, you must create at least two applications to use in your flows.

In this section you create three applications in <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> to represent the <span class="code">MainOffice</span>, `Store_66`, and `Store_89`.

### View the registered Transfer CFTs in <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

#### In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

Select **Products** on the top toolbar to open the **Product List** page.

<img src="/Images/TransferCFT/gettingstarted1.png" class="mediumWidth" />

Copy the host name for each of the three Transfer CFTs that you will use in these exercises, for example copy them into a table as shown here.

<table>
   <th>
      <tr>
<th>Transfer CFT          </th>
<th>Host         </th>
<th>Application name         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> 1         </td>
         <td>&lt; hostname 1&gt;         </td>
         <td>MainOffice         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> 2         </td>
         <td>&lt; hostname 2&gt;         </td>
         <td>Store_66         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> 1         </td>
         <td>&lt; hostname 3&gt;         </td>
         <td>Store_89         </td>
      </tr>
   </tbody>
</table>

### Add an application

#### In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

1.  Select **Applications** on the top toolbar.  
    <img src="/Images/TransferCFT/gettingstarted2.png" class="mediumWidth" />
2.  Click **Add application**, and complete the Name and Host name fields using the values that you copied from the **Products** page. You can leave other values set to the default.
3.  Click **Save application**.

Results: <span style="font-weight: normal;">Your **Application List** page should resemble the following diagram.</span>

<img src="/Images/TransferCFT/application_list_complete.png" class="maxWidth" alt="Application list in Central Governance showing 3 example applications to use in flows" />