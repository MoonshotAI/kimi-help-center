---
title: "Kimi Claw Android 产品介绍"
slug: "android-user-guide"
order: 3
extract_headings: true
preview: true
preview_content: "将 OpenClaw 部署到安卓手机，把闲置手机变成 7x24 在线的 AI 远程助手。"
---

<SeoMeta
  title="Kimi Claw Android 用户使用说明 - Kimi Help Center"
  description="本文将会为你介绍如何将 OpenClaw 部署到安卓手机，把闲置手机变成你 7x24 在线的 AI 远程助手。"
  pageUrl="https://www.kimi.com/help/kimi-claw/android-user-guide"
  ogType="article"
/>

欢迎使用 Kimi Claw Android，本文将会为你介绍如何将 OpenClaw 部署到安卓手机，把闲置手机变成你 7x24 在线的 AI 远程助手。你可以通过 Kimi、飞书、微信等聊天软件远程操控手机、使用 App、接入智能家居，打造独属于你的个性化助手。

<Callout type="warning">
• 建议使用闲置手机部署 Kimi Claw Android，避免与日常使用产生操作冲突。
• 请不要手动升级 OpenClaw 版本，官方会通过版本更新推送适配后的新版本。
</Callout>

<Callout type="info">
可以使用 Control（Command）+ F 快速查找报错信息/关键词。
</Callout>

## Kimi Claw Android 介绍

Kimi Claw Android 是一款将 OpenClaw 部署到安卓手机的应用。与云端 Kimi Claw 不同，Kimi Claw Android 中的 OpenClaw 不是运行在云端虚拟机，而是运行在你自己的手机上，是你终端内的独占机器。

<Frames
  src="./images/android-user-guide/screenshot-01.png"
  alt="Kimi Claw Android Dashboard 主界面"
  width={1080}
  height={2392}
/>

### 系统要求

| 项目 | 要求 |
|------|------|
| 操作系统 | Android 8.0 及以上 |
| 可用存储空间 | 至少 5GB |
| 网络 | 需要稳定的网络连接 |
| 账号 | Kimi Allegretto 及以上订阅 |

建议使用闲置手机，避免与日常使用冲突。

## 下载与安装

### 下载 Kimi Claw Android

你可以通过以下方式下载：

**方式一：网页扫码下载**

登录 Kimi 官网，找到「下载 Kimi Claw Android」入口，使用安卓手机扫描页面上的二维码进行下载。

<Frames
  src="./images/android-user-guide/screenshot-02.png"
  alt="Kimi 网页端下载入口"
  width={2624}
  height={1704}
/>

<Frames
  src="./images/android-user-guide/screenshot-03.png"
  alt="扫码下载弹窗"
  width={2626}
  height={1686}
/>

**方式二：手机应用商店直接下载**

在手机应用商店搜索"Kimi Claw"，完成下载。

<Frames
  src="./images/android-user-guide/screenshot-04.png"
  alt="应用商店搜索下载"
  width={1080}
  height={2392}
/>

**方式三：手机 Kimi App 下载**

打开 Kimi App，点击 Kimi Claw Android 完成下载。

<Frames
  src="./images/android-user-guide/screenshot-05.png"
  alt="Kimi App 下载入口"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-06.png"
  alt="Kimi App 下载页面"
  width={1080}
  height={2392}
/>

### 初始配置

首次打开 Kimi Claw Android，你会看到欢迎页面，了解以下重要信息后点击「开始配置」进入设置流程。

- 快速部署 OpenClaw — 将 OpenClaw 部署到本地手机，可通过 Kimi、飞书等进行通信
- 建议使用闲置手机 — Kimi Claw Android 运行需要稳定网络，建议使用闲置手机
- 请安全使用 — OpenClaw 可能存在隐私安全风险，请谨慎使用

勾选同意《隐私协议》和《用户协议》后继续。

#### Step 1：授予权限

Kimi Claw Android 需要以下权限才能在后台稳定运行，请逐项点击「去授权」完成授权：

