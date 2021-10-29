{
    "title": "Access Tokens",
    "linkTitle": "Access Tokens ",
    "weight": "220"
}An access token is a unique identifier, or credential, that an application can use to access an API. The token indicates to the API that the holder is authorized to access the API and the resources available to that user or account.

The UCONF copilot.restapi.api\_token\_validity parameter sets the access token's expiration period. By default, the value is set to 0, which disables expiration. You can modify this parameter if you want access tokens to have a specific expiration period. The token\_validity parameter applies to tokens at the time they are created. Tokens that exist prior to modifying this value retain the expiration date that was set at the time they were created.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">If you modify the UCONF <span>copilot.restapi.api_token_validity</span> parameter, you must restart Copilot for the change to be taken into account.         </td>
      </tr>
   </tbody>
</table>

Related information includes:

-   Using access tokens with REST APIs, see [Using the Swagger UI](../../../app_integration_intro/using_apis/api_intro/swagger_intro)
-   Token keys and renewal, please see [SSO using SAML](../use_saml)
-   [Changing the key length](../../../governance_services_intro/register_cg) for a Central Governance certificate
-   [Bearer authentication](api_authentication.htm)

## Create a token

In the Transfer CFT UI:

1.  Navigate to your user login in the upper right hand corner.
2.  Select **My Access Tokens** in the drop-down menu.  
    The **My Access Token** page displays.
3.  Click **Generate Token**.  
    The Action, User, Creation date, and Token fields display. In the **Token** field, click the ![](/Images/TransferCFT/copy_icon.png)copy icon to easily copy the entire token.

Alternatively, you can use the Swagger REST API to generate the token.

1.  Log on the Swagger UI at https://&lt;UI\_server\_host>:&lt;RestApi\_port>/cft/api/v1/ui.
2.  Authenticate with a user.
3.  In the **Miscellaneous** category, select **Post** >** objects/cfttoken** option.
4.  Select **Try it out**.
5.  Select **Execute**.
6.  Copy the Value field from the response; this is your generated token.

## Revoke a token

In the Transfer CFT UI:

1.  Navigate to the ![](/Images/TransferCFT/security_icon.png) **Security** icon in the left pane.
2.  Click Access Tokens to open the page.
3.  Select the user and move to the Token field. Click ![](/Images/TransferCFT/revoke_icon.png) to revoke a token.  
    A different message displays depending on if you are removing the first or second token.
4.  Click **Ok** to confirm that you are removing that user's token.

## Impact of modifying the private key

Access tokens and SAML headers are signed using the key associated with the certificates referenced by `copilot.ssl.sslcertfile`. If this parameter is not set, but Central Governance or FM is enabled, the governance certificate is used. If you change the certificate that is referenced in `copilot.ssl.sslcertfile` or you modify the   `cg.certificate.governance.key_len `value, the impact is that the corresponding private key changes. This means that once the new key is generated, access tokens and SAML exchanges with the SAML IDP no longer work.

You can see the [Change the private key length](../../../governance_services_intro/cg_postregister) section for details.

If you change the private key, you must:

1.  From the Transfer CFT user interface, revoke all existing API tokens for all users.
2.  From the Transfer CFT user interface, regenerate the API tokens.
3.  Update each REST API client application with the new API token.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">If you are reregistering Transfer CFT with either <span>Central Governance</span> or <span>Flow Manager</span>, you must revoke and recreate all the tokens from this <span>Transfer CFT</span>.         </td>
      </tr>
   </tbody>
</table>
