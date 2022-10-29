Setting Up a Personal Defensive Cybersecurity Learning Lab: Part 3
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

07. [General VirtualBox Virtual Machine Setup Steps](#general-virtualbox-virtual-machine-setup-steps)

08. [General VMware Workstation Player Virtual Machine Setup Steps](#general-vmware-workstation-player-virtual-machine-setup-steps)

09. [General Guest Operating System (OS) Setup Steps](#general-guest-operating-system-os-setup-steps)

10. [General Guest Operating System (OS) First Boot Steps](#general-guest-operating-system-os-first-boot-steps)

11. [General DoD Cybersecurity Software Download Steps](#general-dod-cybersecurity-software-download-steps)

12. [General DoD Cybersecurity Software Setup Steps](#general-dod-cybersecurity-software-setup-steps)

Audit Log
------------------------------------------------------------------------

```text
Original Created by:
 Christopher M. Hosmer [2xCH]
Original Created On: 29 Oct 2022

Last Modified by:
 Christopher M. Hosmer [2xCH]
Last Modified On: 29 Oct 2022

Version: 1.0.0.0
```

Modification Log
------------------------------------------------------------------------

 Version     | Date    | Modified By           | Change Summary
-------------|---------|-----------------------|-------------------------
 01.00.00.00 | 29OCT22 | Christopher M. Hosmer | -- Version 1.0.0.0.

Summary
------------------------------------------------------------------------

This document helps the user setup a hypervisor on a
single virtual machine running the __Fedora 36__
[Fedora Workstation Linux distribution][Fedora-Homepage] as a guest
operating system.  The document guides the user through installing
and configuring several publicly available U.S. Department of Defense
(DoD) tools on the guest OS so the user can exercise self-learning to
evaluate the guest operating system's security posture and learn how to
securing the guest OS using U.S. DoD standards.

Objective
------------------------------------------------------------------------

This guide provides directions for creating an environment that assists
a user in learning techniques used for securing the __Fedora 36__
[Fedora Workstation Linux distribution][Fedora-Homepage] using U.S. DoD
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

This document does _not_ cover setup of tools within the
[Microsoft Windows 10][Windows10-Support] host operating system (OS),
i.e. the OS installed on the computer prior to following any of
the steps in this document.  Refer to [Setting Up a Personal Defensive Cybersecurity Learning Lab: Part 1](Late-Hours_Setting%20Up%20a%20Personal%20Defensive%20Cybersecurity%20Learning%20Lab_Part%201.html)
for information about setting up the [Oracle VirtualBox][VB-Homepage] or
[VMware Workstation Player][VWP-Homepage] as the hypervisor.

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

* Hypervisor
  > __Note__
  >
  > Refer to
  > [Setting Up a Personal Defensive Cybersecurity Learning Lab: Part 1](Late-Hours_Setting%20Up%20a%20Personal%20Defensive%20Cybersecurity%20Learning%20Lab_Part%201.html)
  > for information about setting up the following hypervisors.

  * [Oracle VirtualBox][VB-Homepage] or
  * [VMware Workstation Player][VWP-Homepage]

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

[Fedora Homepage][Fedora-Homepage]

[Fedora Download Webpage][Fedora-Downloads]

[Fedora 36 Download Webpage][Fedora-Downloads-36]

[Fedora 36 Workstation x86_64 Download Webpage][Fedora-Downloads-36-Workstation-x86_64]

[Fedora 36 Documentation][Fedora-Documentation-36]

[Fedora Documentation][Fedora-Documentation]

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

[Fedora-Homepage]: <https://getfedora.org/> "Fedora Homepage"

[Fedora-Downloads]: <https://getfedora.org/en/workstation/download/> "Fedora Download Webpage"

[Fedora-Downloads-36]: <https://download.fedoraproject.org/pub/fedora/linux/releases/36/> "Fedora 36 Download Webpage"

[Fedora-Downloads-36-Workstation-x86_64]: <https://download.fedoraproject.org/pub/fedora/linux/releases/36/Workstation/x86_64/iso/> "Fedora 36 Workstation x86_64 Download Webpage"

[Fedora-Documentation-36]: <https://docs.fedoraproject.org/en-US/fedora/f36/> "Fedora 36 Documentation"

[Fedora-Documentation]: <https://docs.fedoraproject.org/en-US/docs/> "Fedora Documentation"

[Windows10-Support]: <https://support.microsoft.com/en-us/windows?ui=en-US&rs=en-US&ad=US#WindowsVersion=Windows_10> "Microsoft Windows 10 Support Webpage"

[Windows10-EvalDownloads]: <https://www.microsoft.com/en-us/evalcenter/evaluate-windows-10-enterprise> "Microsoft Windows 10 Evaluation Downloads Webpage"

[CP-Homepage]: <https://www.uscyberpatriot.org/> "CyberPatriot Homepage"

[CX-Homepage]: <https://public.cyber.mil/> "DoD Cyber Exchange Homepage (Public)"

[CX-STIGs]: <https://public.cyber.mil/stigs/> "DoD Security Technical Implementation Guides (STIGs) Webpage [Public]"

------------------------------------
------------------------------------

General VirtualBox Virtual Machine Setup Steps
------------------------------------------------------------------------

>> :warning: **CAUTION**
>>
>> Do not complete this section if you are going to complete the [General VMware Workstation Player Virtual Machine Setup Steps](#general-vmware-workstation-player-virtual-machine-setup-steps) section.

01. [Download][Fedora-Downloads-36-Workstation-x86_64] the __Fedora 36 Workstation__ distribution ISO image file (~2GB).

02. Right-click the "Fedora-Workstation-36-1.5-x86_64-CHECKSUM" link and select the "Save link as" menu item.

03. In the file selection window, click the "Downloads" bookmark in the left pane, change the filename to `Fedora-Workstation-36-1.5-x86_64-CHECKSUM.txt`, and click the "Save" button.

    > __Note__
    >
    > The "Fedora-Workstation-36-1.5-x86_64-CHECKSUM" is a text file, so left-clicking may open it within the browser instead of downloading and saving it to the default download directory.

04. Type `powershell` in the Windows Search Bar and start a `Windows PowerShell` session.

05. Navigate to the `Downloads` directory:

    ```powershell
    # Use a tilde-prefix to automatically insert the user's home directory as the first part of the path.
    cd ~\Downloads
    ```

06. Verify that the directory has the two (2) downloaded files:

    ```powershell
    # -Include: Only show the names that match the patterns
    Get-ChildItem .\* -Include '*Fedora-Workstation*'
    ```

07. Verify the __Integrity__ of the "Fedora 36 Workstation" distribution ISO image file.

    01. Calculate the SHA-256 hash of the downloaded "Fedora 36 Workstation" distribution ISO image file:

        ```powershell
        # .Hash: Only return the hash value
        # .ToLower(): Convert the results to all lowercase
        (Get-FileHash -Algorithm SHA256 .\Fedora-Workstation-Live-x86_64-36-*.iso).Hash.ToLower()
        ```

        > __Note__
        >
        > If the `Get-FileHash` cmdlet is not available try using the `certutil` program:
        >
        > ```powershell
        > # The `certutil` application doesn't seem to accept glob patterns, so the full filename is required.
        > # The following command uses an example filename.
        > certutil -hashfile .\Fedora-Workstation-Live-x86_64-36-1.5.iso SHA256
        > ```

    02. Display the SHA-256 hash provided in the file downloaded from the "Fedora" website:

        ```powershell
        # |: Pipe the results of `Get-Content` into `Select-String`
        # -Pattern: Only return the strings that match the pattern
        # |: Pipe the results of `Select-String` into `ForEach-Object`
        # .Split: Split the string using the specified character as the field delimiter
        # [0]: Only return the first result
        Get-Content .\Fedora-Workstation-36-1.5-x86_64-CHECKSUM.txt | Select-String -Pattern 'Fedora-Workstation-Live-x86_64-36-.*.iso' | ForEach-Object { ([string]$_).Split(' ')[3] }
        ```

    03. Compare the two hashes; if they match then the __Integrity__ of the download is confirmed, else repeat the previous steps to download the file again.

08. Close the `PowerShell` window.

09. Start the "VirtualBox Graphical User Interface" application.

10. Click the "Machine" menu and select the "New..." menu item.

11. In the "Create Virtual Machine" window, fill in the "Name and operating system" form with the following information and then click the "Next >" button:
    * __Name__: WS-F36-01
    * __Machine Folder__: *leave the default*
    * __Type__: Linux
    * __Version__: Fedora (64-bit)

12. In the "Create Virtual Machine" window, type "4096" in the "Memory size" form and then click the "Next >" button.

13. In the "Create Virtual Machine" window, select the "Create a virtual hard disk now" radio button and click the "Create" button.

14. In the "Create Virtual Hard Disk" window on the "Hard disk file type" page, select the "VDI (VirtualBox Disk Image)" radio button and click the "Next >" button.

15. In the "Create Virtual Hard Disk" window on the "Storage on physical hard disk" page, select the "Dynamically allocated" radio button and click the "Next >" button.

16. In the "Create Virtual Hard Disk" window on the "File location and size" page, leave the default path, change the disk size to "64.00 GB" in the text box, and click the "Create" button.

17. In the "VirtualBox Graphical User Interface" right-click the new virtual machine and select the "Settings..." menu item.

18. In the "Settings" window, select the "Storage" section on the left column of the window.

19. In the "Settings" window, select the "Empty" entry under the "Controller: IDE" storage device in the center column of the window.

20. In the "Settings" window, click the disk icon next to the "Optical Drive" drop-down menu in the right column of the window and then select the "Choose a disk file..." menu item.

21. Select the ISO image file downloaded in Step 1 and then click the "Open" button.

22. In the "Settings" window, select the "Display" section on the left column of the window.

23. In the "Settings" window, increase the "Video Memory" to "128 MB" using the slider.

24. In the "Settings" window, check the "Enable 3D Acceleration" checkbox.

25. In the "Settings" window, select the "System" section on the left column of the window.

26. In the "Settings" window, select the "Motherboard" tab and check the "Enable EFI (special OSes only)" checkbox.

27. In the "Settings" window, select the "Processor" tab and increase the "Processor(s)" count to "2" using the slider.

28. In the "Settings" window, click the "OK" button.

29. In the "VirtualBox Graphical User Interface" right-click the new virtual machine and select the "Start" -> "Normal Start" menu item.

------------------------------------

General VMware Workstation Player Virtual Machine Setup Steps
------------------------------------------------------------------------

>> :warning: **CAUTION**
>>
>> Do not complete this section if you have already completed the [General VirtualBox Virtual Machine Setup Steps](#general-virtualbox-virtual-machine-setup-steps) section.

01. [Download][Fedora-Downloads-36-Workstation-x86_64] the __Fedora 36 Workstation__ distribution ISO image file (~2GB).

02. Right-click the "Fedora-Workstation-36-1.5-x86_64-CHECKSUM" link and select the "Save link as" menu item.

03. In the file selection window, click the "Downloads" bookmark in the left pane, change the filename to `Fedora-Workstation-36-1.5-x86_64-CHECKSUM.txt`, and click the "Save" button.

    > __Note__
    >
    > The "Fedora-Workstation-36-1.5-x86_64-CHECKSUM" is a text file, so left-clicking may open it within the browser instead of downloading and saving it to the default download directory.

04. Type `powershell` in the Windows Search Bar and start a `Windows PowerShell` session.

05. Navigate to the `Downloads` directory:

    ```powershell
    # Use a tilde-prefix to automatically insert the user's home directory as the first part of the path.
    cd ~\Downloads
    ```

06. Verify that the directory has the two (2) downloaded files:

    ```powershell
    # -Include: Only show the names that match the patterns
    Get-ChildItem .\* -Include '*Fedora-Workstation*'
    ```

07. Verify the __Integrity__ of the "Fedora 36 Workstation" distribution ISO image file.

    01. Calculate the SHA-256 hash of the downloaded "Fedora 36 Workstation" distribution ISO image file:

        ```powershell
        # .Hash: Only return the hash value
        # .ToLower(): Convert the results to all lowercase
        (Get-FileHash -Algorithm SHA256 .\Fedora-Workstation-Live-x86_64-36-*.iso).Hash.ToLower()
        ```

        > __Note__
        >
        > If the `Get-FileHash` cmdlet is not available try using the `certutil` program:
        >
        > ```powershell
        > # The `certutil` application doesn't seem to accept glob patterns, so the full filename is required.
        > # The following command uses an example filename.
        > certutil -hashfile .\Fedora-Workstation-Live-x86_64-36-1.5.iso SHA256
        > ```

    02. Display the SHA-256 hash provided in the file downloaded from the "Fedora" website:

        ```powershell
        # |: Pipe the results of `Get-Content` into `Select-String`
        # -Pattern: Only return the strings that match the pattern
        # |: Pipe the results of `Select-String` into `ForEach-Object`
        # .Split: Split the string using the specified character as the field delimiter
        # [0]: Only return the first result
        Get-Content .\Fedora-Workstation-36-1.5-x86_64-CHECKSUM.txt | Select-String -Pattern 'Fedora-Workstation-Live-x86_64-36-.*.iso' | ForEach-Object { ([string]$_).Split(' ')[3] }
        ```

    03. Compare the two hashes; if they match then the __Integrity__ of the download is confirmed, else repeat the previous steps to download the file again.

08. Close the `PowerShell` window.

09. Start the "VMware Workstation Player" application.

10. Click the "File" menu and select the "Create a New Virtual Machine" menu item.

11. Select the "Use ISO image" radio button.

12. Click the "Browse..." button.

13. Select the ISO image file downloaded in Step 2 and then click the "Open" button.

14. Select the "I will install the operating system later." radio button.

15. Click the "> Next" button.

16. In the "Guest Operating System" page, verify that the "Linux" radio button is checked; check the radio button, if required.

17. In the "Guest Operating System" page, verify that the "Fedora 64-bit" menu item is selected in the "Version:" menu; select the "Fedora 64-bit" menu item, if required.

18. Click the "> Next" button.

19. In the "Virtual Machine Name" page, fill in the form with the following information and then click the "> Next" button:
    * __Name__: WS-F36-01
    * __Location__: *leave the default*

20. In the "Disk Size" page, change the disk size to "64.00 GB" in the text box, select the "Split virtual disk into multiple files" radio button, and click the "> Next" button.

21. Click the "Customize Hardware..." button.

22. In the "Virtual Machine Settings" window, select the "Memory" section on the left column of the window.

23. Verify that the "Memory for this virtual machine:" text box has a "4096" value; correct the value, if required.

24. In the "Virtual Machine Settings" window, select the "Processors" section on the left column of the window.

25. Verify that the "Number of processor cores:" text box has a "2" value; correct the value, if required.

26. In the "Virtual Machine Settings" window, select the "New CD/DVD (SATA)" section on the left column of the window.

27. Verify that the "Use ISO image:" radio box is selected and that the value is set to what was selected in Step 8; correct the value, if required.

28. In the "Virtual Machine Settings" window, select the "Display" section on the left column of the window.

29. Verify that the "Accelerate 3D graphics" check box is enabled; correct the setting, if required.

30. Click the "Graphics Memory" menu and select the "128 MB" menu item.

31. Click the "Close" button.

32. Click the "> Finish" button.

33. Click the "Close" button.

34. In the "VMware Workstation Player" application right-click the new virtual machine and select the "Power On" menu item.

------------------------------------

General Guest Operating System (OS) Setup Steps
------------------------------------------------------------------------

01. After the virtual machine boots, it will present a GRUB menu.

    01. Using the arrow keys, select the "Start Fedora-Workstation-Live 36" menu item.

    02. Press the "Return" key.

02. After the guest host boots, it will launch the "Welcome to Fedora" window; click the "Install to Hard Drive" button.

    > __Note__
    >
    > If the "Welcome to Fedora" window does not automatically start, then search for and execute the "Install to Hard Drive" application.

03. In the "FEDORA 36 INSTALLATION" window on the "WELCOME TO FEDORA 36" page:

    01. Select "English" in the left pane.

    02. Select "English (United States)" in the right pane.

    03. Click the "Continue" button.

04. In the "FEDORA 36 INSTALLATION" window on the "INSTALLATION SUMMARY" page:

    01. Click the "Installation Destination" button underneath the "SYSTEM" heading.

    02. On the "INSTALLATION DESTINATION" page click the "Done" button.

        > __Notes__
        >
        > * This will not erase the hard drive on which the host operating system is installed.  This will only affect the virtual hard drive that was created for the virtual machine's 'guest operating system.
        > * A secure system should use full disk encryption, which can be done during installation by checking the "Encrypt my data." checkbox, but disk encryption should be left as a manual task so the user can further research this capability, the impacts, and how to apply the required settings after installation.

    03. Click the "Time & Date" button underneath the "LOCALIZATION" heading.

    04. Use the "Region" and "City" menus to set the timezone.

    05. Click the "Done" button.

    06. Click the  "Begin Installation" button.

05. Wait for the operating system to finish installing; when the "Complete!" message appears above the progress bar, click the "Finish Installation" button.

06. Manually reboot the Guest OS:

    01. Click the top-right corner of the "top bar" to activate the "System" menu.

    02. Select the "Power Off/Log Out" menu item.

    03. Select teh "Restart" menu item.

    04. On the "Restart" window, click the "Restart" button.

------------------------------------

General Guest Operating System (OS) First Boot Steps
------------------------------------------------------------------------

01. On first boot the system will automatically login and display the "Setup" window.  Click the "Start Setup" button at the bottom of the "Setup" window.

02. On the "Privacy" page:

    01. Turn the "Location Services" rocker to the "off" position.

    02. Turn the "Automatic Problem Reporting" rocker to the "off" position.

    03. Click the "Next" button.

03. On the "Third-Party Repositories" page:

    01. Click the "Enable Third-Party Repositories" button.

    02. Click the "Next" button.

04. On the "Online Accounts" page, click the "Skip" button.

05. On the "About You" page:

    > __Note__
    >
    > Fedora Workstation disables the "root" account by default.  The initial user is a member of the "wheel" group with "sudo" privileges.

    01. Fill out the form with the following information:
        * __Full Name__: *any descriptive name*
        * __Username__: *any descriptive name*

    02. Click the "Next" button.

06. On the "Password" page:

    01. Fill out the form with the following information:
        * __Password__: *a complex password or passphrase that is longer than 12 characters*

    02. Click the "Next" button.

07. The desktop will refresh; click the "No Thanks" button on the "Welcome to GNOME 42" window when it appears.

08. Click the "Activities" button in the upper-left corner of the "top bar" on the desktop and type "Terminal" in the search bar.

09. Click the "Terminal" icon.

10. Type `sudo hostnamectl hostname WS-F36-01` in the terminal and enter your user password when prompted.

11. Type `sudo dnf update -y` to update the system.

12. If using [VirtualBox][VB-Homepage] as the hypervisor:

    01. Type `sudo dnf list installed *virtualbox*` in the terminal.

    02. Verify that the command returns the following information:

        > __Note__
        >
        > Version numbers may be different than the ones shown below.

        ```text
        Installed Packages
        virtualbox-guest-additions.x86_64    6.1.38-1.fc36    @updates
        ```

    03. If the package is missing install it using the `sudo dnf install virtualbox-guest-additions` command.

13. If using [VMware Workstation Player][VWP-Homepage] as the hypervisor:

    01. Type `sudo dnf list installed *vmware* open-vm*` in the terminal.

    02. Verify that the command returns the following information:

        > __Note__
        >
        > Version numbers may be different than the ones shown below.

        ```text
        Installed Packages
        open-vm-tools.x86_64            12.1.0-1.fc36    @updates 
        open-vm-tools-desktop.x86_64    12.1.0-1.fc36    @updates 
        xorg-x11-drv-vmware.x86_64      13.2.1-16.fc35   @anaconda
        ```

    03. If any of the packages are missing install them using the `sudo dnf install open-vm-tools open-vm-tools-desktop xorg-x11-drv-vmware` command.

14. Resize the virtual machine window in the host operating system and the guest operating system should resize automatically.

15. Manually reboot the Guest OS:

    01. Click the top-right corner of the "top bar" to activate the "System" menu.

    02. Select the "Power Off/Log Out" menu item.

    03. Select teh "Restart" menu item.

    04. On the "Restart" window, click the "Restart" button.

16. After the Guest OS restarts, log back into the desktop:

    01. On the logon window, click the user created during the post installation "Setup" process.

    02. Enter the password set for the user during the post installation "Setup" process.

------------------------------------

General DoD Cybersecurity Software Download Steps
------------------------------------------------------------------------

> __Note__
>
> DoD does not publish STIG or SCAP content for the Fedora Linux distribution.  However, [Fedora is the upstream distribution that Red Hat uses to build Red Hat Enterprise Linux (RHEL)](https://www.redhat.com/en/topics/linux/fedora-vs-red-hat-enterprise-linux), a Linux distribution widely used within DoD and covered by DISA STIGs and SCAP content.  This section will reference the RHEL STIGs and SCAP content since versions for Fedora are not available.  Keep in mind that there are differences, some of them significant, between Fedora and RHEL, so the RHEL STIG content and SCAP results against Fedora may not be accurate, but they will be enough to help the reader gain an understanding of Fedora.  Also keep in mind that implementing the "Fix Text" section of a security control for RHEL may break a Fedora install.  The importance of using this information is to better understand Fedora.  Research content and understand the implication of setting changes prior to making them.

01. Click the "Activities" button on the "top bar" to expose the "dash" at the bottom of the screen.

02. On the "dash" bar, click the "Firefox" icon.

03. Navigate to the [DoD Cyber Exchange homepage (Public)][CX-Homepage] at the `https://public.cyber.mil` URL.

04. On the "DoD Cyber Exchange" website, click the "SRGs/STIGs" button at the top of the webpage.

05. On the left navigation bar of the "Security Technical Implementation Guides (STIGs)" webpage click the "Automation" menu and select the "Security Content Automation Protocol (SCAP)" menu item.

06. Under the "SCAP 1.2 CONTENT" section, download the "Red Hat Enterprise Linux 8 STIG Benchmark - Ver x, Rel x" package and save it to the guest OS.

07. Under the "SCAP TOOLS" section, download the "SCC 5.6 RHEL 9/Oracle Linux 9 x86 64" package and save it to the guest OS.

08. Download the "SCC 5.6 RPM GPG key" package and save it to the guest OS.

09. Right-click the "SCC x.y.z Checksum file" and select the "Save Link As..." menu item.

10. In the file selection window, click the "Downloads" bookmark in the "Places" pane and click the "Save" button.

    > __Note__
    >
    > The "SCC x.y.z Checksum file" is a text file, so left-clicking will open it within the browser instead of downloading and saving it to the default downloads directory.

11. On the left navigation bar of the "Security Technical Implementation Guides (STIGs)" webpage click the "SRG/STIG Tools and Viewing Guidance" menu item.

12. Under the "STIG Viewing Tools" section, download the "STIG Viewer x.y-Linux" package and save it to the guest OS.

13. Right-click the "STIG Viewer x.y Hashes" and select the "Save Link As..." menu item.

14. In the file selection window, click the "Downloads" bookmark in the "Places" pane and click the "Save" button.

    > __Note__
    >
    > The "STIG Viewer x.y Hashes" is a text file, so left-clicking will open it within the browser instead of downloading and saving it to the default downloads directory.

15. On the left navigation bar of the "Security Technical Implementation Guides (STIGs)" webpage click the "Document Library" menu item.

16. On the right side of the "Document Library" page under the "STIG TOPICS" heading, check the "Operating Systems" checkbox.

17. Download the "Red Hat Enterprise Linux 8 STIG - Ver x, Rel x" file.

18. On the "dash" bar, click the "Files" icon.

19. In the "Files" application, click on the "Downloads" bookmark in the left navigation pane.

20. Verify that there are two (2) text files and five (5) ZIP archives in the directory:

    > __Note__
    >
    > Version numbers may be different than the ones shown below.

    ```text
    RPM-GPG-KEY-scc-5.6.zip
    SCC_5.6_Checksums.txt
    scc-5.6_rhel9_oracle-linux9_x86_64_bundle.zip
    U_RHEL_8_V1R7_STIG_SCAP_1-2_Benchmark.zip
    U_RHEL_8_V1R8_STIG.zip
    U_STIGViewer_2-17_Hashes.txt
    U_STIGViewer_2-17_Linux.zip
    ```

21. Click the "Activities" button in the upper-left corner of the "top bar" on the desktop and type "Terminal" in the search bar.

22. Click the "Terminal" icon.

23. Navigate to the `Downloads` directory:

    ```bash
    # Use a tilde-prefix to automatically insert the user's home directory as the first part of the path.
    cd ~/Downloads
    ```

24. Verify that the directory has the same seven (7) files viewed in the `Files` application:

    ```bash
    # -1: Display results in a single column
    # -X: Sort alphabetically by entry extension
    ls -1X
    ```

25. Verify the __Integrity__ of the "SCAP Compliance Checker" ZIP archive.

    01. Calculate the SHA-256 hash of the downloaded "SCAP Compliance Checker" ZIP archive:

        ```bash
        #  |: Pipe the results from 'sha256sum' into 'cut'
        # -d: Use the specified character as the field delimiter
        # -f: Only display the first field
        sha256sum scc-*_rhel9_oracle-linux9_x86_64_bundle.zip | cut -d ' ' -f 1
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
        # -f: Only display the third field
        grep -A 1 -E 'scc-.+_rhel9_oracle-linux9_x86_64_bundle.zip' SCC_*_Checksums.txt | grep -v -E 'scc-.+_rhel9_oracle-linux9_x86_64_bundle.zip' | cut -d ' ' -f 3
        ```

    03. Compare the two hashes; if they match then the __Integrity__ of the download is confirmed, else repeat the previous steps to download the file again.

26. Verify the __Integrity__ of the "STIG Viewer" ZIP archive.

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

27. Close the "Terminal" application.

28. Close the "Files" application.

29. Close the "Firefox" browser.

------------------------------------

General DoD Cybersecurity Software Setup Steps
------------------------------------------------------------------------

01. Click the "Activities" button in the upper-left corner of the "top bar" on the desktop and type "Terminal" in the search bar.

02. Click the "Terminal" icon.

03. Type `sudo -sE` in the terminal and enter your user password when prompted to enter a privileged session.

04. Navigate to the download folder by executing the `cd Downloads` command.

05. Unzip the "STIG Viewer" application by executing the `unzip -d /opt/stigviewer 'U_STIGViewer_*_Linux.zip'` command.

06. Unzip the "SCAP Compliance Checker" RPM GPG key by executing the `unzip 'RPM-GPG-KEY-scc-*.zip'` command.

07. Install the "SCAP Compliance Checker" RPM GPG key by executing the `rpm --import RPM-GPG-KEY-scc-*[0-9]` command.

08. Unzip the "SCAP Compliance Checker" installer by executing the `unzip 'scc-*_rhel9*.zip'` command.

09. Change to the new directory by executing the `cd scc-*_rhel9*_*/` command.

10. Install the "SCAP Compliance Checker" by executing the `dnf install -y scc-*.rhel9.*_*.rpm` command.

11. Change to the installation directory by executing the `cd /opt` command.

12. Type `./scc/scc &` to start the SCAP Compliance Checker.

    01. In the "Content" section under the "SCAP" tab in the "Stream" column, check the "Linux" checkbox.

    02. Right-click the "Linux" entry and select the "Delete All" menu entry.

    03. In the "Content" section click the "Install" button.

    04. In the "Install Content" window, enable all radio buttons and click the "Select Content File(s) to Install" button.

    05. In the file selection window, click the "+ Other Locations" bookmark in the "Places" pane.

    06. Navigate to the user's "Downloads" directory.

    07. Select the "U_RHEL_8_V1R7_STIG_SCAP_1-2_Benchmark.zip" file and click the "Open" button.

    08. In the "Install Content" window, click the "Install" button.

    09. Click the "Options" menu and select the "Show Options" menu item.

    10. In the "Scanning Options" section under "SCAP Processing" check the "Run all SCAP content regardless of applicability" checkbox.

    11. Click the "Save" button.

    12. In the "Scan" section on the left of the application interface, click the "Start Scan" button.

    13. On the "dash" bar, click the "Files" icon.

    14. In the "Files" application, click on the "Home" bookmark in the left navigation pane.

    15. Double-click the "SCC" directory in the right navigation pane.

    16. Double-click the "Sessions" directory in the right navigation pane.

    17. Double-click the directory in the right navigation pane that has the recent date-timestamp of the SCC scan.

    18. Double-click the "SCC_Summary_Viewer_*.html" file to open the scan results.

    19. Click the "HTML" link under the "All Settings" column to open the "All Settings Report."

    20. Review the report to get an idea of the security posture for a default installation of [Fedora][Fedora-Homepage].

        >> :warning: **CAUTION**
        >>
        >> Do not skip over reviewing results that passed; those settings may very well be ones that have been modified on a live or competition system, so the user needs to be familiar with those in addition to the checks that failed.

13. Type `./stigviewer/STIGViewer &` to start the STIG Viewer.

    01. At the top of the application in the menu bar, click the "File" menu and select "Import STIG..." menu item.

    02. In the file selection window, click the "+ Other Locations" bookmark in the "Places" pane.

    03. Navigate to the user's "Downloads" directory.

    04. Select the "U_RHEL_8_VxRx_STIG.zip" file and click the "Open" button.

    05. In the "STIG Explorer" tab under the "STIGs" section, check the "Red Hat Enterprise Linux 8 ..." entry.

    06. At the top of the application in the menu bar, click the "Checklist" menu and select "Create Checklist - Check Marked STIG(s)" menu item.

    07. With the "*New Checklist" tab active, at the top of the application in the menu bar, click the "Import" menu and select "XCCDF Results File..." menu item.

    08. In the file selection window, click the "+ Other Locations" bookmark in the "Places" pane.

    09. Navigate to the user's "Home" directory.

    10. Double-click the "SCC" directory in the right navigation pane.

    11. Double-click the "Sessions" directory in the right navigation pane.

    12. Double-click the directory in the right navigation pane that has the recent date-timestamp of the SCC scan.

    13. Double-click the "Results" directory in the right navigation pane.

    14. Double-click the "SCAP" directory in the right navigation pane.

    15. Double-click the "XML" directory in the right navigation pane.

    16. Select the file with "XCCDF-Results" in the filename and click the "Open" button.

    17. Review all rules by selecting each in the middle pane of the "*New Checklist" tab to gain an understanding of the rule ("Rule Title"), the possible risk to the system if the rule is not followed ("Discussion" section), how to verify that the rule is implemented ("Check Text" section), and how to apply the setting(s) if absent or incorrect on the system ("Fix Text" section) for an installation of [Fedora][Fedora-Homepage].

        >> :warning: **CAUTION**
        >>
        >> * Do not skip over reviewing results that passed, as notated with the "Not a Finding" or "NF" status marker; those settings may very well be ones that have been modified on a live or competition system, so the user needs to be familiar with those in addition to the checks that failed, as notated with the "Open" or "O" status marker.
        >> * Note how many checks require a manual review, as notated with the "Not Reviewed" or "NR" status marker, and cannot be automated with generalized checks using the SCAP tool, but could be with customized scripts.

------------------------------------
