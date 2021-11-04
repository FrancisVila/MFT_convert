{
    "title": "Configure Single Sign-On (SSO) for streaming",
    "linkTitle": "Configure Single Sign-On (SSO) for streaming",
    "weight": "180"
}You can configure Single Sign-On (SSO) functionality when using streaming setups.

Here are the basic steps:

1.  Setup streaming. Refer to <a href="../../c_st_setup/t_st_stream_edge_backend" class="MCXref xref">Configure SecureTransport Back End to Edge streaming communication</a>.
2.  On backend configure the SSO for end-user. Refer to <a href="../c_st_enable_sso_endusers#Enable2" class="MCXref xref">Enable Single Sign-On (SSO) for end-users</a>.
3.  On the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edges navigate to **Authentication > Login Settings** and set **Required** for *SSO* for end-users.

> **Note:**
>
> The sso-enduser.xml file is taken from backend, corresponding to SSO Service Provider Entity ID value in the Setup &gt; Network zone.

For the backend network zones:

-   Private zone - SSO Service Provider Entity ID should be the Entity ID pointing to the Server.
-   Streaming zone - SSO Service Provider Entity ID should be the Entity ID pointing to the Edge.  

> **Note:**
>
> In a SecureTransport deployment, consisting of both backend and edge nodes, SSO must be configured and enabled on all nodes even if users are only logging in through the edge. On the edge, you must enable SSO for end-users. All backend and edge nodes in streaming must have same setting for SSO Authentication (Disabled or Required).