| 权限 | 说明 | 操作 |
|------|------|------|
| 系统通知 | 显示网关状态和提醒 | 去授权 |
| 存储空间权限 | 至少需要 5GB 可用空间 | 空间不足时去清理 |
| 后台运行权限 | 切换到后台时保持网关运行 | 授权后台运行权限 |

自启动权限配置指引：

由于各手机品牌的设置路径不同，以下是通用步骤：

1. 点击「打开设置」，跳转到手机设置页面
2. 进入应用管理列表，选择 Kimi Claw Android
3. 打开自启动开关
4. 在耗电管理中选择「完全允许后台行为」
5. 返回 Kimi Claw Android，点击「我完成了」继续安装

<Frames
  src="./images/android-user-guide/screenshot-07.png"
  alt="授予权限页面"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-08.png"
  alt="权限设置详情"
  width={1080}
  height={2392}
/>

#### Step 2：配置 Kimi 账号

点击「去配置」，跳转至 Kimi App 进行授权。授权后，Kimi 将自动创建一个 Kimi Coding Plan API Key 用于 Kimi Claw Android。

<Frames
  src="./images/android-user-guide/screenshot-09.png"
  alt="配置 Kimi 账号"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-10.png"
  alt="Kimi 授权页面"
  width={1080}
  height={2392}
/>

如果你是免费用户，需要先开通会员权益，点击「升级订阅」进行会员开通。Kimi Claw Android 需要 Allegretto 等级才可激活。

<Frames
  src="./images/android-user-guide/screenshot-11.png"
  alt="会员升级提示"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-12.png"
  alt="订阅计划选择"
  width={1080}
  height={2392}
/>

#### Step 3：安装 OpenClaw

<Frames
  src="./images/android-user-guide/screenshot-13.png"
  alt="安装 OpenClaw"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-14.png"
  alt="OpenClaw 安装完成"
  width={1080}
  height={2392}
/>

如果安装失败，可以点击「重新安装」重试。多次失败请点击「有问题 去反馈」提交问题。

## Dashboard 使用指南

### 主界面

配置完成后进入 Dashboard 主界面，可以看到以下信息：

- **OpenClaw 网关状态** — 正在启动 / 已连接 / 已停止，以及运行时长
- **聊天渠道** — 当前已连接的通信渠道列表
- **OpenClaw 日志** — OpenClaw 运行的原始日志
- **使用 Kimi 对话** — 打开 Kimi App，打开对应 Kimi Claw Android 的对话界面，并自动切换到对应的 Claw

如果 Dashboard 顶部出现权限提醒，说明有权限未授予或已失效，请按照提示逐项完成授权以确保 Kimi Claw Android 正常运行。

<Frames
  src="./images/android-user-guide/screenshot-15.png"
  alt="Dashboard 启动状态"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-16.png"
  alt="Dashboard 启动完成状态"
  width={1080}
  height={2392}
/>

### 聊天渠道管理

在 Dashboard 中你可以管理所有通信渠道：

- 查看已连接的渠道及状态（如 Kimi - 已连接、飞书 - 已连接）
- 点击「+ 连接」添加新的聊天渠道
- 点击已有渠道可查看详情或删除

<Frames
  src="./images/android-user-guide/screenshot-17.png"
  alt="聊天渠道管理"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-18.png"
  alt="渠道详情"
  width={1080}
  height={2392}
/>

<Callout type="warning">
请保留至少一个聊天渠道，以确保能够与 Kimi Claw Android 正常通信。
</Callout>

### 实时日志

实时日志可以帮助你查看 OpenClaw 的运行状态和排查问题：

- **搜索** — 通过关键词搜索日志内容
- **筛选级别** — 按日志级别（Info / Warning / Error 等）过滤
- **自动追底** — 自动滚动到最新日志
- **刷新** — 手动刷新日志内容

<Frames
  src="./images/android-user-guide/screenshot-19.png"
  alt="实时日志页面"
  width={1080}
  height={2392}
/>

### 设置

点击「设置」进入设置页面：

**功能层：**

- **SkillHub Skills**：自动关联 SkillHub 官网，管理 Kimi Claw Android 可用的技能
- **OpenClaw 工作空间**：进入本机 OpenClaw 配置文件目录，编辑个人偏好

