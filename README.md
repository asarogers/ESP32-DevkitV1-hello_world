#Getting starting
This readme is designed to get a user teach a user how to print their first hello world from the ESP32 devkit v1 using windows OS.

#1 First, click this link [click here](https://dl.espressif.com/dl/esp-idf-tools-setup-1.2.exe) for the downloaded needed

#2 After the installation is done, click this link [click here](https://gitforwindows.org/) to download git
    if you already have git installed, you may skip this step.

#3 Please past these commands in the cmd terminal
```
cd %HOMEPATH%
mkdir esp
cd esp
git clone --recursive https://github.com/espressif/esp-idf.git
cd esp-idf
git submodule update --init
```

#4 tap the windows key, type "Edit the system environment variables"
- click on environment variabels
- under neither "User variables for user", click "New.."
- Type "IDF_PATH" into Variable name
- past "C:\esp\esp-idf" into Variable value
- return home

#5 copying hello_world from the example directory, then naming the new file hello_world. past these commands in terminal
```
 cd %HOMEPATH%\esp
 xcopy /e /i %IDF_PATH%\examples\get-started\hello_world hello_world 
```

#6 nearly done, we need to run the menuconfig command, past the following code into terminal
```
 cd %userprofile%\esp\hello_world
 idf.py menuconfig 
```

when it's done, type this into terminal
```
 clear
 idf.py build
```

#7 finally plug in the ESP32 if you have not already. 
- tap windows key
- type "Device Manager"
- click on Ports
- search for the " USB to UART Bridge"
- inside the the parentheses, you should the port. Example: "Silicon LAbs CP210x USB to UART Bridge(COM8)"
my port is COM8

Now run idf.py -p (PORT) flash monitor in the terminal.
Example: idf.py -p COM8 flash monitor

>NOTE: some users will need to tap the upload button on the right side of the board
It will print hello world 4 
