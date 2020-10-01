---
title: 從 MBAM 2.5 升級至 MBAM 2.5 SP1
description: 從 MBAM 2.5 升級至 MBAM 2.5 SP1
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 2/16/2018
ms.openlocfilehash: 330ded822dd9da96a1c33eabcb31d744044dc28e
ms.sourcegitcommit: ae34c5cb5e7979b472b257a4691142e493d5d6fe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "11091618"
---
# 從 MBAM 2.5 升級至 MBAM 2.5 SP1
本主題描述升級 Microsoft BitLocker 管理和監視 (MBAM) Server 2.5 和 MBAM 用戶端（從2.5 到 MBAM 2.5 SP1）的程式。

### 開始之前
#### 下載2019年5月的服務發行
[桌面優化套件](https://www.microsoft.com/download/details.aspx?id=58345)

#### 下載2018年7月的服務發行
[桌面優化套件](https://www.microsoft.com/download/details.aspx?id=57157)


#### 確認安裝 documentaion
確認您有 MBAM 環境的目前檔，包括所有伺服器名稱、資料庫名稱、服務帳戶及其密碼。

### 升級步驟
####  (SQL Server) 升級 MBAM 資料庫的步驟
1. 使用 MBAM 配置器;從 SQL server 移除 [報表] 角色，或從任何託管 SSRS 資料庫的位置移除。 視您的環境而定，這可以是同一個伺服器或不同的伺服器。
  > [!NOTE]
  > 您將不會看到移除資料庫的選項;此為預期。  
2. 從大量授權服務中心網站使用 MDOP-Microsoft 桌上型電腦優化套件2015安裝 2.5 SP1 (：  <https://www.microsoft.com/Licensing/servicecenter/default.aspx>
3. 目前不要設定 
4. 使用 MBAM 配置器;重新新增報表角色
5. 使用 MBAM 配置器;在 SQL Server 上重新新增 SQL 資料庫角色
6. 在結束時，系統會警告您已經存在並無法建立該系統，但預期
7. 這個程式會將現有的資料庫更新為目前安裝的版本。              

#### 升級 MBAM 伺服器 (執行 MBAM 和 IIS 的步驟) 
1. 使用 MBAM 配置器;從 IIS 伺服器移除系統管理和自助服務入口網站
2. 安裝 MBAM 2.5 SP1
3. 目前不要設定  
4. 使用 MBAM 配置器;將系統管理和自助服務入口網站重新新增至 IIS 伺服器 
5. 開啟提升許可權的命令提示字元，輸入 [ **IISRESET**]，然後按 Enter。
 
#### 升級 MBAM 用戶端/端點的步驟
1. 從用戶端端點卸載2.5 代理程式
2. 在用戶端端點上安裝 2.5 SP1 代理程式
3. 將5月的2019匯總用戶端更新推送到執行 2.5 SP1 代理程式的用戶端 
4. 安裝2019匯總前，不需要先卸載現有的用戶端。  
