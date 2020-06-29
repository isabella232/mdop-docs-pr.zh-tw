---
title: 設定環境先決條件
description: 設定環境先決條件
author: dansimp
ms.assetid: 7379e8e5-1cb2-4b8e-8acc-5c04e26f8c91
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8d6fc3b81f6dafbe709dd904b9fba6124d2f6b6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811762"
---
# 設定環境先決條件


在您可以部署並執行 Microsoft 企業版桌面虛擬化（MED-V）2.0 之前，您必須確保您的環境符合下列最低先決條件。

**Windows 7**

MED-V 主機代理程式和 MED-V 工作區包裝程式僅適用于 Windows 7 或更新版本。

**Windows XP SP3**

只有在 Windows XP SP3 中才支援 MED-V 來賓代理程式。

**.NET Framework 3.5 SP1**

MED-V 主機和來賓代理與 MED-V 工作區封裝程式需要 Microsoft .NET Framework 3.5 SP1。

**重要** 您也必須安裝更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) ，這會解決幾個已知的應用程式相容性問題。

 

**記事** 您必須將 .NET Framework 3.5 SP1 和更新 KB959209 手動安裝到您準備搭配 MED-V 使用的 Windows 虛擬電腦映射中。 不過，當您在主機電腦上安裝 Windows 7 時，預設會包含 Microsoft .NET Framework 3.5 SP1 和更新。

 

**Active Directory 基礎結構**

[群組原則] 可在 Active Directory 環境中提供作業系統、應用程式及使用者設定的集中式管理和配置。

## 相關主題


[設定安裝必要條件](configure-installation-prerequisites.md)

[高階架構](high-level-architecturemedv2.md)

[MED-V 2.0 支援的組態](med-v-20-supported-configurations.md)

 

 





