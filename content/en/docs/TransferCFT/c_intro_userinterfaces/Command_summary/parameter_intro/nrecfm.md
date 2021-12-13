{
    "title": "nrecfm",
    "linkTitle": "nrecfm",
    "weight": "2310"
}<span id="nrecfm"></span>

### nrecfm

#### CFTSEND, SEND

**\[NRECFM = {<u>FRECFM value</u> | F | U
| V}\]     ODETTE,
PeSIT, OS**

File record format defined in protocol terms:

-   **F**: fixed
-   <span style="font-weight: bold;">V</span>: variable
-   <span style="font-weight: bold;">U</span>: undefined

```
PeSIT D EXTERN profile
PeSIT ANY profile
PeSIT E
In PeSIT protocol with the  EXTERN profile, the
value NFRECFM = U is not known in protocol terms and is changed by the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
to NFRECFM = V. This value (U) is sent with no modification in PeSIT
D CFT profile or in PeSIT E from  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.
**ODETTE**
For the ODETTE protocol, refer to the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> *Protocol
section* for the use  of this parameter.
**PeSIT SIT profile**
The NRECFM = U value is only recognized between two Transfer
CFTs.
```

[Return to Command index](../../)
