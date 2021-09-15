{
    "title": "Velocity troubleshooting",
    "linkTitle": "Velocity troubleshooting",
    "weight": "350"
}To add additional logging of email notifications events, edit the `tm-log4j.xml` file in the `<FILEDRIVEHOME>/conf/` directory and add the following code where the original `appender` elements are located:

    <appender name="AgentLog"
       >
       <param name="File" value="/opt/TMWD/SecureTransport/var/logs/
          stx-agent.log" />
       <param name="Append" value="true" />
       <param name="DatePattern" value="'.'yyyy-MM-dd" />
       <param name="RotateDirectory"
          value="/opt/TMWD/SecureTransport/var/db/hist/logs" />

       <layout >
          <param name="ConversionPattern" value="%d %p [%t] %c - %m%n" />
       </layout>
    </appender>

Add the following code at the end of the file:

    <logger name="com.tumbleweed.st.server.util.mailer" additivity="false">
       <level value="debug" />
       <appender-ref ref="AgentLog" />
    </logger>
    <logger name="javax.mail" additivity="false">
       <level value="debug" />
       <appender-ref ref="AgentLog" />
    </logger>
    <logger name="org.apache.commons.mail" additivity="false">
       <level value="debug" />
       <appender-ref ref="AgentLog" />
    </logger>

This configuration creates the log file named `stx-agent.log` in the `<FILEDRIVEHOME>/SecureTransport/var/logs/` directory when SecureTransport is restarted.

## Restart SecureTransport

Use the following procedure to restart SecureTransport.

1.  Go to `<FILEDRIVEHOME>/bin` and execute `./stop_all`.
2.  When the prompt returns, execute `./start_all`.

The file `stx-agent.log` logs all events for email notifications.