**系统层：**

- **备份与恢复**：备份当前 OpenClaw 配置与历史记录，支持恢复过往配置与记录
- **无障碍服务**：监测手机的无障碍服务权限
- **后台运行权限**：监测手机的后台运行权限
- **版本升级**：监测版本，点击可自动升级

**关于：**

- **帮助**：基础使用建议说明
- **意见反馈**：反馈意见
- **用户协议**：阅读用户协议
- **隐私协议**：阅读隐私协议

<Frames
  src="./images/android-user-guide/screenshot-20.png"
  alt="设置页面"
  width={1080}
  height={2392}
/>

#### SkillHub Skills

打开后自动跳转 SkillHub，可一键下载 Skill 到 Kimi Claw Android。下拉选择自己要下载的 Skill，进入页面，点击安装，即可完成 Skill 的导入。

<Frames
  src="./images/android-user-guide/screenshot-21.png"
  alt="SkillHub Skills 列表"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-22.png"
  alt="Skill 详情页"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-23.png"
  alt="Skill 安装页面"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-24.png"
  alt="Skill 安装完成"
  width={1080}
  height={2392}
/>

#### OpenClaw 工作空间

打开后进入本机 OpenClaw 的运行目录，可在此定义个人 AGENTS.md、HEARTBEAT.md、IDENTITY.md 等。

<Frames
  src="./images/android-user-guide/screenshot-25.png"
  alt="OpenClaw 工作空间"
  width={1080}
  height={2392}
/>

#### 备份与恢复

Kimi Claw Android 提供自动备份与手动备份功能，确保你的 OpenClaw 历史记录与配置不会丢失。

**自动备份**

Kimi Claw Android 会在每次 OpenClaw Gateway 启动成功后，自动备份当前 OpenClaw 的历史记录与配置，将其打包为压缩文件进行保存。无需手动操作，系统会在后台自动完成。

**手动备份**

如果你希望记录某一特定时刻的状态，也可以主动点击备份，手动保存当前的历史记录与配置快照。点击备份，即可导出当下所有配置备份。

<Frames
  src="./images/android-user-guide/screenshot-26.png"
  alt="备份与恢复页面"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-27.png"
  alt="点击备份后自动导出"
  width={1080}
  height={2392}
/>

**恢复配置**

Kimi Claw Android 支持恢复到过往配置状态。同时支持 Kimi Claw Android 的自动备份状态与主动备份的状态。

在以下场景中，你可以通过恢复功能还原到之前的状态：

- 卸载或重装 App 导致历史记录消失时，可恢复过往记录
- 需要切换 Claw 配置时，可恢复到之前保存的配置状态
- 更换手机重新部署时，导入备份文件即可还原

点击备份列表中对应的备份文件，即可自动恢复到该时间点的历史记录与配置，确保过往记录不被抹去。

<Frames
  src="./images/android-user-guide/screenshot-28.png"
  alt="备份恢复页面"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-29.png"
  alt="选择备份类型"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-30.png"
  alt="选择备份文件"
  width={1080}
  height={2392}
/>

## 配置聊天渠道

### Kimi

Kimi 是默认通信渠道，在 Onboarding 流程中完成 Kimi 账号配置后即自动连接，无需额外操作。

安装配置完毕后，你的 Kimi Claw Android 会自动出现在 Web 端与 App 端的 Bot 切换页面，点击切换后头像和聊天 Thread 会同步切换。

<Frames
  src="./images/android-user-guide/screenshot-31.png"
  alt="Kimi Bot 管理"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-32.png"
  alt="Kimi Claw Android 在 Bot 列表中"
  width={1080}
  height={2392}
/>

<Callout type="info">
Kimi Claw Android 在 Bot 管理中仅支持编辑 Bot 名称和删除 Bot 两项操作。
</Callout>

### 飞书

支持三种连接方式：

**方式一：扫码创建（推荐）**

1. 点击「扫码创建」
2. 使用飞书扫描二维码
3. 在浏览器中完成飞书应用创建
4. 等待状态自动更新

