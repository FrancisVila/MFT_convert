{
    "title": "Velocity troubleshooting",
    "linkTitle": "Velocity troubleshooting",
    "weight": "350"
}To add additional logging of email notifications events, edit the `tm-log4j.xml` file in the `<FILEDRIVEHOME>/conf/` directory and add the following code where the original `appender` elements are located:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>&lt;appender name="AgentLog"<br/>   &gt;<br/>   &lt;param name="File" value="/opt/TMWD/SecureTransport/var/logs/<br/>      stx-agent.log" /&gt;<br/>   &lt;param name="Append" value="true" /&gt;<br/>   &lt;param name="DatePattern" value="'.'yyyy-MM-dd" /&gt;<br/>   &lt;param name="RotateDirectory"<br/>      value="/opt/TMWD/SecureTransport/var/db/hist/logs" /&gt;<br/><br/>   &lt;layout &gt;<br/>      &lt;param name="ConversionPattern" value="%d %p [%t] %c - %m%n" /&gt;<br/>   &lt;/layout&gt;<br/>&lt;/appender&gt;</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

Add the following code at the end of the file:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>&lt;logger name="com.tumbleweed.st.server.util.mailer" additivity="false"&gt;<br/>   &lt;level value="debug" /&gt;<br/>   &lt;appender-ref ref="AgentLog" /&gt;<br/>&lt;/logger&gt;<br/>&lt;logger name="javax.mail" additivity="false"&gt;<br/>   &lt;level value="debug" /&gt;<br/>   &lt;appender-ref ref="AgentLog" /&gt;<br/>&lt;/logger&gt;<br/>&lt;logger name="org.apache.commons.mail" additivity="false"&gt;<br/>   &lt;level value="debug" /&gt;<br/>   &lt;appender-ref ref="AgentLog" /&gt;<br/>&lt;/logger&gt;</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

This configuration creates the log file named `stx-agent.log` in the `<FILEDRIVEHOME>/SecureTransport/var/logs/` directory when SecureTransport is restarted.

## Restart SecureTransport

Use the following procedure to restart SecureTransport.

1.  Go to `<FILEDRIVEHOME>/bin` and execute `./stop_all`.
2.  When the prompt returns, execute `./start_all`.

The file `stx-agent.log` logs all events for email notifications.
