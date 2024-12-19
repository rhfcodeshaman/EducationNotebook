# Subject Overview
**Overview**:
```
```
**Index**:
- Area 1
## OS Fundamentals
**Basic Linux File Structure**

| **Path** | **Description**                                                                                                                                                                                                                                                                                                                    |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/`      | The top-level directory is the root filesystem and contains all of the files required to boot the operating system before other filesystems are mounted, as well as the files required to boot the other filesystems. After boot, all of the other filesystems are mounted at standard mount points as subdirectories of the root. |
| `/bin`   | Contains essential command binaries.                                                                                                                                                                                                                                                                                               |
| `/boot`  | Consists of the static bootloader, kernel executable, and files required to boot the Linux OS.                                                                                                                                                                                                                                     |
| `/dev`   | Contains device files to facilitate access to every hardware device attached to the system.                                                                                                                                                                                                                                        |
| `/etc`   | Local system configuration files. Configuration files for installed applications may be saved here as well.                                                                                                                                                                                                                        |
| `/home`  | Each user on the system has a subdirectory here for storage.                                                                                                                                                                                                                                                                       |
| `/lib`   | Shared library files that are required for system boot.                                                                                                                                                                                                                                                                            |
| `/media` | External removable media devices such as USB drives are mounted here.                                                                                                                                                                                                                                                              |
| `/mnt`   | Temporary mount point for regular filesystems.                                                                                                                                                                                                                                                                                     |
| `/opt`   | Optional files such as third-party tools can be saved here.                                                                                                                                                                                                                                                                        |
| `/root`  | The home directory for the root user.                                                                                                                                                                                                                                                                                              |
| `/sbin`  | This directory contains executables used for system administration (binary system files).                                                                                                                                                                                                                                          |
| `/tmp`   | The operating system and many programs use this directory to store temporary files. This directory is generally cleared upon system boot and may be deleted at other times without any warning.                                                                                                                                    |
| `/usr`   | Contains executables, libraries, man files, etc.                                                                                                                                                                                                                                                                                   |
| `/var`   | This directory contains variable data files such as log files, email in-boxes, web application related files, cron files, and more.                                                                                                                                                                                                |
## Terminal/Shell
The prompt can be customized using special characters and variables in the shell’s configuration file (`.bashrc` for the Bash shell). For example, we can use: the `\u` character to represent the current username, `\h` for the hostname, and `\w` for the current working directory.

|**Special Character**|**Description**|
|---|---|
|`\d`|Date (Mon Feb 6)|
|`\D{%Y-%m-%d}`|Date (YYYY-MM-DD)|
|`\H`|Full hostname|
|`\j`|Number of jobs managed by the shell|
|`\n`|Newline|
|`\r`|Carriage return|
|`\s`|Name of the shell|
|`\t`|Current time 24-hour (HH:MM:SS)|
|`\T`|Current time 12-hour (HH:MM:SS)|
|`\@`|Current time|
|`\u`|Current username|
|`\w`|Full path of the current working directory|

