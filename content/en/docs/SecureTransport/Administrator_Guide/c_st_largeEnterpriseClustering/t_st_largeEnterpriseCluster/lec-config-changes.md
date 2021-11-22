{
    "title": "Configuration optimizations in case of increased transfers load",
    "linkTitle": "Configuration optimizations in case of increased transfers load",
    "weight": "150"
}The following suggested configuration allows the {{< SecureTransport/securetransportname  >}} administrator to specify the number of daemon threads used by the invocation service in the invocation-scheme configuration in `conf/hibernate-cache-config.xml`:



      <!--
        The DefaultInvocationService is used by the com.tumbleweed.st.server.api.cluster.InvocationManager
         -->
        
    <invocation-scheme>
            <scheme-name>invocation-service</scheme-name>
            <service-name>DefaultInvocationService</service-name>
            <thread-count>0</thread-count>
            <autostart>true</autostart>

      </invocation-scheme> 

> **Note:**
>
> &lt;thread-count> is an optional parameter which specifies the number of daemon threads used by the invocation service. When set to zero, all relevant tasks are performed on the service thread. Accepted values include '0' and positive integers. The default value is the value specified in the tangosol-coherence.xml descriptor.
