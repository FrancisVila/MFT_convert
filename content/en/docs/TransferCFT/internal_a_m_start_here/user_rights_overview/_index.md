{
    "title": "About Transfer CFT system users ",
    "linkTitle": "Manage user rights",
    "weight": "190"
}There are two basic types of rights needed to enable <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> flows: the rights required to perform activities, such as starting or configuring Transfer CFT, and the rights that apply to files themselves.

This topic describes the parameters used to manage:

-   Activity rights for users
-   Rights for actions on files

When using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, you can create users and assign them roles and privileges, for example the right to create flows or to send files. Additionally though, you can also set the file properties for the local Transfer CFT to enable or restrict certain user’s ability to perform file transfers.

The <a href="user_rights_security_scenarios" class="MCXref xref">User rights and privileges use cases</a> section provides common user rights use cases, and describes parameter combinations that let you achieve your desired level of security. These scenarios feature users with example privileges that are granted in <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>, your actual user rights might vary.

This topic begins with a brief review of key user control parameters, followed by a User rights use case, step instructions, and then best practices in <a href="user_rights_tips" class="MCXref xref">Recommendations and troubleshooting</a>.

## Procedure overview

After installing <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> and performing system recommendations, you can configure system users as described in these sections.

-   <a href="create_users_cg" class="MCXref xref">1. Create new users</a>
-   <a href="define_file_system_rights" class="MCXref xref">2. Define file permissions</a>
-   <a href="user_rights_copilot" class="MCXref xref">3. Define client user rights</a>
-   <a href="user_rights_file_rights" class="MCXref xref">4. File actions and procedure execution permissions</a>

## <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> user control parameters

There are two principle <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> parameters that control system users, USERCTRL and copilot.misc.createprocessasuser, which you can use in varying combinations to refine the level of security.

-   The [USERCTRL](define_file_system_rights) parameter specifies the way Transfer CFT accesses physical files during the transfer phase. It does not apply to logical objects, or to Transfer CFT configuration files such as the catalog or partner files.
-   The [copilot.misc.createprocessasuser](user_rights_copilot) parameter specifies actions that a user can do when logged on the Transfer CFT client (such as JPI or web services). Note that regardless of the value the transfer owner is the Transfer CFT connected client.

Remember that while Central Governance manages users, the CG roles and privileges are limited to logical resources and do not define the actual rights on physical files. This means that creating successful system users requires a combination of Transfer CFT settings and Central Governance access management. Using the products in tandem to define users that are recognized by the <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> system provides control of both types of system user rights.