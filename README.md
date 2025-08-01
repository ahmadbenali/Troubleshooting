# Troubleshooting
In this repository I add all the problems I have faced and solved.


## SDDM theme

if some theme give you an error, try this before:
`sddm-greeter  --test-mode --theme /usr/share/sddm/themes/<namefile>`

## install Postman

- Extract the file on home
- open console and use `./Postman` 

## message "support for password authentication was removed.

- Go to Settings -> Developer Sittings -> Personal access tokens -> tokens(classic) ->generate new token(classic)
- copy the token and put it in git remote set-url origin https://<Token>@github.com/ahmadbenali/<nameoofrepo> 
- and then paste it in were you are working and continue were your face the problem

## list of command for creating swap file or resize it

- first switch off swap
- sudo swapoff --show

- sudo nano /etc/fstab
- sudo rm /swapfile
- sudo swapon /dev/nvme1n1p4
- sudo swapon --show
- sudo free -h
- sudo update-grub
- sudo update-initramfs -u

## App Crushing while loading in Linux

If you trying to open App but crush during loading process , i have the solution for you
this problem apper because the app is deadlock so you have to kill it and reopen it.

to find if the process is working in background
pgrep <process_name> 
this will give you an PID number for this process

> [!NOTE]
> put the command without ( < > )

to kill process
Kill <with PID>
this will kill the process

> [!NOTE]
> put the command without ( < > )

and now you can open it and will work .

## Fixed Memory usage for windows 11

If you are experiencing high memory usage in Windows 11 without a virus, I have a solution for you.

### Method 1. Do clean boot
A “clean boot” starts Windows with a minimal set of drivers and startup programs, so that you can determine whether a background program is interfering with your game or program.

- In the search box on the taskbar, type msconfig and select System Configuration from the results.

- On the Services tab of System Configuration, select Hide all Microsoft services, and then select Disable all.

- On the Startup tab of System Configuration, select Open Task Manager.

- Under Startup in Task Manager, for each startup item, select the item and then select Disable.

- Close Task Manager.

- On the Startup tab of System Configuration, select OK. When you restart the computer, it's in a clean boot environment.

### Method 2. Run memory diagnostic tool

- Memory diagnostic tool is a RAM test to check if there is any issues with RAM.

- Press Windows key + R then type in mdsched.exe hit OK then restart the device.

### Method 3. Set the PC to best performance:

- Press windows key + Pause/Break (or go to file explorer and right click This PC and click properties)

- click on Advanced system settings> Under Performance click settings> Click Adjust for best performance and click OK

> [!IMPORTANT]
> this will reduce all appearance settings you have but will optimize the performance of the PC.

### Method 4. Chris titus tool (Recommended one)

- open terminal using admin mode
- `iwr -useb https://christitus.com/win | iex`
- will open a tool
- choes whatever you want to download (IF YOU JUST NOW INSTALL WINDWOS)
- if you have a long time with window,go to tweaks then stander
- chose debloat edge and whatever you want
- finally, RUN tweaks and restart the pc
> [!NOTE]
> for more info [Windows Utility Improved for 2024](https://youtu.be/5_AaHXrelTE?si=Cldx7EfRuN8Zf1-3)

## Fix Externally Managed Environment Pip Error in Python in Debian
Encountering the “externally-managed-environment” error when trying to install Python packages with pip can be a common hurdle, especially on Debian-based systems like Ubuntu. This error, often appearing from Python 3.11 onwards, signifies that your system’s package manager (like apt) is responsible for managing Python packages to prevent conflicts and ensure system stability.

Why Does This Happen?
Distributions like Debian and Ubuntu manage Python installations and their associated libraries to maintain consistency and avoid dependency hell. They package Python modules, and when pip attempts to install a package system-wide, it might overwrite or conflict with versions managed by apt. This can lead to unexpected behavior or break other system applications that rely on specific Python library versions.

### Solution One
Create a virtual environment:
1. python3 -m venv my-project-env
2. source my-project-env/bin/activate
3. and install with pip

### Solution Two
Employ pipx for Command-Line Applications:
1. sudo apt install pipx
2. pipx install some-python-application






