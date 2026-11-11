# NETWORKWALKS-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP
Building an isolated virtual lab for penetration testing and ethical hacking practice
INSTALLING ORACLE VIRTUALBOX
AND KALI LINUX

A step-by-step practical guide with illustrative screenshots

Purpose: install Oracle VirtualBox on a Windows computer, then create a Kali Linux virtual machine using either the pre-built VirtualBox image (recommended for beginners) or the installer ISO.

IMPORTANT: The screenshots in this document are illustrative diagrams, not live captures from your computer. Menu names and appearance can vary by version.

1. What you need

A Windows 10/11 computer with hardware virtualization (Intel VT-x or AMD-V) enabled.

An internet connection and sufficient free disk space.

At least 8 GB host RAM is recommended for a comfortable learning setup; allocate only part of it to the VM.

Oracle VirtualBox for Windows hosts.

Kali Linux 64-bit VirtualBox image (recommended) or Kali installer ISO.

2. Download VirtualBox

1. Open the official VirtualBox downloads page: https://www.virtualbox.org/wiki/Downloads

2. Under platform packages, choose Windows hosts.

3. Run the downloaded installer. Accept the licence and keep the default features unless you have a specific reason to change them.

4. Windows may briefly disconnect network connections while VirtualBox network components are installed. Save your work first.

5. Complete setup and open Oracle VM VirtualBox Manager.

Optional: install the Extension Pack only if you need its additional features. Download it from the same official page and ensure its version matches your installed VirtualBox version.

3. Download Kali Linux

Use the official Kali download page: https://www.kali.org/get-kali/

Recommended method: pre-built VirtualBox image

1. On the Kali page, find the Virtual Machines section and select the VirtualBox image for 64-bit AMD64 systems.

2. Download the archive (commonly .7z). The exact filename and current release number change over time.

3. Install 7-Zip from https://www.7-zip.org/ if Windows cannot extract the archive.

4. Right-click the downloaded .7z archive → 7-Zip → Extract to a new folder.

5. Keep the extracted .vbox configuration file and its associated .vdi virtual disk together in that folder.

Alternative method: installer ISO

Download the Installer image from the official Kali page. In VirtualBox, create a new VM, attach the ISO as its optical disk, boot it, and follow the Kali installer. This method takes longer and requires manual disk and user setup.

4. Add the pre-built Kali machine to VirtualBox

Important distinction: use Add to register an existing .vbox machine. New creates a fresh virtual machine. Import is normally used for .ova/.ovf appliances.

1. Open VirtualBox Manager.

2. Choose Add (or Machine → Add, depending on the version).

3. Browse to the extracted Kali folder.

4. Select the file ending in .vbox, then click Open.

5. Kali Linux should appear in the machine list. Do not move or separate the .vbox and .vdi files after adding the machine.



5. Check virtual machine settings

Select Kali in the VirtualBox list → Settings. The following are starting points, not mandatory values:

Setting

Suggested starting point

Base memory (RAM)

4096 MB if the host has 8 GB or more; use less if necessary

Processors

2 virtual CPUs, while leaving resources for Windows

Display video memory

128 MB if available

Network

NAT for ordinary internet access

Virtual disk

Keep the supplied disk attached; do not create a second disk unless needed

If VirtualBox reports that hardware virtualization is unavailable, enable Intel VT-x/Intel Virtualization Technology or AMD-V/SVM in the computer's BIOS/UEFI. The exact menu differs by computer manufacturer.



6. Start Kali and sign in

1. Select Kali Linux in VirtualBox Manager.

2. Click Start and wait for the boot process.

3. At the login screen, use the username and password specified by the official Kali VirtualBox image download notes. Some pre-built images have used kali / kali as defaults, but do not assume this applies to every release.

4. If login fails, check the current image documentation and the download page; do not repeatedly guess credentials.



7. First steps after logging in

Open Terminal and run these commands one at a time:

sudo apt update

sudo apt full-upgrade

The first command refreshes the package index. The second upgrades installed packages. Review prompts before confirming. A large upgrade may take time and require a reliable internet connection.

Change any default password before using the VM beyond a temporary lab. If your account is named kali, use the passwd command and follow the prompts.

passwd



8. Basic troubleshooting

No bootable medium / ISO not selected: If using the ISO method, attach the Kali ISO under Settings → Storage. If using the pre-built image, confirm the virtual hard disk is attached and the VM is the imported .vbox machine.

The .vbox file is not visible: Extract the .7z archive first. Browse into the extracted folder, not the compressed archive.

VirtualBox asks to choose New / Import / Add: Choose Add for an existing .vbox file. Choose Import only for an .ova/.ovf appliance. Choose New only when building a VM from scratch.

64-bit guest option missing or VM will not start: Check that hardware virtualization is enabled in BIOS/UEFI and that host security/hypervisor settings are not conflicting. Consult the VirtualBox manual for your version.

Black screen or very slow display: Power off the VM and review Settings → Display. Try the default graphics controller and 128 MB video memory; change one setting at a time.

No internet in Kali: Check Settings → Network → Adapter 1 is enabled and attached to NAT. Inside Kali, check the network connection.

9. Safe and responsible use

Kali is a security testing distribution. Use scanning, exploitation, password testing and other security tools only on systems you own or have explicit written permission to assess. For practice, use intentionally vulnerable training machines in an isolated lab network. Do not test public IP addresses, workplace systems or other people's devices without authorization.

Take a VirtualBox snapshot before major changes: select the VM → Snapshots → Take. A snapshot can help you return to a known-good state.

10. Official references

VirtualBox downloads: https://www.virtualbox.org/wiki/Downloads

VirtualBox user manual: https://www.virtualbox.org/manual/

Kali Linux downloads: https://www.kali.org/get-kali/

Kali documentation: https://www.kali.org/docs/

7-Zip: https://www.7-zip.org/
