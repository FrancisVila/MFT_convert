{
    "title": "Additional classes",
    "linkTitle": "Additional classes",
    "weight": "160"
}This topic includes the additional {{< SecureTransport/securetransportname  >}} classes needed to create a new custom provider. The javadoc for the provided classes is part of the {{< SecureTransport/securetransportname  >}} SDK package.

## MyAddressBookEntryIteratorImpl class


    package com.axway.st.plugins.abcustomsource.sdk.file.provider;
     
    import java.io.IOException;
    import java.util.Collection;
    import java.util.Collections;
    import java.util.Enumeration;
    import java.util.Iterator;
    import java.util.NoSuchElementException;
     
    import com.axway.st.plugins.absource.AddressBookEntry;
    import com.axway.st.plugins.absource.AddressBookEntryIterator;
     
    import com.axway.st.plugins.abcustomsource.sdk.file.criterion.MyAddressBookEntryBean;
     
    /**
     * AddressBookEntryIteratorImpl.
     */
    public class MyAddressBookEntryIteratorImpl implements AddressBookEntryIterator
    {
     
        /**
         * Enumeration instance to be wrapped by this specific iterator implementation
         * One of the possible AddressBookEntry containers.
         * Available AddressBookEntry containers are: {@code mNamingEnumeration}, {@code mEnumeration} of {@code mIterator}
         * One of them must not be null
         */
        private Enumeration<AddressBookEntry> mEnumeration;
     
        /**
         * Iterator instance to be wrapped by this specific iterator implementation
         * One of the possible AddressBookEntry containers.
         * Available AddressBookEntry containers are: {@code mNamingEnumeration}, {@code mEnumeration} of {@code mIterator}
         * One of them must not be null
         */
        private Iterator<AddressBookEntry> mIterator;
     
        /**
         *
         */
        private AddressBookEntry mDefaultEntry = null;
     
        /**
         *
         */
        private String mSourceId;
     
        /**
         * The default parent group name to be set.
         */
        private String mDefaultGroupName;
     
        /**
         *
         */
        private boolean mIsSorted = false;
     
        /**
         *
         */
        private boolean mIsPaginated = false;
     
        /**
         * Empty AddressBookEntryIterator constructor.
         */
        protected MyAddressBookEntryIteratorImpl() {
            super();
        }
     
        /**
         * @return Empty iterator object
         */
        public static AddressBookEntryIterator getEmpty() {
            return new MyAddressBookEntryIteratorImpl();
        }
     
        /**
         * AddressBookEntryIterator constructor.
         * @param collection Collection with  {@code <AddressBookEntry>} entries.
         */
        public MyAddressBookEntryIteratorImpl(Collection<AddressBookEntry> collection) {
            super();
            mEnumeration = Collections.<AddressBookEntry>enumeration(collection);
        }
     
        /**
         * AddressBookEntryIterator constructor.
         * @param enumeration Enumeration with  {@code <AddressBookEntry>} entries.
         */
        public MyAddressBookEntryIteratorImpl(Enumeration<AddressBookEntry> enumeration) {
            super();
            mEnumeration = enumeration;
        }
     
        /**
         * AddressBookEntryIterator constructor.
         * @param iterator Iterator with  {@code <AddressBookEntry>} entries.
         */
        public MyAddressBookEntryIteratorImpl(Iterator<AddressBookEntry> iterator) {
            super();
            mIterator = iterator;
        }
     
        @Override
        public boolean hasNext() {
            if(mDefaultEntry != null){
                return true;
            }
     
            if (mEnumeration != null) {
                Boolean hasMore = mEnumeration.hasMoreElements();
                return hasMore;
            } else if (mIterator != null) {
                Boolean hasMore = mIterator.hasNext();
                return hasMore;
            } else {
                return false;
            }
        }
     
        @Override
        public AddressBookEntry next() {
            AddressBookEntry result = null;
     
            if(mDefaultEntry != null){
                result = mDefaultEntry;
                mDefaultEntry = null;
                return result;
            }
     
            if (mEnumeration==null && mIterator==null) {
                throw new NoSuchElementException();
            } else if (mIterator!=null) {
                result = mIterator.next();
            } else if (mEnumeration!=null) {
                result = mEnumeration.nextElement();
            }
     
            if (mSourceId != null) {
                String id = result != null && result.getEntryId() != null ? result.getEntryId().getUniqueId() : null;
                result.setEntryId(new MyAddressBookEntryBean.Id(id, mSourceId));
            }
     
            if (mDefaultGroupName != null && (result.getParentGroup() == null || result.getParentGroup().length() == 0)) {
                ((MyAddressBookEntryBean) result).setParentGroup(mDefaultGroupName);
            }
            return result;
        }
     
        /**
         * Closes the context and the tls(if any).
         * @throws LdapAddressBookEntryFinderException
         */
        @Override
        public void close() throws IOException {
        }
     
        @Override
        public void remove() {
            throw new UnsupportedOperationException();
        }
     
        /**
         * Add an address book entry to the iterator.
         * @param entry - the entry to be added
         */
        @Override
        public void addEntry(AddressBookEntry entry){
            mDefaultEntry = entry;
        }
     
        /**
         * Sets the Entry sourceId.
         * @param id
         */
        @Override
        public void setEntrySourceId(String id) {
            mSourceId = id;
        }
     
        /**
         * Gets the Entry sourceId.
         * @return SourceID Associated Entry sourceId to the enumerator
         */
        @Override
        public String getEntrySourceId() {
            return mSourceId;
        }
     
        @Override
        public void setDefaultGroupName(String defaultGroupName) {
            mDefaultGroupName = defaultGroupName;
        }
     
        @Override
        public String getDefaultGroupName() {
            return mDefaultGroupName;
        }
     
        @Override
        public boolean isSorted() {
            return mIsSorted;
        }
     
        @Override
        public boolean isPaginated() {
            return mIsPaginated;
        }
     
        /**
         * @param isSorted
         */
        protected void setIsSorted(boolean isSorted) {
            mIsSorted = isSorted;
        }
     
        /**
         * @param isPaginated
         */
        protected void setIsPaginated(boolean isPaginated) {
            mIsPaginated = isPaginated;
        }
    }