<Frames
  src="./images/android-user-guide/screenshot-33.png"
  alt="飞书扫码创建"
  width={1080}
  height={2392}
/>

**方式二：打开飞书创建**

点击「打开飞书创建」，按提示在飞书中完成应用创建，状态自动更新为「已连接」。

<Frames
  src="./images/android-user-guide/screenshot-34.png"
  alt="打开飞书创建"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-35.png"
  alt="飞书应用创建"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-36.png"
  alt="飞书创建完成"
  width={1080}
  height={2392}
/>

**方式三：手动输入 Bot 信息**

1. 点击「手动输入 Bot 信息」
2. 填入 App ID 和 App Secret
3. 点击「添加」完成连接

<Frames
  src="./images/android-user-guide/screenshot-37.png"
  alt="手动输入 Bot 信息"
  width={1086}
  height={534}
/>

删除飞书渠道：点击已连接的飞书渠道，选择删除。删除后将不再通过该飞书机器人与 OpenClaw 通信。

### 微信

微信渠道需要首先在微信端安装微信 Claw，Kimi Claw Android 将通过微信 Claw 终端来对话。

需要首先完成微信官方指导的 Claw 安装，聊天页面出现微信 ClawBot 即完成了安装。

<Frames
  src="./images/android-user-guide/screenshot-38.png"
  alt="微信 Claw 安装 1"
  width={1280}
  height={813}
/>

<Frames
  src="./images/android-user-guide/screenshot-39.png"
  alt="微信 Claw 安装 2"
  width={1206}
  height={2622}
/>

<Frames
  src="./images/android-user-guide/screenshot-40.png"
  alt="微信 Claw 安装 3"
  width={1206}
  height={2622}
/>

进入 Kimi Claw Android，连接微信渠道，用微信扫码完成。

<Frames
  src="./images/android-user-guide/screenshot-41.png"
  alt="连接微信渠道"
  width={1206}
  height={2622}
/>

<Frames
  src="./images/android-user-guide/screenshot-42.png"
  alt="微信扫码连接"
  width={1080}
  height={2392}
/>

<Frames
  src="./images/android-user-guide/screenshot-43.png"
  alt="微信扫码等待连接"
  width={1080}
  height={2392}
/>

## Automation 自动化

Kimi Claw Android 的核心能力之一是操控手机上的 App 来完成各类任务。通过 Kimi、飞书、微信等聊天渠道向 Claw 发送指令后，Claw 会自动在手机上打开对应的 App，像真人一样执行一系列操作，最终完成你指定的任务。

### 工作原理

当你通过聊天渠道向 Claw 发送任务指令时，Claw 会：

1. 理解你的任务需求
2. 自动打开手机上对应的 App
3. 通过模拟用户操作（点击、滑动、输入等）逐步完成任务
4. 在执行过程中进行截图记录，方便你查看执行过程
5. 完成任务后向你汇报执行结果

<Callout type="warning">
自动化功能运行比较慢，推荐使用闲置手机。
</Callout>

### 典型使用场景

#### 购物与消费

在淘宝、天猫、美团等平台搜索商品、加入购物车、查看订单、领取优惠等。

#### 出行与导航

在高德地图查询打车价格、查看地铁时刻、搜索附近酒店、预约出行等。

#### 社交与内容

在小红书、抖音等平台查看消息、浏览内容、搜索商品、互动操作等。

## 使用技巧

### 通过聊天软件操控手机

配置完成后，你可以在 Kimi、飞书、微信中向 Claw 发送指令，远程操控安卓手机上的应用。例如：

- "帮我打开微信，看看最新消息"
- "打开地图，搜索附近的餐厅"
- "帮我查看日历，看看今天有什么安排"

### 使用 SkillHub Skills

Kimi Claw Android 内置了 SkillHub 技能库，你可以在设置中管理和安装技能，为 Claw 扩展更多能力。

**适合使用 Skill 的场景：**

- **信息整理**：新闻汇总、竞品对比
- **数据分析**：行情梳理、数据解读
- **工作流自动化**：从需求拆解到输出的一整套流程

