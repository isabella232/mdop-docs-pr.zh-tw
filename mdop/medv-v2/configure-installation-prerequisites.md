---
title: 設定安裝必要條件
description: 設定安裝必要條件
author: dansimp
ms.assetid: ff9cf28a-3eac-4b6c-8ce9-bfc202f57947
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6cd9379804c45a2025064a6eecf363c010980369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802165"
---
# 設定安裝必要條件


下列指示是安裝及使用 Microsoft 企業版桌面虛擬化（MED-V）2.0 的先決條件：

[Windows 虛擬電腦](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7)

[Windows 虛擬電腦更新](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update)

[防病毒/備份軟體設定](#bkmk-antivirusbackupsoftwareconfiguration)

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7"></a>如何安裝和設定 Windows 虛擬電腦


**重要** 如果主機電腦上已存在 Windows 版 Virtual PC，您必須先將其卸載，才能安裝 Windows 虛擬電腦。

 

**若要安裝 Windows Virtual 電腦**

1.  從 Microsoft 下載中心下載[Windows 虛擬電腦](https://go.microsoft.com/fwlink/?LinkId=195918)（ https://go.microsoft.com/fwlink/?LinkId=195918) 。

2.  在主機電腦上執行安裝檔，然後依照嚮導中的步驟進行。

**重要** Windows 虛擬電腦包含整合元件套件，提供可改善虛擬環境與物理電腦之間互動的功能。 例如，它可讓您在主機和來賓電腦之間移動滑鼠。 MED-V 需要安裝 [整合元件套件]。

 

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update"></a>如何安裝和設定 Windows 虛擬電腦更新


與文章 KB977206 相關聯的 Microsoft 更新會針對沒有硬體協助虛擬化（HAV）技術的電腦啟用 Windows XP 模式。 我們建議您安裝此更新，因為如果客體作業系統中的整合元件套件與主機電腦上安裝的 Windows Virtual 電腦版本不相符，部分整合功能可能無法正常運作。

**重要** 當您在執行 Windows 7 的主機電腦上安裝 MED-V-V （Service Pack 1）時，您不需要安裝此更新。

 

**秘訣** 除了這裡列出的更新之外，我們建議您查看所有可用的 Windows 虛擬電腦更新，並針對您的環境套用適當或必要的更新。

 

**若要安裝 Windows Virtual 電腦更新**

1.  從 Microsoft 下載中心下載所需的 Windows Virtual PC 更新。

    [32 位更新](https://go.microsoft.com/fwlink/?LinkId=195919)（ https://go.microsoft.com/fwlink/?LinkId=195919) 。

    [64 位更新](https://go.microsoft.com/fwlink/?LinkId=195920)（ https://go.microsoft.com/fwlink/?LinkId=195920) 。

2.  在主機電腦上以提升模式執行安裝檔案，然後依照嚮導中的步驟執行。

    如需適用于 Windows Virtual 電腦之修復程式套件的詳細資訊，請參閱[文章 977206](https://go.microsoft.com/fwlink/?LinkId=195921) （ https://go.microsoft.com/fwlink/?LinkId=195921) 。

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a>如何設定防毒軟體/備份軟體


為了防止防病毒活動影響虛擬桌面電腦的效能，我們建議您將下列虛擬機器檔案類型排除在主機電腦上執行的任何防毒軟體或備份程式中：

-   \*.VMC

-   \*.VUD

-   \*.VSV

-   \*.VHD

## 相關主題


[設定環境先決條件](configure-environment-prerequisites.md)

[高階架構](high-level-architecturemedv2.md)

[MED-V 2.0 支援的組態](med-v-20-supported-configurations.md)

 

 





