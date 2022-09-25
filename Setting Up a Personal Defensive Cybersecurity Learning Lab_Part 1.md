Setting Up a Personal Defensive Cybersecurity Learning Lab: Part 1
========================================================================

License
------------------------------------------------------------------------

[![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa]

Setting Up a Personal Defensive Cybersecurity Learning Lab © 2022 by Christopher M. Hosmer is licensed under a
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa]. To view a copy of this license, visit <http://creativecommons.org/licenses/by-nc-sa/4.0/>

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg

Table of Contents
------------------------------------------------------------------------

01. [Table of Contents](#table-of-contents)

02. [Summary](#summary)

03. [Objective](#objective)

04. [Notes](#notes)

05. [Prerequisites](#prerequisites)

06. [References](#references)

07. [General VirtualBox Hypervisor and Virtual Machine Setup Steps](#general-virtualbox-hypervisor-and-virtual-machine-setup-steps)

08. [General VMware Workstation Player Hypervisor and Virtual Machine Setup Steps](#general-vmware-workstation-player-hypervisor-and-virtual-machine-setup-steps)

09. [General Guest Operating System (OS) Setup Steps](#general-guest-operating-system-os-setup-steps)

10. [General Guest Operating System (OS) First Boot Steps](#general-guest-operating-system-os-first-boot-steps)

11. [General DoD Cybersecurity Software Download Steps](#general-dod-cybersecurity-software-download-steps)

12. [General DoD Cybersecurity Software Setup Steps](#general-dod-cybersecurity-software-setup-steps)

Audit Log
------------------------------------------------------------------------

```text
Original Created by:
 Christopher M. Hosmer [2xCH]
Original Created On: 25 Jan 2022

Last Modified by:
 Christopher M. Hosmer [2xCH]
Last Modified On: 21 May 2022

Version: 1.1.0.0
```

Modification Log
------------------------------------------------------------------------

 Version     | Date    | Modified By           | Change Summary
-------------|---------|-----------------------|-------------------------
 01.01.00.00 | 21MAY22 | Christopher M. Hosmer | Removed header and footer markings.
 01.00.00.00 | 19APR22 | Christopher M. Hosmer | -- Version 1.0.0.0.

Summary
------------------------------------------------------------------------

This document helps the user setup a hypervisor on a
[Microsoft Windows 10][Windows10-Support] host operating system (OS) and
a single virtual machine running the __Ubuntu 18.04.6 LTS (Bionic Beaver)__
[Ubuntu Desktop Linux distribution][Ubuntu-Homepage] as a guest
operating system.  The document guides the user through installing
and configuring several publicly available U.S. Department of Defense
(DoD) tools on the guest OS so the user can exercise self-learning to
evaluate the guest operating system's security posture and learn how to
securing the guest OS using U.S. DoD standards.

Objective
------------------------------------------------------------------------

This guide provides directions for creating an environment that assists
a user in learning techniques used for securing the __Ubuntu 18.04.6 LTS (Bionic Beaver)__
[Ubuntu Desktop Linux distribution][Ubuntu-Homepage] using U.S. DoD
tools and standards.  The guide does not cover how to use Linux, to
apply security principles, or to evaluate security standards within a
specific architecture.  It does help establish the environment needed
for the user to perform self-discovery about a commonly used Linux
distribution and the methods used by the U.S. DoD to both secure that
operating system and evaluate its security posture.  The objective is
for the user to exercise manual techniques, vs. automated scripts, to
step through each security control and apply the "Fix Text" so the user
can gain an understanding of each risk and the technical implementation
for mitigating the risk.  The user should read through each control
thoroughly researching each technology, the stated risk, and the impacts
of the fix text.  In the process the user will learn more about Linux,
how it works, and how to control its operational environment.

Notes
------------------------------------------------------------------------

This document only covers setup of tools within
[Microsoft Windows 10][Windows10-Support] as the host operating system
(OS), i.e. the OS installed on the computer prior to following any of
the steps in this document.  This document also covers use of either
[Oracle VirtualBox][VB-Homepage] or
[VMware Workstation Player][VWP-Homepage] as the hypervisor;
[Oracle VirtualBox][VB-Homepage] is supported on a wider range of host
operating systems while [VMware Workstation Player][VWP-Homepage] is the
required hypervisor for [CyberPatriot][CP-Homepage] competitions.  Both
hypervisors are free to use, but [Oracle VirtualBox][VB-Homepage] has a
richer set of available features compared tp
[VMware Workstation Player][VWP-Homepage] so might be more desirable for
some users.

>>> :warning: **WARNING**
>>>
>>> Users are responsible for ensuring they meet all vendor licensing
>>> and usage requirements of the respective products.

Prerequisites
------------------------------------------------------------------------

* Host Computer
  > __Notes__
  >
  > * This document does not address how to check or enable
  >   virtualization extensions as the procedure differs for each
  >   computer.  Consult the manufacture's documentation.
  > * The following is not an exhaustive list of system requirements.

  * Intel or AMD CPU that supports virtualization extensions (i.e. Intel VT, Intel VT-x, or AMD-V)
  * Virtualization support enabled in the BIOS/UEFI firmware
  * At least 8GB of RAM
  * At least 64GB of free disk space

* Host Operating System (OS)
  > __Note__
  >
  > Other host operating systems are supported, but are not covered in
  > this document.  Refer to the vendor documentation for more
  > information:  
  > [VirtualBox Host OS Compatibility Guide][VB-HostOS]  
  > [VMware Workstation Player Host OS Compatibility Guide][VWP-HostOS]  

  * [Microsoft Windows 10][Windows10-Support] 64-bit
  * Administrative rights

References
------------------------------------------------------------------------

These references may provide additional information about content
covered by this Documentation File, but not all may have been used to
develop the Documentation File.

------------------------------------

[VirtualBox Homepage][VB-Homepage]

[VirtualBox Download Webpage][VB-Downloads]

[VirtualBox Online Manual][VB-Manual]

[VirtualBox Host OS Compatibility Guide][VB-HostOS]

[VMware Workstation Player Homepage][VWP-Homepage]

[VMware Workstation Player Download Webpage][VWP-Downloads]

[VMware Workstation Player Online Manual][VWP-Manual]

[VMware Workstation Player Host OS Compatibility Guide][VWP-HostOS]

[Canonical Ubuntu Homepage][Ubuntu-Homepage]

[Canonical Ubuntu Download Webpage][Ubuntu-Downloads]

[Canonical Ubuntu 18.04.6 Download Webpage][Ubuntu-Downloads-18.04.6]

[Debian Linux Homepage][Debian-Homepage]

[Debian Linux Download Webpage][Debian-Downloads]

[Microsoft Windows 10 Support Webpage][Windows10-Support]

[Microsoft Windows 10 Evaluation Download Webpage][Windows10-EvalDownloads]

[CyberPatriot Homepage][CP-Homepage]

[DoD Cyber Exchange Homepage [Public]][CX-Homepage]

[DoD Security Technical Implementation Guides (STIGs) Webpage [Public]][CX-STIGs]

[VB-Homepage]: <https://www.virtualbox.org/> "VirtualBox Homepage"

[VB-Downloads]: <https://www.virtualbox.org/wiki/Downloads> "VirtualBox Download Webpage"

[VB-Manual]: <https://www.virtualbox.org/manual/> "VirtualBox Online Manual"

[VB-HostOS]: <https://www.virtualbox.org/manual/ch01.html#hostossupport> "VirtualBox Supported Host Operating Systems"

[VWP-Homepage]: <https://www.vmware.com/products/workstation-player.html> "VMware Workstation Player Homepage"

[VWP-Downloads]: <https://www.vmware.com/go/downloadplayer> "VMware Workstation Player Download Webpage"

[VWP-Manual]: <https://www.vmware.com/support/pubs/player_pubs.html> "VMware Workstation Player Online Manual"

[VWP-HostOS]: <https://kb.vmware.com/s/article/80807> "Supported host operating systems for Workstation Pro 16.x and Workstation Player 16.x (80807)"

[Ubuntu-Homepage]: <https://ubuntu.com/> "Canonical Ubuntu Homepage"

[Ubuntu-Downloads]: <https://ubuntu.com/download> "Canonical Ubuntu Download Webpage"

[Ubuntu-Downloads-18.04.6]: <https://releases.ubuntu.com/18.04.6/> "Canonical Ubuntu 18.04.6 Download Webpage"

[Debian-Homepage]: <https://www.debian.org/> "Debian Linux Homepage"

[Debian-Downloads]: <https://www.debian.org/download> "Debian Linux Download Webpage"

[Windows10-Support]: <https://support.microsoft.com/en-us/windows?ui=en-US&rs=en-US&ad=US#WindowsVersion=Windows_10> "Microsoft Windows 10 Support Webpage"

[Windows10-EvalDownloads]: <https://www.microsoft.com/en-us/evalcenter/evaluate-windows-10-enterprise> "Microsoft Windows 10 Evaluation Downloads Webpage"

[CP-Homepage]: <https://www.uscyberpatriot.org/> "CyberPatriot Homepage"

[CX-Homepage]: <https://public.cyber.mil/> "DoD Cyber Exchange Homepage (Public)"

[CX-STIGs]: <https://public.cyber.mil/stigs/> "DoD Security Technical Implementation Guides (STIGs) Webpage [Public]"

------------------------------------
------------------------------------

General VirtualBox Hypervisor and Virtual Machine Setup Steps
------------------------------------------------------------------------

>> :warning: **CAUTION**
>>
>> Do not complete this section if you are going to complete the [General VMware Workstation Player Hypervisor and Virtual Machine Setup Steps](#general-vmware-workstation-player-hypervisor-and-virtual-machine-setup-steps) section.

01. [Download][VB-Downloads] the __VirtualBox__ platform package for Windows hosts (~103MB).

02. [Download][VB-Downloads] the __Oracle VM VirtualBox Extension Pack__ for all supported platforms (~10.6MB).

03. Right-click the "SHA256 checksums" link and select the "Save link as" menu item.

04. In the file selection window, click the "Downloads" bookmark in the left pane, change the filename to `VirtualBox-SHA256SUMS.txt`, and click the "Save" button.

    > __Note__
    >
    > The "SHA256 checksums" is a text file, so left-clicking will open it within the browser instead of downloading and saving it to the default download directory.

05. [Download][Ubuntu-Downloads-18.04.6] the __Ubuntu 18.04.6 LTS Desktop Linux__ distribution ISO image file (~2.3GB).

06. Right-click the "SHA256SUMS" link and select the "Save link as" menu item.

07. In the file selection window, click the "Downloads" bookmark in the left pane, change the filename to `Ubuntu18-SHA256SUMS.txt`, and click the "Save" button.

    > __Note__
    >
    > The "SHA256SUMS" is a text file, so left-clicking will open it within the browser instead of downloading and saving it to the default download directory.

08. Type `powershell` in the Windows Search Bar and start a `Windows PowerShell` session.

09. Navigate to the `Downloads` directory:

    ```powershell
    # Use a tilde-prefix to automatically insert the user's home directory as the first part of the path.
    cd ~\Downloads
    ```

10. Verify that the directory has the five (5) downloaded files:

    ```powershell
    # -Include: Only show the names that match the patterns
    Get-ChildItem .\* -Include '*VirtualBox*','*Ubuntu*'
    ```

11. Verify the __Integrity__ of the "VirtualBox" installer.

    01. Calculate the SHA-256 hash of the downloaded "VirtualBox" installer:

        ```powershell
        # .Hash: Only return the hash value
        # .ToLower(): Convert the results to all lowercase
        (Get-FileHash -Algorithm SHA256 .\VirtualBox-*-Win.exe).Hash.ToLower()
        ```

        > __Note__
        >
        > If the `Get-FileHash` cmdlet is not available try using the `certutil` program:
        >
        > ```powershell
        > # The `certutil` application doesn't seem to accept glob patterns, so the full filename is required.
        > # The following command uses an example filename.
        > certutil -hashfile .\VirtualBox-6.1.32-149290-Win.exe SHA256
        > ```

    02. Display the SHA-256 hash provided in the file downloaded from the "VirtualBox" website:

        ```powershell
        # |: Pipe the results of `Get-Content` into `Select-String`
        # -Pattern: Only return the strings that match the pattern
        # |: Pipe the results of `Select-String` into `ForEach-Object`
        # .Split: Split the string using the specified character as the field delimiter
        # [0]: Only return the first result
        Get-Content .\VirtualBox-SHA256SUMS.txt | Select-String -Pattern 'VirtualBox-.*-Win.exe' | ForEach-Object { ([string]$_).Split(' ')[0] }
        ```

    03. Compare the two hashes; if they match then the __Integrity__ of the download is confirmed, else repeat the previous steps to download the file again.

12. Verify the __Integrity__ of the "Oracle VM VirtualBox Extension Pack" file.

    01. Calculate the SHA-256 hash of the downloaded "Oracle VM VirtualBox Extension Pack" file:

        ```powershell
        # .Hash: Only return the hash value
        # .ToLower(): Convert the results to all lowercase
        (Get-FileHash -Algorithm SHA256 .\Oracle_VM_VirtualBox_Extension_Pack-*.vbox-extpack).Hash.ToLower()
        ```

        > __Note__
        >
        > If the `Get-FileHash` cmdlet is not available try using the `certutil` program:
        >
        > ```powershell
        > # The `certutil` application doesn't seem to accept glob patterns, so the full filename is required.
        > # The following command uses an example filename.
        > certutil -hashfile .\Oracle_VM_VirtualBox_Extension_Pack-6.1.32.vbox-extpack SHA256
        > ```

    02. Display the SHA-256 hash provided in the file downloaded from the "VirtualBox" website:

        ```powershell
        # |: Pipe the results of `Get-Content` into `Select-String`
        # -Pattern: Only return the strings that match the pattern
        # |: Pipe the results of `Select-String` into `ForEach-Object`
        # .Split: Split the string using the specified character as the field delimiter
        # [0]: Only return the first result
        Get-Content .\VirtualBox-SHA256SUMS.txt | Select-String -Pattern 'Oracle_VM_VirtualBox_Extension_Pack-.*.vbox-extpack' | ForEach-Object { ([string]$_).Split(' ')[0] }
        ```

    03. Compare the two hashes; if they match then the __Integrity__ of the download is confirmed, else repeat the previous steps to download the file again.

13. Verify the __Integrity__ of the "Ubuntu 18.04.6 LTS Desktop Linux" distribution ISO image file.

    01. Calculate the SHA-256 hash of the downloaded "Ubuntu 18.04.6 LTS Desktop Linux" distribution ISO image file:

        ```powershell
        # .Hash: Only return the hash value
        # .ToLower(): Convert the results to all lowercase
        (Get-FileHash -Algorithm SHA256 .\ubuntu-18.04.6-desktop-amd64.iso).Hash.ToLower()
        ```

        > __Note__
        >
        > If the `Get-FileHash` cmdlet is not available try using the `certutil` program:
        >
        > ```powershell
        > # The `certutil` application doesn't seem to accept glob patterns, so the full filename is required.
        > # The following command uses an example filename.
        > certutil -hashfile .\ubuntu-18.04.6.4-desktop-amd64.iso SHA256
        > ```

    02. Display the SHA-256 hash provided in the file downloaded from the "Ubuntu" website:

        ```powershell
        # |: Pipe the results of `Get-Content` into `Select-String`
        # -Pattern: Only return the strings that match the pattern
        # |: Pipe the results of `Select-String` into `ForEach-Object`
        # .Split: Split the string using the specified character as the field delimiter
        # [0]: Only return the first result
        Get-Content .\Ubuntu18-SHA256SUMS.txt | Select-String -Pattern 'ubuntu-18.04.6-desktop-amd64.iso' | ForEach-Object { ([string]$_).Split(' ')[0] }
        ```

    03. Compare the two hashes; if they match then the __Integrity__ of the download is confirmed, else repeat the previous steps to download the file again.

14. Close the `PowerShell` window.

15. Install the VirtualBox executable downloaded in Step 1.

16. Install the VirtualBox extension pack downloaded in Step 2.

17. Start the "VirtualBox Graphical User Interface" application.

18. Click the "Machine" menu and select the "New..." menu item.

19. In the "Create Virtual Machine" window, fill in the "Name and operating system" form with the following information and then click the "Next >" button:
    * __Name__: WS-U18-01
    * __Machine Folder__: *leave the default*
    * __Type__: Linux
    * __Version__: Ubuntu (64-bit)

20. In the "Create Virtual Machine" window, type "4096" in the "Memory size" form and then click the "Next >" button.

21. In the "Create Virtual Machine" window, select the "Create a virtual hard disk now" radio button and click the "Create" button.

22. In the "Create Virtual Hard Disk" window on the "Hard disk file type" page, select the "VDI (VirtualBox Disk Image)" radio button and click the "Next >" button.

23. In the "Create Virtual Hard Disk" window on the "Storage on physical hard disk" page, select the "Dynamically allocated" radio button and click the "Next >" button.

24. In the "Create Virtual Hard Disk" window on the "File location and size" page, leave the default path, change the disk size to "64.00 GB" in the text box, and click the "Create" button.

25. In the "VirtualBox Graphical User Interface" right-click the new virtual machine and select the "Settings..." menu item.

26. In the "Settings" window, select the "Storage" section on the left column of the window.

27. In the "Settings" window, select the "Empty" entry under the "Controller: IDE" storage device in the center column of the window.

28. In the "Settings" window, click the disk icon next to the "Optical Drive" drop-down menu in the right column of the window and then select the "Choose a disk file..." menu item.

29. Select the ISO image file downloaded in Step 5 and then click the "Open" button.

30. In the "Settings" window, select the "Display" section on the left column of the window.

31. In the "Settings" window, increase the "Video Memory" to "128 MB" using the slider.

32. In the "Settings" window, check the "Enable 3D Acceleration" checkbox.

33. In the "Settings" window, select the "System" section on the left column of the window.

34. In the "Settings" window, select the "Motherboard" tab and check the "Enable EFI (special OSes only)" checkbox.

35. In the "Settings" window, select the "Processor" tab and increase the "Processor(s)" count to "2" using the slider.

36. In the "Settings" window, click the "OK" button.

37. In the "VirtualBox Graphical User Interface" right-click the new virtual machine and select the "Start" -> "Normal Start" menu item.

------------------------------------

General VMware Workstation Player Hypervisor and Virtual Machine Setup Steps
------------------------------------------------------------------------

>> :warning: **CAUTION**
>>
>> Do not complete this section if you have already completed the [General VirtualBox Hypervisor and Virtual Machine Setup Steps](#general-virtualbox-hypervisor-and-virtual-machine-setup-steps) section.

01. [Download][VWP-Downloads] the __VMware Workstation Player__ installer package for Windows hosts (~584MB).

02. Click the "Read More" link underneath the "VMware Workstation 16.2.3 Player for Windows 64-bit Operating Systems" entry.

03. Highlight and copy the text in the right-column of the displayed table.

    > _EXAMPLE TEXT_
    >
    > ```text
    > VMware Workstation 16.2.3 Player for Windows 64-bit Operating Systems
    > MD5SUM: e27665f745618fd1c0e2388c63d9c2de
    > SHA1SUM: 3fd74d8e48d7abca8d466f927597752ceb22d052
    > SHA256SUM: c05b61e8c70fd75a4e22984c3432c1f63480239d219937d13cad73cc41da1e09
    > ```

04. Open "File Explorer" and click the "Downloads" bookmark in the left pane.

05. Right-click a blank area in the right pane and select the "New > Text Document" menu item.

06. Name the file `VMware-Hashes.txt` when prompted and then double-click the file to open it.

07. Paste the text copied from the VMware website, save, and then close the `VMware-Hashes.txt` file.

    >> :warning: **CAUTION**
    >>
    >> After pasting the text, replace all tab characters with single spaces.

08. [Download][Ubuntu-Downloads-18.04.6] the __Ubuntu 18.04.6 LTS Desktop Linux__ distribution ISO image file (~3GB).

09. Right-click the "SHA256SUMS" link and select the "Save link as" menu item.

10. In the file selection window, click the "Downloads" bookmark in the left pane, change the filename to `Ubuntu18-SHA256SUMS.txt`, and click the "Save" button.

    > __Note__
    >
    > The "SHA256SUMS" is a text file, so left-clicking will open it within the browser instead of downloading and saving it to the default download directory.

11. Type `powershell` in the Windows Search Bar and start a `Windows PowerShell` session.

12. Navigate to the `Downloads` directory:

    ```powershell
    # Use a tilde-prefix to automatically insert the user's home directory as the first part of the path.
    cd ~\Downloads
    ```

13. Verify that the directory has the four (4) downloaded files:

    ```powershell
    # -Include: Only show the names that match the patterns
    Get-ChildItem .\* -Include '*VMware*','*Ubuntu*'
    ```

14. Verify the __Integrity__ of the "VMware Workstation Player" installer.

    01. Calculate the SHA-256 hash of the downloaded "VMware Workstation Player" installer:

        ```powershell
        # .Hash: Only return the hash value
        # .ToLower(): Convert the results to all lowercase
        (Get-FileHash -Algorithm SHA256 .\VMware-player-full-*.exe).Hash.ToLower()
        ```

        > __Note__
        >
        > If the `Get-FileHash` cmdlet is not available try using the `certutil` program:
        >
        > ```powershell
        > # The `certutil` application doesn't seem to accept glob patterns, so the full filename is required.
        > # The following command uses an example filename.
        > certutil -hashfile .\VMware-player-full-16.2.3-19376536.exe SHA256
        > ```

    02. Display the SHA-256 hash provided in the file downloaded from the "VMware" website:

        ```powershell
        # |: Pipe the results of `Get-Content` into `Select-String`
        # -Pattern: Only return the strings that match the pattern
        # |: Pipe the results of `Select-String` into `ForEach-Object`
        # .Split: Split the string using the specified character as the field delimiter
        # [1]: Only return the second result
        Get-Content .\VMware-Hashes.txt | Select-String -Pattern 'SHA256' | ForEach-Object { ([string]$_).Split(' ')[1] }
        ```

    03. Compare the two hashes; if they match then the __Integrity__ of the download is confirmed, else repeat the previous steps to download the file again.

15. Verify the __Integrity__ of the "Ubuntu 18.04.6 LTS Desktop Linux" distribution ISO image file.

    01. Calculate the SHA-256 hash of the downloaded "Ubuntu 18.04.6 LTS Desktop Linux" distribution ISO image file:

        ```powershell
        # .Hash: Only return the hash value
        # .ToLower(): Convert the results to all lowercase
        (Get-FileHash -Algorithm SHA256 .\ubuntu-18.04.6-desktop-amd64.iso).Hash.ToLower()
        ```

        > __Note__
        >
        > If the `Get-FileHash` cmdlet is not available try using the `certutil` program:
        >
        > ```powershell
        > # The `certutil` application doesn't seem to accept glob patterns, so the full filename is required.
        > # The following command uses an example filename.
        > certutil -hashfile .\ubuntu-18.04.6.4-desktop-amd64.iso SHA256
        > ```

    02. Display the SHA-256 hash provided in the file downloaded from the "Ubuntu" website:

        ```powershell
        # |: Pipe the results of `Get-Content` into `Select-String`
        # -Pattern: Only return the strings that match the pattern
        # |: Pipe the results of `Select-String` into `ForEach-Object`
        # .Split: Split the string using the specified character as the field delimiter
        # [0]: Only return the first result
        Get-Content .\Ubuntu18-SHA256SUMS.txt | Select-String -Pattern 'ubuntu-18.04.6-desktop-amd64.iso' | ForEach-Object { ([string]$_).Split(' ')[0] }
        ```

    03. Compare the two hashes; if they match then the __Integrity__ of the download is confirmed, else repeat the previous steps to download the file again.

16. Close the `PowerShell` window.

17. Install the VMware Workstation Player executable downloaded in Step 1.

18. Start the "VMware Workstation Player" application.

19. Click the "File" menu and select the "Create a New Virtual Machine" menu item.

20. Select the "Use ISO image" radio button.

21. Click the "Browse..." button.

22. Select the ISO image file downloaded in Step 8 and then click the "Open" button.

23. Select the "I will install the operating system later." radio button.

24. Click the "> Next" button.

25. In the "Guest Operating System" page, verify that the "Linux" radio button is checked; check the radio button, if required.

26. In the "Guest Operating System" page, verify that the "Ubuntu 64-bit" menu item is selected in the "Version:" menu; select the "Ubuntu 64-bit" menu item, if required.

27. Click the "> Next" button.

28. In the "Virtual Machine Name" page, fill in the form with the following information and then click the "> Next" button:
    * __Name__: WS-U18-01
    * __Location__: *leave the default*

29. In the "Disk Size" page, change the disk size to "64.00 GB" in the text box, select the "Split virtual disk into multiple files" radio button, and click the "> Next" button.

30. Click the "Customize Hardware..." button.

31. In the "Virtual Machine Settings" window, select the "Memory" section on the left column of the window.

32. Verify that the "Memory for this virtual machine:" text box has a "4096" value; correct the value, if required.

33. In the "Virtual Machine Settings" window, select the "Processors" section on the left column of the window.

34. Verify that the "Number of processor cores:" text box has a "2" value; correct the value, if required.

35. In the "Virtual Machine Settings" window, select the "New CD/DVD (SATA)" section on the left column of the window.

36. Verify that the "Use ISO image:" radio box is selected and that the value is set to what was selected in Step 8; correct the value, if required.

37. In the "Virtual Machine Settings" window, select the "Display" section on the left column of the window.

38. Verify that the "Accelerate 3D graphics" check box is enabled; correct the setting, if required.

39. Click the "Graphics Memory" menu and select the "128 MB" menu item.

40. Click the "Close" button.

41. Click the "> Finish" button.

42. Click the "Close" button.

43. In the "VMware Workstation Player" application right-click the new virtual machine and select the "Power On" menu item.

------------------------------------

General Guest Operating System (OS) Setup Steps
------------------------------------------------------------------------

01. After the virtual machine boots, it will launch the operating system installer.

    > __Note__
    >
    > If the "Install" window does not automatically start, then double-click the "Install Ubuntu 18.04.6 LTS" icon on the desktop.  In the "Install" window on the "Welcome" page, select "English" and click the "Continue" button.  Continue to Step 2.

    01. Wait until a the Ubuntu Graphical User Interface (GUI) loads and displays the "Install" window.

    02. In the "Install" window on the "Welcome" page, select "English" and click the "Install Ubuntu" button.

02. In the "Install" window on the "Keyboard layout" page, select "English (US) for both options and click the "Continue" button.

03. In the "Install" window on the "Updates and other software" page, select the "Normal installation" radio button, check the "Download updates while installing Ubuntu" checkbox, check the "Install third-party software for graphics and Wi-Fi hardware and additional media formats" checkbox, and click the "Continue" button.

04. In the "Install" window on the "Installation type" page, select the "Erase disk and install Ubuntu" radio button and click the "Install Now" button.

    > __Notes__
    >
    > * This will not erase the hard drive on which the host operating system is installed.  This will only affect the virtual hard drive that was created for the virtual machine's 'guest operating system.
    > * A secure system should use full disk encryption, which can be done during installation by checking both the "Encrypt the new Ubuntu installation for security" and "Use LVM with the new Ubuntu installation" checkboxes, but disk encryption should be left as a manual task so the user can further research this capability, the impacts, and how to apply the required settings after installation.

05. On the "Write the changes to disk?" window click the "Continue" button.

06. In the "Install" window on the "Where are you?" page, type "Huntsville" in the text box, then select "Huntsville (Alabama, United States)" in the menu, and then click the "Continue" button.

07. In the "Install" window on the "Who are you?" page, fill out the form with the following information:
    * __Your name__: *any descriptive name*
    * __Your computer's name__: WS-U18-01
    * __Pick a username__: *any descriptive name*
    * __Choose a password__: *a complex password or passphrase that is longer than 12 characters*

08. Verify that the "Require my password to log in" radio button is selected and then click the "Continue" button.

09. Wait for the operating system to finish installing; when the "Installation Complete" window appears click the "Restart Now" button.

10. When the "Please remove the installation medium, then press ENTER:" message appears, press the "Enter" button.

------------------------------------

General Guest Operating System (OS) First Boot Steps
------------------------------------------------------------------------

01. On the logon window, click the user created during the installation.

02. Enter the password set for the user during the installation process.

    >>> :warning: **WARNING**
    >>>
    >>> If the "Ubuntu 20.04.x LTS Upgrade Available" window appears click the "Don't Upgrade" button and then the "OK" button in the "You have declined the upgrade to Ubuntu 20.04.x LTS" window.

03. If the "Software Updater" window appears, click the "Install Now" button.

    > __Note__
    >
    > It might take a few minutes for the "Software Updater" window to appear.

04. When the "What's new in Ubuntu" window appears, click the "Next" button.

05. In the "Livepatch" window click the "Next" button.

06. In the "Help improve Ubuntu" window select the "No, don't send system info" radio button and click the "Next" button.

07. In the "Ready to go" window click the "Done" button.

    >> :warning: **CAUTION**
    >>
    >> If updates are being installed, wait until the software updates complete before continuing; click on the "Software Updater" icon and click the "Restart Now" button, if prompted.  After the system reboots, log back into a desktop session.

08. Click the "Activities" button in the upper-left corner of the "top bar" on the desktop and type "Terminal" in the search bar.

09. Click the "Terminal" icon.

10. If using [VirtualBox][VB-Homepage] as the hypervisor:

    01. Type `sudo apt install build-essential dkms linux-headers-$(uname -r)` in the terminal and enter your user password when prompted.

    02. Type `y` in the terminal at the "Do you want to continue [Y/n]" prompt.

    03. Type `exit` to terminate the terminal.

    04. In the "VirtualBox Graphical User Interface" virtual machine window, click the "Devices" menu and select the "Insert Guest Additions CD image..." menu item.

    05. In the guest operating system, in the ""VBox_GAs_x.y.z" contains software intended to be automatically started. Would you like to run it?" prompt click the "Run" button and enter your user password when prompted.

    06. After the installer finishes, click the down arrow in the upper-right corner of the "top bar" on the desktop, and click the "Power" button.

    07. In the "Power Off" prompt click the "Restart" button.

    08. After the system reboots, log back into a desktop session.

11. If using [VMware Workstation Player][VWP-Homepage] as the hypervisor:

    01. Type `sudo apt list --installed *vmware* open-vm*` in the terminal and enter your user password when prompted.

    02. Verify that the command returns the following information:

        > __Note__
        >
        > Version numbers may be different than the ones shown below.

        ```text
        Listing... Done
        open-vm-tools/bionic-updates,now 2:11.0.5-4ubuntu0.18.04.1 amd64 [installed,automatic]
        open-vm-tools-desktop/bionic-updates,now 2:11.0.5-4ubuntu0.18.04.1 amd64 [installed,automatic]
        xserver-xorg-video-vmware-hwe-18.04/bionic-updates,now 1:13.3.0-2build1~18.04.1 amd64 [installed,automatic]
        ```

    03. If any of the packages are missing install them using the `sudo apt install open-vm-tools open-vm-tools-desktop xserver-xorg-video-vmware-hwe` command.

12. Resize the virtual machine window in the host operating system and the guest operating system should resize automatically.

------------------------------------

General DoD Cybersecurity Software Download Steps
------------------------------------------------------------------------

01. On the side "dash" bar, click the "Firefox" icon.

02. Navigate to the [DoD Cyber Exchange homepage (Public)][CX-Homepage] at the `https://public.cyber.mil` URL.

03. On the "DoD Cyber Exchange" website, click the "SRGs/STIGs" button at the top of the webpage.

04. On the left navigation bar of the "Security Technical Implementation Guides (STIGs)" webpage click the "Automation" menu and select the "Security Content Automation Protocol (SCAP)" menu item.

05. Under the "SCAP 1.2 CONTENT" section, download the "Canonical Ubuntu 18.04 LTS STIG Benchmark - Ver x, Rel x" package and save it to the guest OS.

06. Under the "SCAP TOOLS" section, download the "SCC x.y Ubuntu 18 AMD64" package and save it to the guest OS.

07. Right-click the "SCC x.y.z Checksum file" and select the "Save Link As..." menu item.

08. In the file selection window, click the "Downloads" bookmark in the "Places" pane and click the "Save" button.

    > __Note__
    >
    > The "SCC x.y.z Checksum file" is a text file, so left-clicking will open it within the browser instead of downloading and saving it to the default downloads directory.

09. On the left navigation bar of the "Security Technical Implementation Guides (STIGs)" webpage click the "SRG/STIG Tools and Viewing Guidance" menu item.

10. Under the "STIG Viewing Tools" section, download the "STIG Viewer x.y-Linux" package and save it to the guest OS.

11. Right-click the "STIG Viewer x.y Hashes" and select the "Save Link As..." menu item.

12. In the file selection window, click the "Downloads" bookmark in the "Places" pane and click the "Save" button.

    > __Note__
    >
    > The "STIG Viewer x.y Hashes" is a text file, so left-clicking will open it within the browser instead of downloading and saving it to the default downloads directory.

13. On the left navigation bar of the "Security Technical Implementation Guides (STIGs)" webpage click the "Document Library" menu item.

14. On the right side of the "Document Library" page under the "STIG TOPICS" heading, check the "Operating Systems" checkbox.

15. Download the "Canonical Ubuntu 18.04 LTS STIG - Ver x, Rel y" file.

16. On the side "dash" bar, click the "Files" icon.

17. In the "Files" application, click on the "Downloads" bookmark in the left navigation pane.

18. Verify that there are two (2) text files and four (4) ZIP archives in the directory:

    > __Note__
    >
    > Version numbers may be different than the ones shown below.

    ```text
    SCC_5.4.2_Checksums.txt
    U_STIGViewer_2-16_Hashes.txt
    scc-5.4.2_ubuntu18_amd64_bundle.zip
    U_CAN_Ubuntu_18-04_V2R6_STIG_SCAP_1-2_Benchmark.zip
    U_CAN_Ubuntu_18-04_LTS_V2R7_STIG.zip
    U_STIGViewer_2-16_Linux.zip
    ```

19. Click the "Activities" button in the upper-left corner of the "top bar" on the desktop and type "Terminal" in the search bar.

20. Click the "Terminal" icon.

21. Navigate to the `Downloads` directory:

    ```bash
    # Use a tilde-prefix to automatically insert the user's home directory as the first part of the path.
    cd ~/Downloads
    ```

22. Verify that the directory has the same six (6) files viewed in the `Files` application:

    ```bash
    # -1: Display results in a single column
    # -X: Sort alphabetically by entry extension
    ls -1X
    ```

23. Verify the __Integrity__ of the "SCAP Compliance Checker" ZIP archive.

    01. Calculate the SHA-256 hash of the downloaded "SCAP Compliance Checker" ZIP archive:

        ```bash
        #  |: Pipe the results from 'sha256sum' into 'cut'
        # -d: Use the specified character as the field delimiter
        # -f: Only display the first field
        sha256sum scc-*_ubuntu18_amd64_bundle.zip | cut -d ' ' -f 1
        ```

    02. Display the SHA-256 hash provided in the file downloaded from the "DoD Cyber Exchange" website:

        ```bash
        # -A: Display the # of lines after the match
        # -E: Interpret PATTERNS as extended regular expressions
        #  |: Pipe the results from 'grep' into 'grep'
        # -v: Display all ines that do not match
        # -E: Interpret PATTERNS as extended regular expressions
        #  |: Pipe the results from 'grep' into 'cut'
        # -d: Use the specified character as the field delimiter
        # -f: Only display the fifth field
        grep -A 1 -E 'scc-.+_ubuntu18_amd64_bundle.zip' SCC_*_Checksums.txt | grep -v -E 'scc-.+_ubuntu18_amd64_bundle.zip' | cut -d ' ' -f 5
        ```

    03. Compare the two hashes; if they match then the __Integrity__ of the download is confirmed, else repeat the previous steps to download the file again.

24. Verify the __Integrity__ of the "STIG Viewer" ZIP archive.

    01. Calculate the SHA-256 hash of the downloaded "STIG Viewer" ZIP archive:

        ```bash
        #  |: Pipe the results from 'sha256sum' into 'cut'
        # -d: Use the specified character as the field delimiter
        # -f: Only display the first field
        sha256sum U_STIGViewer_*_Linux.zip | cut -d ' ' -f 1
        ```

    02. Display the SHA-256 hash provided in the file downloaded from the "DoD Cyber Exchange" website:

        ```bash
        # -A: Display the # of lines after the match
        # -E: Interpret PATTERNS as extended regular expressions
        #  |: Pipe the results from 'grep' into 'grep'
        # -i: Make the match string case insensitive
        #  |: Pipe the results from 'grep' into 'cut'
        # -d: Use the specified character as the field delimiter
        # -f: Only display the fifth field
        #  |: Pipe the results from 'cut' into 'tr'
        grep -A 3 -E 'U_STIGViewer_.+_Linux.zip' U_STIGViewer_*_Hashes.txt | grep -i 'SHA256' | cut -d ' ' -f 2 | tr [:upper:] [:lower:]
        ```

    03. Compare the two hashes; if they match then the __Integrity__ of the download is confirmed, else repeat the previous steps to download the file again.

25. Close the "Terminal" application.

26. Close the "Files" application.

27. Close the "Firefox" browser.

------------------------------------

General DoD Cybersecurity Software Setup Steps
------------------------------------------------------------------------

01. Click the "Activities" button in the upper-left corner of the "top bar" on the desktop and type "Terminal" in the search bar.

02. Click the "Terminal" icon.

03. Type `sudo -sE` in the terminal and enter your user password when prompted to enter a privileged session.

04. Navigate to the download folder by executing the `cd ~/Downloads` command.

05. Unzip the "STIG Viewer" application by executing the `unzip -d /opt/stigviewer 'U_STIGViewer_*_Linux.zip'` command.

06. Unzip the "SCAP Compliance Checker" installer by executing the `unzip 'scc-*_ubuntu*.zip'` command.

07. Change to the new directory by executing the `cd scc-*_ubuntu*_*/` command.

08. Install the "SCAP Compliance Checker" by executing the `dpkg -i scc-*.ubuntu.*_*.deb` command.

09. Change to the installation directory by executing the `cd /opt` command.

10. Type `./scc/scc &` to start the SCAP Compliance Checker.

    01. In the "Content" section under the "SCAP" tab in the "Stream" column, check the "Linux" checkbox.

    02. Right-click the "Linux" entry and select the "Delete All" menu entry.

    03. In the "Content" section click the "Install" button.

    04. In the "Install Content" window, enable all radio buttons and click the "Select Content File(s) to Install" button.

    05. In the file selection window, click the "Downloads" bookmark in the "Places" pane.

    06. Select the "U_CAN_Ubuntu_18-04_VxRy_STIG_SCAP_1-2_Benchmark.zip" file and click the "Open" button.

    07. In the "Install Content" window, click the "Install" button.

    08. In the "Scan" section on the left of the application interface, click the "Start Scan" button.

    09. On the side "dash" bar, click the "Files" icon.

    10. In the "Files" application, click on the "Home" bookmark in the left navigation pane.

    11. Double-click the "SCC" directory in the right navigation pane.

    12. Double-click the "Sessions" directory in the right navigation pane.

    13. Double-click the directory in the right navigation pane that has the recent date-timestamp of the SCC scan.

    14. Double-click the "SCC_Summary_Viewer_*.html" file to open the scan results.

    15. Click the "HTML" link under the "All Settings" column to open the "All Settings Report."

    16. Review the report to get an idea of the security posture for a default installation of [Canonical Ubuntu][Ubuntu-Homepage].

        >> :warning: **CAUTION**
        >>
        >> Do not skip over reviewing results that passed; those settings may very well be ones that have been modified on a live or competition system, so the user needs to be familiar with those in addition to the checks that failed.

11. Type `./stigviewer/STIGViewer &` to start the STIG Viewer.

    01. At the top of the application in the menu bar, click the "File" menu and select "Import STIG..." menu item.

    02. In the file selection window, click the "Downloads" bookmark in the "Places" pane.

    03. Select the "U_CAN_Ubuntu_18-04_LTS_VxRy_STIG.zip" file and click the "Open" button.

    04. In the "STIG Explorer" tab under the "STIGs" section, check the "Canonical Ubuntu 18.04.6 LTS ..." entry.

    05. At the top of the application in the menu bar, click the "Checklist" menu and select "Create Checklist - Check Marked STIG(s)" menu item.

    06. With the "*New Checklist" tab active, at the top of the application in the menu bar, click the "Import" menu and select "XCCDF Results File..." menu item.

    07. In the file selection window, click on the "Home" bookmark in the left navigation pane.

    08. Double-click the "SCC" directory in the right navigation pane.

    09. Double-click the "Sessions" directory in the right navigation pane.

    10. Double-click the directory in the right navigation pane that has the recent date-timestamp of the SCC scan.

    11. Double-click the "Results" directory in the right navigation pane.

    12. Double-click the "SCAP" directory in the right navigation pane.

    13. Double-click the "XML" directory in the right navigation pane.

    14. Select the file with "XCCDF-Results" in the filename and click the "Open" button.

    15. Review all rules by selecting each in the middle pane of the "*New Checklist" tab to gain an understanding of the rule ("Rule Title"), the possible risk to the system if the rule is not followed ("Discussion" section), how to verify that the rule is implemented ("Check Text" section), and how to apply the setting(s) if absent or incorrect on the system ("Fix Text" section) for an installation of [Canonical Ubuntu][Ubuntu-Homepage].

        >> :warning: **CAUTION**
        >>
        >> * Do not skip over reviewing results that passed, as notated with the "Not a Finding" or "NF" status marker; those settings may very well be ones that have been modified on a live or competition system, so the user needs to be familiar with those in addition to the checks that failed, as notated with the "Open" or "O" status marker.
        >> * Note how many checks require a manual review, as notated with the "Not Reviewed" or "NR" status marker, and cannot be automated with generalized checks using the SCAP tool, but could be with customized scripts.

------------------------------------
