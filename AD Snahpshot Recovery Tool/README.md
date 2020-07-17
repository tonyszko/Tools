# AD Snaphost Recovery Tool

Snapshot Recovery tool is command line interface tool which simplifies process of Active Directory deleted objects reanimation and populating these objects with data from Active Directory snapshot mounted in active instance.

This tool can be also used to populate existing (not deleted) object with data from Active Directory snapshot without performing actual un-delete operation. This functionality makes this tool perfect choice for performing quick AD object recovery to state from given point in time. In opposite to other recovery methods like using CSV or LDIF data export from snapshot this tool allows to complete whole operation in single command for multiple objects.

You can read more about AD snapshots and how to work with them in Daniel's Petri excelent article: [Working with Active Directory Snapshots in Windows Server 2008](https://petri.com/working-active-directory-snapshots-windows-server-2008).

Usage:

Snapshot Recovery Tool ver.1.0.2rel
-help Basic help information
Usage:
 oirecmgr.exe [-o:objectGUID]
[Target options]
 -o objectGUID GUID of object to recover.
 Multiple GUIDs can be specified separated with spaces.
 -of <file name> Name of file which contains input data.
 Each GUID has to be specified in separated line.
Switches:
[Connection options]
 -h ldapHost[:port] LDAP host in host:port format. If port will not be
 specified, default 389 port number will be used
 -sh snapshot[:port] Snapshot LDAP host in host:port format. If port will not be
 specified, default 1389 port number will be used
 -u username Username. If not specified current security context
 will be used
 -p pwd Password. If not specified current security context
 will be used
[Recovery options]
 -real Performs real recovery operation.
 By default this tool runs in preview mode
-ol Recover object with recovering attributes from snapshot data.
 Specifing snaphsot connection option (-sh) is required.
-ra [attrs] Recover all non-linked attributes for object. Requires -ol to be specified.
 List of attributes to recover can be specified separated with spaces.
-rfl[attrs] Recover all forward-link attributes for object. Requires -ol to be specified.
 List of attributes to recover can be specified separated with spaces.
-rbl [attrs] Recover linked value attributes for all naming contexts.
 LDIF files will be generated for object from other naming cotnext.
 List of attributes to recover can be specified separated with spaces.
-rta Recover attributes preserved in tombstone from snapshot data.
-errok Ignore single attribute level recovery errors
[Snapshot search options]
 -sb <search base> LDAP query search base specified as DN
 -ss <base|onelevel|subtree> LDAP query scope
 -sf <filter> LDAP query filter
[Misc options]
 -v Verbose output mode.
 -d [file name] Enable debug logging to file. If file name will not
 be specified debug.log will be used


 ---------
 Example 1:
 oirecmgr.exe -o cdd5250b-3a7f-4d13-a331-a9fae8075eab -real
 Recover single AD object without recovering attributes from snapshot data.

 	
Snapshot Recover Tool

Snapshot Recovery tool is command line interface tool which simplifies process of Active Directory deleted objects reanimation and populating these objects with data from Active Directory snapshot mounted in active instance.

This tool can be also used to populate existing (not deleted) object with data from Active Directory snapshot without performing actual un-delete operation. This functionality makes this tool perfect choice for performing quick AD object recovery to state from given point in time. In opposite to other recovery methods like using CSV or LDIF data export from snapshot this tool allows to complete whole operation in single command for multiple objects.

Snapshot Recovery Tool can be executed on following systems:

    Windows XP (execution only)
    Windows Vista (execution only)
    Windows 2003
    Windows Server 2008 (except Server Core)

Snapshot Recovery Tool supports following Active Directory environments:

    Windows 2003 (un-delete operation only)
    Windows 2008 (un-delete and attribute recovery)
    Windows 2008 R2 (un-delete and attribute recovery)

This tool requires .NET Framework 2.0 installed in system on which it is being executed. It will not run without .NET Framework 2.0.

**********************
Download tool now

**********************

Suggestions, comments and bugs can be reported to t.onyszko@w2k.pl.

Current Snapshot Recovery Tool usage information:

Snapshot Recovery Tool ver.1.0.2rel
-help Basic help information
Usage:
 oirecmgr.exe [-o:objectGUID]
[Target options]
 -o objectGUID GUID of object to recover.
 Multiple GUIDs can be specified separated with spaces.
 -of <file name> Name of file which contains input data.
 Each GUID has to be specified in separated line.
Switches:
[Connection options]
 -h ldapHost[:port] LDAP host in host:port format. If port will not be
 specified, default 389 port number will be used
 -sh snapshot[:port] Snapshot LDAP host in host:port format. If port will not be
 specified, default 1389 port number will be used
 -u username Username. If not specified current security context
 will be used
 -p pwd Password. If not specified current security context
 will be used
[Recovery options]
 -real Performs real recovery operation.
 By default this tool runs in preview mode
-ol Recover object with recovering attributes from snapshot data.
 Specifing snaphsot connection option (-sh) is required.
-ra [attrs] Recover all non-linked attributes for object. Requires -ol to be specified.
 List of attributes to recover can be specified separated with spaces.
-rfl[attrs] Recover all forward-link attributes for object. Requires -ol to be specified.
 List of attributes to recover can be specified separated with spaces.
-rbl [attrs] Recover linked value attributes for all naming contexts.
 LDIF files will be generated for object from other naming cotnext.
 List of attributes to recover can be specified separated with spaces.
-rta Recover attributes preserved in tombstone from snapshot data.
-errok Ignore single attribute level recovery errors
[Snapshot search options]
 -sb <search base> LDAP query search base specified as DN
 -ss <base|onelevel|subtree> LDAP query scope
 -sf <filter> LDAP query filter
[Misc options]
 -v Verbose output mode.
 -d [file name] Enable debug logging to file. If file name will not
 be specified debug.log will be used

---------
 Example 1:
 oirecmgr.exe -o cdd5250b-3a7f-4d13-a331-a9fae8075eab -real
 Recover single AD object without recovering attributes from snapshot data.

---------
 Example 2:
 oirecmgr.exe -o cdd5250b-3a7f-4d13-a331-a9fae8075eab -sh lhfdc1:1389 -ol -real
 Recover single AD object and recovers all attributes from snapshot using specified snapshot host.


 ---------
 Example 3:
 oirecmgr.exe -of guids.txt -sh lhfdc1:1389 -ol -real
 Recover AD objects with GUIDs specified in file and recovers all attributes from snapshot using specified snapshot host.


 ## Disclaimer

 This software is distributed as free download. Use it at your own risk.
Iput a lot of efforts in this software development and testing,
 however 1Identity does not warrant that this software will meet specific
 requirements or will not make any damage to directory service data.