{
    "title": "Regular expressions",
    "linkTitle": "Regular expressions",
    "weight": "280"
}This appendix provides information about the syntax for regular expressions supported by Axway SecureTransport.

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

The following topics describe the components of SecureTransport regular expressions:

-   [Regular expression characters](r_st_regularexpressioncharacters)
-   [General character classes](r_st_regularexpressiongeneralcharacterclasses)
-   [Predefined character classes](r_st_regularexpressionpredefinedcharacterclasses)
-   [Boundary matches](r_st_regularexpressionboundarymatches)
-   [Regular expression closures](r_st_regularexpressionclosures)
-   [Logical and grouping operators](r_st_regularexpressionlogicalandgroupingoperators)
-   [Back references](r_st_regularexpressionbackreferences)