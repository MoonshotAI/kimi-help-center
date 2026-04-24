---
title: "Kimi Claw Android overview"
slug: "kimi-claw-android-guide"
order: 3
extract_headings: true
preview: false
---

<SeoMeta
  title="Kimi Claw Android overview - Kimi Help Center"
  description="Learn how to deploy OpenClaw on your Android phone and turn it into a 24/7 AI remote assistant."
  ogType="article"
/>

<Callout type="tip">
Welcome to Kimi Claw Android. This article will introduce how to deploy OpenClaw to Android phones and turn your idle phone into your 24/7 AI remote assistant. You can remotely control your phone, use apps, connect to smart homes, and create your own personalized assistant through messaging apps such as Kimi, Feishu, and WeChat.
</Callout>

It is recommended to deploy Kimi Claw Android on idle phones to avoid permission conflicts with daily use. Please do not manually upgrade the OpenClaw version; official adapted updates will be delivered through in-app version updates.

## Kimi Claw Android Introduction
<Frames
  src="./images/kimi-claw-android-guide/img-06.png"
/>

System requirements:

| Project | Requirement |
| --- | --- |
| Operating system | Android 8.0 and above |
| Available storage space | At least 5GB |
| Network | A stable network connection is required |
| Account | Kimi Allegretto and above subscription |

<Callout type="info">
It is recommended to use idle phones to avoid conflicts with daily use
</Callout>

## Download and install
### Download Kimi Claw Android

