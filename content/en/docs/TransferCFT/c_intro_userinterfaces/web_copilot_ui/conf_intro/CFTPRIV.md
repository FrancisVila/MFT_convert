{
    "title": "Privileges - CFTPRIV",
    "linkTitle": "Privileges - CFTPRIV",
    "weight": "260"
}Use this procedure to view a list of privileges and descriptions and perform related tasks in the user interface. See also [Access Management using Flow Manager](../../../../internal_a_m_start_here/fm_access_management)

### Using CFTPRIV

Privileges give users authorization to access and perform actions in the user interface. Examples of actions include CREATE, DELETE, VIEW, EDIT (use \* to assign all actions).

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Type</p>
</th>
         <th>
            <p>Comment</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>id</p>
         </td>
         <td>
            <p>String32</p>
         </td>
         <td>
            <p>Privilege identifier</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>comment</p>
         </td>
         <td>
            <p>String80</p>
         </td>
         <td>
            <p>Comment</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>resource</p>
         </td>
         <td>
            <p>String32</p>
         </td>
         <td>
            <p>Resource on which this privilege applies</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>actions</p>
         </td>
         <td>
            <p>List of String32</p>
         </td>
         <td>
            <p>Actions authorized on the resource (1 to 16 actions)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>condition</p>
         </td>
         <td>
            <p>String256</p>
         </td>
         <td>
            <p>Condition to check for authorizing (<a href="#specifyi">see below</a>)</p>
         </td>
      </tr>
   </tbody>
</table>

Example of CFTPRIV in a configuration file:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTPRIV      ID          = 'MYPRIV1',</p>
            <p>            COMMENT     = 'My comment',</p>
            <p>             RESOURCE    = 'TRANSFER',</p>
            <p>             ACTIONS     = ( 'CREATE' , 'DELETE', 'VIEW', 'EDIT', 'CANCEL', 'RESUME', </p>
            <p>                            'PAUSE', 'EXECUTE', 'SUBMIT', 'END' ),</p>
            <p>             CONDITION   = '',</p>
            <p>             ORIGIN      = 'CFTUTIL',</p>
            <p>             MODE        = 'REPLACE'</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Specifyi"></span>Specifying conditions

Conditions allow you to assign finer control on resources and actions by specifying a logical condition that must be true to authorize the action.

Examples

In these examples PART and ID are properties of the resource being checked. As you can see, you can use parenthesis and logical operators && (AND) and || (OR).

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>PART=="PARIS" &amp;&amp; ID=="IDFDEF"</p>
            <p>(PART=="PARIS" || PART==”NEWYORK”) &amp;&amp; ID~="IDF*"</p>
         </td>
      </tr>
   </tbody>
</table>

Comparison operators include:

-   == : equals
-   != : not equal
-   ~= : matches (use \* and ? for jokers)
-   /= : not matching (use \* and ? for jokers)
-   &lt; : inferior to
-   &gt; : superior to
-   &lt;= : inferior or equal to
-   &gt;= :superior or equal to
