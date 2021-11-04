{
    "title": "Enable Logger service",
    "linkTitle": "Enable Logger service",
    "weight": "120"
}In order to enable logging when using the Logger service, edit the `com.axway.st.plugins` loggers in the `tm-log4j.xml` file. For example, with Pluggable Transfer Sites:


    <logger name="com.axway.st.plugins.site" additivity="false">      
        <level value="info" />
        <appender-ref ref="ServerLog" /> 
    </logger>

For fine-tuning debug logging, add the transfer site name in conjunction with the `com.axway.st.plugins` logger.

In this case, use `com.axway.st.plugins.site.<tr>` as shown on the example:


    <logger name="com.axway.st.plugins.site.ts" additivity="false">      
        <level value="debug" />
        <appender-ref ref="ServerLog" /> 
    </logger>
