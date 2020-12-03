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
