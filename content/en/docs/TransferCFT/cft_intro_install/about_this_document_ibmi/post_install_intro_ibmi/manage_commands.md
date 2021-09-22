{
    "title": "Manage commands",
    "linkTitle": "Manage commands",
    "weight": "180"
}This section describes all of the command available to manage your Transfer CFT product.

## Standard commands

<table border="1" cellpadding="0" cellspacing="0" xmlns="http://www.w3.org/TR/REC-html40">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
<p xmlns="http://www.w3.org/TR/REC-html40">Command</p>
</th>
         <th>
<p xmlns="http://www.w3.org/TR/REC-html40">Comment</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>CFTSTART</p>
         </td>
         <td>
            <p>Start Transfer CFT</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTSTOP</p>
         </td>
         <td>
            <p>Stop Transfer CFT</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>COPSTART</p>
         </td>
         <td>
            <p>Start the UI server</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>COPSTOP</p>
         </td>
         <td>
            <p>Stop the UI server</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTMN</p>
         </td>
         <td>
            <p>This is the procedure to manage Transfer CFT and to configure multi-node. Add
 the following action(s) to manage your product:</p>
            <ul xmlns="">
               <li>START               </li>
               <li>  STOP                </li>
               <li>RESTART                </li>
               <li>ADD_NODE                </li>
               <li>REMOVE_NODE                </li>
               <li>ADD_HOST                </li>
               <li>REMOVE_HOST                </li>
               <li>REMOVE_NODE                </li>
               <li>ENABLE_NODE                </li>
               <li>DISABLE_NODE                </li>
            </ul>
            <p><table cellpadding="0" cellspacing="0" xmlns="">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">CFTMN is the equivalent of <span>cft script</span> for UNIX or
 Windows.         </td>
      </tr>
</table></p>
         </td>
      </tr>
   </tbody>
</table>

## Deprecated commands

<table border="1" cellpadding="0" cellspacing="0" xmlns="http://www.w3.org/TR/REC-html40">
         <col xmlns=""/>
         <col xmlns=""/>
<thead xmlns="">
      <tr>
         <th>Replace this command...</th>
         <th>With the new command...</th>
      </tr>
   </thead>
<tbody xmlns="">
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">
            <p>SHUT</p>
         </td>
         <td valign="top" width="337">
            <p>CFTSTOP + COPSTOP</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">
            <p>CFTMGSBM</p>
         </td>
         <td valign="top" width="337">
            <p>CFTSTART</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">
            <p>STARTCOPB</p>
         </td>
         <td valign="top" width="337">
            <p>COPSTART</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">
            <p>COPSMNG </p>
         </td>
         <td valign="top" width="337">
            <p>COPSTART</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">
            <p>COPSTOPM</p>
         </td>
         <td valign="top" width="337">
            <p>COPSTOP</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">
            <p>STOPCOPL</p>
         </td>
         <td valign="top" width="337">
            <p>COPSTOP</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">
            <p>BACKGROUND_C</p>
         </td>
         <td valign="top" width="337">
<p xmlns="">BACKGROUND</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">SNDCFTF
         </td>
         <td valign="top" width="337" xmlns="">CFTUTIL (See <b>Example 1</b>)         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">SNDCFTSPLF         </td>
         <td valign="top" width="337" xmlns="">CFTUTIL (See <b>Example 2</b>)         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">MAJSECINI         </td>
         <td valign="top" width="337" xmlns="">No replacement         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">MAJSECENVG          </td>
         <td valign="top" width="337" xmlns="">No replacement         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td valign="top" width="255">GENEDICT         </td>
         <td valign="top" width="337" xmlns="">No replacement         </td>
      </tr>
   </tbody>
</table>

**Example 1**

Send a member:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL send PART=&lt;PART&gt;, IDF=&lt;IDF&gt;, FNAME=&amp;LIB/&amp;FILE(&amp;MBR)         </td>
      </tr>
   </tbody>
</table>

**Example 2**

Send a spool file:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL send PART=&lt;PART&gt;, IDF=&lt;IDF&gt;, FNAME=&amp;FILE/&amp;SPLNBR/&amp;WORK/&amp;JOBNBR         </td>
      </tr>
   </tbody>
</table>

 
