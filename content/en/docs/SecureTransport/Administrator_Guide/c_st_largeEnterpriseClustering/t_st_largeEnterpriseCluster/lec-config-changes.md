{
    "title": "Configuration optimizations in case of increased transfers load",
    "linkTitle": "Configuration optimizations in case of increased transfers load",
    "weight": "160"
}The following suggested configuration allows the SecureTransport administrator to specify the number of daemon threads used by the invocation service in the invocation-scheme configuration in `conf/hibernate-cache-config.xml`:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>  &lt;!--
    The DefaultInvocationService is used by the com.tumbleweed.st.server.api.cluster.InvocationManager
     --&gt;
    </p><pre>&lt;invocation-scheme&gt;
</pre><pre>        &lt;scheme-name&gt;invocation-service&lt;/scheme-name&gt;
</pre><pre>        &lt;service-name&gt;DefaultInvocationService&lt;/service-name&gt;
</pre><pre>        &lt;thread-count&gt;0&lt;/thread-count&gt;
</pre><pre>        &lt;autostart&gt;true&lt;/autostart&gt;
</pre>
            <p>  &lt;/invocation-scheme&gt; </p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><code>&lt;thread-count&gt;</code> is an optional parameter which specifies the number of daemon threads used by the invocation service.  When set to zero, all relevant tasks are performed on the service thread.  Accepted values include '<code>0</code>' and positive integers. The default value is the value specified in the <code>tangosol-coherence.xml</code> descriptor.         </td>
      </tr>
</table>