## MyAddressBookEntryBean class


    package com.axway.st.plugins.abcustomsource.sdk.file.criterion;
     
    import java.util.HashMap;
    import java.util.Map;
    import java.util.Objects;
    import com.axway.st.plugins.absource.AddressBookEntry;
     
    /**
     *
     */
    public class MyAddressBookEntryBean implements AddressBookEntry {
        /**
         *
         */
        private static final long serialVersionUID = 861135864414006671L;
     
        /** The entry ID. It is a composition of unique ID and address book source ID. */
        private AddressBookEntry.EntryId mId;
     
        /** The entry display name. */
        private String mDisplayName;
     
        /** The entry email address. */
        private String mEmail;
     
        /** The entry parent group. */
        private String mParentGroup;
     
        /** The entry type. It could be a user or a group type. */
        private Type mType;
     
        /** The custom properties of the entry. */
        private Map<String, String> mCustomProperties;
     
        /**
         * Default constructor.
         */
        public MyAddressBookEntryBean() {
            mCustomProperties = new HashMap<>();
        }

    /**
     * Copyright (c) Axway Software, 2016. All Rights Reserved.
     */
     
        /**
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
        }
     
        /**
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
                Map<String, String> customProperties) {
            this(id, displayName, email, parentGroup, type);
            mCustomProperties.putAll(customProperties);
        }
     
        @Override
        public AddressBookEntry.EntryId getEntryId() {
            return mId;
        }
     
        @Override
        public String getDisplayName() {
            return mDisplayName;
        }
     
        @Override
        public String getEmail() {
            return mEmail;
        }
     
        @Override
        public String getParentGroup() {
            return mParentGroup;
        }
     
        @Override
        public Type getType() {
            return mType;
        }
     
        @Override
        public Map<String, String> getCustomProperties() {
            Map<String, String> result = new HashMap<String, String>();
            result.putAll(mCustomProperties);
            return result;
        }
     
        /**
         * Gets the id.
         *
         * @return the id
         */
         public AddressBookEntry.EntryId getId() {
             return mId;
        }
     
        /**
         * Sets the custom properties.
         *
         * @param customProperties - the custom properties map
         */
        public void setCustomProperties(Map<String, String> customProperties) {
            mCustomProperties.clear();
            mCustomProperties.putAll(customProperties);
        }
     
        /**
         * Sets the id.
         *
         * @param id the id to set
         */
         public void setId(AddressBookEntry.EntryId id) {
             mId = id;
         }
     
        /**
         * Sets the displayName.
         *
         * @param displayName the displayName to set
         */
        public void setDisplayName(String displayName) {
            mDisplayName = displayName;
        }
     
        /**
         * Sets the email.
         *
         * @param email the email to set
         */
        public void setEmail(String email) {
            mEmail = email;
        }
     
        /**
         * Sets the parentGroup.
         *
         * @param parentGroup the parentGroup to set
         */
        public void setParentGroup(String parentGroup) {
            mParentGroup = parentGroup;
        }
     
        /**
         * Sets the type.
         *
         * @param type the type to set
         */
        public void setType(Type type) {
            mType = type;
        }
     
        @Override
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
        }
     
        @Override
        public boolean equals(Object o) {
            if (this == o) {
                return true;
            }
     
            if (o == null) {
                return false;
            }
     
            if (!(o instanceof MyAddressBookEntryBean)) {
                return false;
            }
     
            MyAddressBookEntryBean entry = (MyAddressBookEntryBean) o;
            if (mId != null) {
                return mId.equals(entry.mId);
            }
     
            if (mDisplayName == null) {
                if (entry.mDisplayName != null) {
                    return false;
                }
            } else if (!mDisplayName.equals(entry.mDisplayName)) {
                return false;
            }
     
            if (mEmail == null) {
                if (entry.mEmail != null) {
                    return false;
                }
            } else if (!mEmail.equals(entry.mEmail)) {
                return false;
            }
     
            if (mParentGroup == null) {
                if (entry.mParentGroup != null) {
                    return false;
                }
            } else if (!mParentGroup.equals(entry.mParentGroup)) {
                return false;
            }
     
            if (mType == null) {
                if (entry.mType != null) {
                    return false;
                }
            } else if (!mType.equals(entry.mType)) {
                return false;
            }
     
            if (mCustomProperties == null) {
                if (entry.mCustomProperties != null) {
                    return false;
                }
            } else if (!mCustomProperties.equals(entry.mCustomProperties)) {
                return false;
            }
            return true;
        }
     
        @Override
        public String toString() {
            return "{display name [" + mDisplayName + "] " + "email [" + mEmail + "] parent group [" + mParentGroup + "] "
                + "custom properties " + mCustomProperties + "}";
        }
     
        @Override
        public void setEntryId(AddressBookEntry.EntryId entryId) {
            mId = entryId;
        }
     
        /**
         * Address book entry Id implementation.
         */
        public static class Id implements AddressBookEntry.EntryId {
     
            /** The serial version. */
            private static final long serialVersionUID = 6066501149301629310L;
     
            /** The provider specific entry id combined with the source id. */
            private String mUniqueId;
     
            /** The address book source id. */
            private String mAddressBookSourceId;
     
            /** The address book entry id. */
            private String mEntryId;
     
            /**
             * Create a new entry id instance.
             *
             * @param id - the entry id.
             */
            public Id(String id) {
                mEntryId = id;
                mUniqueId = id;
                mAddressBookSourceId = null;
            }
     
            /**
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
            }
     
            @Override
            public String getUniqueId() {
                return mUniqueId;
            }
     
            /**
             * Returns entry ID.
             *
             * @return Entry id
             */
            public String getEntryId() {
                return mEntryId;
            }
     
            /**
             * Get the address book source ID.
             *
             * @return the address book source id or <code>null</code> if not specified.
             */
            public String getAddressBookSourceId() {
                return mAddressBookSourceId;
            }
     
            @Override
            public String toString() {
                return mUniqueId;
            }
     
            @Override
            public int hashCode() {
                return Objects.hash(mUniqueId, mAddressBookSourceId);
            }
     
            @Override
            public boolean equals(Object id) {
                if (id == null) {
                    return false;
                }
     
                if (id == this) {
                    return true;
                }
     
                if (id instanceof Id) {
                    Id entryId = (Id) id;
                    if (entryId.getUniqueId().equals(mUniqueId)) {
                        return true;
                    }
                }
                return false;
            }
        }
    }

