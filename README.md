# fixing-neo4j-issue-for-bloodhound

### Error:
[Java error](https://imgur.com/Fl3rPPI)

1. Install JDK 11 by registering to oracle and downloading the installer from this link: https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html
2. If errors still persist after installing java, fix it by modifying `Get-Java.ps1` powershell script which looks for the Java version, and point the $javaPath variable to the JDK 11 directory.

`$javaPath = 'C:\Program Files\Java\jdk-11.x.x\'`

Should be fixed now.

# fixing LinkedIt tool install errors

1. Remove "pkg-resources==0.0.0" from requirements.txt
2. pip install -r requirements.txt
2. pip2.7 install thready

# fixing control+left or right arrow to go back a word iTerm2 for MacOS

for zsh:

1. edit ~/.zshrc
2. add `bindkey -e; bindkey '\e\e[C' forward-word; bindkey '\e\e[D' backward-word`
3. option+arrow works

# Bullets not appearing (Microsoft Word MacOS)
https://superuser.com/questions/1143247/word-2013-bullets-dont-appear-when-creating-bullet-list
```
In case anyone else is having the issue (I had it with Word 2019 Office 365 for Mac): I realised that for me the problem was being caused by page breaks. If I hit enter then I could create a bullet list on the line above, just not for the line that included the page break. I hope this helps!
```

# Copy paste not working from host to guest (VMWare Fusion)
Restart vm-tools
```
# restart vm-tools
```

# Office 365 (Your message wasn't delivered because the recipient's email provider rejected it.)

Access https://protection.office.com/antispam

Login with email@email.com
Click on Expand Outbound spam filter policy and click Edit policy.
Click on Expand Automatic forwarding and set the setting to On.
Click Save.

# Apache webserver - permission issues writing to a file
```
# chown -Rf www-data:www-data test/*
```

# Apache webserver - don't remove "others" read permission to your folder 
```
# chmod -R o-rwx directory/
```

# Error: Skipping bootstrap because certbot-auto is deprecated on this system. (When installing SSL thru Let's Encrypt)
https://snapcraft.io/docs/installing-snap-on-kali

https://certbot.eff.org/lets-encrypt/pip-apache

# Error: Proxychains nmap
Error: ```nmap: netutil.cc:1319: int collect_dnet_interfaces(const intf_entry*, void*): Assertion `rc == 0' failed.```

Solution: Uncomment "proxy_dns" from /etc/proxychains.conf then run:
```
proxychains nmap -Pn -sT -p 1433 -sC -sV 10.10.1.2 
```

# Error: E:\Tools\Creds\helpers\prac\execute_assembly_bin.nim(15, 13) Error: cannot open file: winim/clr
Fix: https://github.com/khchen/winim
```
PS E:\Tools\Creds\helpers\prac> nimble.exe install winim
```
# CrackMapExec segmentation fault when generating SSL certificate
```
openssl req -new -x509 -keyout ~/.cme/cme.pem -out ~/.cme/cme.pem -days 365 -nodes -subj "/C=US"
```

# Virtualbox VM freezing top left quarter
https://askubuntu.com/questions/1014172/virtualbox-unresponsive-area-on-desktop
For me killing instances ran with --draganddrop parameter restored the functionality of that area.

You can open terminal using keyboard combination of ctrl+alt+t, and type:
```
ps aux www | grep VBoxClient --
```
to look for the process ID (PID) then kill it with
```
kill -9 PID
```
Alternatively `pkill VBoxClient` might do the trick.

After this to restore drag and drop support you can run
```
VBoxClient-all
```

# Enable shared folder VMWare workstation 

https://superuser.com/questions/588304/no-mnt-hgfs-in-ubuntu-guest-under-vmware-fusion/1323483
```
sudo mkdir /mnt/hgfs
```
Use the above command first, followed by the following:
```
sudo /usr/bin/vmhgfs-fuse .host:/ /mnt/hgfs -o subtype=vmhgfs-fuse,allow_other
```

# Copy paste not working after Kali upgrade (VMWare PRO)

https://askubuntu.com/questions/691585/copy-paste-and-dragdrop-not-working-in-vmware-machine-with-ubuntu

# TMUX autoscroll when highlighting in terminal
https://www.youtube.com/watch?v=XR5_hPT5i2g
```
set -g terminal-overrides 'xterm*:smcup@:rmcup@'
```

# Turn of Kali Linux or any debian's loud beep

` sudo xset b off`

# MACOS terminal skip a word using ctrl+ right or left arrow keys

https://apple.stackexchange.com/questions/52147/control-arrow-key-to-jump-to-the-next-word

Uncheck the two boxes:

![image](https://user-images.githubusercontent.com/66387143/149575874-929e4694-5a27-428d-b1c8-9e4dce4e7a88.png)

# Configuring Flameshot key for Kali

https://askubuntu.com/questions/1036473/how-to-change-screenshot-application-to-flameshot-on-ubuntu-18-04

1. Search "keyboard" and go to "Application Shortcuts"
2. +Add a shortcut
3. Command: /usr/bin/flameshot gui
4. Select a shortcut by pressing keys
