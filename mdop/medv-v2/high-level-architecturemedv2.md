---
title: 高階架構
description: 高階架構
author: dansimp
ms.assetid: a00edb9f-207b-4f32-9e8f-522ea2739d2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a5db4a56b2abfb0df19b0d6d86f4bf88380c2bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812267"
---
# 高階架構


本節說明 Microsoft 企業桌面虛擬化（MED-V）2.0 的高層次系統架構和元件設計。

## 系統架構


MED-V 可增強 Windows 虛擬電腦，在一個裝置上執行兩個作業系統、新增虛擬影像傳遞、群組原則的資源調配，以及集中式管理。 透過使用 MED-V，您可以在任何執行 Windows 7 專業版、企業版或 Windows 7 旗艦版的 Windows 桌上型電腦上，輕鬆地設定、部署及管理企業 Windows 虛擬電腦影像。 MED-V 方案包含下列元件：

<a href="" id="---------------med-v-host"></a> **MED-V 主機**  
Windows 7 環境，其中包含 MED-V 主機代理程式、電子軟體發佈（ESD）系統、註冊表管理系統和 MED-V 來賓。 MED-V 主機會與 MED-V 來賓互動，讓您可以處理某些設定函數和系統資訊。

<a href="" id="-------------------med-v-host-agent"></a> **MED-V 主機代理程式**  
MED-V 主機中包含的 MED-V 軟體，提供與 MED-V 來賓進行通訊的通道。 它也提供第一次設定和應用程式發佈等功能。

**記事** 已安裝 MED-V 和其必要元件之後，必須設定 MED-V-V。 MED-V 的設定稱為第一次設定。

 

<a href="" id="esd-system"></a>**ESD 系統**  
您的現有軟體發佈方法，可讓您部署並安裝 MED-V 所建立的 MED-V 工作區套件檔案。

<a href="" id="registry-management-system"></a>**註冊管理系統**  
您現有的管理群組原則設定和喜好設定的方法。

<a href="" id="windows-virtual-pc-image"></a>**Windows 虛擬電腦影像**  
系統管理員定義的虛擬機器，內含下列元件：

<a href="" id="corporate-operating-system"></a>**公司作業系統**  
您的標準公司作業系統。

<a href="" id="management-and-security-tools"></a>**管理和安全性工具**  
您的標準管理和安全性工具，例如防防毒保護。

<a href="" id="-----------------------med-v-guest"></a> **MED-V 來賓**  
Windows XP SP3 環境，是在 Windows 7 上執行的 windows 虛擬電腦（包含下列元件）的一部分：

<a href="" id="---------------------------med-v-guest-agent"></a> **MED-V 來賓代理程式**  
MED-V 來賓中包含的 MED-V 軟體，提供與 MED-V 主機進行通訊的通道。 它也支援 MED-V 主機代理程式，其中包含執行第一次設定等函數。

**記事** MED-V 來賓代理程式會在第一次設定期間自動安裝。

 

<a href="" id="esd-client"></a>**ESD 用戶端**  
ESD 系統的選擇性元件，可將軟體套件及報告狀態安裝至 ESD 系統。

## 相關主題


[規劃應用程式作業系統相容性](planning-for-application-operating-system-compatibility.md)

[準備 MED-V 的部署環境](prepare-the-deployment-environment-for-med-v.md)

 

 





