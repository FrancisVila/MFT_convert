{
    "title": "ICAP scan policy expression language",
    "linkTitle": "ICAP Expression language variables",
    "weight": "270"
}This topic provides the expression language and variable available with the ICAP **Scan Policy Expression** option part of the **ICAP scan filtering settings**.

The samples are distributed in dedicated subtopics, as follows:

-   <a href="#Transfer" class="MCXref xref">Transfer-related expressions</a>
-   <a href="#Session-" class="MCXref xref">Session-related expressions</a>
-   <a href="#LDAP-rel" class="MCXref xref">LDAP-related</a>
-   <a href="#HTTP-rel" class="MCXref xref">HTTP-related expressions</a>
-   <a href="#Flow" class="MCXref xref">Flow attributes expressions</a>
-   <a href="#Account-" class="MCXref xref">Account-related expressions</a>
-   <a href="#User-rel" class="MCXref xref">User-related expressions</a>
-   <a href="#Business" class="MCXref xref">Business Unit-related expressions</a>

> **Note:**
>
> All the environment variables that are styled in italics, depend on user input and the values shown in the tables are only sample. For more detailed examples about expression language usage, see Custom Expression Language functions and variables.

<span id="Transfer"></span>

## Transfer-related expressions

<table>
   <thead>
      <tr>
<th style="text-align: left;" colspan="2" class="HeadD-Column1-Header1"><p>Transfer-related</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td> <strong>Expression</strong>         </td>
         <td><strong>Possible/Sample Values</strong>         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">transfer.targetDirFull</code>         </td>
         <td><code>/stusers/sthome/acc1/</code><br />
The path to the transferred file current directory         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">transfer.transferredBytes</code>         </td>
         <td><code>10</code><br />
The amount of bytes transferred         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">transfer.startTime</code>         </td>
         <td><code>1520951365644</code><br />
The difference, measured in milliseconds, between the time the transfer has started and midnight, January 1,1970 UTC         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">transfer.endTime</code>         </td>
         <td><code>1520951366212</code><br />
The difference, measured in milliseconds, between the time the transfer has ended and midnight, January 1, 1970 UTC         </td>
      </tr>
      <tr>
         <td><code>transfer.xferType</code>         </td>
         <td>‘<code>A</code>’ – stands for ASCII<br />
‘<code>I</code>’ – stands for Binary         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">transfer.targetDir</code>         </td>
         <td><code>/</code><br />
The root directory of the TARGETPATH         </td>
      </tr>
   </tbody>
</table>

<span id="Session-"></span>

## Session-related expressions

<table>
   <thead>
      <tr>
<th style="text-align: left;" colspan="2" class="HeadD-Column1-Header1">Session-related         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Expression</strong>         </td>
         <td><strong>Possible/Sample Values</strong>         </td>
      </tr>
      <tr>
         <td><code>session.protocol</code>         </td>
         <td><code>HTTP</code>, <code>FTP</code>, <code>SSH</code>, <code>Routing</code>, <code>AS2</code>, <code>PESIT</code>         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">session.remoteAddress</code>         </td>
         <td><code>10.134.12.224</code><br />
The IP address of the machine from which the transfer has been initiated         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">session.remoteHost</code>         </td>
         <td><code>10.232.15.109</code><br />
The IP of the ST server that performed the scanning         </td>
      </tr>
      <tr>
         <td><code>session.streamingClient</code>         </td>
         <td><code>Server</code>, <code>HTTPD</code>, <code>FTPD</code>, <code>SSHD</code>         </td>
      </tr>
      <tr>
         <td><code>session.isSSL</code>         </td>
         <td><code>0</code>, <code>1</code>         </td>
      </tr>
      <tr>
         <td><code>session.siteProtocol</code>         </td>
         <td><code>AS2</code>, <code>FTP</code>, <code>HTTP</code>, <code>SSH</code>, <code>PeSIT</code>, <code>FM</code>, <code>SystemToHuman</code>         </td>
      </tr>
   </tbody>
</table>

<span id="LDAP-rel"></span>

## LDAP-related

<table>
   <thead>
      <tr>
<th colspan="2" class="HeadD-Column1-Header1">LDAP-related         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td> <strong>Expression</strong>         </td>
         <td><strong>Possible/Sample Values</strong>         </td>
      </tr>
      <tr>
         <td><p><code style="font-style: italic;">ldap.attributes[‘ATTRIBUTE_NAME’]</code></p>
<p>or<br />
<code style="font-style: italic;">ldap.attributes.ATTRIBUTE_NAME</code></p>         </td>
         <td><code>ldap.attributes.mail</code><br />
where<br />
<code>ATTRIBUTE_NAME</code> stands for any exported LDAP attribute         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">ldap.domainName</code>         </td>
         <td><code>ldapDomain</code><br />
The name of the domain to which a user has been logged in         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">ldap.dn</code>         </td>
         <td><code>cn=mike.smith</code><br />