You can download it in the following ways:
#### Method 1: Scan the QR code to download from the webpage.
Log in to the [kimi.com](https://kimi.com), find the "Download Kimi Claw Android" entrance, and use your Android phone to scan the QR code on the page to download.
<Frames
  src="./images/kimi-claw-android-guide/img-03.png"
/>

#### Method 2: Download directly from Google Play
Search for "Kimi Claw" in the mobile app store and complete the download

#### Method 3: Download the Kimi App on mobile
Open the Kimi App, click Kimi Claw Android, and you can also link an existing OpenClaw instance.

### Initial Configuration 

When you first open Kimi Claw Android, you will see a welcome page. After understanding the following important information, click "Start Configuration" to enter the setup process.

- Rapid OpenClaw Deployment - Deploy OpenClaw to local phones to communicate via Kimi, Feishu, etc.
- It is recommended to use an idle phone - Kimi Claw Android requires a stable network to run, and it is recommended to use an idle phone
- Please use safely - OpenClaw may involve privacy and security risks, so please use it with caution.

After selecting Agree to the Privacy Policy and User Agreement, proceed.

#### Step 1: Grant permissions
Kimi Claw Android requires the following permissions to run stably in the background. Please click "Authorize" one by one to complete the authorization.

| Permissions | Explanation |
| --- | --- |
| System notification | Display gateway status and reminders |
| Storage space permissions | At least 5GB of available space is required |
| Background running permission | Keep the gateway running when switching to the background |

Since the settings paths vary among different mobile phone brands, the following are the general steps:

1. Click "Open Settings" to jump to the phone settings page
2. Enter the application management list and select Kimi Claw Android
3. Turn on the auto-start switch
4. Select "Fully Allow Background Behavior" in Power Consumption Management
5. Return to Kimi Claw Android, click "I'm done" to continue installation

#### Step 2: Configure Kimi Account

1. Click "Go to Configure" to jump to Kimi App for authorization
2. After authorization, Kimi will automatically create a Kimi Coding Plan API key for Kimi Claw Android
3. If you are a free user, you need to activate membership privileges first. Click "Go to Upgrade" to activate your membership.

#### Step 3: Install OpenClaw
<Frames
  src="./images/kimi-claw-android-guide/img-08.png"
/>
If the installation fails, you can click "Reinstall" to try again. If it fails multiple times, please click "Having issues? Go to feedback" to submit the problem.

## Dashboard User Guide

### Main Interface
<Frames
  src="./images/kimi-claw-android-guide/img-14.png"
/>
After the configuration is completed, enter the Dashboard main interface, and you can see the following information:

- OpenClaw Gateway Status — Starting / Connected / Stopped, and Runtime
- Chat Channels — List of currently connected communication channels
- OpenClaw Log — The original log of OpenClaw operation
- Use Kimi Conversation — Open the Kimi App, open the conversation interface corresponding to Kimi Claw Android, and automatically switch to the corresponding Claw.

If a permission reminder appears at the top of the Dashboard, it indicates that some permissions have not been granted or have expired. Please follow the prompts to complete the authorization item by item to ensure the normal operation of Kimi Claw Android.

### Chat Channel Management
<Frames
  src="./images/kimi-claw-android-guide/img-33.png"
/>
In the Dashboard, you can manage all communication channels:

- View connected channels and their statuses (e.g., Kimi - Connected, Feishu - Connected)
- Click "+ Connect" to add a new chat channel
- Click on an existing channel to view details or delete it

<Callout type="info">
Please keep at least one chat channel to ensure normal communication with Kimi Claw Android.
</Callout>

### OpenClaw Logs

- Search — Search log content by keyword
- Filter Level — Filter by log level (Info / Warning / Error, etc.)
- Auto Scroll to Bottom — Automatically scroll to the latest log
- Refresh — Manually refresh the log content
<Frames
  src="./images/kimi-claw-android-guide/img-16.png"
/>

### Settings
<Frames
  src="./images/kimi-claw-android-guide/img-21.png"
/>
Click Settings to enter the settings page:

**Functional Layer:**

- ClawHub Skills: Automatically associate with the ClawHub official website and manage skills available for Kimi Claw Android
- OpenClaw Workspace: Enter the local OpenClaw configuration file directory and edit personal preferences

**System Layer:**
<Frames
  src="./images/kimi-claw-android-guide/backup.png"
/>
- Backup & Restore: Back up the current OpenClaw configuration and history, and support restoring past configurations and records
- Accessibility Service: Monitor the accessibility service permissions of the mobile phone
- Background running permission: Monitor the background running permission of the mobile phone
- Version Upgrade: Monitor the version, click to automatically upgrade

**About:**

- Help: Instructions on Basic Usage Recommendations
- Feedback: Submit feedback
- User Agreement: Read the User Agreement
- Privacy Policy: Read Privacy Policy

#### ClawHub Skills

Automatically associate with the ClawHub official website and manage skills available for Kimi Claw Android. You can download and install Skills to extend Claw's capabilities.

#### OpenClaw Workspace
<Frames
  src="./images/kimi-claw-android-guide/img-19.png"
/>

#### Backup and Recovery

Kimi Claw Android provides both automatic and manual backup functions to ensure that your OpenClaw history and configuration are not lost.

Automatic Backup

Kimi Claw Android will automatically back up the current OpenClaw's history and configuration at regular intervals, package them into a compressed file for storage. There is no need for manual operation, and the system will automatically complete it in the background.

Manual Backup:

If you wish to record the state at a specific moment, you can also actively click Backup to manually save the current history and configuration snapshot. Click  Backup  to export all current configuration backups.

**Restore Configuration:**

Kimi Claw Android supports restoring to previous configuration states. It also supports both the automatic backup state and the active backup state of Kimi Claw Android.

In the following scenarios, you can restore to a previous state using the recovery function:

- When uninstalling or reinstalling the app causes historical records to disappear, past records can be restored
- When it is necessary to switch the Claw configuration, you can restore it to the previously saved configuration state
- When replacing the phone and redeploying, simply import the backup file to restore

Click on the corresponding backup file in the backup list, and you can automatically restore the historical records and configurations to that point in time, ensuring that past records are not erased.

## Configure chat channels

### Kimi
Kimi is the default communication channel, and it will automatically connect after completing the Kimi account configuration in the Onboarding process, without the need for additional operations.

After installation and configuration are completed, your Kimi Claw Android will automatically appear on the Bot Switching page of the Web client (kimi.com). After clicking to switch, the avatar and chat thread will be synchronously switched.

Kimi Claw Android only supports editing Bot name and deleting Bot in Bot management.

### Feishu
<Frames
  src="./images/kimi-claw-android-guide/img-25.png"
/>

Supports three connection methods:

Method 1: Open Feishu to create

Click "Open Feishu to Create", complete the app creation in Feishu as prompted, and the status will automatically update to "Connected".

Method 2: Scan the QR code to create

1. Click "Scan QR Code to Create"
2. Use Feishu to scan the QR code
3. Complete the creation of Feishu application in the browser

**Method 3: Manually enter Bot information**

1. Click "Manually Enter Bot Information"
2. Enter the App ID and App Secret
3. Click "Add" to complete the connection

### WeChat
WeChat channel needs to first install WeChat Claw on the WeChat side, and Kimi Claw Android will communicate through the WeChat Claw terminal

You need to first complete the installation of WeChat Claw as guided by WeChat official. The installation is completed when WeChat ClawBot appears on the chat page.

Enter Kimi Claw Android, connect to the WeChat channel, and complete the process by scanning the QR code with WeChat

### Telegram
<Frames
  src="./images/kimi-claw-android-guide/img-34.png"
/>

Kimi Claw Android supports Telegram integration, requiring users to first obtain their bot token and user ID.

## Automation

One of the core capabilities of Kimi Claw Android is to control apps on the phone to complete various tasks. After sending instructions to Claw via chat channels such as Kimi, Feishu, and WeChat, Claw will automatically open the corresponding app on the phone, perform a series of operations like a real person, and finally complete the tasks you specify.

### Working Principle

When you send task instructions to Claw via the chat channel, Claw will:

1. Understand your task requirements
2. Automatically open the corresponding app on the phone
3. Complete tasks step by step by simulating user operations (clicking, swiping, inputting, etc.)
4. Take screenshots during the execution process to facilitate your review of the execution process
5. Report the execution results to you after completing the task

### Typical Usage Scenarios

#### Shopping and Consumption

Search for products, add to cart, view orders, claim discounts, etc. on platforms such as Taobao, Tmall, and Meituan.

#### Travel and Navigation

Query taxi fares, check subway schedules, search for nearby hotels, book trips, etc. on Amap.

#### Social and Content

Check messages, browse content, search for products, perform interactive operations, etc. on platforms such as WeChat, Rednote, and Douyin.

## Usage Tips

### Control the phone via chat software

After the configuration is completed, you can send commands to Claw in Kimi, Feishu, and WeChat to remotely control applications on Android phones. For example:

- Help me open WeChat and check the latest messages
- Open the map and search for nearby restaurants
- "Help me check the calendar to see what's on the schedule for today"

### Use ClawHub Skills
<Frames
  src="./images/kimi-claw-android-guide/img-18.png"
/>
Kimi Claw Android comes with ClawHub, a built-in skill library. You can manage and install skills in the settings to expand more capabilities for Claw.

Scenarios suitable for using Skills:
- Information Organization: News Aggregation, Competing Product Comparison
- Data Analysis: Market Review, Data Interpretation
- Workflow Automation: A Complete Process from Requirement Decomposition to Output

### Multi-channel simultaneous online
You can connect multiple channels such as Kimi, Feishu, and WeChat simultaneously, and chat with Claw across different messaging apps. Simply click on "+ Connect" in the Channel Management section of the Dashboard to add them.

## Security and Restricted Applications

### Safety Instructions

Before using Kimi Claw Android, please note the following safety precautions:

1. Use an idle phone — Kimi Claw Android will occupy the phone's system permissions, which may affect daily use. It is recommended to use an idle phone

2.  Sensitive Data Isolation — Kimi Claw Android will read local file data, please clean or isolate sensitive information in advance

3. Financial Application Protection — The system has automatically blocked access to banking, payment, securities, and insurance applications to safeguard funds

### Restricted Application List

Due to financial security and privacy concerns, the following categories of apps are automatically blocked from access by Kimi Claw Android and cannot be operated remotely:

1. Social

| Package | Risk description |
| --- | --- |
| wechat | Important private social and payment functions are involved |

2. Banking

| Package | App name | Risk description |
| --- | --- | --- |
| com.android.bankabc | abc, Agricultural Bank of China | Agricultural Bank of China, which can perform operations such as transfers and wealth management |
| com.bankcomm.main | bocom, Bank of Communications | Bank of Communications, which supports operations such as transfers and wealth management |
| com.bjbk.im | Bank of Beijing | Bank of Beijing, which can perform operations such as transfers and wealth management |
| com.cebbank.im | Everbright Bank | China Everbright Bank, which can perform operations such as transfers and wealth management |
| com.cgb.im | Guangfa Bank | Guangfa Bank, which can perform operations such as transfers and wealth management |
| com.chinamworld.bocmbci | boc, Bank of China | Bank of China, one of the Big Four Banks |
| com.chinamworld.main | CCB, China Construction Bank | China Construction Bank, one of the Big Four Banks |
| com.cib.im | Industrial Bank | Industrial Bank, which can perform operations such as transfers and wealth management |
| com.citic.im | China CITIC Bank | China CITIC Bank, which supports operations such as transfers and wealth management |
| com.cmbc.im | Minsheng Bank | China Minsheng Bank, which can perform operations such as transfers and wealth management |
| com.cmbchina.ccd.pluto.customerView | cmb, China Merchants Bank | China Merchants Bank, which supports operations such as transfers and wealth management |
| com.hxb.im | Huaxia Bank | Huaxia Bank, which can perform operations such as transfers and wealth management |
| com.hzbk.im | Hangzhou Bank | Hangzhou Bank, which supports operations such as transfers and wealth management |
| com.icbc | ICBC, Industrial and Commercial Bank of China | Industrial and Commercial Bank of China, one of the Big Four Banks |
| com.jsbk.im | Jiangsu Bank | Jiangsu Bank, which supports operations such as transfers and wealth management |
| com.nbbk.im | Ningbo Bank | Ningbo Bank, which supports operations such as transfers and wealth management |
| com.pingan.paces.cloud | Ping An Pocket Bank | Ping An Bank Mobile Client |
| com.psbc.im | Postal Savings Bank | Postal Savings Bank of China |
| com.shbk.im | Shanghai Bank | Shanghai Bank, which supports operations such as transfers and wealth management |
| com.spdb.im | Shanghai Pufa Bank | Shanghai Pufa Development Bank |

3. Payment

| Package | App name | Risk description |
| --- | --- | --- |
| com.eg.android.AlipayGphone | Alipay, 支付宝 | Alipay, China's largest third-party payment platform |
| com.paypal.android.p2pmobile | paypal | PayPal, the world's largest online payment platform |
| com.unionpay | ysf, Cloud Flash Payment | China UnionPay Cloud Flash Payment, a bank card payment instrument |
| com.squareup.cash | cashapp | Cash App, a US mobile payment platform |
| com.venmo | venmo | Venmo, a US P2P payment platform |
| com.google.android.apps.walletnfcrel | googlewallet, wallet | Google Wallet, Google's payment wallet |

4. Securities

| Package | App name | Risk description |
| --- | --- | --- |
| com.citics.pbm | CITIC, Xin E Tou | CITIC Securities Trading Client |
| com.cmschina.stock | China Merchants Securities | China Merchants Securities Trading Client |
| com.csc108.newpda | CITIC Construction Investment | CITIC Construction Investment Securities Trading Client |
| com.dfzq.stock | Orient Securities | Orient Securities Trading Client |
| com.eastmoney.android.berlin | eastmoney, Orient Fortune | East Money, Stock/Fund Trading Platform |
| com.ebscn.stock | ebscn, Golden Sunshine | Everbright Securities Trading Client |
| com.foundersc.stock | founder, Xiaofang | Founder Securities Trading Client |
| com.gf.gfstocks | GF Easy Gold Rush | GF Securities Trading Client |
| com.guosen.stock | guosen, Golden Sun | Guoxin Securities Trading Client |
| com.guotai.junan.guiyang | Guotai Junan | Guotai Junan Securities Trading Client |
| com.hexin.plat.android | ths, Flush | Flush, Stock/Fund Trading and Market Platform |
| com.htsc.mdc | Huatai, Zhangle Fortune Link | Huatai Securities Trading Client |
| com.htsec.android | Haitong Securities | Haitong Securities Trading Client |
| com.pingan.stock | Ping An Securities | Ping An Securities Trading Client |
| com.tfzq.stock | Tianfeng Securities | Tianfeng Securities Trading Client |
| com.xueqiu.android | xueqiu, Snowball | Xueqiu, Stock Community and Trading Platform |
| com.xyzq.stock | Industrial Securities | Industrial Securities Trading Client |

5. Insurance / Financial

| Package | App name | Risk description |
| --- | --- | --- |
| com.pingan.lifeinsurance | Ping An Financial Services Client | Ping An Insurance of China, which allows operations such as insurance purchase and claims settlement |
| com.jd.jrapp | JD Finance | JD Finance provides financial services such as wealth management, lending, and payment |

## Supported and Unsupported Features

### Supported Features

| Function | Description |
| --- | --- |
| Remote control mobile application | Remotely use apps on a mobile phone via chat software commands |
| Multi-channel communication | Supports communication with Claw via Kimi, Feishu, and WeChat |
| Real-time Log Viewing | View OpenClaw gateway operation logs, supporting search and level filtering |
| Configuration Backup and Restoration | Back up the current configuration, which can be restored after reinstallation or device replacement |
| Gateway Status Monitoring | View the connection status and running duration of the OpenClaw gateway in real time |
| Channel Management | Add, view, and delete communication channels |
| OpenClaw Dashboard | Manage OpenClaw via the built-in Dashboard |

### Unsupported Features and Limitations

| Area | Limitation |
| --- | --- |
| Platform support | Currently only Android devices are supported; iOS is not supported |
| Membership | Available only to Allegretto and above Kimi members |
| Financial apps | Applications related to banking, payment, securities, and insurance are prohibited from accessing (see Chapter 6 for details) |
| Bot management | The Bot of Kimi Claw Android only supports editing the name and deletion, and does not support other Bot configurations |
| Terminal | Kimi Claw Android does not currently provide the ability for direct command-line operations |

## Frequently Asked Questions (FAQ)

<Callout type="info">
The following is a reference to Kimi Claw Android.
</Callout>

### Installation and Configuration

#### What should I do if the installation of OpenClaw fails?

- Please ensure that there is sufficient storage space (at least 5GB), and do not exit the application or lock the screen during the installation process
- Click "Reinstall" to retry
- If you experience multiple failures, please click "Have an issue, go to feedback" to submit the problem

#### After permission authorization, the status is not updated?

- For some mobile phone brands, permission grants require restarting the app to take effect
- Please return to Kimi Claw Android. If the status has not been updated, you can try closing and reopening the App

#### Can free users use it?

- Currently, you need to activate Allegretto or higher Kimi membership privileges to use Kimi Claw Android
- Click "Go to Upgrade" in the steps of configuring the Kimi account to open it

#### When restoring the configuration, it prompts "Configuration file is invalid"?

- The backup file may be corrupted or from an incompatible version
- Please use "Kimi App One-Click Configuration" to reconfigure

### Connectivity and Stability

#### Why does the gateway status always show "Starting"?

- Check if the network connection is normal
- Confirm that all required permissions (notifications, battery optimization, storage, autostart) have been granted
- Try clicking "Backup and Restart" in the settings to restart the gateway service

#### Did the gateway suddenly disconnect?

- Check if the phone has entered power-saving mode, causing background apps to be cleared
- Confirm that "Ignore battery optimization" and "Autostart permission" have been correctly granted
- Check the gateway status on the Dashboard. If it shows "Stopped", click Restart

#### Does Kimi Claw Android drop connection after the phone is locked?

- This is usually because the phone's battery optimization strategy causes background applications to be killed
- Please ensure that the following settings have been completed:
  - Ignore Battery Optimization - Authorized
  - Self-start permission — Enabled
  - Power Consumption Management — Select "Fully Allow Background Behavior"

### Channels and Communication

#### Can multiple chat channels be connected simultaneously?

- Yes. You can connect multiple channels such as Kimi, Feishu, WeChat, etc. simultaneously
- Simply click "+ Connect" in the channel management of the Dashboard to add it
- Please keep at least one channel to ensure normal communication

#### After scanning the Feishu QR code, it keeps waiting for status updates?

- Please ensure that you have completed the Feishu application creation process in your browser
- If there has been no update for a long time, you can try to connect by manually entering Bot information

#### WeChat connection failed?

- Please confirm that the WeChat Claw credentials are filled in correctly and match the values from the WeChat-side setup
- Please follow the official WeChat Claw setup guide to regenerate and rebind credentials if needed
- Check if the mobile network can access WeChat services normally

#### Why can't I see Kimi Claw Android in the Kimi App?

- Please confirm that the Onboarding process has been fully completed (permission granting → installation of OpenClaw → configuration of Kimi account)
- Check if the gateway status in the Dashboard is "Connected"
- Try refreshing the Bot list in the Kimi App

### Function Usage

#### Why can't some applications be remotely operated?

- For security reasons, financial applications such as banking, payment, securities, and insurance have been automatically blocked by the system from accessing
- For the complete list, please refer to Chapter 6 "Restricted Application List".

#### Why do we need to use idle phones?

- Kimi Claw Android may occupy the phone's operating permissions during runtime, which may affect your normal use
- Using a spare phone can avoid permission conflicts and protect your private data

#### How to redeploy after changing the phone?

1. Export the configuration file in Dashboard → Settings → Backup & Restore on the old phone
2. Install Kimi Claw Android on the new phone
3. Select "Restore Configuration" in Step 3 and import the previous backup file.

#### How to view the running status of Kimi Claw Android?

- On the main interface of the Dashboard, you can view the gateway status and running time
- Click "Real-time Log" to view detailed operation logs
- Through the search and level filtering functions of logs, problems can be quickly located

### Upgrade and Version

#### How to upgrade Kimi Claw Android?

- Check and upgrade to the latest version in Dashboard → Settings → "Version Upgrade"
- It is recommended to perform the upgrade in a Wi-Fi environment

#### Can I manually upgrade the OpenClaw version?

- Manual upgrade is not recommended. Manual upgrade may lead to compatibility issues
- The official will push the upgrade via in-app notification after the adaptation is completed

## Feedback and Help

If you encounter any problems or have suggestions during use:

### In-app feedback

- Dashboard → Settings → User Feedback
- OpenClaw Installation Page → "If you have problems, provide feedback"

Please provide the following when giving feedback:

- Your Kimi Claw Android ID (visible when clicking on the Kimi channel)
- Device Model and Android Version
- Problem description and screenshot

<Callout type="info">
Providing the Kimi Claw Android ID helps technicians quickly locate issues, so please include it when providing feedback.
</Callout>
