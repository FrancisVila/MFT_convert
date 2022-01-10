{
    "title": "for",
    "linkTitle": "for",
    "weight": "1250"
}<span id="for"></span>

### FOR

#### CFTDEST

\[ FOR
= {
| COMMUT |
LOCAL } \]

Option include:

- BOTH
    (default value): On a local {{< TransferCFT/hflongproductname >}} with both LOCAL and COMMUT facilities.
- COMMUT:
    On a local {{< TransferCFT/hflongproductname >}} that serves as an intermediate site. {{< TransferCFT/hflongproductname >}} receives
    a file or a message whose identifier in the CFTDEST object is set to the
    recipient’s network name. It then broadcasts the file or message to all
    partners in the list.
- LOCAL:
    On a local {{< TransferCFT/hflongproductname >}} to send (broadcast) or receive (collect) a file  

[Return to Command index](../../)
