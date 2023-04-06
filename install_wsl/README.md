# Installing WSL #
Before installing linux from the microsoft Store or through the powerShell, you need to _enable WSL 2_ by Opening the Windows Features window by navigating to 

**Control Panel -> Programs -> Turn Windows feature on or off**
<p align="center">
    <img src="https://github.com/caxefaizan/developers_101/blob/main/install_wsl/images/image 1.PNG"/>
</p>

You will get a dialogue box where you need to ensure that the **Virtual Machine Platform** and **Windows Subsystem for Linux** and **Hyper -V** features are selected.
<p align="center">
    <img src="https://github.com/caxefaizan/developers_101/blob/main/install_wsl/images/image 2.PNG"/>
</p>

After clicking on the **OK** button, Windows will enable WSL 2.
**Also**, you need to enable the _Virtual Machine Platform Windows feature_ to use WSL 2. To enable, follow the given steps :

Go to:

**Windows Security -> App & Browser Control -> exploit protection -> exploit protection settings -> program settings**

 Locate  **C:\WINDOWS\System32\vmcompute.exe** in the list and expand it
 click **Edit**
 <p align="center">
    <img src="https://github.com/caxefaizan/developers_101/blob/main/install_wsl/images/image 3.PNG"/>
</p>

 Scroll down to ***Code flow guard (CFG)*** and uncheck ***Override system settings***

<p align="center">
    <img src="https://github.com/caxefaizan/developers_101/blob/main/install_wsl/images/imagex.PNG"/>
</p>

 Then open powerShell prompt as an Administrator and start vmcompute from powershell 
 
 `net start vmcompute`

Next install WSL by running the following commands:

`wsl --set-default-version 2`

`wsl –install`

<p align="center">
    <img src="https://github.com/caxefaizan/developers_101/blob/main/install_wsl/images/image 5.PNG"/>
</p>
Then proceed with the installation of ubuntu by choosing from the available distros by running 

`wsl --list --online`
<p align="center">
    <img src="https://github.com/caxefaizan/developers_101/blob/main/install_wsl/images/image 6.PNG"/>
</p>
followed by

`wsl --install -d Ubuntu-20.04` (-d is to refer to the distro name)

Once it has finished its initial setup, you will need to create a _username_ and _password_

Finally, it’s always good practice to install the latest updates with the following commands, entering your password when prompted.

`sudo apt update`

Then, 

`sudo apt full-upgrade`

Press **Y** when prompted.

## (Optional) Enable systemd ##
To enable _systemd_ you will need make a small modification to _/etc/wsl.conf_ in your Ubuntu distribution.
Run 

`sudo nano /etc/wsl.conf` 
 in ubuntu terminal to open the wsl.config file and insert the following lines:
```
[boot]
systemd=true
```
and save by pressing _ctrl+X_ and reply **y** to confirm the changes
Then restart your distro by running 

`wsl --shutdown`
in powershell and relaunching by running 

 `wsl` 
 in powershell.

*The installation is complete !*