### 多渠道同时在线

你可以同时连接 Kimi、飞书、微信等多个渠道，在不同的聊天软件中都能和 Claw 对话。在 Dashboard 的渠道管理中点击「+ 连接」即可添加。

## 安全与受限应用

### 安全须知

使用 Kimi Claw Android 前，请注意以下安全事项：

1. **使用闲置手机** — Kimi Claw Android 会占用手机操作权限，可能影响日常使用，建议使用闲置手机
2. **敏感数据隔离** — Kimi Claw Android 会读取本机文件数据，请提前清理或隔离敏感信息
3. **金融应用保护** — 系统已自动禁止访问银行、支付、证券、保险类应用，保障资金安全。同时也强烈建议不要安装银行、支付、证券、保险等金融类 App 在当前手机

### 受限应用列表

出于用户资金和隐私安全考虑，以下类别的应用被 Kimi Claw Android 自动禁止访问，无法通过远程指令操作：

#### 社交类（Social）- 1 个

| # | Package | 别名 | 风险说明 |
|---|---------|------|---------|
| 1 | wechat | 微信，wechat | 涉及重要私人社交与支付功能 |

#### 银行类（Banking）- 20 个

| # | Package | 别名 | 风险说明 |
|---|---------|------|---------|
| 1 | com.android.bankabc | abc, 农业银行 | 中国农业银行，可进行转账、理财等操作 |
| 2 | com.bankcomm.main | bocom, 交通银行 | 交通银行，可进行转账、理财等操作 |
| 3 | com.bjbk.im | 北京银行 | 北京银行，可进行转账、理财等操作 |
| 4 | com.cebbank.im | 光大银行 | 中国光大银行，可进行转账、理财等操作 |
| 5 | com.cgb.im | 广发银行 | 广发银行，可进行转账、理财等操作 |
| 6 | com.chinamworld.bocmbci | boc, 中国银行 | 中国银行，四大行之一 |
| 7 | com.chinamworld.main | ccb, 建设银行 | 中国建设银行，四大行之一 |
| 8 | com.cib.im | 兴业银行 | 兴业银行，可进行转账、理财等操作 |
| 9 | com.citic.im | 中信银行 | 中信银行，可进行转账、理财等操作 |
| 10 | com.cmbc.im | 民生银行 | 中国民生银行，可进行转账、理财等操作 |
| 11 | com.cmbchina.ccd.pluto.customerView | cmb, 招商银行 | 招商银行，可进行转账、理财等操作 |
| 12 | com.hxb.im | 华夏银行 | 华夏银行，可进行转账、理财等操作 |
| 13 | com.hzbk.im | 杭州银行 | 杭州银行，可进行转账、理财等操作 |
| 14 | com.icbc | icbc, 工商银行 | 中国工商银行，四大行之一 |
| 15 | com.jsbk.im | 江苏银行 | 江苏银行，可进行转账、理财等操作 |
| 16 | com.nbbk.im | 宁波银行 | 宁波银行，可进行转账、理财等操作 |
| 17 | com.pingan.paces.cloud | 平安口袋银行 | 平安银行手机客户端 |
| 18 | com.psbc.im | 邮储银行 | 中国邮政储蓄银行 |
| 19 | com.shbk.im | 上海银行 | 上海银行，可进行转账、理财等操作 |
| 20 | com.spdb.im | 浦发银行 | 上海浦东发展银行 |

#### 支付类（Payment）- 6 个

| # | Package | 别名 | 风险说明 |
|---|---------|------|---------|
| 1 | com.eg.android.AlipayGphone | alipay, 支付宝 | 支付宝，中国最大的第三方支付平台 |
| 2 | com.paypal.android.p2pmobile | paypal | PayPal，全球最大的在线支付平台 |
| 3 | com.unionpay | ysf, 云闪付 | 中国银联云闪付，银行卡支付工具 |
| 4 | com.squareup.cash | cashapp | Cash App，美国移动支付平台 |
| 5 | com.venmo | venmo | Venmo，美国 P2P 支付平台 |
| 6 | com.google.android.apps.walletnfcrel | googlewallet, wallet | Google Wallet，Google 支付钱包 |

