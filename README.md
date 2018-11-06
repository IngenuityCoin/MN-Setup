# Ingenuity
Shell script to install a [Ingenuity Masternode](https://ingy.io) on a Linux server running Ubuntu 14.04, 16.04 or 18.04. Use it on your own risk.

***
## Installation:
```
wget -q https://raw.githubusercontent.com/IngenuityCoin/MN-Setup/master/ingyinstall.sh
sudo apt update
sudo apt install dos2unix
ENTER MASTERNODE GENKEY AND TX OUTPUTS USING STEPS BELOW
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the Ingenuity Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **1000** **INGY** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type and copy the following command: **masternode genkey**
7. In **"Debug console - Console"** type and copy following command: **masternode outputs**
8. Go to  ** Tools -> "Open Masternode Configuration File"
9. Add the following entry:
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
12. Click on masternode and click start alias.
***

## Usage:
```
ingenuity-cli getinfo
ingenuity-cli mnsync status
ingenuity-cli masternode status
```
Also, if you want to check/start/stop **Ingenuity** , run one of the following commands as **root**:

**Ubuntu 16.04**:
```
systemctl status Ingenuity #To check the service is running.
systemctl start Ingenuity #To start Ingenuity service.
systemctl stop Ingenuity #To stop Ingenuity service.
systemctl is-enabled Ingenuity #To check whether Ingenuity service is enabled on boot or not.
```
**Ubuntu 14.04**:  
```
/etc/init.d/Ingenuity start #To start Ingenuity service
/etc/init.d/Ingenuity stop #To stop Ingenuity service
/etc/init.d/Ingenuity restart #To restart Ingenuity service
```
***
