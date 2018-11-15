# EAZY
Shell script to install a [EASY Masternode](https://www.eazynode.com/) on a Linux server running Ubuntu 14.04 or 16.04. Use it on your own risk.

***
## Installation:
```
git clone https://github.com/EAZYCommunityNode/Eazy-install.git
cd Eazy-Linux
bash eazy-install.sh
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
eazy-cli getinfo
eazy-cli mnsync status
eazy-cli masternode status
```
Also, if you want to check/start/stop **EAZY** , run one of the following commands as **root**:

**Ubuntu 16.04**:
```
systemctl status eazy #To check the service is running.
systemctl start eazy #To start EAZY service.
systemctl stop eazy #To stop EAZY service.
systemctl is-enabled eazy #To check whetether EAZY service is enabled on boot or not.
```
**Ubuntu 14.04**:  
```
/etc/init.d/eazy start #To start EAZY service
/etc/init.d/eazy stop #To stop EAZY service
/etc/init.d/eazy restart #To restart EAZY service
```
***