Тhe distinguished name for that LDAP server         </td>
      </tr>
      <tr>
         <td><code>ldap.authByEmail</code>         </td>
         <td><code>0, 1</code>         </td>
      </tr>
   </tbody>
</table>

<span id="HTTP-rel"></span>

## HTTP-related expressions

<table>
   <thead>
      <tr>
<th colspan="2" class="HeadD-Column1-Header1">HTTP-related         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td> <strong>Expression</strong>         </td>
         <td><strong>Possible/Sample Values</strong>         </td>
      </tr>
      <tr>
         <td><p><code style="font-style: italic;">http.headers[‘HEADER_NAME’]</code></p>
<p>or</p>
<p><code style="font-style: italic;">http.headers.HEADER_NAME</code></p>         </td>
         <td><code>http.headers.myHeader</code><br />
where ‘myHeader’ is the name of any available HTTP header         </td>
      </tr>
   </tbody>
</table>

<span id="Flow"></span>

## Flow attributes expressions

 

<table>
   <thead>
      <tr>
<th style="text-align: center;" colspan="2" class="HeadD-Column1-Header1">Flow attributes         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td> <strong>Expression</strong>         </td>
         <td><strong>Possible/Sample Values</strong>         </td>
      </tr>
      <tr>
         <td><p><code style="font-style: italic;">flow.attributes[‘userVars.NAME’]</code></p>
<p>or<br />
<code style="font-style: italic;">flow.attributes.userVars.NAME</code></p>         </td>
         <td><p><code>Flow.attributes.userVars.name</code><br />
By replacing NAME with a value any additional attribute declared in user account userVars and any flow attribute declared in subscriptions userVars can be retrieved</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Account-"></span>

## Account-related expressions

<table>
   <thead>
      <tr>
<th colspan="2" class="HeadD-Column1-Header1">HTTP-related         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td> <strong>Expression</strong>         </td>
         <td><strong>Possible/Sample Values</strong>         </td>
      </tr>
      <tr>
         <td><code>account.disabled</code>         </td>
         <td><code>0</code>, <code>1</code>         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">account.email</code>         </td>
         <td><code>acc1@aa.bb</code><br />
The email of the account         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">account.name</code>         </td>
         <td><code>acc1</code><br />
The name of the account         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">account.notes</code>         </td>
         <td><code>Notes</code><br />
The notes of the account         </td>
      </tr>
      <tr>
         <td><code>account.type</code>         </td>
         <td><code>template</code>, <code>service</code>, <code>user</code>, <code>unlicensed</code>         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">account.home</code>         </td>
         <td><code>/stusers/sthome/acc1</code><br />
The path to the account home directory         </td>
      </tr>
      <tr>
         <td><code>account.attributes.transferType</code>         </td>
         <td><code>‘N</code>’ – stands for Unspecified<br />
‘<code>I</code>’ – stands for Internal<br />
‘<code>E</code>’ – stands for Partner         </td>
      </tr>
      <tr>
         <td><p><code style="font-style: italic;">account.attributes[‘ATTRIBUTE_NAME’]</code></p>
<p>or<br />
<code style="font-style: italic;"> account.attributes.ATTRIBUTE_NAME</code></p>         </td>
         <td><code>account.attributes.transferType</code><br />
where<br />
<code>ATTRIBUTE_NAME</code><br />
stands for any account custom property         </td>
      </tr>
   </tbody>
</table>

<span id="User-rel"></span>

## User-related expressions

<table>
   <thead>
      <tr>
<th style="text-align: center;" colspan="2" class="HeadD-Column1-Header1">User-related         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td> <strong>Expression</strong>         </td>
         <td><strong>Possible/Sample Values</strong>         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">account.user.loginName</code>         </td>
         <td><code>acc1</code><br />
The user login name         </td>
      </tr>
      <tr>
         <td><code>account.user.type</code>         </td>
         <td><code>virtual</code>, <code>real</code>, <code>sso</code>, <code>siteminder</code>         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">account.user.class</code>         </td>
         <td><code>VirtClass</code><br />
The user class name         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">account.user.gid</code>         </td>
         <td><p><code>1000</code><br />
The user unique group identifier by which its belonging to a group of users is determined</p>         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">account.user.uid</code>         </td>
         <td><code>1000</code><br />
User account unique identifier         </td>
      </tr>
   </tbody>
</table>

<span id="Business"></span>

## Business Unit-related expressions

<table>
   <thead>
      <tr>
<th style="text-align: center;" colspan="2" class="HeadD-Column1-Header1">Business Unit-related         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td> <strong>Expression</strong>         </td>
         <td><strong>Possible/Sample Values</strong>         </td>
      </tr>
      <tr>
         <td><code style="font-style: italic;">account.businessUnit.name</code>         </td>
         <td><code>bu1</code><br />
The name of the business unit to which the account is related         </td>
      </tr>
   </tbody>
</table>
