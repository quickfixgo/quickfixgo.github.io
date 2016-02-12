---
layout: default
---

### QuickFIXGo Settings

<table class='table table-bordered'>
  <thead>
  <tr>
    <th>ID</th>
    <th>Description</th>
    <th>Valid Values</th>
    <th>Default</th>
  </tr>
  </thead>
  <tbody>
  <tr>
    <th>BeginString</th>
    <td>Version of FIX this session should use</td>
    <td>
      FIXT.1.1<br/>
      FIX.4.4<br/>
      FIX.4.3<br/>
      FIX.4.2<br/>
      FIX.4.1<br/>
      FIX.4.0<br/>
    </td>
    <td/>
  </tr>
  <tr>
    <th>SenderCompID</th>
    <td>Your ID as associated with this FIX session</td>
    <td>case-sensitive alpha-numeric string</td>
    <td/>
  </tr>
  <tr>
    <th>TargetCompID</th>
    <td>Counter parties ID as associated with this FIX session</td>
    <td>case-sensitive alpha-numeric string</td>
    <td/>
  </tr>
  <tr>
    <th>SessionQualifier</th>
    <td>Additional qualifier to disambiguate otherwise identical sessions</td>
    <td>case-sensitive alpha-numeric string</td>
    <td/>
  </tr>
  <tr>
    <th>DefaultApplVerID</th>
    <td>Required only for FIXT 1.1 (and newer). Ignored for earlier transport versions. Specifies the default application version ID for the session. This can either be the ApplVerID enum (see the ApplVerID field) or the BeginString for the default version.</td>
    <td>FIX.5.0SP2
FIX.5.0SP1<br/>
FIX.5.0<br/>
FIX.4.4<br/>
FIX.4.3<br/>
FIX.4.2<br/>
FIX.4.1<br/>
FIX.4.0<br/>
9<br/>
8<br/>
7<br/>
6<br/>
5<br/>
4<br/>
3<br/>
2</td>
    <td/>
   <tr>
    <th>ResetOnLogon</th>
    <td>Determines if sequence numbers should be reset when recieving a logon request. Acceptors only.</td>
    <td>Y<br/>N<br/></td>
    <td>N</td>
  </tr>
 </tr>

  <tr>
    <th colspan='4' class="text-center">Validation</th>
  </tr>
   <tr>
    <th>DataDictionary</th>
    <td>
      <p>XML definition file for validating incoming FIX messages. If no DataDictionary is supplied, only basic message validation will be done.</p>
      <p>This setting should only be used with FIX transport versions older than FIXT.1.1. See TransportDataDictionary and AppDataDictionary for FIXT.1.1 settings.</p></td>
    <td>
      <p>valid XML data dictionary file, QuickFIX comes with the following defaults in the spec directory</p>
FIX44.xml<br/>
FIX43.xml<br/>
FIX42.xml<br/>
FIX41.xml<br/>
FIX40.xml</td>
    <td/>
  </tr>
   <tr>
    <th>TransportDataDictionary</th>
    <td>
      <p>XML definition file for validating admin (transport) messages. This setting is only valid for FIXT.1.1 (or newer) sessions.</p>
      <p>See DataDictionary for older transport versions (FIX.4.0 - FIX.4.4) for additional information.</p></td>
    <td>
      <p>valid XML data dictionary file, QuickFIX comes with the following defaults in the spec directory</p>
FIXT1.1.xml</td>
    <td/>
  </tr>
  <tr>
    <th>AppDataDictionary</th>
    <td>
      <p>XML definition file for validating application messages. This setting is only valid for FIXT.1.1 (or newer) sessions.</p>
      <p>See DataDictionary for older transport versions (FIX.4.0 - FIX.4.4) for additional information.</p>
      <p>This setting supports the possibility of a custom application data dictionary for each session. This setting would only be used with FIXT 1.1 and new transport protocols. This setting can be used as a prefix to specify multiple application dictionaries for the FIXT transport. For example:</p>
<pre>
DefaultApplVerID=FIX.4.2
# For default application version ID
AppDataDictionary=FIX42.xml
# For nondefault application version ID
# Use BeginString suffix for app version
AppDataDictionary.FIX.4.4=FIX44.xml
</pre>
    </td>
    <td>
      <p>valid XML data dictionary file, QuickFIX comes with the following defaults in the spec directory</p>
FIX50SP2.xml<br/>
FIX50SP1.xml<br/>
FIX50.xml<br/>
FIX44.xml<br/>
FIX43.xml<br/>
FIX42.xml<br/>
FIX41.xml<br/>
FIX40.xml</td>
    <td/>
  </tr>
  <tr>
    <th colspan='4' class='text-center'>Initiator</th>
  </tr>
   <tr>
    <th>HeartBtInt</th>
    <td>Heartbeat interval in seconds. Only used for initiators.</td>
    <td>positive integer</td>
    <td/>
  </tr>
   <tr>
    <th>SocketConnectPort</th>
    <td>Socket port for connecting to a session. Only used with a SocketInitiator</td>
    <td>positive integer</td>
    <td/>
  </tr>
   <tr>
    <th>SocketConnectHost</th>
    <td>Host to connect to. Only used with a SocketInitiator</td>
    <td>valid IP address in the format of x.x.x.x or a domain name</td>
    <td/>
  </tr>
  <tr>
    <th colspan='4' class='text-center'>Acceptor</th>
  </tr>
   <tr>
    <th>SocketAcceptPort</th>
    <td>Socket port for listening to incoming connections, Only used with a SocketAcceptor</td>
    <td>positive integer, valid open socket port. Currently, this must be defined in the [DEFAULT] section.</td>
    <td/>
  </tr>
  <tr>
    <th colspan='4' class='text-center'>Logging</th>
  </tr>
   <tr>
    <th>FileLogPath</th>
    <td>Directory to store logs.</td>
    <td>valid directory for storing files, must have write access</td>
    <td/>
  </tr>
  </tbody>
</table>
