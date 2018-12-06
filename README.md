# WiFi-connection-with-no-GUI-env

*Sometimes we may use pure linux command mode environment to connect to internet and incur some problems, you can read the following step to try to resolve these problems.

*Wifi setup:  

-Install driver . 

Netgear A6210 wifi driver, ref: https://github.com/kaduke/Netgear-A6210 . 

  (1) git clone https://github.com/kaduke/Netgear-A6210 . 

  (2) cd Netgear-A6210 . 

  (3) make . 

  (4) sudo make install . 


-install wpa_supplicant(if needed) . 

sudo apt-get install wpasupplicant

-setup ssid/password via wpa_passphrase and save to config file . 

  cmd:sudo wpa_passphrase ssid password . 
  sudo wpa_passphrase Mobile Lightsail@350 > /home/rich/Mobile.conf . 

-connect . 

  sudo wpa_supplicant -Dn80211 -iwlan0 -c/home/rich/Mobile.conf -C

FAQ:
1. connect fail.

    (1) maybe network manager want to connect to AP too, please stop network manager if exits.

    sudo /etc/init.d/network-manager stop . 
