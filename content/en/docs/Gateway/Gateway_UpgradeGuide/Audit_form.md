{
    "title": "Audit form",
    "linkTitle": "Audit form",
    "weight": "40"
}Before upgrading to a new version of Gateway, record the characteristics of your existing installation. Use the tables provided in this topic.

## General information

<table>
   <tbody>
      <tr>
         <td><p>Operating system</p>         </td>
      </tr>
      <tr>
         <td><p>Gateway version number (#)</p>         </td>
      </tr>
      <tr>
         <td><p>Name and alias of the Local Site (*)</p>         </td>
      </tr>
   </tbody>
</table>

\(#\) Recover this information using the <span class="code">peladm –Identity </span>command or consult the <span class="code">\*.out</span> files.

(\*) Recover this information via the Gateway configuration menu.

## Security

Recover the following information via the Gateway configuration menu.

<table>
   <tbody>
      <tr>
         <td><p>User access control</p>         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>Default user name</p>         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>Connection control</p>         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Check database protection         </td>
         <td><p>Option:</p>
<p>Password derived key file:</p>
<p>Password encrypted file:</p>         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

Note that Password derived key file and Password encrypted file can be copied from 6.16.x or can be recreated using <span class="code">pelencpass </span>command.

## Protocols

Recover the following information via the Gateway configuration menu.

<table>
   <tbody>
      <tr>
         <td>          </td>
         <td>TCP/IP
Address/Port         </td>
         <td>SSL         </td>
      </tr>
      <tr>
         <td>PEL         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT HS D         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT HS E         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>OFTP         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>FTP         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>HTTP         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>SMTP         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>POP3         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>SFTP         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>AS1         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>AS2         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>AS3         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>RosettaNet         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>SWIFTNet         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>JMS         </td>
         <td>          </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

## Server

Recover the following information via the Gateway configuration menu.

<table>
   <tbody>
      <tr>
         <td>          </td>
         <td>APICS         </td>
         <td>Axway MFT
Navigator
(IUI -
Internet User
Interface)         </td>
      </tr>
      <tr>
         <td>Local address         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Listening port         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>TLS         </td>
         <td>          </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

## Maintenance

Recover the following information via the Gateway **Configuration** menu.

<table>
   <tbody>
      <tr>
         <td><p>Archive of the log file</p>         </td>
      </tr>
   </tbody>
</table>

## Connectors

Recover the following information via the <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> **Configuration** menu.

<table>
   <tbody>
      <tr>
         <td>Axway Integrator         </td>
         <td><span style="font-weight: normal;">Address for the Integrator
server:
</span>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Listening port:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Directory:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Passport PS</strong>         </td>
         <td>Address for the PassPort PS
server:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Listening port for the
Passport PS server:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Listening port for the passport PS server with TLS:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Component Login:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Passport CA certificate:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Client certificate location:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Passport PM V3.3, V3.4</strong>         </td>
         <td>Directory where PassPort PM
is installed:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>PassPort PM parameters file:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Passport PM/AM V4.x</strong>         </td>
         <td>Address for the Passport
PM/AM server:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Listening port for the
Passport PM/AM server:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Listening port for the Passport PM/AM server with TLS:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Passport PM/AM server:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Login for Passport PM/AM
server:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Password for Passport PM/AM
Server:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Passport CA certificate:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Client certificate location:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Axway Sentinel</strong>         </td>
         <td>Address for the Sentinel
Server:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Listening port:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Backup address:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Listening backup port:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Transfer filter
Server CA:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Log filter:         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

## Others

<table>
   <tbody>
      <tr>
         <td><span style="font-weight: normal;">Programs that call the APIs:
</span>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Installation directory:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Default reception directory:<br />
(Recover this information via<br />
the Gateway configuration menu)<br />
         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Encryption of received files:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Files that contain the certificates:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>Specific parameters set in the files</p>
<ul>
<li><span class="code">conffile </span></li>
<li><span class="code">conffile.ini </span><br />
under Windows)</li>
<li><span class="code">pelsetup.ini </span></li>
</ul>         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

## Parameters defined via the Gateway Configuration menu

Parameters defined via the Gateway Configuration menu can be recovered by copying <span class="code">\*.ini</span> files from <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> 6.16.x.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
