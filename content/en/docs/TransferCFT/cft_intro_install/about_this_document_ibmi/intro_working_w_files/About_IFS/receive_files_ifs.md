{
    "title": "Configure receive mode (IFS)",
    "linkTitle": "Configure receive mode (IFS)",
    "weight": "230"
}## File types

The following table lists the different types of files that can be received on an IBM i system when using IFS.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <b>FRECFM</b> possibilities for all FTYPE are: <b>‘V’</b>, <b>‘F’</b>, and <b>‘ ’</b>	.         </td>
      </tr>
</table>

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>FTYPE</th>
         <th>Type of sent file</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>             ‘S’	         </td>
         <td>Text           </td>
      </tr>
      <tr>
         <td>            ‘D’ , ‘ ’	         </td>
         <td>Text          </td>
      </tr>
      <tr>
         <td>             ‘E’	         </td>
         <td>Text          </td>
      </tr>
      <tr>
         <td>             ‘Z’	         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td>             ‘J’         </td>
         <td>
            <p>Stream text  is an alternative way to transfer a text file. Every line of a file must end with an LF or CR/LF. However, during a transfer the CR/LF are changed to LFs. This enables a quicker reading, and a faster transfer.
</p>
            <p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.
</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
   </tbody>
</table>

Key

If your partner sends a PF-SRC file to be received on IFS, the content is slightly different depending on if you use the FTYPE ‘S’ or ‘E’. With the FTYPE ‘E‘, the content of the file is only the original content of the PF-SRC file. When the FTYPE is ‘S’, the content is the original content of the PF-SRC file along with the record character in the header line.

When sending a file from the part of an IBM i machine in text mode, the file is expected to be a standard text file. This means that every line of the file to transfer is finished either by a LF, either by a CR/LF. If not, the file is considered to be binary and Transfer CFT cannot read it. Use the binary mode to allow it to be transferred.