#### 证券/股票类（Securities）- 17 个

| # | Package | 别名 | 风险说明 |
|---|---------|------|---------|
| 1 | com.citics.pbm | citic, 信e投 | 中信证券交易客户端 |
| 2 | com.cmschina.stock | 招商证券 | 招商证券交易客户端 |
| 3 | com.csc108.newpda | 中信建投 | 中信建投证券交易客户端 |
| 4 | com.dfzq.stock | 东方证券 | 东方证券交易客户端 |
| 5 | com.eastmoney.android.berlin | eastmoney, 东方财富 | 东方财富，股票/基金交易平台 |
| 6 | com.ebscn.stock | ebscn, 金阳光 | 光大证券交易客户端 |
| 7 | com.foundersc.stock | founder, 小方 | 方正证券交易客户端 |
| 8 | com.gf.gfstocks | 广发易淘金 | 广发证券交易客户端 |
| 9 | com.guosen.stock | guosen, 金太阳 | 国信证券交易客户端 |
| 10 | com.guotai.junan.guiyang | 国泰君安 | 国泰君安证券交易客户端 |
| 11 | com.hexin.plat.android | ths, 同花顺 | 同花顺，股票/基金交易及行情平台 |
| 12 | com.htsc.mdc | huatai, 涨乐财富通 | 华泰证券交易客户端 |
| 13 | com.htsec.android | 海通证券 | 海通证券交易客户端 |
| 14 | com.pingan.stock | 平安证券 | 平安证券交易客户端 |
| 15 | com.tfzq.stock | 天风证券 | 天风证券交易客户端 |
| 16 | com.xueqiu.android | xueqiu, 雪球 | 雪球，股票社区及交易平台 |
| 17 | com.xyzq.stock | 兴业证券 | 兴业证券交易客户端 |

#### 保险/金融类（Insurance/Financial）- 2 个

| # | Package | 别名 | 风险说明 |
|---|---------|------|---------|
| 1 | com.pingan.lifeinsurance | 平安金管家 | 中国平安保险，可进行保险购买、理赔等操作 |
| 2 | com.jd.jrapp | 京东金融 | 京东金融，提供理财、借贷、支付等金融服务 |

## 支持与不支持的功能

### 支持的功能

| 功能 | 说明 |
|------|------|
| 远程操控手机应用 | 通过聊天软件指令远程使用手机上的 App |
| 多渠道通信 | 支持通过 Kimi、飞书、微信与 Claw 通信 |
| 实时日志查看 | 查看 OpenClaw 网关运行日志，支持搜索和级别筛选 |
| 配置备份与恢复 | 备份当前配置，可在重新安装或更换设备后恢复 |
| 网关状态监控 | 实时查看 OpenClaw 网关连接状态和运行时长 |
| 渠道管理 | 添加、查看、删除通信渠道 |
| OpenClaw Dashboard | 通过内置 Dashboard 管理 OpenClaw |

### 不支持的功能与限制

| 限制项 | 说明 |
|--------|------|
| iOS 设备 | 当前仅支持 Android 设备，不支持 iOS |
| 会员限制 | 需开通 Allegretto 及以上 Kimi 会员方可使用 |
| 金融类 App 操作 | 银行、支付、证券、保险类应用被禁止访问（详见第 7 章） |
| Bot 管理能力 | Kimi Claw Android 的 Bot 仅支持编辑名称和删除，不支持其他 Bot 配置 |
| 终端/命令行 | Kimi Claw Android 暂不提供终端直接操作能力 |

## 常见问题（FAQ）

### 安装与配置

**安装 OpenClaw 失败怎么办？**

- 请确保存储空间充足（至少 5GB），安装过程中不要退出应用或锁屏
- 点击「重新安装」重试
- 多次失败请点击「有问题 去反馈」提交问题

**权限授权后，状态没有更新？**

- 部分手机品牌的权限授予需要重启应用才能生效
- 请返回 Kimi Claw Android，如果状态未更新，可以尝试关闭并重新打开 App

