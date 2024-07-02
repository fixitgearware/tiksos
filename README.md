<img src="https://github.com/fixitgearware/tiksos/blob/main/fixitgearwaretiksosbg.png">
<h1>TIKSOS:Troubleshooting AND Installing Kali-linux SoftwareS.</h1>
<h2>A curation of Kali-Linux software installations and problems troubleshooting.</h2>


|         NAME      |          Problem Type            |                           Description                                     |
|-------------------|----------------------------------|---------------------------------------------------------------------------|
|  <strong>python</strong>  |     whereis python not working.  | 1. Run the code below: <br><strong>sudo apt-get install python3</strong> (This will install the python afresh)<br> 2. Next to ensure we can locate python we need to type the command below:<br><strong>sudo apt install python-is-python3.</strong><br>(This will install the library which we can use to use the following command below. Also, this command fixes everything including the location of other tools in our Kali-virtual box).<br>3. To locate python in our VirtualBox, and ensure everything is accurately installed, we can type the following command below:<br><strong>type python</strong><br><strong>type python2</strong><br><strong>type python3</strong><br><strong>command -v python</strong><br><strong>type -a python</strong>|
|  <strong>Burpsuite</strong>  |    Installation.  | 1. Type the command below, to check for the version of installed Burpsuite.<br><strong>Burpsuite -v</strong><br>[fires up burpsuite, and shows which version]<br> 2. NHead to Portswigger academy, to download the *.jar file for Burpsuite into your computer.<br>3. To locate python in our VirtualBox, and ensure everything is accurately installed, we can type the following command below:<br><strong>type python</strong><br><strong>type python2</strong><br><strong>type python3</strong><br><strong>command -v python</strong><br><strong>type -a python</strong>|
               


