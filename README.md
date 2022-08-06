# UTM_Code-Server
> Run Visual Studio Code with UTM

# Requirements Before installation
1) Please install [UTM](https://github.com/utmapp/UTM)
2) Import Debian [Pre-Installed VM](https://mac.getutm.app/gallery/debian-10-4-minimal) to UTM.

# 1. Modifying Debian VM

1. RAM) More Ram for the VM will increase the speed. Hence, increase the RAM to 2GB with 1.5GB of JIT Cache.
If you have a bigger RAM on your device, you may try increasing RAM till 4GBs. 
Try with ```Increased-Memory-Limit``` for who have Apple Developer Account (Paid)

2. Cores, CPUs) Go to the ```System```of your Debian VM. 
Now, type '4' to the CPU number, and toggle on ```Force Multicore```. This will speed up the VM.


# 2. Port Forwarding the VM

Go to your Debian VM's Configuration and click ```Network```. 
You will be able to see ```Portforward```option. Click it, and open it.
Now, on ```Guest Port```, type 8080 in. 
On ```Host Port```, type 22222. 
Now save the changes and start the VM.

# 3. Installing Code-Server.

Start the VM in Console mode, and you will see some commmand lines and GRUB Boot Loader.
Select the First One on the GRUB Bootloader and it will continue booting in to Debian.

You will reach to login page of Debian.
Pre-Configured VM's Default Users are ```debian``` and ```root```.

Password for ```debian``` is ```debian```

Password for ```root``` is ```password```


We will use the debian account for the ```code-server```.
Because Debian 10.4 released in 2020, the packages need to be updated.
So, we will update the packagaes with the command:

```sudo apt update```

This will ask for our password, just type ```debian``` in.

After update is done, we need to install ```curl```. 
install it with ```sudo apt install curl```

now, to install ```code-server```

Type ```curl -fsSL https://code-server.dev/install.sh | sh``` in.
Soon it will be installed.

# 4. Editing code-server

Because we want ```code-server``` to be hosted on our Device, we need to edit some files.

```nano ~/.config/code-server/config.yaml``` to enter the nano editer.

You will see something like this:

```
bind-addr: 127.0.0.1:8080
auth: password
password: Your_Own_Password
cert: false
```

Now, you're gonna change ```127.0.0.1:8080``` to ```0.0.0.0:8080```.
Also, make sure to change your password!

then save the file and exit the nano editer.

# 5. Run code-server

After You did everything as I instructed, start code-server with the command:

```code-server```

Now, You're going to use split view. Open Safari or Chrome or whatever browser you want, and Split-view it

next the VM. Make sure the VM 1/3 of the screen and Browser is 2/3 of the screen! 

Now, go to ```localhost:22222``` in the Browser.

It will open the code-server login screen. Type in your password.

There you go! Now you can code-server without a conputer!
