# Homelab Resources

- https://roadtohomelab.blog/homelab-homepage-guide
- Docker Tutorial https://docker-curriculum.com/

## Homelab - laptop keep from going asleep


If you are using a old laptop here is how to disable entering the sleep mode I had to edit the /etc/systemd/logind.conf file and modify the line:
  

#HandleLidSwitch=suspend

to

HandleLidSwitch=ignore

Additionally, ensure that the file also has this line:

LidSwitchIgnoreInhibited=no

Then restart the OS via:

sudo service systemd-logind restart