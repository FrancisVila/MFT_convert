{
    "title": "Create a criteria class",
    "linkTitle": "Create a criteria class",
    "weight": "130"
}The Address Book (AB) criteria object will be passed to each provider method which needs to apply filtering over the result set of its own entries. In order to add the custom implementation of the AB criteria, the `AddressBookCriteria` interface must be implemented.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The Address Book framework use the provider specific criteria object when getting entries from it. How they are filtered depends on the provider itself. Address Book entries are not passed to the provider, only combinations of the criteria, user info, and pagination settings.         </td>
      </tr>
</table>

In the sample code, the `AddressBookFileCriteria` class extends the system base class which provides implementation for all Gets and Sets of the Address Book entry properties.

The `AddressBookFileCriteria` class defines a new method which handles the filtering:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">package com.axway.st.plugins.abcustomsource.sdk.file.criterion;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Collections;
import java.util.LinkedList;
import java.util.List;
import java.util.ListIterator;

import com.axway.st.plugins.absource.AddressBookEntry;

/**
 * Address Book File Criteria.
 *
 */
public class AddressBookFileCriteria extends MyAddressBookCriteriaBean {

    /**
     *
     */
    private static final long serialVersionUID = -9087309532695089048L;

    /**
     * Apply the search criterion.
     *
     * @param entries the input entries
     * @param start the offset
     * @param count the max size
     * @return filtered and ordered set of address book entries
     */
    public List&lt;AddressBookEntry&gt; applyCriterion(Collection&lt;AddressBookEntry&gt; entries, int start, int count){
        List&lt;AddressBookEntry&gt; resultSet = new ArrayList&lt;&gt;();
        for(AddressBookEntry entry : entries){
            if(getDisplayName() != null){
                if(!getDisplayName().equals(entry.getDisplayName())){
                    continue;
                }
            }

            if(getEmail() != null){
                if(!getEmail().equals(entry.getEmail())){
                    continue;
                }
            }

            if(getId() != null){
                if(!getId().getUniqueId().equals(entry.getEntryId().getUniqueId())){
                    continue;
                }
            }

            if(getParentGroup() != null){
                if(!getParentGroup().equals(entry.getParentGroup())){
                    continue;
                }
            }

            if(getSearchFor() != null){
                if(!entry.getParentGroup().toLowerCase().
                        contains(getSearchFor().toLowerCase())
                    &amp;&amp; !entry.getDisplayName().toLowerCase().
                        contains(getSearchFor().toLowerCase())
                    &amp;&amp; !entry.getEmail().toLowerCase().</pre><pre xml:space="preserve">                        contains(getSearchFor().toLowerCase())){
                    continue;
                }
            }

            if (getType() != null) {
                if (getType() == AddressBookEntry.Type.Group) {
                    continue;
                }
            }

            resultSet.add(entry);
        }

        Collections.sort(resultSet, new MyAddressBookContactComparator(getOrder()));

        List&lt;AddressBookEntry&gt; paginatedView = new LinkedList&lt;&gt;();
        if (start &gt; resultSet.size() - 1) {
            return paginatedView;
        }
        ListIterator&lt;AddressBookEntry&gt; iterator = resultSet.listIterator(start);
        while (iterator.hasNext()) {
            AddressBookEntry entry = iterator.next();
            paginatedView.add(entry);
            if (paginatedView.size() == count) {
                break;
            }
        }
        return paginatedView;
    }
}
</pre>
         </td>
      </tr>
   </tbody>
</table>
