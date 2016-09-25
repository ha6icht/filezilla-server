#FileZilla Server#

Copyright 2001-2016  
by [Tim Kosse](mailto:tim.kosse@filezilla-project.org)[  
https://filezilla-project.org/](https://filezilla-project.org/)

##Features:##

*   almost unlimited number of users
*   multi-threaded engine
*   runs as service under Windows Vista, 7, 8, 8.1 and 10
*   anti fxp / bounce attack filter
*   secure password storage (as MD5 hash)
*   real-time user/group management
*   all options can be set at runtime, there's no need to take the server offline
*   no-transfer timeout which can kick idle users which use basic keep alive systems
*   Server and user/group speed limits based on rule sets.
*   MODE Z file transfer compression

<u>**Release Notes:**</u>

Please report any bugs immediately to [tim.kosse@filezilla-project.org](mailto:tim.kosse@filezilla-project.org) and don't forget to include some system details as it helps to identify the bugs.

<u>**The tray icon**</u>

From the tray icon you've access to different features of FileZilla Server. You can enable/disable, lock/unlock or exit the server as well as restoring it to normal size.

<table border="0">

<tbody>

<tr>

<td colspan="3">

<u>List of tray icon states:</u>

</td>

</tr>

<tr>

<td>red</td>

<td>server offline</td>

</tr>

<tr>

<td>yellow</td>

<td>server online</td>

</tr>

<tr>

<td>green</td>

<td>client connected</td>

</tr>

<tr>

<td>flashing red-green</td>

<td>server will go offline or will exit when all clients are disconnected</td>

</tr>

<tr>

<td>flashing red-yellow</td>

<td>server is locked</td>

</tr>

<tr>

<td>flashing yellow-green</td>

<td>server is locked and clients are still connected</td>

</tr>

</tbody>

</table>

**<u>Version History:</u>**

For a more detailed list of changes, please have a look at the SVN changelog located at [https://filezilla-project.org/changelog.php?type=2](https://filezilla-project.org/changelog.php?type=2).

**Version 0.9.59**

> <u>Bug fixes:</u>
> 
> *   Updated OpenSSL to 1.0.2i due to several security vulnerabilities in OpenSSL
> *   Fixed getting list of connected users when connecting with the admin interface
> *   Fixed crash if the administration connection is closed while an administrative command is being processed

**Version 0.9.58**

> <u>New features and improvements:</u>
> 
> *   TCP send buffer auto-tuning
> *   Performance improvements to reduce CPU usage under high load
> *   Disabled IDEA and SEED ciphers for FTP over TLS
> 
> <u>Bug fixes:</u>
> 
> *   Fixed potential crash if closing connections with pending socket messages
> *   A missing home directory is no longer treaded like an empty directory

**Version 0.9.57**

> <u>Improvements:</u>
> 
> *   Rearranged "Connect to Server" dialog and added some helpful labels
> 
> <u>Bug fixes:</u>
> 
> *   Updated OpenSSL to 1.0.2h
> *   FileZilla Server no longer fails to read or write its settings if installed in a directory containing characters not expressible in the system's default multibyte character set.

**Version 0.9.56.1**

> <u>Bug fixes:</u>
> 
> *   Updated installer to NSIS 3.0b3 to prevent DLL hijacking

**Version 0.9.56**

> <u>Bug fixes:</u>
> 
> *   Improve compatibility with broken clients that always try anonymous logins even if the user has explicitly specified a username.
> *   Updated OpenSSL to 1.0.2g

**Version 0.9.55**

> <u>New features:</u>
> 
> *   The maximum amount of reconnect attempt for the administration interface can be configured in its settings file
> 
> <u>Bug fixes:</u>
> 
> *   The administration interface no longer starts if it cannot load the TLS libraries
> *   Small fixes to the Copy user functionality
> *   Updated OpenSSL to 1.0.2f

**Version 0.9.54**

> <u>New features and incompatible changes:</u>
> 
> *   Newly set account passwords are now stored in form of salted SHA512 hashes
> *   The undocumented 8+3 filename feature has been removed
> 
> <u>Bug fixes:</u>
> 
> *   Waiting for transfers to finish when taking the server offline now correctly closes the sockets
> *   Clarified a few error messages related to FTP over TLS
> *   Updated OpenSSL to 1.0.2d

**Version 0.9.53**

> <u>Bug fixes:</u>
> 
> *   Updated OpenSSL to 1.0.2b due to several security vulnerabilities in OpenSSL

**Version 0.9.52**

> <u>New features:</u>
> 
> *   Add support for TLS ciphers using DHE and ECDHE to allow perfect forward secrecy
> *   In the settings file, "Minimum TLS version" can be used to further increase the minimum required TLS version a client needs to speak in order to connect
> 
> <u>Bug fixes:</u>
> 
> *   Allow 0.0.0.0/0 CIDR notation in IP filters.

**Version 0.9.51**

> <u>Bug fixes:</u>
> 
> *   Security fix: The code that checks that the peer's data connection IP address matches the control connection IP had been nonfunctional. Vulnerability discovered and reported by Amit Klein.
> 
> <u>New features:</u>
> 
> *   Security fix: Added option to force TLS session resumption on the data connection to prevent data connection stealing
> *   Security fix: FileZilla Server now randomizes the port used for passive mode transfers to mitigate data connection stealing when using plain FTP
> *   Added diagnostic message to the administration interface if FTP over TLS is disabled and if the configured certificate is expired or otherwise invalid
> *   Added diagnostic message to the administration interface if no passive mode IP has been configured and the server appears to be behind a NAT router
> *   The settings dialog layout had a spring cleaning. The security settings, passive mode settings and TLS settings pages have received the most cleanup.

**Version 0.9.50**

> <u>Bug fixes:</u>
> 
> *   Updated to OpenSSL 1.0.2a due to several security vulnerabilities in OpenSSL
> *   Fixed default network buffer size to match its description
> *   Fixed silent uninstallation

**Version 0.9.49**

> <u>Bug fixes:</u>
> 
> *   Updated OpenSSL library to due to several security vulnerabilties in OpenSSL
> *   Fixed crash if updating permissions under load
> *   Changing admin interface IP bindings did not recreate the listening socket on ::1
> *   Fix display of welcome message and FEAT reply in log

**Version 0.9.48**

> <u>New features:</u>
> 
> *   Allow use of the OPTS command prior to login
> *   EPSV and EPRT support are now advertised in the reponse to the FEAT command
> *   Minidumps are now automatically written in the installation directory in the unfortunate case of a server crash
> 
> <u>Bug fixes:</u>
> 
> *   Updated OpenSSL libraries and fixed memory leaks when unloading OpenSSL

**Version 0.9.47**

> <u>New features and important changes:</u>
> 
> *   Self-signed certificates created with FileZilla Server are now signed using SHA-256
> *   Interface settings (as opposed to server settings) are now stored in %APPDATA%/FileZilla Server
> *   Increased maximum IP filter size for users and groups by 50%
> *   The administration protocol now allows up to 16 million users and groups
> 
> <u>Bug fixes:</u>
> 
> *   Fix sporadic crashes when using FTP over TLS
> *   Fix timestamps in LIST output being off up to 7 minutes in extreme cases
> *   Speed up querying file attributes
> *   Autoban did not work over IPv6
> *   Fixed selection in user list sort dropdown behind the corresponding toolbar button

**Version 0.9.46**

> <u>New features and important changes:</u>
> 
> *   FTP over TLS: Disallow insecure and weak cipher suites. Algorithms no longer supported include 3DES, RC4, MD5
> *   Small performance improvements
> 
> <u>Bug fixes:</u>
> 
> *   Fix stalling or improperly terminated connections when using FTP over TLS
> *   Fix crash with enabled speed limits

**Version 0.9.45**

> <u>New features and important changes:</u>
> 
> *   Security fix: Update to OpenSSL 1.0.1h to address CVE-2014-0224
> *   Clarified wording and offer additional help when setting up aliases
> 
> <u>Bug fixes:</u>
> 
> *   Through the RMD command it was possible to delete aliases

**Version 0.9.44**

> <u>New features and important changes:</u>
> 
> *   Security fix: Update to OpenSSL 1.0.1g to address CVE-2014-0160
> *   Improve alias description and guide user towards alias creation if multiple unrelated directories are being shared. Support for the old non-virtual alias configuration has been removed.
> *   Display additional information if a certificate or key file cannot be loaded

**Version 0.9.43**

> <u>New features and important changes:</u>
> 
> *   Security fix: Disallow renaming and deleting of aliases through FTP commands
> *   Removed outdated and untested Kerberos GSSAPI support
> *   Removed support for the nonstandard OPTS UTF8 OFF command which is not part of the FTP specifications
> *   Added TLS 1.2 support
> *   Minimum RSA key size for generated certificates is now 1280 bit
> 
> <u>Bug fixes:</u>
> 
> *   Fix handling of leading/trailing whitespace in filenames
> *   Fix display of file name at the end of a transfer
> *   The 8+3 account setting is now stored in the correct XML element
> *   Increase number of tries searching for a free port after the PASV/EPSV command
> *   Fix text clipping on the miscellaneous page in the settings dialig
> *   Fixed memory leaks when changing settings
> *   The numbers to the PORT command are now always treated as decimal numbers as per the FTP specifications even if they have leading zeroes
> 
> <u>Build system:</u>
> 
> *   Modernized and cleaned up workspace files for Visual Studio 2013
> *   Removed all non-Unicode configurations

**Version 0.9.42**

> <u>New features:</u>
> 
> *   Last version ever to support Windows XP
> *   More verbose replies to the transfer commands
> 
> <u>Fixed bugs:</u>
> 
> *   Fix an endless loop if a client closes a connection using the QUIT command while a speed limit was in effect on a low-latency connection
> *   Fixed a rare memory leak
> *   Correct handling of 0.0.0.0/0 in IP address filters
> *   Use UTF8 in the distinguished names of created certificates

**Version 0.9.41**

> <u>Fixed bugs:</u>
> 
> *   Fix parsing of IP address filters ending with :0 or equivalent substrings.
> *   Allow speed limits larger than 64 MiB/s.
> *   Show more verbose error messages if transfer connection cannot be established.

**Version 0.9.40**

> <u>Fixed bugs:</u>
> 
> *   The service no longer crashes if connecting with the administration interface when there are clients connected over IPv6
> *   Close the connection if there is additional data in the input buffers when processing the AUTH command.
> *   Display correct connection state item in administration interface when getting initial list of connected clients

**Version 0.9.39**

> <u>Fixed bugs:</u>
> 
> *   Do not attempt to display a message box if creating an administration interface binding fails. This freezes the service on some machines.
> *   On FTP over TLS connections, the socket address family was not initialized from the underlaying socket
> *   Fix a bug in IPv4 address filters and increase their performance

**Version 0.9.38**

> <u>New features:</u>
> 
> *   IPv6 support
> 
> <u>Incompatible changes:</u>
> 
> *   Range, wildcard, regular expression and dot-decimal notation subnet IP address filters have been removed. These filter rules need to be recreated using CIDR notation.
> 
> <u>Fixed bugs:</u>
> 
> *   Upon /reload-config, notify all running instances, not just the first found.
> *   Report correct physical path of aliases in administration interface
> *   Fix reply code on permanent bans, not of 5yz type
> *   Increased default size of socket buffers
> *   Fix a crash when entering invalid IP filters
> *   Fixed a crash when a connection closes
> *   Updated to most recent OpenSSL version

**Version 0.9.37**

> <u>Fixed bugs:</u>
> 
> *   Advertise support for PBSZ and PROT in FEAT reply
> *   Allow PROT after PORT/PASV/EPRT/EPSV but before transfer command
> *   Use correct replies for RNTO, EPRT and MKD command
> *   Reply with correct error code in response to transfer commands if PROT P is required but not set
> *   Fix display of non-ASCII characters in log
> *   Ignore read-only attribute on DELE

**Version 0.9.36**

> <u>Fixed bugs:</u>
> 
> *   Fix welcome message

**Version 0.9.35**

> <u>New features:</u>
> 
> *   Administration interface is now Unicode enabled.
> 
> <u>Fixed bugs:</u>
> 
> *   Fix saving of speed-limit rules

**Version 0.9.34**

> <u>New features:</u>
> 
> *   Show address of server in title bar of administration interface (patch submitted by eyebex)
> 
> <u>Fixed bugs:</u>
> 
> *   Disable some weak TLS/SSL ciphers such as DES-CBC-SHA which shouldn't be used anymore
> *   Work around some obscure error reported by OpenSSL, fixes spurious transfer failures
> *   Use case-insensitive comparison instead of always converting to lowercase in permissions handling. Fixes problems with sharing case-sensitive network resources.
> *   Settings with empty data were not loaded from settings file correctly and reverted back to default values (patch submitted by eyebex)
> *   Improve performance of (re-)loading settings

**Version 0.9.33**

> <u>New features:</u>
> 
> *   Add /servicename and /servicedisplayname options to change the (display) name of the server service.
> 
> <u>Fixed bugs:</u>
> 
> *   Fix potential double-delete in admin connection code, could be used for remote denial of service if using remote administration (not enabled by default).
> *   Increase minimum value for maximum allowed login attempts before autoban to 10.

**Version 0.9.32**

> <u>New features:</u>
> 
> *   Use thousands separator in output of large numbers.
> 
> <u>Fixed bugs:</u>
> 
> *   Disallow weak SSLv2.
> *   Slightly reword FTP over TLS/SSL settings page.
> *   Adjust width of user and group lists on permissions dialogs.

**Version 0.9.31**

> <u>Fixed bugs:</u>
> 
> *   Fix buffer overflow in SSL code leading to a potential security vulnerability.

**Version 0.9.30**

> <u>Fixed bugs:</u>
> 
> *   Fix a rare case in which SSL shutdown notifications were created but not actually sent.

**Version 0.9.29**

> <u>Fixed bugs:</u>
> 
> *   Executable path did not get quoted properly in service creation leading to a **local** privilege escalation vulnerability.

**Version 0.9.28**

> <u>Fixed bugs:</u>
> 
> *   Directly reject PROT C if PROT P is required instead of complaining after a transfer command
> *   Fix race in transfer connection initialization leading to timeouts
> *   No-transfer timeouts could not be disabled in 0.9.27
> *   Server startup options in installer had no effect

**Version 0.9.27**

> <u>Fixed bugs:</u>
> 
> *   An orderly SSL/TLS shutdown was not performed in all cases
> *   Disallow no-transfer timeouts smaller than 600 seconds

For a more detailed list of changes, please have a look at the CVS changelog located at [https://filezilla-project.org/changelog.php?type=2](https://filezilla-project.org/changelog.php?type=2).

**Version 0.9.26**

> <u>Fixed bugs:</u>
> 
> *   Downloading empty files over TLS connections no longer closes the connection prematurely
> *   Updated to latest OpenSSL version

**Version 0.9.25**

> <u>Fixed bugs:</u>
> 
> *   Implement OPTS MLST as required by RFC 3659
> *   Add some more validation to prevent "Protocol Error, invalid data" errors
> *   Attempt to fix problems with certificate loading some users are experiencing

**Version 0.9.24**

> <u>Fixed bugs:</u>
> 
> *   Fix MFMT command from not accepting all valid dates
> *   Fix keysize selection in certificate generation dialog
> *   Updated to latest OpenSSL version

**Version 0.9.23**

> <u>New features:</u>
> 
> *   Add support for MFMT command to change file modification time
> *   Add basic autoban implementation for the paranoid server admins
> *   Add TYPE L 8 as an alias for TYPE I
> 
> <u>Fixed bugs:</u>
> 
> *   Fix some timezone issues
> *   Fix CTRL+C for message log

**Version 0.9.22**

> <u>Fixed bugs:</u>
> 
> *   Fix denial of service vulnerability due to nullpointer dereference.
> *   Added support for broken clients sending CWD command without arguments.

**Version 0.9.21**

> <u>Changed features:</u>
> 
> *   The default address for the "Retrieve external IP address from:" option has changed.
> 
> <u>Fixed bugs:</u>
> 
> *   Fix SSL related issue on empty directory listings

**Version 0.9.20**

> <u>New features:</u>
> 
> *   Add option to ban user to the context menu of the connected users list.
> 
> <u>Fixed bugs:</u>
> 
> *   Fix SSL shutdown behaviour, fixes compatibility with some clients.
> *   Internal changes to allow larger lists of banned IP addresses.
> *   Improved datasocket creation in active mode.

**Version 0.9.19**

> <u>Fixed bugs:</u>
> 
> *   Updated to OpenSSL 0.9.8d due to security vulnerabilites in OpenSSL

**Version 0.9.18**

> <u>Fixed bugs:</u>
> 
> *   Fix MLSD command not displaying all aliases
> *   Fix keyboard nagivation in settings dialog
> *   Added OPTS UTF8 OFF command

**Version 0.9.17**

> <u>Fixed bugs:</u>
> 
> *   Fix critical buffer overflow in admin interface. Remote code execution with the rights of the user running the admin interface might have been possible. Only the interface was affected, the service was unaffected.
> *   Fix memory leak in service
> *   Compatibility fixes for systems with more than one CPU

**Version 0.9.16**

> <u>Fixed bugs:</u>
> 
> *   Fix conversion problem if any configuration data had a non-English character.
> *   Internal changes to make whole service use Unicode
> *   Fix explicit SSL (0.9.16a)
> *   Fix buffer overflow in settings dialog (0.9.16b)
> *   Fix problem with list of connected users (0.9.16c)

**Version 0.9.15**

> <u>New features:</u>
> 
> *   UTF-8 support as specified in [RFC 2640](http://www.faqs.org/rfcs/rfc2640.html). As result, the minimum required Windows version is now Windows 2000.
> 
> <u>Fixed bugs:</u>
> 
> *   SSL file truncation problem
> *   Compatiblity fix for NAT-in-NAT environments
> *   Compatibility with clients sending the STRU command
> *   Fix loading of aliases in UNC format

**Version 0.9.14**

> <u>Fixed bugs:</u>
> 
> *   Fixed problem with SSL transfers aborting or even crashing the server.

**Version 0.9.13**

> <u>New features:</u>
> 
> *   Option to not use external ip address in passive mode if client is within local network. Enabled by default.
> *   Option to ignore the address given in the PORT command if it's from an unrouteable address range, but the client has a routeable address. Enabled by default.
> 
> <u>Fixed bugs:</u>
> 
> *   Fixed problems with the case-(in)sensitivity of aliases
> *   (0.9.13b) Fixed passive mode problems introduced in 0.9.13

**Version 0.9.12**

> <u>New features:</u>
> 
> *   Alias targets can now be virtual paths as well
> *   Add option to allow reading of files which are opened for writing by another process
> *   Always require a set password even for local connections now. If you don't remember your password, delete it from **FileZilla Server.xml**
> *   Workaround for SMC routers with P@SW bug
> *   Added SITE NAMEFMT command with "1" as only supported naming format. Required by at least one client running on AS/400 server.
> 
> <u>Fixed bugs:</u>
> 
> *   Don't allow AUTH SSL/TLS command if already using SSL/TLS, broadcast SSL/TLS availability in FEAT response

**Version 0.9.11**

> <u>Fixed bugs:</u>
> 
> *   No longer freezes if using a password protected keyfile.
> *   It was not possible to access filenames starting with multiple dots

**Version 0.9.10**

> <u>New features:</u>
> 
> *   Option to force SSL login for selected users/groups
> 
> <u>Fixed bugs:</u>
> 
> *   SSL mode fixes, fix truncated downloads
> *   fix creation of multiple ports if not bound to all IP addresses

**Version 0.9.9**

> <u>New features:</u>
> 
> *   Option to force PROT P for SSL/TLS connections.
> 
> <u>Fixed bugs:</u>
> 
> *   Now compiled against zlib 1.2.3 to fix potential security vulnerability

**Version 0.9.8c**

> <u>Fixed bugs:</u>
> 
> *   Sometimes file downloads aborted prematurely leading to incomplete files.
> *   Don't send MODE Z in FEAT response if MODE Z has been disabled.

**Version 0.9.8b**

> <u>New features:</u>
> 
> *   Added option to set socket buffer size, increased default buffer sizes
> 
> <u>Fixed bugs:</u>
> 
> *   Wildcards in argument to LIST command were not handled properly
> *   Use proper reply code for AUTH SSL and AUTH TLS commands

**Version 0.9.8**

> <u>New features:</u>
> 
> *   Service and Admin interface can be installed separately in the installer
> 
> <u>Fixed bugs:</u>
> 
> *   Infinite loop if user disconnects while throttled by anti-hammering code
> *   Accept PBSZ command if using SSL/TLS

**Version 0.9.7**

> <u>New features:</u>
> 
> *   Option to force explicit SSL
> 
> <u>Fixed bugs:</u>
> 
> *   Available bandwidth was not distributed properly if using speedlimits
> *   possible crash after closing client connections if using SSL
> *   time based speed limits over midnight did not work properly
> *   Connection freeze after SSL initialization
> *   taking server offline and back online did not work properly if used multiple times in a row
> *   fix infinite loop if speedlimits are enabled

**Version 0.9.6a**

> <u>fixed bugs:</u>
> 
> *   Sockets for admin interface or transfer connections could not be created on all systems
> *   Input box for the listen ports did not accept separator characters.
> *   reserved MSDOS device name did not work properly

**Version 0.9.6**

> <u>New features:</u>
> 
> *   SSL/TLS encryption. This feature is still experimental, use at your own risk.
> 
> <u>Fixed bugs:</u>
> 
> *   Infinite loop on file uploads or directory listings if using zlib compression
> *   Sending commands with filenames as arguments which did contain reserved MSDOS device names (such as NUL, CON, COM1, LPT1) could freeze FileZilla Server on older systems. Those filenames are now considered invalid
> *   Fixed crash if taking server offline
> *   Connection limits for users did not work as intended
> *   The /reload-config command line switch has been fixed

**Version 0.9.5**

> <u>fixed bugs:</u>
> 
> *   Typo in anti-hammering code, delayed connections were never unstalled
> *   Aliases for directories containing :u did not work if username did contain uppercase chars
> *   If renaming groups, adjust user accounts accordingly
> *   If deleting groups which are in use, ask what to do with the affected users
> *   Use same network interface for transfer connection as for the control connection to solve some firewall issues, patch by dartonw

**Version 0.9.4e**

> <u>fixed bugs:</u>
> 
> *   Fixed buffer overflow in admin interface
> *   Aliases did not always display in NLST listings

**Version 0.9.4**

> <u>new features:</u>
> 
> *   List of connected users displays more details: IP, current file, progress and speed. Based on patch by "Tropics"
> *   Admininterface reconnects automatically after connection loss
> *   Folders to which the user has no access, won't be displayed in directory listings
> *   All IP filters can now also filter hostnames using regular expressions, based on patch from Sebastian Schuberth
> *   implemented MLSD and MLST commands
> *   implemented ALLO command
> *   If user password in settings file is not 32 characters long (and thus not a MD5 hash) convert it to a MD5 hash.
> 
> <u>removed features:</u>
> 
> > The permissions handling code has been simplified a lot. In the process some features as described above have been removed, partially due to better alternatives.
> > 
> > *   Removed non-relative directory structure mode. It did expose the servers physical directory structure. Also there were some bugs regarding this mode in the previous code.
> > *   Removed "Resolve Shortcuts" option. Aliases are more flexible since they allow username replacement (using **:u**) and don't depend on some files on your drive which could be replaced by other applications.
> 
> <u>fixed bugs:</u>
> 
> *   Dashes as prefix for command line options did not work
> *   Time pickers in speedlimit rule dialog did change type to date pickers.
> *   Internal changes for 64bit portability
> *   Fixed rare crash which could occur whenever a user disconneced
> *   Fixed crashes if stopping server
> *   Use proper reply for MKD commands to already existing directories
> *   No longer display folder selection dialog for remote administration sessions.
> *   Internal changes to reduce CPU load

**Version 0.9.3**

> <u>new features:</u>
> 
> *   Welcome messages can be hidden to no longer display in the interface and logfiles. Based on patch by Jason Jackson.
> *   Max. Welcome message size greatly increased
> 
> <u>fixed bugs:</u>
> 
> *   security fix for zlib which could lead to denial of service attacks if MODE Z transfers are allowed.

**Version 0.9.2**

> <u>new features:</u>
> 
> *   increased speed of admin interface
> *   implemented anti-hammering code to prevent brute force password cracking. Can't be disabled for good reason.

**Version 0.9.1**

> <u>new features:</u>
> 
> *   Directory aliases to simplify usage of virtual file system
> *   IP filter to limit access to server
> *   Users / groups can be disabled
> *   Comments field for users and groups
> *   Added HELP command (0.9.1b)
> 
> <u>fixed bugs:</u>
> 
> *   ip filter did not work properly together with groups (0.9.1a)
> *   fixed deadlock in external IP check and speed limit code
> *   fixed infinite loop in zlib mode
> *   speed limits were not calculcated properly
> *   wrong timezone was used in speed limit rules
> *   global speed limits weren't initialized properly
> *   fixed error message if editing speed limit rules
> *   groups no longer duplicate if opening groups dialog on inactive servers without any user accounts

**Version 0.9.0**

> <u>new features:</u>
> 
> *   MODE Z file transfer compression
> *   server listening socket can be bound to specific IPs
> 
> <u>fixed bugs:</u>
> 
> *   server did not shutdown properly

**Version 0.8.9**

> <u>fixed bugs:</u>
> 
> *   Interface could crash if kicking user
> *   group ip based connection limit did not work
> *   fixed alignment of years in directory listings
> *   fixed crash if listening socket can't be created
> *   changed MKD return code to 257

**Version 0.8.8**

> <u>new features:</u>
> 
> *   added hostname support for external PASV IP address
> *   support for remote IP detection scripts
> *   config file can be reloaded by calling <u>"FileZilla Server.exe" /reload-config</u>
> 
> <u>fixed bugs:</u>
> 
> *   Fixed format of permissions field in directory listings
> *   group membership for user accounts wasn't set on startup
> *   somtimes the last few bytes were missing on uploaded files
> *   fixed missing titles of users and groups dialog

**version 0.8.7**

> <u>new features and improvements:</u>
> 
> *   lots of performance improvements:
>     *   connection establishment is up to 100ms faster
>     *   some optimizations in the welcome message, directory listing and permission codeThanks to Tom Diviney for a lot of testing.
> *   Improved behaviour of LIST and NLST with arguments, should fix the mget issue, fix provided by Bengt Johannesson
> 
> <u>fixed bugs:</u>
> 
> *   Creation of transfer connection in active mode was not RFC 959 compatible.
> *   possible fix for stalling GSS transfers

**version 0.8.6**

> <u>new features:</u>
> 
> *   new log window, it's now possible to select text
> 
> <u>fixed bugs:</u>
> 
> *   due to a bug in the Windows api function CreateDirectory it was possible to create directories with one or more dots at the end of their name. Such directories can't be accessed or deleted by most programs. FileZilla Server now checks for dots at the end of diretories and denies creation of such directories. If you already have such directories on your disk, you can delete them in the console using **rmdir \\?\<path>**, replace path with the full path of the invalid directory.
> *   Usergroups no longer change randomly if there are more than one user group.

**version 0.8.5:**

> <u>new features:</u>
> 
> *   Added server menu to interface with Active and Lock items (same funcionality as the first two icons)
> 
> <u>fixed bugs:</u>
> 
> *   Users without delete permission could delete empty directories
> *   Files could be renamed over account boundaries
> *   Locking the server did not work
> *   Defatult width of users pane was zero if starting the interface on low resolution (800x600 or fewer) monitors.

**version 0.8.4:**

> <u>new features:</u>
> 
> *   Global as well as user specific speed limits can be set
> *   Added user groups
> *   Support for Kerberos GSSAPI authentication
> *   Transfer buffer size can now be set

**version 0.8.3:**

> <u>new features:</u>
> 
> *   remote administration
>     
>     
> *   logging to file
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   admin interface could hang during connect (fixed in 0.8.3a)
>     
>     
> *   F2 to rename user accounts / dirs in users dialog now works correctly
>     
>     
> *   sometimes files sent to clients were not sent correctly

**version 0.8.2**

> <u>fixed bugs:</u>
> 
> *   fixed "account duplication" if taking server offline and back online
>     
>     
> *   fixed timeouts, active clients no longer timeout without reason.

**version 0.8.1**

> <u>new features:</u>
> 
> *   added settings converter due to popular request
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   not all account settings could be read correctly from xml file
>     
>     
> *   fixed some bugs in the server <--> interface protocol
>     
>     
> *   fixed buffer overflow in server side admin socket class
>     
>     
> *   some minor fixes

**version 0.8.0:**

> <u>new features:</u>
> 
> *   Separated server from the user interface, interface now runs in its own process
>     
>     
> *   Sever now runs as service under Windows NT4, 2000 and XP
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   fixed problems with non relative paths and drive letters. This should also fix the compatibility to some versions of the IE and other browsers (fixed by TJ Drennan)
>     
>     
> *   fixed crash if a directory did contain files with a year larger than 2038
>     
>     
> *   server no longer sometimes stops responding after issuing shutdown

**version 0.7.4:**

> <u>new features:</u>
> 
> *   installer now uses modernUI style
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   added warning if accepting a new connection failed. Some bad firewalls do allow creating listen sockets and pass through connection attempts but block accepting them.
>     
>     
> *   fixed some problems with the socket class
>     
>     
> *   fixed GDI-resource leak

**version 0.7.3:**

> <u>fixed bugs:</u>
> 
> *   improved thread responsiveness to messages
>     
>     
> *   fixed display of transferrate
>     
>     
> *   reduced flicker of main window while resizing
>     
>     
> *   when deleting a user, the user data could get mixed up
>     
>     
> *   now no error message appears when "Enable custom PASV settings" is disabled
>     
>     
> *   now NULL passwords are supported if an account does not require a password (anonymous for example)
>     
>     
> *   "Maximum connection count" for user accounts did not work

**version 0.7.2:**

> <u>new features:</u>
> 
> *   added custom PASV IP and port settings
>     
>     
> *   added XCUP, XPWD, XMKD, XRMD and NOP commands
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   QUIT works without beeing logged on
>     
>     
> *   Telnet commands no longer show up in message log
>     
>     
> *   fixed cancel button in users dialog not working properly
>     
>     
> *   added missing users dialog menu entry

**version 0.7.1:**

> <u>fixed bugs:</u>
> 
> *   fixed problems with usernames containing uppercase characters
>     
>     
> *   fixed installer creating source project shortcut in wrong directory
>     
>     
> *   fixed security hole, could list directories outside your ftproot.

**version 0.7:**

> <u>enhanced features:</u>
> 
> *   new Winsock wrapper class, should increase performance a little bit
>     
>     
> *   prepared the use of format specifications in welcome message. If you had used a custom welcome message before using version 0.7, you would have to reenter the message.
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   fixed problem with LIST and NLST command and parameters
>     
>     
> *   files are now stored with the names passed with the STOR command, no longer all lowercase
>     
>     
> *   correct handling of quoted arguments

**version 0.6:**

> <u>new features:</u>
> 
> *   custom welcome message
>     
>     
> *   server port can be changed without having to manually close and reopen it.
>     
>     
> *   increased performance under heavy load
>     
>     
> *   added NLST and MDTM (last modified time) commands
>     
>     
> *   crash log generation
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   fixed security hole that allowed to list directories within your ftp root without list permission.
>     
>     
> *   fixed some more deadlocks

**version 0.5.2 beta:**

> <u>fixed bugs:</u>
> 
> *   fixed problem with usernames containing uppercase characters
>     
>     
> *   Server hanged when it was unable to get the homedir of a user

**version 0.5.1 beta:**

> <u>fixed bugs:</u>
> 
> *   could not always determinate filesize correctly

**version 0.5 beta:**

> <u>new featurs:</u>
> 
> *   NLST command added
>     
>     
> *   a path can be passed to LIST and NLST as argument
>     
>     
> *   start minimized option
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   multiple problems with files larger than 2GB

**version 0.4 beta:**

> <u>new features:</u>
> 
> *   APPE and QUIT command added
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   sometimes permissions could not be retrieved due to a bug in GetRealDirectory(), permission was always denied.
>     
>     
> *   when using APPE or "REST x" (x!=0), it was possible to upload new files in folders with append permission but no write permission.
>     
>     
> *   fixed some minor bugs

**version 0.3 beta:**

> <u>new features:</u>
> 
> *   ip limit per user
>     
>     
> *   users can be renamed
>     
>     
> *   transfer count and rate will be displayed
>     
>     
> *   NOOP command implemented
>     
>     
> 
> <u>enhanced features:</u>
> 
> *   speed of directory listings improved
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   <u>timeouts weren't calculated properly</u>

**version 0.2 beta:**

> <u>new features:</u>
> 
> *   ABOR and SYST commands added
>     
>     
> *   login timeout integrated
>     
>     
> *   users can be kicked
>     
>     
> *   number of threads can be changed at runtime
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   MKD could not create multiple directory levels at once
>     
>     
> *   files were not sent completely to clients
>     
>     
> *   some problems in the users dialog
>     
>     
> *   control channel now sends line endings with <CRLF> as specified in RFC 959 instead of <LF>
>     
>     
> *   InitTransfer called too early in some rare cases
>     
>     
> *   a whole bunch of bugs causing crashes or freezes

**version 0.1 beta:**

> <u>new featuers:</u>
> 
> *   options dialog
>     
>     
> *   timeout and no transfer timeout
>     
>     
> *   port selection
>     
>     
> *   number of threads can be selected
>     
>     
> *   max number of users
>     
>     
> *   user-specific bypass max user and local max user setting
>     
>     
> *   all connected users are displayed on the right pane of the main window
>     
>     
> *   added systray icon
>     
>     
> *   bounce attack / fxp protection
>     
>     
> *   ABOR command implemented
>     
>     
> *   now only one file transfer and one directory listing can be active at the same time, so you can still browse the server during file transfers.
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   sometimes the threads were not shut down correctly with FileZilla
>     
>     
> *   fixed some issues in the user account manager
>     
>     
> *   Server could crash if a new transfer was initiated while another transfer is still active. 

**version 0.0.2 alpha:**

> <u>new features:</u>
> 
> *   non relative paths
>     
>     
> *   file transfers
>     
>     
> *   PASV mode support
>     
>     
> *   delete files and directory
>     
>     
> *   create directories
>     
>     
> *   renaming of files/dirs
>     
>     
> 
> <u>fixed bugs:</u>
> 
> *   the message log now displays the seconds, too

**version 0.0.1 alpha:**

> first public release
> 
> <u>new features:</u>
> 
> *   user account manager
>     
>     
> *   browsing of directories
>     
>     
> *   Windows shorcut files (.lnk files) resolving
>     
>     
> *   multithreaded engine with very basic load balancing
