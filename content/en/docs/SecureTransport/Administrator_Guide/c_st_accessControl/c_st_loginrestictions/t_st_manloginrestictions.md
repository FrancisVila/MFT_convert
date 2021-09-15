{
    "title": "Manage Login Restriction Policies",
    "linkTitle": "Manage Login Restriction Policies",
    "weight": "300"
}Login restrictions limit access to SecureTransport Servers and SecureTransport Edges through the evaluation of `ALLOW_THEN_DENY` and `DENY_THEN_ALLOW` Login Restriction Policies for end users. The following table describes the evaluation result for different types of Login Restriction Policies.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Match</th>
         <th>ALLOW_THEN_DENY</th>
         <th>DENY_THEN_ALLOW</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Match Allow only         </td>
         <td>Request allowed         </td>
         <td>Request allowed         </td>
      </tr>
      <tr>
         <td>Match Deny only         </td>
         <td>Request denied         </td>
         <td>Request denied         </td>
      </tr>
      <tr>
         <td>No match         </td>
         <td>Default to second directive: Denied         </td>
         <td>Default to second directive: Allowed         </td>
      </tr>
      <tr>
         <td>Match both 
Allow and Deny
         </td>
         <td>Final match controls: Denied         </td>
         <td>Final match controls: Allowed         </td>
      </tr>
   </tbody>
</table>

To access and manage the Login Restriction Policies, select **Access &gt; Login Restrictions** in the SecureTransport Administration Tool. The *Login Restriction Policies for End Users* page will be displayed. Use the *Login Restriction Policies for End Users* page to create and maintain Login Restriction Policies.

The following topics provide how-to instructions for managing Login Restriction Policies:

-   [Add Login Restriction Policies](#adding)
-   [Edit a Login Restriction Policy](#editing)
-   [Change the default Login Restriction Policy](#changing)
-   [Delete Login Restriction Policies](#deleting)

**Related topic:**

-   [Create Login Restriction Policy entries](../t_st_manloginrestictionpolicies)

## <span id="Adding"></span>Add Login Restriction Policies

Use the following instructions to add a new Login Restriction Policy:

1.  Click **New Login Restriction Policy**.  
    The *New Login Restriction Policy entry* page will be displayed.
2.  Refer to [Create a Login Restriction Policy](../t_st_manloginrestictionpolicies) for instructions on creating a new Login Restriction Policy.

## <span id="Editing"></span>Edit a Login Restriction Policy

Use the following instructions to edit an existing Login Restriction Policy:

1.  Click on the Policy Name to edit the selected Login Restriction Policy.  
    The *Edit Login Restriction Policy entry* page will be displayed.
2.  Refer to [Edit a Login Restriction Policy](../t_st_manloginrestictionpolicies) for instructions on editing an existing Login Restriction Policy.

## <span id="Changing"></span>Change the default Login Restriction Policy

Use the following instructions to change the default Login Restriction Policy:

1.  Select the desired Login Restriction Policy to make the default policy using the *Policy Name* checkbox.
2.  Click **Change Default**.

The selected Login Restriction Policy is now the default policy. The default Login Restriction Policy is indicated by the addition of (default) to the policy name.

You can also unselect the default Login Restriction Policy use the following instructions:

1.  Select the current default Login Restriction Policy using the *Policy Name* checkbox.
2.  Click **Change Default**.

The selected Login Restriction Policy is no longer the default policy and no Login Restriction Policies are set as the default policy.

## <span id="Deleting"></span>Delete Login Restriction Policies

Use the following instructions to delete a Login Restriction Policy:

1.  Select the desired Login Restriction Policy to delete using the *Policy Name* checkbox.
2.  Click Delete.
3.  Confirm the deletion of the selected Login Restriction Policy.
