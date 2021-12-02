{
    "title": "Extended  catalog query APIs",
    "linkTitle": "Extended catalog query APIs",
    "weight": "170"
}This topic describes the additional
fields relating to transport security that can be accessed via the catalog
query APIs (cftaix). These fields are used to determine whether transport
security was implemented for a terminated transfer, and if so, the session
parameters (authentication mode, suite negotiated, certificates used,
and so on).

<span id="Extended_catalog_query_API_structure"></span>

### Extended catalog query API structure

The output structure of the extended catalog query API, cftaix, has
been modified. New fields relating to transport security have been added.
These fields are as follows:

The following table describes the new fields declared in the structure
returned by the extended catalog query API, cftaix.

All string-type fields, char name\[n+1\], are expressed in text format,
either ASCII or EBCDIC depending on the system, are left justified, and
terminated by a null byte.

Fields in cftaix queries