**免费用户可以使用吗？**

- 目前需要开通 Allegretto 及以上 Kimi 会员权益才能使用 Kimi Claw Android
- 在配置 Kimi 账号步骤中点击「去升级」即可开通

**恢复配置提示「配置文件无效」？**

- 备份文件可能已损坏或来自不兼容的版本
- 请使用「Kimi App 一键配置」重新配置

### 连接与稳定性

**网关状态一直显示「正在启动」？**

- 网关启动速度跟手机性能有关，请耐心等待 2 分钟
- 检查网络连接是否正常
- 确认已授予全部所需权限（通知、电池优化、存储、自启动）
- 尝试在设置中点击「备份与重启」重启网关服务

**网关突然断开连接？**

- 检查手机所在网络是否正常
- 检查手机是否进入了省电模式，导致后台应用被清理
- 确认「忽略电池优化」和「自启动权限」已正确授予
- 在 Dashboard 查看网关状态，如果显示「已停止」，点击重启

**手机锁屏后 Kimi Claw Android 掉线？**

- 这通常是因为手机的电池优化策略导致后台应用被杀死
- 请确保已完成以下设置：
  - 忽略电池优化 — 已授权
  - 自启动权限 — 已开启
  - 耗电管理 — 选择「完全允许后台行为」

### 渠道与通信

**可以同时连接多个聊天渠道吗？**

- 可以。你可以同时连接 Kimi、飞书、微信等多个渠道
- 在 Dashboard 的渠道管理中点击「+ 连接」添加即可
- 请至少保留一个渠道以确保正常通信

**飞书扫码后一直等待状态更新？**

- 请确保在浏览器中完成了飞书应用的创建流程
- 如果长时间未更新，可以尝试手动输入 Bot 信息的方式连接

**为什么在 Kimi App 里看不到 Kimi Claw Android？**

- 请确认 Onboarding 流程已全部完成（权限授予 → 安装 OpenClaw → 配置 Kimi 账号）
- 检查 Dashboard 中网关状态是否为「已连接」
- 尝试在 Kimi App 中刷新 Bot 列表

### 功能使用

**为什么某些应用无法远程操作？**

- 出于安全考虑，银行、支付、证券、保险等金融类应用已被系统自动禁止访问
- 完整列表详见第 7 章「受限应用列表」

**为什么需要使用闲置手机？**

- Kimi Claw Android 操作 App 时可能影响你的正常使用
- 使用闲置手机可以避免权限冲突，也能保护你的隐私数据
- OpenClaw Gateway 需要稳定的网络环境，所以手机最好插电在 WiFi 网络运行

**如何更换手机重新部署？**

- 在旧手机的 Dashboard → 设置 →「备份与重启」中导出配置文件
- 在新手机安装 Kimi Claw Android
- 在 Step 3 选择「恢复配置」，导入之前的备份文件即可

**如何查看 Kimi Claw Android 的运行状态？**

- 在 Dashboard 主界面可以查看网关状态和运行时长
- 点击「实时日志」可以查看详细的运行日志
- 通过日志的搜索和级别筛选功能，可以快速定位问题

### 升级与版本

**如何升级 Kimi Claw Android？**

- 在 Dashboard → 设置 →「版本升级」中检查并升级到最新版本
- 建议在 Wi-Fi 环境下进行升级

**可以手动升级 OpenClaw 版本吗？**

- 不建议手动升级。手动升级可能导致兼容性问题
- 官方会在适配完成后通过应用内推送升级

## 反馈与帮助

如果你在使用过程中遇到问题或有建议：

**应用内反馈**

- Dashboard → 设置 → 用户反馈
- OpenClaw 安装页面 →「有问题 去反馈」

**反馈时请提供：**

- 你的 Kimi Claw Android ID（在点击 Kimi 渠道时可以看到）
- 设备型号和 Android 版本
- 问题描述和截图

<Callout type="info">
提供 Kimi Claw Android ID 有助于技术人员快速定位问题，请在反馈时一并附上。
</Callout>
