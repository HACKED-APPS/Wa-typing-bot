# WhatsApp "Always Typing" Bot

![Node.js](https://img.shields.io/badge/Node.js-18.x+-brightgreen.svg)
![Library](https://img.shields.io/badge/Library-Baileys-blue.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

A simple yet effective WhatsApp bot built with Node.js and `@whiskeysockets/baileys`. Its primary function is to maintain a constant "typing..." presence in all your chats, both private and group, making it appear as if you are always online and about to write a message.

This bot uses a "Turbo" mechanism, sending presence updates to all chats simultaneously for maximum efficiency.

## ✨ Features

-   **Always Typing**: Sets your status to "typing..." in all discovered chats every 5 seconds.
-   **Turbo Mode**: Sends presence updates to all chats in parallel, handling potential errors for individual chats without interrupting the others.
-   **Pairing Code Authentication**: No need to scan a QR code. Simply enter a code on your phone.
-   **Session Persistence**: Saves your session, so you only need to log in once.
-   **Dynamic Chat Discovery**: Automatically detects new chats as you receive messages.
-   **Automatic Reconnection**: Tries to reconnect automatically if the connection is lost.
-   **Startup Notifications**: Sends a confirmation message to yourself and another contact upon successful connection.

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
-   [Node.js](https://nodejs.org/) (version 18.x or higher is recommended)
-   npm (comes bundled with Node.js)
-   A WhatsApp account

## 🚀 Installation & Setup (Desktop)

Follow these steps to get your bot up and running on a PC/Mac/Linux machine.

**1. Clone the Repository**
Open your terminal and clone this repository to your local machine.

```bash
git clone https://github.com/your-username/your-repository-name.git
```

**2. Navigate to the Project Directory**

```bash
cd your-repository-name
```

**3. Install Dependencies**
Install the necessary npm packages.

```bash
npm install
```
This will install `@whiskeysockets/baileys`, `pino`, and other required dependencies.

## ▶️ Running the Bot (Desktop)

**1. Start the Bot**
Run the main script using Node.js. Let's assume you saved the code as `bot.js`.

```bash
node bot.js
```

**2. First-Time Authentication (Pairing Code)**
On the first run, the bot needs to be linked to your WhatsApp account.

-   The terminal will prompt you to enter your phone number, including the international prefix (e.g., `972501234567`).
-   After you enter the number, a pairing code will be generated and displayed in the terminal.

    ```
    Your pairing code is: XXXX-XXXX
    ```

-   On your phone, open WhatsApp and go to:
    **Settings > Linked Devices > Link a Device > Link with phone number instead**.
-   Enter the code shown in your terminal.

Once done, the bot will connect. A folder named `auth_info_baileys` will be created to store your session credentials. You won't need to repeat this process unless you delete this folder or log out from another device.

**3. The Bot is Live!**
Once you see the "Successfully connected to WhatsApp!" message, the bot is active. It will start discovering your chats and sending "typing..." presence updates.

## 📱 Running on Termux (Android)

You can run this bot 24/7 directly on your Android device using the Termux terminal emulator.

**1. Install Termux**
Download and install Termux from **[F-Droid](https://f-droid.org/en/packages/com.termux/)**. The version on the Google Play Store is outdated and will not work.

**2. Update Termux Packages**
Open Termux and run the following commands to update its internal packages:

```bash
pkg update && pkg upgrade
```

**3. Install Required Tools**
Install Node.js and Git:

```bash
pkg install nodejs git -y
```

**4. Clone the Repository**
Clone this project into your Termux home directory.

```bash
git clone https://github.com/your-username/your-repository-name.git
```

**5. Navigate and Install Dependencies**

```bash
cd your-repository-name
npm install
```

**6. Run the Bot with Wake Lock**
To prevent Android from killing the bot process when the app is in the background or the screen is off, you must run it with `termux-wake-lock`.

```bash
termux-wake-lock node bot.js
```
The authentication process (Pairing Code) is the same as on desktop. The code will be displayed directly in your Termux terminal. The bot will now run continuously as long as your Termux session is active.


## ⚠️ Disclaimer

Using automated scripts or bots on WhatsApp may be against their Terms of Service. This project is for educational purposes only. Use it at your own risk. The developer is not responsible for any consequences, including the potential banning of your WhatsApp account.

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
