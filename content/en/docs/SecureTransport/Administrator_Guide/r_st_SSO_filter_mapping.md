{
    "title": "SSO filter mapping",
    "linkTitle": "SSO filter mapping",
    "weight": "300"
}An Identity Provider can return attributes attached to the authenticated user. A mapping using this attributes may be executed by the SSO agent before they are transmitted to the application.

Two kinds of mapping are supported: *Rename* mapping and *Filter* mapping.

## Rename mapping

With this mapping, you can rename an attribute from the Identity Provider, keeping its value.

## Filter mapping

This mapping creates output attributes when a filter matches the input attributes from the Identity Provider.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Currently, the output attribute value is fixed. It cannot take the value from an input attribute.         </td>
      </tr>
</table>

### Filter syntax

Only a subset of the full syntax is supported as described below. A filter consists of one or more criteria. If more than one criterion exist in one filter definition, they can be concatenated by logical operators.

#### Criteria

The criteria have to be put in parentheses. A criteria can only be an equality.

Example:

`(givenName=Sandra)`

#### Operators

The logical operators are always placed in front of the criteria. The whole term have to be put in parentheses.

##### AND Operator

`(&(criteria1)(criteria2))` means: criteria1 AND criteria2

With more than two criteria: `(&(criteria1)(criteria2)(criteria3)(criteria n)`

##### OR Operator

`(|(criteria1)(criteria2))` means: criteria1 OR criteria2

With more than two criteria: `(|(criteria1)(criteria2)(criteria3)(criteria n))`

##### NOT Operator

`(!(criteria1)` means NOT criteria1

##### Nested Operators

`(&(|(criteria1) (criteria2))(|(criteria3) (criteria4)))` means : (criteria1 OR criteria2) AND ( criteria3 OR criteria4)

## Examples

Rename the *user* attribute to *username*:

    <Mappings>
        <RenameMapping source="user" target="username"/>
    </Mappings>

Add two attributes when the name attribute from the Identity Provider is set to Bob:

    <Mappings>
        <FilterMapping>
            <Filter>(name=Bob)</Filter>
            <OutputAttribute name="role">SPRole</OutputAttribute>
            <OutputAttribute name="user">Bob</OutputAttribute>
        </FilterMapping>
    </Mappings>
