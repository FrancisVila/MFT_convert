{
    "title": "Modify date and time format",
    "linkTitle": "Modify date and time format",
    "weight": "80"
}You can modify the displayed date and time format. The default format is: `M/D/YYYY, h:mm:ss A`

1.  In the `stwebclient.config.json` file, specify the preferred format in the `i18n` section:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>{</pre><pre xml:space="preserve">  ...</pre><pre xml:space="preserve">  "i18n": {</pre><pre xml:space="preserve">    "dateFormat": "MMMM Do YYYY, h:mm:ss a"</pre><pre xml:space="preserve">  }</pre><pre xml:space="preserve">  ...</pre><pre>}</pre>
         </td>
      </tr>
   </tbody>
</table>

2.  Refresh the ST Web Client.

For a list of date and time formatting options, refer to [Formatting options](https://momentjs.com/docs/#/displaying/).
