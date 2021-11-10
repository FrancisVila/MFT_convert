{
    "title": "Listing  partner details",
    "linkTitle": "LISTPART - List partner details",
    "weight": "350"
}This topic describes how to use the LISTPART command to view partner
characteristics.

Use this command to view the characteristics of partners
(general or network characteristics), according to the selection criteria
indicated in the command.

In the absence of a previous CONFIG TYPE = OUTPUT command,
the execution report is written on the standard output of the CFTUTIL
program.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Parameters</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/id">ID</a> </p>         </td>
         <td><p>Partner or partner list identifier.</p>
<p>Used to select a single partner or a set of partners, using
the special wildcard character "<strong>*</strong>".</p>
<p>Example:</p>
<p>ID = PART1: for the partner PART1 only<br />
ID = IB*: for all the partners whose identifier begins with "IB"<br />
ID = *: for all the partners</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/type">TYPE</a></p>         </td>
         <td><p>Defines the type of characteristics to be listed.</p>
<p>TYPE can take the predefined values indicated in the Type
table.</p>         </td>
      </tr>
   </tbody>
</table>

Example 1

To view all the contents of the records of the PARTNER
file:


    LISTPART TYPE = ALL

Example 2

To view broadcasting lists:


    LISTPART TYPE = DEST
