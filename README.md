<img src="https://github.com/fixitgearware/tiksos/blob/main/fixitgearwaretiksosbg.png">
<h1>TIKSOS:Troubleshooting AND Installing Kali-linux SoftwareS.</h1>
<h2>A curation of Kali-Linux software installations and problems troubleshooting.</h2>


|         NAME      |          Problem Type            |                           Description                                     |
|-------------------|----------------------------------|---------------------------------------------------------------------------|
|    DEBUGGING PYTHON PROBLEMS IN KALI-LINUX VIRTUAL BOX                         |     software installation   | 1. Run the code below:
sudo apt-get install python3 (This will install the python afresh) 2.  Next to ensure we can locate python we need to type the command below: sudo apt install python-is-python3
(This will install the library which we can use to use the following command below. Also, this command fixes everything including the location of other tools in our Kali-virtual box).
3. To locate python in our VirtualBox, and ensure everything is accurately installed, we can type the following command below:

type python
type python2
type pytho3
command -v python
type -a python |
               


