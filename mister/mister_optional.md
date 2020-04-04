### Optional Configuration

#### Setting up WIFI
Connect your wifi device to USB.
Inside the Scripts menu, select 'wifi'
Select your SSID from the menu and enter your wifi password.
That's it!
___

#### Enable Samba file sharing
[Official wiki page](https://github.com/MiSTer-devel/Main_MiSTer/wiki/Samba)

By default Samba service is not active.
You need to rename /media/fat/linux/_samba.sh to linux/samba.sh, then edit this file if you need specific user name and password
Default username = root | password = 1
Reboot the MiSTer.
You can access the MiSTer either by IP address or by name \\MiSTer (or \\mister - case insensitive).

If you need to add any additional folders to Samba (eg for additional drives) you will need to ssh into the MiSTer device
Using your ssh client, connect to the MiSTer device using the default username and password.
Type the following command :-

    nano /etc/samba/smb.conf

At the bottom of the file, add the following lines :-

    [usb]
      path = /media/usb0
      public = yes
      writeable = yes
      printable = no

Press Ctrl+X and then Y to save
At the command prompt, type 'reboot'

The MiSTer will now restart and the new share should be visible.