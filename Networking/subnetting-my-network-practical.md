# Subnetting My Network: Practical Guide

> **Tool Used:** Cisco Packet Tracer (Network simulation & visualization)

---

## Installation Guide

### Windows
1. **Download:**
   - Create a free account on [Cisco Networking Academy](https://www.netacad.com/).
   - Log in and visit the [Lab Downloads](https://www.netacad.com/resources/lab-downloads) page.
   - Download the 64-bit Windows installer (use 32-bit only if needed).
2. **Run Installer:**
   - Double-click the downloaded `.exe` file.
   - Click **Yes** if prompted by User Account Control.
3. **Accept License:**
   - Read and accept the agreement, then click **Next**.
4. **Choose Destination:**
   - Select the installation folder (default or custom), then click **Next**.
5. **Create Shortcuts:**
   - Choose shortcut locations, then click **Next**.
6. **Install:**
   - Review settings and click **Install**. Wait for completion.
7. **Finish:**
   - Click **Finish**. Ensure **Launch Cisco Packet Tracer** is checked.
   - Click **Yes** if prompted for multi-user mode.
8. **Log In:**
   - On first launch, log in with your NetAcad credentials.
   - Optionally, select **Keep me logged in**.

### Linux
1. **Download:**
   - Create a free NetAcad account and log in.
   - Download the `.deb` package for Ubuntu/Debian.
2. **Open Terminal:**
   - Navigate to Downloads: `cd ~/Downloads`
3. **Install Dependencies:**
   ```bash
   sudo apt update
   sudo apt install libqt5widgets5 libqt5gui5 libqt5core5a libqt5network5 libqt5svg5 libgl1-mesa-glx libxcb-xinerama0-dev
   ```
4. **Install Packet Tracer:**
   ```bash
   sudo dpkg -i CiscoPacketTracer*.deb
   ```
   - Replace `CiscoPacketTracer*.deb` with the exact filename if needed.
5. **Fix Dependencies (if needed):**
   ```bash
   sudo apt-get install -f
   ```
6. **Launch:**
   - Start with: `packettracer`
7. **Log In:**
   - Use your NetAcad credentials on first launch.

---

## Subnetting Example

Let’s subnet the Class C network `192.168.100.0` into **two subnets**.

| Step | Description |
|------|-------------|
| **1** | **Default Subnet Mask:** 255.255.255.0 (`/24`) <br> Binary: `11111111.11111111.11111111.00000000` |
| **2** | **Bits to Borrow:** <br> Formula: $2^n = 2$ (where $n$ = number of borrowed host bits) <br> For 2 subnets, $n = 1$ |
| **3** | **New Subnet Mask:** <br> Binary: `11111111.11111111.11111111.10000000` <br> Decimal: 255.255.255.128 (`/25`) |
| **4** | **Block Size:** $256 - 128 = 128$ |
| **5** | **Subnet Addresses:** <br> - `192.168.100.0/25` <br> - `192.168.100.128/25` |
| **6** | **Usable Hosts per Subnet:** 126 |
| **7** | **Default Gateway:** <br> The router interface address for each subnet (e.g., next address after assigned hosts) |

**Example:**
- In `192.168.100.0/25`:
  - PC1: `192.168.100.1`
  - PC2: `192.168.100.2`
  - Gateway: `192.168.100.3` (or any unused host address assigned to the router interface)

---

## Video Walkthrough

For a detailed, visual explanation, watch the video below:

[Subnetting Practical Video (MEGA link)](https://mega.nz/file/QNBzhDoD#JMImAnNd9MPofmiTo5QNHhaUtif3tHP45UYH8kMplZk)

---

*This guide provides a concise, professional overview for practical subnetting using Cisco Packet Tracer. For more details, refer to the video.*
