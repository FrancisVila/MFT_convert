{
    "title": "Configure Single Sign-On (SSO) for streaming",
    "linkTitle": "Configure Single Sign-On (SSO) for streaming",
    "weight": "180"
}You can configure Single Sign-On (SSO) functionality when using streaming setups.

Here are the basic steps:

1.  Setup streaming. Refer to [Configure SecureTransport Back End to Edge streaming communication](../../c_st_setup/t_st_stream_edge_backend).
2.  On backend configure the SSO for end-user. Refer to [Enable Single Sign-On (SSO) for end-users](../c_st_enable_sso_endusers#Enable2).
3.  On the {{< SecureTransport/componentshortname >}} Edges navigate to **Authentication > Login Settings** and set **Required** for *SSO* for end-users.

> **Note:**
>
> The sso-enduser.xml file is taken from backend, corresponding to SSO Service Provider Entity ID value in the Setup &gt; Network zone.

For the backend network zones:

-   Private zone - SSO Service Provider Entity ID should be the Entity ID pointing to the Server.
-   Streaming zone - SSO Service Provider Entity ID should be the Entity ID pointing to the Edge.  

> **Note:**
>
> In a SecureTransport deployment, consisting of both backend and edge nodes, SSO must be configured and enabled on all nodes even if users are only logging in through the edge. On the edge, you must enable SSO for end-users. All backend and edge nodes in streaming must have same setting for SSO Authentication (Disabled or Required).
