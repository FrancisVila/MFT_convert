{
    "title": "Configure Single Sign-On (SSO) for streaming",
    "linkTitle": "Configure Single Sign-On (SSO) for streaming",
    "weight": "190"
}You can configure Single Sign-On (SSO) functionality when using streaming setups.

Here are the basic steps:

1.  Setup streaming. Refer to [Configure SecureTransport Back End to Edge streaming communication](../../c_st_setup/t_st_stream_edge_backend).
2.  On backend configure the SSO for end-user. Refer to [Enable Single Sign-On (SSO) for end-users](../c_st_enable_sso_endusers).
3.  On the SecureTransport Edges navigate to **Authentication > Login Settings** and set **Required** for *SSO* for end-users.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <code>sso-enduser.xml</code> file is taken from backend, corresponding to SSO Service Provider Entity ID value in the<strong> Setup &gt; Network zone</strong>.         </td>
      </tr>
</table>

For the backend network zones:

-   Private zone - SSO Service Provider Entity ID should be the Entity ID pointing to the Server.
-   Streaming zone - SSO Service Provider Entity ID should be the Entity ID pointing to the Edge.  

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In a SecureTransport deployment, consisting of both backend and edge nodes, SSO must be configured and enabled on all nodes even if users are only logging in through the edge. On the edge, you must enable SSO for end-users. All backend and edge nodes in streaming must have same setting for SSO Authentication (Disabled or Required).         </td>
      </tr>
</table>
