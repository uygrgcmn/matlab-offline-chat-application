# matlab-offline-chat-application
"An offline, real-time point-to-point chat application built with MATLAB App Designer using Bluetooth and Serial Port protocols. Features asynchronous data transfer and a hybrid client/server architecture
# MATLAB Bluetooth Offline Chat 📡

![MATLAB](https://img.shields.io/badge/MATLAB-R2023b-orange.svg)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen.svg)
![License](https://img.shields.io/badge/License-MIT-blue.svg)

An offline, point-to-point communication system designed to enable text-based messaging between devices without an internet connection. Developed entirely within **MATLAB App Designer**, utilizing the **Instrument Control Toolbox**.

## 🚀 Features

* **Offline Communication:** No internet required; works via Bluetooth (RFCOMM) and Serial Ports (SPP).
* **Hybrid Architecture:** Acts as both **Client** (Initiator) and **Server** (Listener) in a single application.
* **Asynchronous I/O:** Utilizes `configureCallback` for non-blocking, event-driven data transfer.
* **Smart Discovery:** Scans both remote Bluetooth devices and local COM ports simultaneously.
* **Protocol:** Implements CR/LF termination for robust data synchronization.
* **GUI:** User-friendly interface with a modern Dark Theme.

## 📸 Screenshots

| Device Scanning | Active Chat |
|:---:|:---:|
| <img src="screenshots/2.png" width="400"> | <img src="screenshots/4.png" width="400"> |

*Figure 1: Scanning for devices (Left) and Real-time messaging (Right)*

## 🛠️ Requirements

To run this application, you need:

1.  **MATLAB** (R2020b or later recommended).
2.  **Instrument Control Toolbox** (Required for Bluetooth and Serial objects).
3.  Bluetooth hardware on your PC/Laptop.

## 📥 Installation & Usage

1.  Clone this repository:
    ```bash
    git clone [https://github.com/KullaniciAdin/Matlab-Bluetooth-Chat.git](https://github.com/KullaniciAdin/Matlab-Bluetooth-Chat.git)
    ```
2.  Open MATLAB and navigate to the project folder.
3.  Double-click `BluetoothChat.mlapp` (or `app1.mlapp`) to open it in App Designer.
4.  Click **Run**.

### How to Connect?

* **PC 1 (Server):**
    1.  Click **Scan Devices**.
    2.  Select the Local **COM Port** (e.g., `COM5`) from the list.
    3.  Click **Connect**. (Status: Waiting for connection...)
* **PC 2 (Client):**
    1.  Click **Scan Devices**.
    2.  Select **PC 1's Name** (e.g., `DESKTOP-XYZ`) from the list.
    3.  Click **Connect**.
* **Start Chatting!**

## 🏗️ Architecture

The application uses a custom Class-based structure inheriting from `matlab.apps.AppBase`.

* **`ScanButtonPushed`**: Merges `instrhwinfo('Bluetooth')` and `serialportlist` results.
* **`ConnectButtonPushed`**: Decides whether to instantiate a `bluetooth` object (Client) or `serialport` object (Server) based on user selection.
* **`readData`**: A private method triggered by the `BytesAvailable` event to read incoming ASCII data asynchronously.

## 👥 Authors

* **Uygar Ali Göçmen**
* **Hasan Kılınç**
* **Fevzihan Alkan**
* **Mert Turkaslan**

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
