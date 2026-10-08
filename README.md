<p align="center">
  <img src="assets/icon.png" width="128" height="128" alt="SIMHub">
</p>

<h1 align="center">SIMHub 下载</h1>

SIMHub 是一款管理实体 SIM / eSIM 卡的 App（iPhone / iPad，以及 Android）：接上读卡器就能管理 eSIM 芯片卡里的 Profile，还能让读卡器里的卡直接在手机上用 Wi-Fi 通话收发短信、打接电话。

> **2026-10-07 起 SIMHub 已从 App Store 移除，正在申诉中。** 已经安装的用户可以继续使用，但无法从 App Store 重新下载。这里提供 IPA 安装包，供已有用户换机 / 重装使用。本仓库只放安装包，不含源代码。

## 下载

去 [Releases](../../releases) 页面下载：

| 平台 | 版本 | 文件 | 要求 | 说明 |
|---|---|---|---|---|
| iOS / iPadOS | 29.11 (1) | `esimSubscription.ipa` | iOS / iPadOS 17.0 及以上 | 与 App Store 最后一版相同 |
| Android | 0.1.2 (3) | `SIMHub-Android-0.1.2.apk` | Android 8.0 及以上 | 见下方「Android 版」 |

## 怎么安装

这个 IPA 是 Ad Hoc 签名，只能直接装到开发者登记过的设备上。其他设备需要**用自己的 Apple ID 重新签名**后安装，常用工具：

- [AltStore](https://altstore.io)（Mac / Windows 配合 AltServer）
- [Sideloadly](https://sideloadly.io)（Mac / Windows）
- 其他自签工具（轻松签、牛蛙助手等）

重签时请注意：

1. 免费 Apple ID 签出来的 App **7 天到期**，到期前用同一工具刷新一次即可，数据不会丢；付费开发者账号一年。
2. 重签时请**去掉**这几项权限（工具里一般叫「移除权限 / Remove entitlements」）：iCloud（CloudKit）、推送通知（aps-environment）、密码自动填充（autofill-credential-provider）。免费账号签不了这些，不去掉会安装失败。去掉后 iCloud 同步和推送不可用，其他功能不受影响。
3. App Group 和 Bundle ID 按工具默认处理即可。

## Android 版

[下载 SIMHub-Android-0.1.2.apk](../../releases/tag/android-v0.1.2)

**安装**：在 Android 手机上下载 APK 后打开，按提示允许浏览器或文件管理器「安装未知应用」即可，不需要重签。

**说明**：

- Android 版的读卡器只支持 **USB（CCID）读卡器**，需要手机支持 USB OTG；暂不支持蓝牙读卡器、4G 模块和 Mac / NAS 转发。
- Wi-Fi 通话、短信、打接电话（系统通话界面）、卡片台账与到期提醒等功能与 iOS 版一致。
- 本 APK 与 Google Play 测试版**签名不同，不能互相覆盖安装**。换渠道前请先在 App 内导出备份，卸载后再安装新的。
- 不支持紧急呼叫；为防诈骗，不支持拨打中国大陆号码（+86）。
- 校验文件：Release 页面写有签名证书和 APK 的 SHA-256。

## 主要功能

- **读卡器 eSIM 管理**：USB（CCID）或蓝牙读卡器，读取 EID / ICCID，启用、停用、删除、下载 Profile；支持 5ber、Xesim、eSTK、9eSIM 等多芯片卡与 SIM PIN。
- **Wi-Fi 通话**：读卡器里的卡直接在手机上收发短信、打接电话（IKEv2 / IPsec、EAP-AKA、IMS），带运营商适配表；电话风格的信息 / 通讯录 / 拨号 / 通话记录。
- **4G 模块**：外接 4G 模块作为卡源。
- **Mac / NAS 转发**：把 Mac 或 NAS 上的读卡器、模块卡经局域网或 Tailscale 借给手机用。
- **卡片台账**：每张卡的订阅、流量、账单与到期提醒，日历集成、小组件；五种语言。

## 数据安全

- 所有数据只存在本机（和你自己的 iCloud），不经过任何第三方服务器。
- 换机或重装前请先在 App 内**导出备份**，重装后再导入（iOS 与 Android 的备份文件互通）。

## 校验

`esimSubscription.ipa` (29.11) SHA-256：

```
7e17d1411c244760e00971e0fb9ddbbfe7a6e8b84577130478e9261ec1b43af4
```

## 反馈

问题和建议请发 [Issues](../../issues)。