## MyAddressBookCriteriaBean class


    package com.axway.st.plugins.abcustomsource.sdk.file.criterion;
     
    import com.axway.st.plugins.absource.AddressBookCriteria;
    import com.axway.st.plugins.absource.AddressBookEntry.EntryId;
    import com.axway.st.plugins.absource.AddressBookEntry.Type;
    import com.axway.st.plugins.absource.AddressBookProviderOrder;
     
    /**
     * Local (BU) address book criteria class.
     */
    public class MyAddressBookCriteriaBean implements AddressBookCriteria{
     
        /** Display Name. */
        private String mDisplayName;
     
        /** ID. */
        private EntryId mId;
     
        /** The email. */
        private String mEmail;
     
        /** The parent group. */
        private String mParentGroup;
     
        /** The search for.*/
        private String mSearchFor;
     
        /** The type.*/
        private Type mType;
     
        /** The order. */
        private AddressBookProviderOrder mOrder = AddressBookProviderOrder.DISPLAY_NAME_ASC;
     
        /**
         * Constructor.
         */
        public MyAddressBookCriteriaBean() {
        }
     
        /**
         * Constructor.
         * @param beanClass Bean class
         * @param alias Cache Alias
         */
        public MyAddressBookCriteriaBean(Class<?> beanClass, String alias) {
        }
     
        @Override
        public AddressBookCriteria entryId(EntryId entryId) {
            mId = entryId;
            return this;
        }
     
        @Override
        public AddressBookCriteria displayName(String displayName) {
            mDisplayName = displayName;
            return this;
        }
     
        @Override
        public AddressBookCriteria email(String email) {
            mEmail = email;
            return this;
        }
     
        @Override
        public AddressBookCriteria parentGroup(String parentGroup) {
            mParentGroup = parentGroup;
            return this;
        }
     
        @Override
        public AddressBookCriteria type(Type type) {
            mType = type;
            return this;
        }
     
        @Override
        public AddressBookCriteria searchFor(String searchFor) {
            mSearchFor = searchFor;
            return this;
        }
     
        @Override
        public AddressBookCriteria orderByDisplayName(boolean ascending) {
            mOrder = ascending?AddressBookProviderOrder.DISPLAY_NAME_ASC:AddressBookProviderOrder.DISPLAY_NAME_DESC;
            return this;
        }
     
        @Override
        public AddressBookCriteria orderByEmail(boolean ascending) {
            mOrder = ascending?AddressBookProviderOrder.EMAIL_ASC:AddressBookProviderOrder.EMAIL_DESC;
            return this;
        }
     
        @Override
        public String getDisplayName() {
            return mDisplayName;
        }
        @Override
        public void setDisplayName(String displayName) {
            mDisplayName = displayName;
        }
     
        @Override
        public EntryId getId() {
            return mId;
        }
     
        @Override
        public void setId(EntryId id) {
            mId = id;
        }
     
        @Override
        public String getEmail() {
            return mEmail;
        }
     
        @Override
        public void setEmail(String email) {
            mEmail = email;
        }
     
        @Override
        public String getParentGroup() {
            return mParentGroup;
        }
     
        @Override
        public void setParentGroup(String parentGroup) {
            mParentGroup = parentGroup;
        }
     
        @Override
        public String getSearchFor() {
            return mSearchFor;
        }
     
        @Override
        public void setSearchFor(String searchFor) {
            mSearchFor = searchFor;
        }
     
        @Override
        public Type getType() {
            return mType;
        }
     
        @Override
        public void setType(Type type) {
            mType = type;
        }
     
        @Override
        public AddressBookProviderOrder getOrder() {
            return mOrder;
        }
     
        @Override
        public void setOrder(AddressBookProviderOrder order) {
            mOrder = order;
        }
    }

## MyAddressBookContactComparator class


    package com.axway.st.plugins.abcustomsource.sdk.file.criterion;
     
    import java.util.Comparator;
     
    import com.axway.st.plugins.absource.AddressBookEntry;
    import com.axway.st.plugins.absource.AddressBookProviderOrder;
     
    /**
    * LDAP AddressBookContactComparator.
    *
    */
    public class MyAddressBookContactComparator implements Comparator<AddressBookEntry> {
     
        /**
         * Order.
         */
        private AddressBookProviderOrder mOrder;
     
        /**
         * Constructor.
         * @param order Order
         */
        public MyAddressBookContactComparator(AddressBookProviderOrder order) {
            mOrder = order;
        }
     
        @Override
        public int compare(AddressBookEntry contact1, AddressBookEntry contact2) {
            int res = compareContactField(mOrder, contact1, contact2, 0);
            return res;
        }
     
        /**
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
            if (field1 == null && field2 == null) {
                res = 0;
            } else if (field2 == null) {
                res = 1;
            } else if (field1 == null) {
                res = -1;
            } else {
                res = field1.compareToIgnoreCase(field2);
            }
     
            return order.isAscending() ? res : -res;
        }
    }
