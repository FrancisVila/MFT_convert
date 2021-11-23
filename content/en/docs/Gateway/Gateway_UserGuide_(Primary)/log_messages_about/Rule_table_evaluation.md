{
    "title": "Rule Table evaluation ",
    "linkTitle": "Rule Table evaluation",
    "weight": "430"
}{{< Gateway/componentlongname  >}}: Messages and codes

The type of process is listed in the error message and varies depending on the message originator. In the following tables the process is represented by **\[process\]**.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO500E"></span>500</p>         </td>
         <td><p><span style="font-weight: bold;">[%1] E SYMBVAR_E [%2] decision rule [%3], symbolic variable (%4) in the condition (%5 %6</span> <span style="font-weight: bold;">%7) is not recognized</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Unknown symbolic variable in condition.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Condition contents - operand</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Condition contents - operator</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Condition contents - operand</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the symbolic variables used are correct for the given Rule Table type.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO501E"></span>501</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] decision rule [%3], symbolic variable (%4) in the condition (%5 %6 %7) does not have a value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The symbolic variable in the condition has a void value.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Condition contents - operand</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Condition contents - operator</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Condition contents - operand</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO502E"></span>502</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] decision rule [%3], symbolic variable (%4) in the condition (%5 %6 %7) has an incorrect value, the rule table routing has ended</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with an invalid value in the condition.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Condition contents - operand</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Condition contents - operator</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Condition contents - operand</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO503E"></span>503</p>         </td>
         <td><p><span style="font-weight: bold;">[%1] E SYNTAX_E [%2] decision rule [%3],  the condition (%4,%5,%6) contains a syntax error</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a syntax error in the condition.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Condition contents - operand</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Condition contents - operator</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Condition contents - operand</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the condition syntax.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO504E"></span>504</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] decision rule [%3], the symbolic variable (%4) used in the field %5 for the model %6 is unknown</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is an unknown symbolic variable in the transfer Model</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Model field</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the symbolic variables used are correct for the given the Rule Table type</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO505E"></span>505</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] decision rule [%3], the symbolic variable (%4) used in the field %5 for the model %6 does not have a value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with a void value in the transfer Model.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Model field</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO506E"></span>506</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] decision rule [%3], the symbolic variable (%4) used in the field %5 for the model %6 contains an incorrect value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with an invalid value in the transfer model</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Model field</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO507E"></span>507</p>         </td>
         <td><p>[%1] E SYNTAX_E [%2] decision rule [%3], the field %4 for the model %5 contains a syntax error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a syntax error in the transfer model</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Field name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the field syntax</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO508E"></span>508</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] The symbolic variable (%3) used in the field %4 in the default transfer model %5 is unknown</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is an unknown symbolic variable in the default transfer model</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Default Model field</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Default Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the symbolic variables used are correct for the given the Rule Table type</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO509E"></span>509</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] The symbolic variable (%3) used in the field %4 in the model %5 did not receive a value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with a void value in the default transfer model</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer Model (default)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Model field name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO510E"></span>510</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] The symbolic variable (%3) used in the field %4 in the default transfer model %5 received an incorrect value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with an invalid value in the default transfer model</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer Model (default)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Model field name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO511E"></span>511</p>         </td>
         <td><p>[%1] E SYNTAX_E [%2] The field %3 in the default transfer model %4 contains a syntax error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a syntax error in the default transfer model</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer Model (default)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Model field name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the syntax of the default transfer model field</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO512E"></span>512</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] decision rule [%3], the symbolic variable (%4) used in the command line to execute (%5) is unknown</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is an unknown symbolic variable in the command line</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Command line</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the symbolic variables used are correct for the given the Rule Table type</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO513E"></span>513</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] decision rule [%3], the symbolic variable (%4) used in the command line to execute (%5) did not receive a value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with a void value in the command line.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Command line</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO514E"></span>514</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] decision rule [%3], the symbolic variable (%4) used in the command line to execute (%5) received an incorrect value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with an invalid value in the command line.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Command line</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO515E"></span>515</p>         </td>
         <td><p>[%1] E SYNTAX_E [%2] decision rule [%3], the command line to execute (%4) contains a syntax error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a syntax error in the command line.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Command line</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the syntax for the line to execute</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO516E"></span>516</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] the symbolic variable (%3) used in the default command line to execute (%4) is unknown</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is an unknown symbolic variable in the default command line.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Command line</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the used symbolic variables is correct for the given the Rule Table type.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO517E"></span>517</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] the symbolic variable (%3) used in the default command line to execute (%4) did not receive a value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with a void value in the default command line.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Command line</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO518E"></span>518</p>         </td>
         <td><p>[%1] E SYMBVAR_E [%2] the symbolic variable (%3) used in the default command line to execute (%4) received an incorrect value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with an invalid value in the default command line.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Command line</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO519E"></span>519</p>         </td>
         <td><p>[process] E SYNTAX_E [%2] decision rule [%3], the default command line (%4) contains a syntax error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a syntax error in the default command line.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Command line</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the syntax of the default command line.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO520E"></span>520</p>         </td>
         <td><p>[process] E SYMBVAR_E [%2] decision rule [%3], the symbolic variable (%4) used in the field %5 in the purge model %6 is unknown</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is an unknown symbolic variable in the purge Model.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Purge Model field name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the used symbolic variables is correct for the given the Rule Table type.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO521E"></span>521</p>         </td>
         <td><p>[process] E SYMBVAR_E [%2] decision rule [%3], the symbolic variable (%4) used in the field %5 in the purge model %6 did not receive a value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with a void value in the purge Model.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Purge Model field name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO522E"></span>522</p>         </td>
         <td><p>[process] E SYMBVAR_E [%2] decision rule [%3], the symbolic variable (%4) used in the field %5 in the purge model %6 received an incorrect value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with an invalid value in the purge Model.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Purge Model field name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Model</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO523E"></span>523</p>         </td>
         <td><p>[process] E SYNTAX_E [%2] decision rule [%3], the field %4 in the purge model %5 contains a syntax error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a syntax error in the purge Model.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Purge Model field name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Model</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the syntax of the purge Model field.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO524E"></span>524</p>         </td>
         <td><p>[process] E SYMBVAR_E [%2] The symbolic variable (%3) used in the field %4 in the default purge model %5 is unknown</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is an unknown symbolic variable in the default purge Model.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Default purge Model field name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the used symbolic variables is correct for the given Rule Table type.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO525E"></span>525</p>         </td>
         <td><p>[process] E SYMBVAR_E [%2] The symbolic variable (%3) used in the field %4 in the default purge model %5 did not receive a value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a symbolic variable with a void value in the default purge Model.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Default purge Model field name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Default purge Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO526E"></span>526</p>         </td>
         <td><p>[process] E SYMBVAR_E [%2] The symbolic variable (%3) used in the field %4 in the default purge model %5 received an incorrect value</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Symbolic variable with invalid value in the default purge Model</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Default purge Model field name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Default purge Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO527E"></span>527</p>         </td>
         <td><p>[process] E SYNTAX_E [%2] The field %3 in the default purge model %4 contains a syntax error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Syntax error in the default purge Model</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Default purge Model field name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Default purge Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the syntax of the default purge Model field</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO528E"></span>528</p>         </td>
         <td><p>[process] E OP_E [%2] In the decision rule [%3] the operator (%4) in the condition (%5 %6 %7) is not correct for this type of operand</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Invalid operator for the type of operands</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Operator</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Operand</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Operator</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Operand</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the operator is correct for the type of the operands</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO529E"></span>529</p>         </td>
         <td><p>[process] E TYPES_E [%2] in decision rule [%3], the left operand and the right operand in the condition (%4 %5 %6) cannot be compared because they are not the same type</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Incompatible type for operands</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Operand</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Operator</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Operand</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the type of operand is correct.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO530E"></span>530</p>         </td>
         <td><p>[process] E OPERAND_E [%2] decision rule [%3], the number of arguments to the right of the operator  (%4) in the condition (%5 %6 %7) is incorrect</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Incorrect number of right operands.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Operator</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Operand</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Operator</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Operand</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check and change the condition.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO531E"></span>531</p>         </td>
         <td><p>[process] E EX_TYPE_E [%2] decision rule [%3], the task to execute is %4 type while the rule table is %5 type. This configuration is incorrect.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Incompatible execution type in Decision Rule task.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Task type</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Rule Table type</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check and change the Decision Rule.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO532E"></span>532</p>         </td>
         <td><p>[process] E EX_TYPE_E [%2] The task to execute (default task) is %3 type while the rule table is %4 type. This configuration is incorrect.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Incompatible task type for the Rule Table.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Task type</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Rule Table type</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check and change the task type or Rule Table.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO533I"></span>533</p>         </td>
         <td><p>[process] I TEMP_EVT The scheduled event planned for %2 occurs; the rule table %3 is going to be scanned</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The scheduled event is started</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Date/time</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO534I"></span>534</p>         </td>
         <td><p>[process] I FS_EVT The file %2 was put in the watch directory %3, the rule table %4 is going to be scanned</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Scheduled Directory Scanning is started.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>The deposited file name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Watch directory name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO535I"></span>535</p>         </td>
         <td><p>[process] I XMS_EVT The XMS message  %2 was recuperated in the queue %3, the rule table %4 is going to be scanned</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Axway Messaging is started.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Axway Messaging message</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Axway Messaging queue name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO536I"></span>536</p>         </td>
         <td><p>[process] I DR_SELECT [%2] the decision rule %3 having the execution type %4 was selected</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Decision Rule was selected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Execution type</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO537I"></span>537</p>         </td>
         <td><p>[process] I DR_SELECT [%2] the decision rule %3 was refused because the condition (%4 %5 %6) is invalid</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Decision Rule was not selected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Operand</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Operator</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Operand</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO538I"></span>538</p>         </td>
         <td><p>[process] I MDL_EX [%2] decision rule [%3], the model %4 will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The selected Decision Rule model will be applied.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO539I"></span>539</p>         </td>
         <td><p>[process] I D_MDL_EX [%2] the default model %3 will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default Model will be applied.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Default Model name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO540E"></span>540</p>         </td>
         <td><p>[process] E MDL_E [%2] decision rule [%3], the model %4 does not exist</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Model was not found</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the model name is correct. If model does not exist, create new model.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO541E"></span>541</p>         </td>
         <td><p>[process] E D_MDL_E [%2] the default model %3 does not exist</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default Model was not found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Default Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the Model name is correct. If Model does not exist, create new Model.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO542I"></span>542</p>         </td>
         <td><p>[process] I SS_EX [%2] decision rule [%3], the batch script %4 will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The batch script will be applied.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Batch script</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO543I"></span>543</p>         </td>
         <td><p>[process] I D_SS_EX [%2] the default batch script  %3 will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default batch script will be applied.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Default batch script</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO544E"></span>544</p>         </td>
         <td><p>[process] E SS_E [%2] decision rule [%3], the batch script is not specified</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The batch script is not referenced.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Specify the batch script in the Decision Rule action.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO545E"></span>545</p>         </td>
         <td><p>[process] E D_SS_E [%2] the default batch script is not specified</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default script is not referenced</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Specify the batch script in the Rule Table default action</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO546I"></span>546</p>         </td>
         <td><p>[process] I PS_EX [%2] decision rule [%3], the PERL script %4 will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Perl script will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Perl script</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO547I"></span>547</p>         </td>
         <td><p>[process] I D_PS_EX [%2] the default Perl script %3 will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default Perl script will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Default Perl script</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO548E"></span>548</p>         </td>
         <td><p>[process] E PS_E [%2] decision rule [%3], the Perl script is not specified</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Perl script is not referenced.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Specify the Perl script in the Decision Rule action.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO549E"></span>549</p>         </td>
         <td><p>[process] E D_PS_E [%2] the default Perl script is not specified</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default Perl script is not referenced.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Specify the Perl script in the Rule Table default action.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO550E"></span>550</p>         </td>
         <td><p>[process] E PS_E [%2] decision rule [%3], the specified Perl script can not be found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Perl script does not exist</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the name of the Perl script, or create a new script.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO551E"></span>551</p>         </td>
         <td><p>[process] E D_PS_E    [%2] the default Perl script specified in the rule table cannot be found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default Perl script does not exist</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the name of the Perl script, or create a new script.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO552I"></span>552</p>         </td>
         <td><p>[process] I NOP [%2] decision rule [%3], no task will be launched</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The task cannot be applied.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO553I"></span>553</p>         </td>
         <td><p>[process] I D_NOP [%2] Default task, no task will be launched</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Default task. None will be applied.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO554I"></span>554</p>         </td>
         <td><p>[process] I PUR_EX [%2] decision rule [%3], the purge model %4 will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Mailbox cleaning will be applied.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Purge Model name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO555I"></span>555</p>         </td>
         <td><p>[process] I D_PUR_EX [%2] the default purge model  %3 will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default Mailbox cleaning will be applied.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Default purge Model</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO556E"></span>556</p>         </td>
         <td><p>[process] E PUR_E [%2] decision rule [%3], the purge model %4 does not exist</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The purge Model was not found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Purge Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the name of the purge Model or create a new one if it does not exist.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO557E"></span>557</p>         </td>
         <td><p>[process] E PUR_E [%2] the default purge model %3 doesn't exist</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default purge Model was not found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Purge Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the name of the purge Model or create a new one if it does not exist.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO558I"></span>558</p>         </td>
         <td><p>[process] I LPUR_EX [%2] decision rule [%3], the log will be purged</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Log cleaning will be applied.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO559I"></span>559</p>         </td>
         <td><p>[process] I DLPUR_EX [%2] Default task, the log will be purged</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Default: log cleaning will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO560I"></span>560</p>         </td>
         <td><p>[process] I SPUR_EX [%2] decision rule [%3], the stats will be purged</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The stats cleaning will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO561I"></span>561</p>         </td>
         <td><p>[process] I DSPUR_EX [%2] Default task, the stats will be purged</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default stats cleaning will be applied</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO562I"></span>562</p>         </td>
         <td><p>[process] I PS_E The Perl script %2 could not be executed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Perl script was not launched.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Perl script</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO563I"></span>563</p>         </td>
         <td><p>[process] I PS_EX The Perl script %2 was executed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Perl script was launched.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Perl script</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO564I"></span>564</p>         </td>
         <td><p>[process] I XFER_EX [%2] transfer launched according to the model %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The transfer was started.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO565W"></span>565</p>         </td>
         <td><p>[process] W XFER_E The transfer according to the model %2 could not be launched. The reason for the failure is: %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The transfer was not started.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error returned</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the Model parameters are set correctly.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO566I"></span>566</p>         </td>
         <td><p>[process] I SS_E The batch script %2 could not be executed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The script was not started</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Batch script</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO567I"></span>567</p>         </td>
         <td><p>[%1] I SS_EX The batch script %2 was executed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The script was launched.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Batch script</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO568I"></span>568</p>         </td>
         <td><p>[NORMALLY NOT DISPLAYED]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO569I"></span>569</p>         </td>
         <td><p>%1 I MB_CLEA The mailbox was successfully cleaned according to the purge model %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Mailbox cleaning task is complete.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Purge Model</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO570E"></span>570</p>         </td>
         <td><p>%1 E MB_CLEA_E The mailbox could not be cleaned according to the purge model %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Mailbox could not be cleaned.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Purge Model</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO571I"></span>571</p>         </td>
         <td><p>[process] I LG_CLEA The log was successfully cleared.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The log cleaning task is complete.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO572I"></span>572</p>         </td>
         <td><p>[process] I LG_CLEA_E The log could not be cleared</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Log cleaning was not performed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO573I"></span>573</p>         </td>
         <td><p>[process] I ST_CLEA The stats were successfully cleaned.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The stats cleaning was performed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO574I"></span>574</p>         </td>
         <td><p>[%1] I ST_CLEA_E The stats could not be cleaned.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The stats cleaning was not performed</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO575I"></span>575</p>         </td>
         <td><p>[process] I EXIT_YES [%2] The user exit %3 returned the value 1. The rule table scanning can begin.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The user exit was successful</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>User exit name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO576I"></span>576</p>         </td>
         <td><p>[process] I EXIT_NO [%2] The user exit %3 returned the value 0. The rule table scanning is cancelled.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The user exit was not successful</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>User exit name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO577I"></span>577</p>         </td>
         <td><p>[process] I EXIT_ERR [%2] The user exit  %3 returned the value -1. The rule table scanning is cancelled.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The exit returned an error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>User exit name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO578I"></span>578</p>         </td>
         <td><p>[%1] I NO_CONDS [%2] decision rule %3 does not contain conditions. It is therefore automatically selected.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There are no conditions in the Decision Rule.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PRO579I"></span>579</p>         </td>
         <td><p>[%1] I WORK_DONE [%2] The rule table task is completed.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Task complete.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Rule Table name</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
