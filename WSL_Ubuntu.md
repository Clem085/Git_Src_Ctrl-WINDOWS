Open Command Prompt
Enter the Following Command
```cmd
wsl.exe --install Ubuntu-24.04
```

Error:
```cmd
Downloading: Ubuntu 24.04 LTS
The connection with the server was reset
Error code: Wsl/InstallDistro/0x80072eff
```

Solution:
For some reason, this connection is blocked on the LAN Network. To get around it, I disconnected the computer from Ethernet, and connected it to my phone's hotspot. 

Ensure your phone is NOT connected to the Guest WiFi, and that cellular data is being used for Network and Hotspot connectivity. 

After Resolving the Error, reenter the command
```cmd
wsl.exe --install Ubuntu-24.04
```

Expected Output:
```cmd
Downloading: Ubuntu 24.04 LTS
Installing: Ubuntu 24.04 LTS
Distribution successfully installed. It can be launched via 'wsl.exe -d Ubuntu-24.04'
Launching Ubuntu-24.04...
Provisioning the new WSL instance Ubuntu-24.04
This might take a while...
```

This output will be followed by several prompts to configure the system. After answering each prompt, press `enter` to complete you answer:

**Create a default Unix user account:** `<username>`
> I believe that the name of the computer's current user is input here by default. I am unsure how or if this name can be modified

**New password:** `<password>`

**Retype new password:** `<password>`
> For Both Password Prompts, your keystrokes will be hidden. (Although you cannot see it, you are typing) This is a security feature built into almost every linux distro available.

Expected Output:
```cmd
passwd: password updated successfully
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.
```

