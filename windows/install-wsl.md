# Install WSL

__Category: Windows__

Windows System for Linux (WSL) provides support for running a Linux kernel natively on Windows 10, Windows 11, and Windows Server 2019. The latest version at the time of writing is WSL 2.

List available distros using the following command:

```command
wsl --list --online
```

Output:

```command
The following is a list of valid distributions that can be installed.
The default distribution is denoted by '*'.
Install using 'wsl --install -d <Distro>'.

  NAME            FRIENDLY NAME
* Ubuntu          Ubuntu
  Debian          Debian GNU/Linux
  kali-linux      Kali Linux Rolling
  openSUSE-42     openSUSE Leap 42
  SLES-12         SUSE Linux Enterprise Server v12
  Ubuntu-16.04    Ubuntu 16.04 LTS
  Ubuntu-18.04    Ubuntu 18.04 LTS
  Ubuntu-20.04    Ubuntu 20.04 LTS
```

Install a distro (Ubuntu 20.04) with the following command:

```command
wsl --install -d Ubuntu-20.04
```

Output:

```command
Installing: Virtual Machine Platform
Virtual Machine Platform has been installed.
Installing: Windows Subsystem for Linux
Windows Subsystem for Linux has been installed.
Downloading: WSL Kernel
Installing: WSL Kernel
WSL Kernel has been installed.
Downloading: Ubuntu 20.04 LTS
The requested operation is successful. Changes will not be effective until the system is rebooted.
```

You may need to reboot based on the output from the installation.

__Note:__ You will need to run the installation using administrative priviledges in an elevated command prompt. 
