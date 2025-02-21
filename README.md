
![VPS Edition](https://github.com/user-attachments/assets/821a88c5-c20f-4842-9e93-a8a362a5289e)

# **Dogecoin Node Setup on a VPS 🚀**
*A step-by-step guide to setting up a Dogecoin node on a VPS server.*

---

## **🛠️ VPS Requirements**
- **Minimum Specs:**
  - 4 CPU Cores
  - 250+ GB Storage
  - **Linux Ubuntu 22.04 LTS**

---

## **🛠️ Step 1: Set Up Your VPS Server**
1. Boot up a **VPS server** with **Ubuntu 22.04 LTS**.
2. Open a terminal and update system packages:
   ```bash
   sudo apt update && sudo apt upgrade
   ```
3. When prompted, press **Y** and hit **Enter** to install updates.
4. If a menu appears, use the **arrow keys** to navigate, press **space bar** to select all options, then hit **Enter**.

---

## **🛠️ Step 2: Install Dogecoin Core**
1. Download and extract Dogecoin Core:
   ```bash
   curl -L https://github.com/dogecoin/dogecoin/releases/download/v1.14.9/dogecoin-1.14.9-x86_64-linux-gnu.tar.gz | tar -xz
   ```
2. Navigate to the extracted Dogecoin directory:
   ```bash
   cd dogecoin-1.14.9/bin/
   ```
3. Start Dogecoin Core:
   ```bash
   ./dogecoind
   ```
   - It will **look like nothing is happening**—let it run for **30-60 seconds**.
4. Stop the process:
   ```bash
   Ctrl + C
   ```
5. Move Dogecoin binaries to a system-wide location:
   ```bash
   sudo cp dogecoin* /usr/bin/
   ```

---

## **⚙️ Step 3: Configure Dogecoin Node**
1. Navigate to the Dogecoin configuration directory:
   ```bash
   cd ~/.dogecoin/
   ```
2. Create and edit the configuration file:
   ```bash
   nano dogecoin.conf
   ```
3. **Copy & paste** the following configuration (modify username/password/IP)(added txindex incase you want to do other developments or indexing:
   ```ini
   rpcuser=your_username
   rpcpassword=your_password
   rpcallowip=127.0.0.1
   maxconnections=50
   rpcport=22555
   txindex=1
   server=1
   ```
4. **Save the file** (`Ctrl + X`, then `Y`, then `Enter`).

---

## **🚀 Step 4: Create a Start Script**
1. Open a new script file:
   ```bash
   nano start.sh
   ```
2. **Copy & paste** the following:
   ```bash
   dogecoind -conf=/yourusernamehere/.dogecoin/dogecoin.conf -daemon
   ```
   *(Replace `yourusernamehere` with your VPS username, usually `root`.)*
3. **Save the file** (`Ctrl + X`, then `Y`, then `Enter`).
4. Make the script executable:
   ```bash
   chmod +x start.sh
   ```
5. Run the script:
   ```bash
   ./start.sh
   ```

✅ **Your node is now running!** 🎉

---

## **🔍 Checking Node Status**
Run the following commands to check your node:

1. **Check block sync progress:**
   ```bash
   dogecoin-cli getblockcount
   ```
2. **Check active connections:**
   ```bash
   dogecoin-cli getconnectioncount
   ```
   - If **connections = 8**, your **port forwarding is incorrect**!  

✅ **Your node is fully operational!** 🎯

---

## **🌟 Summary**
### **✔️ What We Did:**
- Set up a **VPS server**
- Installed **Dogecoin Core**
- Created **Configuration Files**
- Started **Dogecoin Node**
- Verified **Node Sync Status**

💚 **You now have a fully functional Dogecoin Node!** 🐶🚀  

---

## **🙋 Need Help?**
If you have any issues, feel free to **open an issue** or reach out to the **@Heimdall_bull** on X! 🐕✨  

---
🚀 **Happy Mining & Supporting the Dogecoin Network!** 🐶

