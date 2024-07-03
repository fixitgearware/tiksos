<img src="https://github.com/fixitgearware/tiksos/blob/main/fixitgearwaretiksosbg.png">
<h1>TIKSOS:Troubleshooting AND Installing Kali-linux SoftwareS.</h1>
<h2>A curation of Kali-Linux software installations and problems troubleshooting.</h2>


|         NAME      |          Problem Type            |     Troubleshooting Description & Solutions                               |
|-------------------|----------------------------------|---------------------------------------------------------------------------|
|  <strong>Python</strong>  |     whereis python not working.  | 1. Run the code below: <br><strong>sudo apt-get install python3</strong> (This will install the python afresh)<br> 2. Next to ensure we can locate python we need to type the command below:<br><strong>sudo apt install python-is-python3.</strong><br>(This will install the library which we can use to use the following command below. Also, this command fixes everything including the location of other tools in our Kali-virtual box).<br>3. To locate python in our VirtualBox, and ensure everything is accurately installed, we can type the following command below:<br><strong>type python</strong><br><strong>type python2</strong><br><strong>type python3</strong><br><strong>command -v python</strong><br><strong>type -a python</strong>|
|  <strong>Burpsuite</strong>  |    Installation.  | 1. Type the command below, to check for the version of installed Burpsuite.<br><strong>Burpsuite -v</strong><br>[fires up burpsuite, and shows which version]<br>2.Head to Portswigger academy, to download the <strong>*.jar</strong> file for Burpsuite into your computer.<br>3. Navigate to Downloads on your Kali.Using the <strong>“cd Downloads”</strong> command, in your terminal.<br>4.From the download directory, type the command below, to rename the <strong>*.jar</strong>file of the version of Burpsuite downloaded. <br><strong> sudo mv burpsuite_community_v2023.11.1.3.jar burpsuite</strong><br> This will rename “burpsuite_community_v2023.11.1.3.jar” to “Burpsuite”<br>5. Next while still in the download directory, run the command below to move the latest burpsuite <strong>*.jar</strong> file, to the bin directory:<br><strong>chmod +x burpsuite && sudo mv burpsuite/usr/bin/burpsuite</strong><br>After this has been done, launch your burpsuite.|
|  <strong>VirtualBox </strong>  |     shared folder issues and Drag-Drop Between Host Machine and VBox.  | 1. Go to oracle website url below, and download latest VirtualBox file and guest addition e.g. this is version 7.0.14:<br> https://download.virtualbox.org/virtualbox/7.0.14/<br> 2. shutdown the kali-Linux running on the VirtualBox machine, and then close the VirtualBox machine to install the latest version.<br>3. Next download & install the VirtualBox extension pack latest version, by visiting the link below.<br>:https://download.virtualbox.org/virtualbox/7.0.14/Oracle_VM_VirtualBox_Extension_Pack-7.0.14.vbox-extpack <br><strong>Note the version would vary, this is just a demo example.</strong><br>4. Launch your VirtualBox machine, and select the specific machine having this issue, and go to settings, to add the <strong>"virtualbox guest addition"</strong>, to the boot-sector. Here we are assuming your VirtualBox, is running multiple VM’s. <br>5. Start the machine, and then login with your credentials. <br>6. Upon login, you will see the <strong>CD icon (Disk Icon)</strong>, click on it, to view the entire content or files. <br>7.Then scroll down to the end, and <strong>right click</strong>, select <strong>“open-in-terminal”</strong><br>8. Next type the command below, to list all the files: <br><strong>ls -la</strong><br> 9. Look for the file name <strong>"VboxLinuxAdditions.run"</strong>and copy it.<br>10. Next we need to give permissions to the file, by typing the command below:<br><strong>chmod +x VBoxLinuxAdditions.run</strong><br>11. Then finally to install VirtualBox guest addition, we run the command below:<br><strong> sudo sh ./VboxLinuxAdditions.run</strong><br>12.Reboot system and Login. That's all.|
|  <strong>VirtualBox </strong>  |     Error notification popping up after installing Guest Additions.  |1. Type the command below to troubleshoot and reboot the Kali-Linux OS <br><strong>sudo apt-get update && sudo apt-get install -y virtualbox-guest-* && reboot</strong><br>2. Upon reboot, type the command below in the terminal.<br><strong>sudo apt-get install virtualbox-guest-dkms</strong><br><br><strong>NOTE: The drag and drop functionality only work for older version of virtualbox machine. Since the latest update release, the drag and drop between HOST and GUEST machine, has been discontinued. Virtualbox now supports only shared folder functionality.</strong>|
|  <strong>Kali-Linux</strong>  |     Header Issues.  |<strong><ins>Error Message Should Look as Shown Below:</ins><br></strong><br><br>dpkg:dependency problems prevent configuration of linux-headers-amd64:<br>linux-headers-amd64 depends on linux-headers-6.5.0-kali3-amd64 (= 6.5.6-1kali1)<br>; however:<br>Package <strong><ins>linux-headers-6.5.0-kali3-amd64</ins></strong> is not configured yet.<br><br>dpkg: error processing package linux-headers-amd64 (--configure):<br>dependency problems - leaving unconfigured<br>Processing triggers for kali-menu (2023.4.6) ...<br>Processing triggers for man-db (2.12.0-3) ...<br>Errors were encountered while processing:<br>linux-image-6.5.0-kali3-amd64<br>linux-headers-6.5.0-kali3-amd64<br>linux-image-amd64<br>linux-headers-amd64<br>E: Sub-process /usr/bin/dpkg returned an error code (1)<br><br><strong>NOTE: Take note of the highlighted part, as this is important in the next stage of troubleshooting.</strong><br><br>1. Run the command below to remove the linux header version.<br><strong>sudo rm -rf /usr/src/linux-headers-version*</strong><br>2. Then run the command below to remove the specific header version, as we highlighted in the header error message above:<br><strong>sudo rm -rf /usr/src/linux-headers-6.5.0-kali3-amd64*</strong><br>3.  Next we need to force install headers, by running the command below:<br><strong>sudo apt-get -f install </strong><br>There would probably be an error message as shown below:<br><strong><ins>dkms: autoinstall for kernel 6.5.0-kali3-amd64 was skipped since the kernel headers for this kernel do not seem to be installed.</ins></strong><br>4. Then run the command below, to fix that issue:<br><strong>sudo apt autoremove</strong><br>That is all.|
|  <strong>Installing GO</strong>  |     Installing Go Lang in VirtualBox Kali-Linux or Direct Kali-Linux.  | 1. Visit the website  https://go.dev/dl/ and download the <strong>*. amd64 linux</strong> latest version of the go lang program. For example, your file name, should be as shown below, assuming we are downloading <strong>version 1.22.4.</strong> It is important to lookout for amd64 and of course for linux:<br><strong>go1.22.4.linux-amd64.tar.gz</strong><br>2. Navigate to your download’s directory, using the command below. By default, linux saves all downloaded files in the download’s directory. However, if you have a custom directory, where you save your download files, then cd into that directory:<br><strong>cd Downloads</strong><br>3. Untar or unzip the file, using the command below.<br><strong>tar -xvf <go-file-version></strong><br>for example: <strong>tar -xvf go1.22.4.linux-amd64.tar.gz</strong><br>4. Next we move the unzip <strong>“go”</strong> directory which contains the go package to the <strong>/usr/local</strong>directory by running the command below:<br><strong>sudo mv go /usr/local</strong><br>5. Next navigate to the <strong>/usr/local</strong> directory, using the cd command as shown below:<br><strong>cd /usr/local</strong><br>6.To export go path, then type the command below:<br><strong>export PATH=$PATH:/usr/local/go/bin</strong><br>7. Next refresh the shell database, by using any of the two commands below. i.e. for Bash, or Zsh:<br><strong>source ~/.bashrc</strong><br><strong>source ~/.zshrc</strong><br>8. To check the version of Go installed, type any of the commands below. Reason sometimes go needs to run as <strong>GROOT</strong>, so which ever one of the two commands below, that works should be what command you should be using to access Go functionalities:<br><strong>A.  go version</strong><br><strong>B.  GOROOT=/usr/local/go go version</strong>|
               


