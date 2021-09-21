{
    "title": "Additional classes",
    "linkTitle": "Additional classes",
    "weight": "160"
}This topic includes the additional SecureTransport classes needed to create a new custom provider. The javadoc for the provided classes is part of the SecureTransport SDK package.

## MyAddressBookEntryIteratorImpl class

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>package com.axway.st.plugins.abcustomsource.sdk.file.provider;</pre><pre> </pre><pre xml:space="preserve">import java.io.IOException;
import java.util.Collection;
import java.util.Collections;
import java.util.Enumeration;
import java.util.Iterator;
import java.util.NoSuchElementException;</pre><pre> </pre><pre xml:space="preserve">import com.axway.st.plugins.absource.AddressBookEntry;
import com.axway.st.plugins.absource.AddressBookEntryIterator;</pre><pre> </pre><pre>import com.axway.st.plugins.abcustomsource.sdk.file.criterion.MyAddressBookEntryBean;</pre><pre> </pre><pre xml:space="preserve">/**
 * AddressBookEntryIteratorImpl.
 */
public class MyAddressBookEntryIteratorImpl implements AddressBookEntryIterator
{</pre><pre> </pre><pre xml:space="preserve">    /**
     * Enumeration instance to be wrapped by this specific iterator implementation
     * One of the possible AddressBookEntry containers.
     * Available AddressBookEntry containers are: {@code mNamingEnumeration}, {@code mEnumeration} of {@code mIterator}
     * One of them must not be null
     */
    private Enumeration&lt;AddressBookEntry&gt; mEnumeration;</pre><pre> </pre><pre xml:space="preserve">    /**
     * Iterator instance to be wrapped by this specific iterator implementation
     * One of the possible AddressBookEntry containers.
     * Available AddressBookEntry containers are: {@code mNamingEnumeration}, {@code mEnumeration} of {@code mIterator}
     * One of them must not be null
     */
    private Iterator&lt;AddressBookEntry&gt; mIterator;</pre><pre> </pre><pre xml:space="preserve">    /**
     *
     */
    private AddressBookEntry mDefaultEntry = null;</pre><pre> </pre><pre xml:space="preserve">    /**
     *
     */
    private String mSourceId;</pre><pre> </pre><pre xml:space="preserve">    /**
     * The default parent group name to be set.
     */
    private String mDefaultGroupName;</pre><pre> </pre><pre xml:space="preserve">    /**
     *
     */
    private boolean mIsSorted = false;</pre><pre> </pre><pre xml:space="preserve">    /**
     *
     */
    private boolean mIsPaginated = false;</pre><pre> </pre><pre xml:space="preserve">    /**
     * Empty AddressBookEntryIterator constructor.
     */
    protected MyAddressBookEntryIteratorImpl() {
        super();
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * @return Empty iterator object
     */
    public static AddressBookEntryIterator getEmpty() {
        return new MyAddressBookEntryIteratorImpl();
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * AddressBookEntryIterator constructor.
     * @param collection Collection with  {@code &lt;AddressBookEntry&gt;} entries.
     */
    public MyAddressBookEntryIteratorImpl(Collection&lt;AddressBookEntry&gt; collection) {
        super();
        mEnumeration = Collections.&lt;AddressBookEntry&gt;enumeration(collection);
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * AddressBookEntryIterator constructor.
     * @param enumeration Enumeration with  {@code &lt;AddressBookEntry&gt;} entries.
     */
    public MyAddressBookEntryIteratorImpl(Enumeration&lt;AddressBookEntry&gt; enumeration) {
        super();
        mEnumeration = enumeration;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * AddressBookEntryIterator constructor.
     * @param iterator Iterator with  {@code &lt;AddressBookEntry&gt;} entries.
     */
    public MyAddressBookEntryIteratorImpl(Iterator&lt;AddressBookEntry&gt; iterator) {
        super();
        mIterator = iterator;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public boolean hasNext() {
        if(mDefaultEntry != null){
            return true;
        }</pre><pre> </pre><pre xml:space="preserve">        if (mEnumeration != null) {
            Boolean hasMore = mEnumeration.hasMoreElements();
            return hasMore;
        } else if (mIterator != null) {
            Boolean hasMore = mIterator.hasNext();
            return hasMore;
        } else {
            return false;
        }
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public AddressBookEntry next() {
        AddressBookEntry result = null;</pre><pre> </pre><pre xml:space="preserve">        if(mDefaultEntry != null){
            result = mDefaultEntry;
            mDefaultEntry = null;
            return result;
        }</pre><pre> </pre><pre xml:space="preserve">        if (mEnumeration==null &amp;&amp; mIterator==null) {
            throw new NoSuchElementException();
        } else if (mIterator!=null) {
            result = mIterator.next();
        } else if (mEnumeration!=null) {
            result = mEnumeration.nextElement();
        }</pre><pre> </pre><pre xml:space="preserve">        if (mSourceId != null) {
            String id = result != null &amp;&amp; result.getEntryId() != null ? result.getEntryId().getUniqueId() : null;
            result.setEntryId(new MyAddressBookEntryBean.Id(id, mSourceId));
        }</pre><pre> </pre><pre xml:space="preserve">        if (mDefaultGroupName != null &amp;&amp; (result.getParentGroup() == null || result.getParentGroup().length() == 0)) {
            ((MyAddressBookEntryBean) result).setParentGroup(mDefaultGroupName);
        }
        return result;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Closes the context and the tls(if any).
     * @throws LdapAddressBookEntryFinderException
     */
    @Override
    public void close() throws IOException {
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public void remove() {
        throw new UnsupportedOperationException();
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Add an address book entry to the iterator.
     * @param entry - the entry to be added
     */
    @Override
    public void addEntry(AddressBookEntry entry){
        mDefaultEntry = entry;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Sets the Entry sourceId.
     * @param id
     */
    @Override
    public void setEntrySourceId(String id) {
        mSourceId = id;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Gets the Entry sourceId.
     * @return SourceID Associated Entry sourceId to the enumerator
     */
    @Override
    public String getEntrySourceId() {
        return mSourceId;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public void setDefaultGroupName(String defaultGroupName) {
        mDefaultGroupName = defaultGroupName;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public String getDefaultGroupName() {
        return mDefaultGroupName;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public boolean isSorted() {
        return mIsSorted;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public boolean isPaginated() {
        return mIsPaginated;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * @param isSorted
     */
    protected void setIsSorted(boolean isSorted) {
        mIsSorted = isSorted;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * @param isPaginated
     */
    protected void setIsPaginated(boolean isPaginated) {
        mIsPaginated = isPaginated;
    }
}</pre>
         </td>
      </tr>
   </tbody>
</table>

## MyAddressBookEntryBean class

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>package com.axway.st.plugins.abcustomsource.sdk.file.criterion;</pre><pre> </pre><pre xml:space="preserve">import java.util.HashMap;
import java.util.Map;
import java.util.Objects;
import com.axway.st.plugins.absource.AddressBookEntry;</pre><pre> </pre><pre xml:space="preserve">/**
 *
 */
public class MyAddressBookEntryBean implements AddressBookEntry {
    /**
     *
     */
    private static final long serialVersionUID = 861135864414006671L;</pre><pre> </pre><pre xml:space="preserve">    /** The entry ID. It is a composition of unique ID and address book source ID. */
    private AddressBookEntry.EntryId mId;</pre><pre> </pre><pre xml:space="preserve">    /** The entry display name. */
    private String mDisplayName;</pre><pre> </pre><pre xml:space="preserve">    /** The entry email address. */
    private String mEmail;</pre><pre> </pre><pre xml:space="preserve">    /** The entry parent group. */
    private String mParentGroup;</pre><pre> </pre><pre xml:space="preserve">    /** The entry type. It could be a user or a group type. */
    private Type mType;</pre><pre> </pre><pre xml:space="preserve">    /** The custom properties of the entry. */
    private Map&lt;String, String&gt; mCustomProperties;</pre><pre> </pre><pre xml:space="preserve">    /**
     * Default constructor.
     */
    public MyAddressBookEntryBean() {
        mCustomProperties = new HashMap&lt;&gt;();
    }</pre><pre><br/></pre><pre xml:space="preserve">/**
 * Copyright (c) Axway Software, 2016. All Rights Reserved.
 */
</pre><pre xml:space="preserve"> </pre><pre xml:space="preserve">    /**
     * Create a new address book entry.
     *
     * @param id - the entry id
     * @param displayName - the display name
     * @param email - the email.
     * @param parentGroup - the parent group.
     * @param type - the type of entry
     */
    public MyAddressBookEntryBean(Id id, String displayName, String email, String parentGroup, Type type) {
        this();
        mId = id;
        mDisplayName = displayName;
        mEmail = email;
        mParentGroup = parentGroup;
        mType = type;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Create a new address book entry.
     *
     * @param id - the entry id
     * @param displayName - the display name
     * @param email - the email.
     * @param parentGroup - the parent group.
     * @param type - the type of entry
     * @param customProperties - the custom properties
     */
    public MyAddressBookEntryBean(Id id, String displayName, String email, String parentGroup, Type type,
            Map&lt;String, String&gt; customProperties) {
        this(id, displayName, email, parentGroup, type);
        mCustomProperties.putAll(customProperties);
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public AddressBookEntry.EntryId getEntryId() {
        return mId;
    }</pre><pre xml:space="preserve"> </pre><pre xml:space="preserve">    @Override
    public String getDisplayName() {
        return mDisplayName;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public String getEmail() {
        return mEmail;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public String getParentGroup() {
        return mParentGroup;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public Type getType() {
        return mType;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public Map&lt;String, String&gt; getCustomProperties() {
        Map&lt;String, String&gt; result = new HashMap&lt;String, String&gt;();
        result.putAll(mCustomProperties);
        return result;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Gets the id.
     *
     * @return the id
     */
     public AddressBookEntry.EntryId getId() {
         return mId;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Sets the custom properties.
     *
     * @param customProperties - the custom properties map
     */
    public void setCustomProperties(Map&lt;String, String&gt; customProperties) {
        mCustomProperties.clear();
        mCustomProperties.putAll(customProperties);
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Sets the id.
     *
     * @param id the id to set
     */
     public void setId(AddressBookEntry.EntryId id) {
         mId = id;
     }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Sets the displayName.
     *
     * @param displayName the displayName to set
     */
    public void setDisplayName(String displayName) {
        mDisplayName = displayName;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Sets the email.
     *
     * @param email the email to set
     */
    public void setEmail(String email) {
        mEmail = email;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Sets the parentGroup.
     *
     * @param parentGroup the parentGroup to set
     */
    public void setParentGroup(String parentGroup) {
        mParentGroup = parentGroup;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Sets the type.
     *
     * @param type the type to set
     */
    public void setType(Type type) {
        mType = type;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public int hashCode() {
        if (mId != null) {
            return mId.hashCode();
        } else {
            int result = 1;
            int prime = 31;
            result = prime * result + (mDisplayName == null ? 0 : mDisplayName.hashCode());
            result = prime * result + (mEmail == null ? 0 : mEmail.hashCode());
            result = prime * result + (mParentGroup == null ? 0 : mParentGroup.hashCode());
            result = prime * result + (mType == null ? 0 : mType.hashCode());
            result = prime * result + (mCustomProperties == null ? 0 : mCustomProperties.hashCode());
            return result;
        }
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public boolean equals(Object o) {
        if (this == o) {
            return true;
        }</pre><pre> </pre><pre xml:space="preserve">        if (o == null) {
            return false;
        }</pre><pre> </pre><pre xml:space="preserve">        if (!(o instanceof MyAddressBookEntryBean)) {
            return false;
        }</pre><pre> </pre><pre xml:space="preserve">        MyAddressBookEntryBean entry = (MyAddressBookEntryBean) o;
        if (mId != null) {
            return mId.equals(entry.mId);
        }</pre><pre> </pre><pre xml:space="preserve">        if (mDisplayName == null) {
            if (entry.mDisplayName != null) {
                return false;
            }
        } else if (!mDisplayName.equals(entry.mDisplayName)) {
            return false;
        }</pre><pre> </pre><pre xml:space="preserve">        if (mEmail == null) {
            if (entry.mEmail != null) {
                return false;
            }
        } else if (!mEmail.equals(entry.mEmail)) {
            return false;
        }</pre><pre> </pre><pre xml:space="preserve">        if (mParentGroup == null) {
            if (entry.mParentGroup != null) {
                return false;
            }
        } else if (!mParentGroup.equals(entry.mParentGroup)) {
            return false;
        }</pre><pre> </pre><pre xml:space="preserve">        if (mType == null) {
            if (entry.mType != null) {
                return false;
            }
        } else if (!mType.equals(entry.mType)) {
            return false;
        }</pre><pre> </pre><pre xml:space="preserve">        if (mCustomProperties == null) {
            if (entry.mCustomProperties != null) {
                return false;
            }
        } else if (!mCustomProperties.equals(entry.mCustomProperties)) {
            return false;
        }
        return true;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public String toString() {
        return "{display name [" + mDisplayName + "] " + "email [" + mEmail + "] parent group [" + mParentGroup + "] "
            + "custom properties " + mCustomProperties + "}";
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public void setEntryId(AddressBookEntry.EntryId entryId) {
        mId = entryId;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Address book entry Id implementation.
     */
    public static class Id implements AddressBookEntry.EntryId {</pre><pre> </pre><pre xml:space="preserve">        /** The serial version. */
        private static final long serialVersionUID = 6066501149301629310L;</pre><pre> </pre><pre xml:space="preserve">        /** The provider specific entry id combined with the source id. */
        private String mUniqueId;</pre><pre> </pre><pre xml:space="preserve">        /** The address book source id. */
        private String mAddressBookSourceId;</pre><pre> </pre><pre xml:space="preserve">        /** The address book entry id. */
        private String mEntryId;</pre><pre> </pre><pre xml:space="preserve">        /**
         * Create a new entry id instance.
         *
         * @param id - the entry id.
         */
        public Id(String id) {
            mEntryId = id;
            mUniqueId = id;
            mAddressBookSourceId = null;
        }</pre><pre> </pre><pre xml:space="preserve">        /**
         * Create a new entry id instance.
         *
         * @param id - the entry id.
         * @param sourceId - the source id.
         */
        public Id(String id, String sourceId) {
            mEntryId = id;
            mAddressBookSourceId = sourceId;
            if (sourceId != null) {
                mUniqueId = id + ":" + sourceId;
            } else {
                mUniqueId = id;
            }
        }</pre><pre> </pre><pre xml:space="preserve">        @Override
        public String getUniqueId() {
            return mUniqueId;
        }</pre><pre> </pre><pre xml:space="preserve">        /**
         * Returns entry ID.
         *
         * @return Entry id
         */
        public String getEntryId() {
            return mEntryId;
        }</pre><pre> </pre><pre xml:space="preserve">        /**
         * Get the address book source ID.
         *
         * @return the address book source id or &lt;code&gt;null&lt;/code&gt; if not specified.
         */
        public String getAddressBookSourceId() {
            return mAddressBookSourceId;
        }</pre><pre> </pre><pre xml:space="preserve">        @Override
        public String toString() {
            return mUniqueId;
        }</pre><pre> </pre><pre xml:space="preserve">        @Override
        public int hashCode() {
            return Objects.hash(mUniqueId, mAddressBookSourceId);
        }</pre><pre> </pre><pre xml:space="preserve">        @Override
        public boolean equals(Object id) {
            if (id == null) {
                return false;
            }</pre><pre> </pre><pre xml:space="preserve">            if (id == this) {
                return true;
            }</pre><pre> </pre><pre xml:space="preserve">            if (id instanceof Id) {
                Id entryId = (Id) id;
                if (entryId.getUniqueId().equals(mUniqueId)) {
                    return true;
                }
            }
            return false;
        }
    }
}</pre>
         </td>
      </tr>
   </tbody>
</table>

## MyAddressBookCriteriaBean class

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>package com.axway.st.plugins.abcustomsource.sdk.file.criterion;</pre><pre> </pre><pre xml:space="preserve">import com.axway.st.plugins.absource.AddressBookCriteria;
import com.axway.st.plugins.absource.AddressBookEntry.EntryId;
import com.axway.st.plugins.absource.AddressBookEntry.Type;
import com.axway.st.plugins.absource.AddressBookProviderOrder;</pre><pre> </pre><pre xml:space="preserve">/**
 * Local (BU) address book criteria class.
 */
public class MyAddressBookCriteriaBean implements AddressBookCriteria{</pre><pre> </pre><pre xml:space="preserve">    /** Display Name. */
    private String mDisplayName;</pre><pre> </pre><pre xml:space="preserve">    /** ID. */
    private EntryId mId;</pre><pre> </pre><pre xml:space="preserve">    /** The email. */
    private String mEmail;</pre><pre> </pre><pre xml:space="preserve">    /** The parent group. */
    private String mParentGroup;</pre><pre> </pre><pre xml:space="preserve">    /** The search for.*/
    private String mSearchFor;</pre><pre> </pre><pre xml:space="preserve">    /** The type.*/
    private Type mType;</pre><pre> </pre><pre xml:space="preserve">    /** The order. */
    private AddressBookProviderOrder mOrder = AddressBookProviderOrder.DISPLAY_NAME_ASC;</pre><pre> </pre><pre xml:space="preserve">    /**
     * Constructor.
     */
    public MyAddressBookCriteriaBean() {
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Constructor.
     * @param beanClass Bean class
     * @param alias Cache Alias
     */
    public MyAddressBookCriteriaBean(Class&lt;?&gt; beanClass, String alias) {
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public AddressBookCriteria entryId(EntryId entryId) {
        mId = entryId;
        return this;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public AddressBookCriteria displayName(String displayName) {
        mDisplayName = displayName;
        return this;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public AddressBookCriteria email(String email) {
        mEmail = email;
        return this;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public AddressBookCriteria parentGroup(String parentGroup) {
        mParentGroup = parentGroup;
        return this;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public AddressBookCriteria type(Type type) {
        mType = type;
        return this;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public AddressBookCriteria searchFor(String searchFor) {
        mSearchFor = searchFor;
        return this;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public AddressBookCriteria orderByDisplayName(boolean ascending) {
        mOrder = ascending?AddressBookProviderOrder.DISPLAY_NAME_ASC:AddressBookProviderOrder.DISPLAY_NAME_DESC;
        return this;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public AddressBookCriteria orderByEmail(boolean ascending) {
        mOrder = ascending?AddressBookProviderOrder.EMAIL_ASC:AddressBookProviderOrder.EMAIL_DESC;
        return this;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public String getDisplayName() {
        return mDisplayName;
    }<br/><br/>    @Override
    public void setDisplayName(String displayName) {
        mDisplayName = displayName;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public EntryId getId() {
        return mId;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public void setId(EntryId id) {
        mId = id;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public String getEmail() {
        return mEmail;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public void setEmail(String email) {
        mEmail = email;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public String getParentGroup() {
        return mParentGroup;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public void setParentGroup(String parentGroup) {
        mParentGroup = parentGroup;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public String getSearchFor() {
        return mSearchFor;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public void setSearchFor(String searchFor) {
        mSearchFor = searchFor;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public Type getType() {
        return mType;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public void setType(Type type) {
        mType = type;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public AddressBookProviderOrder getOrder() {
        return mOrder;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public void setOrder(AddressBookProviderOrder order) {
        mOrder = order;
    }
}</pre>
         </td>
      </tr>
   </tbody>
</table>

## MyAddressBookContactComparator class

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>package com.axway.st.plugins.abcustomsource.sdk.file.criterion;</pre><pre> </pre><pre>import java.util.Comparator;</pre><pre> </pre><pre xml:space="preserve">import com.axway.st.plugins.absource.AddressBookEntry;
import com.axway.st.plugins.absource.AddressBookProviderOrder;</pre><pre> </pre><pre xml:space="preserve">/**
* LDAP AddressBookContactComparator.
*
*/
public class MyAddressBookContactComparator implements Comparator&lt;AddressBookEntry&gt; {</pre><pre> </pre><pre xml:space="preserve">    /**
     * Order.
     */
    private AddressBookProviderOrder mOrder;</pre><pre> </pre><pre xml:space="preserve">    /**
     * Constructor.
     * @param order Order
     */
    public MyAddressBookContactComparator(AddressBookProviderOrder order) {
        mOrder = order;
    }</pre><pre> </pre><pre xml:space="preserve">    @Override
    public int compare(AddressBookEntry contact1, AddressBookEntry contact2) {
        int res = compareContactField(mOrder, contact1, contact2, 0);
        return res;
    }</pre><pre> </pre><pre xml:space="preserve">    /**
     * Compares fields.
     * @param order Order.
     * @param contact1 Item 1.
     * @param contact2 Item 2.
     * @param defValue Default value
     * @return compare index
     */
    private int compareContactField(AddressBookProviderOrder order, AddressBookEntry contact1, AddressBookEntry contact2, int defValue) {
        String field1 = null;
        String field2 = null;
        if (order == null) {
            return defValue;
        }
        switch (order) {
        case EMAIL_ASC:
        case EMAIL_DESC:
            field1 = contact1!=null?contact1.getEmail():null;
            field2 = contact2!=null?contact2.getEmail():null;
            break;
        default:
            field1 = contact1!=null?contact1.getDisplayName():null;
            field2 = contact2!=null?contact2.getDisplayName():null;
        }
        int res;
        if (field1 == null &amp;&amp; field2 == null) {
            res = 0;
        } else if (field2 == null) {
            res = 1;
        } else if (field1 == null) {
            res = -1;
        } else {
            res = field1.compareToIgnoreCase(field2);
        }</pre><pre> </pre><pre xml:space="preserve">        return order.isAscending() ? res : -res;
    }
}</pre>
         </td>
      </tr>
   </tbody>
</table>
