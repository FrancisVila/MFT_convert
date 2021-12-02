{
    "title": "phases",
    "linkTitle": "phases",
    "weight": "2560"
}### phases

SWAITCAT

\[ PHASES = { A | T | Y | Z | <u>X</u> } \]

Where the string **sizemax= 5**.

Possible values:

-   \(A\) preprocessing: All pre-transfer script execution occurs here
-   \(T\) Transferring: All transfer execution occurs in this phase
-   (Y) Post-processing: All the post-transfer script execution occurs here
-   (Z) Acknowledgement: Acknowledgement reception/send steps and ack script execution occur here
-   (<u>X</u>) Done: End condition when all of the previous phases are completed (default)

Example
