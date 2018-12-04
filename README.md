# EAZY
Shell script to install a [EASY Masternode](https://www.eazynode.pro/) on a Linux server running Ubuntu 14.04 or 16.04. Use it on your own risk.

***
## Installation:
```
git clone https://github.com/EAZYCommunityNode/Eazy-install.git
cd Eazy-install
bash eazy-install.sh

***
## Config file for Masternode VPS

First run command systemctl stop ezy to stop masternode.

Next do cd .ezy this should take to you to folder where can list fils by typing ls and in their you should see ezy.conf

Now to edit.

type in nano ezy.conf

After the line where your masternodeprivkey is create a new line and place the following in.
addnode=194.99.23.28
addnode=23.94.189.54
addnode=23.94.189.53
addnode=37.48.67.162
addnode=207.148.122.124

Now do CTRL X hit letter Y to confirm changes and hit enter this should now save the new config.

Now type cd hit enter should take you back to main root or user.
Now to start server again systemctl start ezy

Now you can do watch ezy-cli getinfo this should show active connections and refreshed every 2 sec.
To come out of this simplyhit CTRL C and will go back to main window.



```
***
## Single Line Command for MN Installation: Copy and paste it in your VPS
```
curl https://github.com/EAZYCommunityNode/Eazy-install/blob/master/eazy-install.sh | bash

```
***
## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the EAZY Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **5000** **Eazy** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Open **Debug Console** and type:
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
