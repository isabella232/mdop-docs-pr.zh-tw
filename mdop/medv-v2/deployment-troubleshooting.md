---
title: 部署疑難排解
description: 部署疑難排解
author: dansimp
ms.assetid: 9ee980f2-4e77-4020-9f0e-8c2ffdc390ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe9677175c9538bc070d2adea17a96351397d9a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809632"
---
# 部署疑難排解


本主題包含的資訊可協助您針對 Microsoft 企業版桌面虛擬化（MED-V）2.0 中的部署問題進行疑難排解。

## MED-V 部署中的疑難排解問題


在您部署 MED-V 時，可能會發生下列問題。 此方案可協助您解決這個問題。

**如果您只為目前的使用者安裝 MED-V，就會發生問題。** MED-V 只支援安裝 MED-V 工作區包裝程式、MED-V 主機代理程式，以及所有使用者的 MED-V 工作區。 安裝目前的使用者只會在元件安裝和 MED-V 工作區的設定中造成失敗。

**解決方案**

安裝 MED-V 元件時，請勿使用選項**ALLUSERS = ""** 。

**MED-V 需要獨佔使用虛擬化堆疊。** 一次只能在電腦上執行一個虛擬化堆疊。 Windows 虛擬電腦必須使用虛擬堆疊，而 MED-V 則視 Windows 虛擬電腦而定。 因此，如果您嘗試在執行使用虛擬堆疊的其他應用程式時，部署或使用 MED-V，則無法執行或成功安裝 MED-V。

**解決方案**

在您安裝或執行 MED-V 之前，請先關閉執行使用虛擬化堆疊的任何應用程式。

**[快捷方式] 會在卸載後保留。** 根據預設，當您卸載 MED-V 時，系統會移除最終使用者 [**開始**] 功能表中的快捷方式。 不過，在某些情況下（例如，在執行漫遊設定檔的使用者），MED-V 發佈的應用程式的快捷方式仍會保留在使用者的 [**開始**] 功能表中。

**解決方案**

若要手動刪除 [**開始**] 功能表上剩餘的快速鍵，請以滑鼠右鍵按一下快捷方式，然後按一下 [**移除**]。

**[MED-V 工作區] 中的 [停用登入訊息群組原則] 設定。** 如果在 MED-V 工作區啟用 Windows XP 登入訊息，則使用者必須在每次想要開啟 MED-V 虛擬應用程式時登入。 這會產生較差的使用者體驗。

**解決方案**

在 MED-V 虛擬機器中停用下列群組原則設定：

**互動式登入: 給登入使用者的訊息本文**

**互動式登入: 給登入使用者的訊息標題**

## 相關主題


[作業疑難排解](operations-troubleshooting-medv2.md)

 

 





