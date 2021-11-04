{
    "title": "Regular expressions",
    "linkTitle": "Regular expressions",
    "weight": "270"
}This appendix provides information about the syntax for regular expressions supported by <span class="mc-variable axway_variables.Component_Long_Name variable">Axway SecureTransport</span>.

For matching file names with the glob pattern method, SecureTransport uses `org.apache.oro.text.GlobCompile` class. We can refer to its [GlobCompiler Class javaDoc](https://svn.apache.org/repos/asf/jakarta/oro/tags/oro-2.0.9-dev-1/docs/api/org/apache/oro/text/GlobCompiler.html) which describes the following syntax:

-   `*` - Matches zero or more instances of any character.
-   `?` - Matches one instance of any character.
-   `[...]` - Matches any of characters enclosed by the brackets. \*\*\* and ? lose their special meanings within a character class. Additionally if the first character following the opening bracket is a ! or a ^, then any character not in the character class is matched. A between two characters can be used to denote a range. A at the beginning or end of the character class matches itself rather than referring to a range. A \] immediately following the opening \[ matches itself rather than indicating the end of the character class, otherwise it must be escaped with a backslash to refer to itself.
-   / - A backslash matches itself in most situations. But when a special character such as a \*\*\* follows it, a backslash escapes the character, indicating that the special character should be interpreted as a normal character instead of its special meaning.
-   All other characters match themselves.

**Examples:**

-   `[a-c]test*` – matches file name which include any of the letters "a", "b" or "c" , followed by the string "test". The asterisk \* character means that any character(s) can follow the word "test".
-   `[^a-c]d?` – matches file names which <u>do not</u> include any of the letters "a", "b" or "c", followed by the a single instance of the letter "d".
-   `*a*` – matches file names which include any sequence of characters, which include the letter "a".
-   `\*dir` – matches path names that include the string "dir".

The following topics describe the components of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> regular expressions:

-   <a href="r_st_regularexpressioncharacters" class="MCXref xref">Regular expression characters</a>
-   <a href="r_st_regularexpressiongeneralcharacterclasses" class="MCXref xref">General character classes</a>
-   <a href="r_st_regularexpressionpredefinedcharacterclasses" class="MCXref xref">Predefined character classes</a>
-   <a href="r_st_regularexpressionboundarymatches" class="MCXref xref">Boundary matches</a>
-   <a href="r_st_regularexpressionclosures" class="MCXref xref">Regular expression closures</a>
-   <a href="r_st_regularexpressionlogicalandgroupingoperators" class="MCXref xref">Logical and grouping operators</a>
-   <a href="r_st_regularexpressionbackreferences" class="MCXref xref">Back references</a>
