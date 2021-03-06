# EAZY
Shell script to install a [EASY Masternode](https://www.eazynode.pro/) on a Linux server running Ubuntu 14.04 or 16.04. Use it on your own risk.


## Installation:

When logged into your Masternode VPS, copy and paste the following commands to install the Masternode client:
```
git clone https://github.com/EAZYCommunityNode/Eazy-install.git
cd Eazy-install
bash eazy-install.sh
```
***
## Config file for Masternode VPS (If you are having trouble connecting to the nodes):

1. Run command **systemctl stop ezy** to stop masternode.
2. Run **cd .ezy** this will show you all the files related to ezy. Locate **ezy.conf**.
3. Type in **nano ezy.conf**
4. After the line where your masternodeprivkey is create a new line and place the following in.
```
addnode=116.203.60.112
addnode=159.69.126.178
addnode=5.8.101.60
addnode=116.202.26.195
addnode=95.217.85.170
addnode=149.28.161.29
addnode=80.211.53.110
addnode=80.211.10.201
addnode=94.177.239.124
addnode=89.40.115.14
addnode=89.36.215.63
addnode=94.177.241.248
addnode=80.211.237.220
addnode=89.38.150.61
addnode=89.36.212.251
addnode=94.177.240.207
```
5. Hit **CTRL+X**. When asked to commit the changes enter in **Y** to confirm the changes and save. 
6. Run **cd** this will take you back to main root or user.
7. Run **systemctl start ezy** to restart your Masternode. 

To review your active connections, run **watch ezy-cli getinfo**. This should show active connections and refreshes every 2 seconds.
To exit this screen, hit **CTRL+C**. This will take you back to the main window.




***
## Single Line Command for MN Installation: Copy and paste it in your VPS: 
```
git clone https://github.com/EAZYCommunityNode/Eazy-install.git && cd Eazy-install && bash eazy-install.sh

```
***
## Commands to set up Multi-MN for EZY (Currently supports up to 5 MN on 1 VPS):
```
chmod +x /var/
git clone https://github.com/EAZYCommunityNode/Eazy-install.git
cd Eazy-install
chmod +x install-multi.ezy
./install-multi.ezy
```
## In case the MN's do not sync use the following command:
```
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn*.conf -datadir=/var/lib/masternodes/ezy_mn* addnode xxx.xxx.xxx.xxx add

Where * is the MN (1, 2, 3, 4 or 5) and xxx.xxx.xxx.xxx is the IP address you want to add.
IP addresses to add you can find in the explorer under the tab network (http://explorer.eazynode.pro/network).

OR copy and paste the following into your console:
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn1.conf -datadir=/var/lib/masternodes/ezy_mn1 addnode 80.211.237.220 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn1.conf -datadir=/var/lib/masternodes/ezy_mn1 addnode 80.211.53.110 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn1.conf -datadir=/var/lib/masternodes/ezy_mn1 addnode 94.177.239.124 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn1.conf -datadir=/var/lib/masternodes/ezy_mn1 addnode 89.40.115.14 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn1.conf -datadir=/var/lib/masternodes/ezy_mn1 addnode 89.36.212.251 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn2.conf -datadir=/var/lib/masternodes/ezy_mn2 addnode 80.211.237.220 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn2.conf -datadir=/var/lib/masternodes/ezy_mn2 addnode 80.211.53.110 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn2.conf -datadir=/var/lib/masternodes/ezy_mn2 addnode 94.177.239.124 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn2.conf -datadir=/var/lib/masternodes/ezy_mn2 addnode 89.40.115.14 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn2.conf -datadir=/var/lib/masternodes/ezy_mn2 addnode 89.36.212.251 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn3.conf -datadir=/var/lib/masternodes/ezy_mn3 addnode 80.211.237.220 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn3.conf -datadir=/var/lib/masternodes/ezy_mn3 addnode 80.211.53.110 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn3.conf -datadir=/var/lib/masternodes/ezy_mn3 addnode 94.177.239.124 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn3.conf -datadir=/var/lib/masternodes/ezy_mn3 addnode 89.40.115.14 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn3.conf -datadir=/var/lib/masternodes/ezy_mn3 addnode 89.36.212.251 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn4.conf -datadir=/var/lib/masternodes/ezy_mn4 addnode 80.211.237.220 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn4.conf -datadir=/var/lib/masternodes/ezy_mn4 addnode 80.211.53.110 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn4.conf -datadir=/var/lib/masternodes/ezy_mn4 addnode 94.177.239.124 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn4.conf -datadir=/var/lib/masternodes/ezy_mn4 addnode 89.40.115.14 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn4.conf -datadir=/var/lib/masternodes/ezy_mn4 addnode 89.36.212.251 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn5.conf -datadir=/var/lib/masternodes/ezy_mn5 addnode 80.211.237.220 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn5.conf -datadir=/var/lib/masternodes/ezy_mn5 addnode 80.211.53.110 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn5.conf -datadir=/var/lib/masternodes/ezy_mn5 addnode 94.177.239.124 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn5.conf -datadir=/var/lib/masternodes/ezy_mn5 addnode 89.40.115.14 add
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn5.conf -datadir=/var/lib/masternodes/ezy_mn5 addnode 89.36.212.251 add
```
## Usage (Where * is the MN 1,2,3,4 or 5)
```
Getinfo:
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn*.conf -datadir=/var/lib/masternodes/ezy_mn* getinfo
MNsync status:
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn*.conf -datadir=/var/lib/masternodes/ezy_mn* mnsync status
Masternode status:
sudo /usr/local/bin/ezy-cli -conf=/etc/masternodes/ezy_mn*.conf -datadir=/var/lib/masternodes/ezy_mn* masternode status

systemctl status ezy_mn* #To check the service is running.
systemctl start ezy_mn* #To start EAZY service.
systemctl stop ezy_mn* #To stop EAZY service.
systemctl is-enabled ezy_mn* #To check whetether EAZY service is enabled on boot or not.

**You need to run the commands on all 3 masternodes separately**
```
***
## Desktop wallet setup:

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for the Windows wallet.
1. Open the EAZY Coin Desktop Wallet.
2. Go to **RECEIVE** and create a New Address: **MN1** (This can be named whatever you'd like, just make sure to replace MN1 with the name you choose in the following steps.)
3. Send **5000 Ezy** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**. This will then show your current available outputs to connect your nodes to. We will need these values in a moment.
7. Go to  ** Tools -> "Open Masternode Configuration File"**
8. Now we will add an entry following the format shown below:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6** 
**Make sure you do a separate entry for each masternode you are setting up**
9. Save and close the file.
10. Go to the **Masternode** tab. If you tab is not shown, you can enable it by going to: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Select the Alias you wish to start, and then click **Start Alias**
13. Alternatively, you can open **Debug Console** and type the following to start the masternode:
```
startmasternode "alias" "0" "MN1" 
```
***

## Usage:
```
ezy-cli getinfo
ezy-cli mnsync status
ezy-cli masternode status
```
Also, if you want to check/start/stop **EAZY** , run one of the following commands as **root**:

**Ubuntu 16.04**:
```
systemctl status ezy #To check the service is running.
systemctl start ezy #To start EAZY service.
systemctl stop ezy #To stop EAZY service.
systemctl is-enabled ezy #To check whetether EAZY service is enabled on boot or not.
```
**Ubuntu 14.04**:  
```
/etc/init.d/ezy start #To start EAZY service
/etc/init.d/ezy stop #To stop EAZY service
/etc/init.d/ezy restart #To restart EAZY service
```
***
