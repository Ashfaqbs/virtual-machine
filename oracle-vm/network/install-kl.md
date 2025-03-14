**Kali Linux Installation Guide for Oracle VM VirtualBox**

---

### **1. Create a New Virtual Machine (VM)**
1. Open **Oracle VM VirtualBox** and click **New**.
2. Name the VM **Kali-Linux** (or any preferred name).
3. Set **Type:** `Linux`, and **Version:** `Debian (64-bit)`.
4. Assign **RAM**: `5GB (5120MB)`.
5. Create a **Virtual Hard Disk** (`50GB` recommended, **Dynamically Allocated**).
6. Click **Create**.

---

### **2. Configure VM Settings**
1. **System → Processor**: Assign `4 Threads` (or half of our CPU cores).
2. **Display → Video Memory**: Set to `128MB`.
3. **Storage**:
   - Select the **empty disk** and attach the **Kali ISO**.
4. **Network**:
   - **Adapter 1**: `NAT` (for internet access).
   - **Adapter 2**: `Host-Only Adapter` (for local access to the host machine).

---

### **3. Start Installation**
1. Start the VM and select **Graphical Install**.
2. **Language Selection**: Choose our preferred language.
3. **Location & Keyboard**: Set location (`India`) and keyboard layout (`English (US)`).
4. **Hostname**: `kali-linux-vm` (or any name we prefer).
5. **Domain Name**: Leave blank (unless you're using a domain).
6. **Set Password**: Choose a strong root password.

---

### **4. Disk Partitioning**
When prompted for disk partitioning, choose **one of the following**:
- **All files in one partition** (Recommended for simplicity ✅).
- **Separate `/home` partition** (Recommended for developers).
- **Separate `/home`, `/var`, and `/tmp` partitions** (Advanced users).
- **Manual Partitioning** (For custom setups).

Proceed with partitioning and continue installation.

---

### **5. Software Selection**
1. Keep all pre-selected options.
2. **GNOME and KDE Plasma** are unchecked by default:
   - **If we want a GUI**, select **GNOME**.
   - **If we only need CLI**, leave them unticked.

---

### **6. Display Manager Selection**
- **GDM3** (Graphical, recommended for GNOME).
- **LightDM** (Lighter, recommended for XFCE or CLI-based systems ✅).

Choose **LightDM** if we want better performance in VirtualBox.

---

### **7. Install GRUB Boot Loader**
- **Select YES** to install the GRUB bootloader.
- Choose the boot device (usually `/dev/sda`).

---

### **8. Network Configuration in VirtualBox**
1. **Adapter 1: NAT** → Internet Access ✅.
2. **Adapter 2: Host-Only Adapter** → Local communication with host.

---

### **9. Complete Installation & First Boot**
1. Finish the installation process and reboot.
2. Log in using the root user and the password set earlier.
3. **(Optional)** Install GUI manually if needed:
   ```bash
   sudo apt update && sudo apt install kali-desktop-gnome -y
   ```

our Kali Linux VM is now ready for use! 🚀

---

### **Additional Configurations (Post Installation)**
✅ **Enable SSH:**
```bash
sudo systemctl enable ssh
sudo systemctl start ssh
```
✅ **Check IP Address:**
```bash
ip a
```
✅ **Resize VirtualBox Display:**
```bash
sudo apt install virtualbox-guest-x11 -y
reboot
```
✅ **Update System:**
```bash
sudo apt update && sudo apt upgrade -y
```
