{
    "title": "Enable Logger service",
    "linkTitle": "Enable Logger service",
    "weight": "120"
}In order to enable logging when using the Logger service, edit the `com.axway.st.plugins` loggers in the `tm-log4j.xml` file. For example, with Pluggable Transfer Sites:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>&lt;logger name="com.axway.st.plugins.site" additivity="false"&gt;      </pre><pre xml:space="preserve">	&lt;level value="info" /&gt;</pre><pre xml:space="preserve">	&lt;appender-ref ref="ServerLog" /&gt; </pre><pre>&lt;/logger&gt;</pre>
         </td>
      </tr>
   </tbody>
</table>

For fine-tuning debug logging, add the transfer site name in conjunction with the `com.axway.st.plugins` logger.

In this case, use `com.axway.st.plugins.site.<transfer_site_name>` as shown on the example:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>&lt;logger name="com.axway.st.plugins.site.ts" additivity="false"&gt;      </pre><pre xml:space="preserve">	&lt;level value="debug" /&gt;</pre><pre xml:space="preserve">	&lt;appender-ref ref="ServerLog" /&gt; </pre><pre>&lt;/logger&gt;</pre>
         </td>
      </tr>
   </tbody>
</table>
