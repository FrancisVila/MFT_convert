{
    "title": "CFTPRIV",
    "linkTitle": "Privileges - CFTPRIV",
    "weight": "260"
}Use this procedure to view a list of privileges and descriptions and perform related tasks in the user interface. See also <a href="../../../../internal_a_m_start_here/fm_access_management" class="MCXref xref">Access Management using Flow Manager</a>

### Using CFTPRIV

Privileges give users authorization to access and perform actions in the user interface. Examples of actions include CREATE, DELETE, VIEW, EDIT (use \* to assign all actions).

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>id</p>         </td>
         <td><p>String32</p>         </td>
         <td><p>Privilege identifier</p>         </td>
      </tr>
      <tr>
         <td><p>comment</p>         </td>
         <td><p>String80</p>         </td>
         <td><p>Comment</p>         </td>
      </tr>
      <tr>
         <td><p>resource</p>         </td>
         <td><p>String32</p>         </td>
         <td><p>Resource on which this privilege applies</p>         </td>
      </tr>
      <tr>
         <td><p>actions</p>         </td>
         <td><p>List of String32</p>         </td>
         <td><p>Actions authorized on the resource (1 to 16 actions)</p>         </td>
      </tr>
      <tr>
         <td><p>condition</p>         </td>
         <td><p>String256</p>         </td>
         <td><p>Condition to check for authorizing (<a href="#Specifyi">see below</a>)</p>         </td>
      </tr>
   </tbody>
</table>

Example of CFTPRIV in a configuration file:



    CFTPRIV      ID          = 'MYPRIV1',
                COMMENT     = 'My comment',
                 RESOURCE    = 'TRANSFER',
                 ACTIONS     = ( 'CREATE' , 'DELETE', 'VIEW', 'EDIT', 'CANCEL', 'RESUME', 
                                'PAUSE', 'EXECUTE', 'SUBMIT', 'END' ),
                 CONDITION   = '',
                 ORIGIN      = 'CFTUTIL',
                 MODE        = 'REPLACE'

<span id="Specifyi"></span>

### Specifying conditions

Conditions allow you to assign finer control on resources and actions by specifying a logical condition that must be true to authorize the action.

Examples

In these examples <span class="code">PART </span>and <span class="code">ID </span>are properties of the resource being checked. As you can see, you can use parenthesis and logical operators <span class="code">&&</span> (AND) and <span class="code">||</span> (OR).



    PART=="PARIS" && ID=="IDFDEF"
    (PART=="PARIS" || PART==”NEWYORK”) && ID~="IDF*"

Comparison operators include:

-   == : equals
-   != : not equal
-   ~= : matches (use \* and ? for jokers)
-   /= : not matching (use \* and ? for jokers)
-   &lt; : inferior to
-   &gt; : superior to
-   &lt;= : inferior or equal to
-   &gt;= :superior or equal to
