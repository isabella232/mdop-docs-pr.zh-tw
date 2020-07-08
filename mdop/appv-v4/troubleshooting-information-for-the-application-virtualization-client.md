---
title: Application Virtualization Client 的疑難排解資訊
description: Application Virtualization Client 的疑難排解資訊
author: dansimp
ms.assetid: 260a8dad-847f-4ec0-b7dd-6e6bc52017ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c2ab332f5f3b7f8cdc40f6d35e8712d55028a60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800770"
---
# Application Virtualization Client 的疑難排解資訊


本主題包含一些資訊，您可以用來針對應用程式虛擬化（App-v）用戶端的各種問題進行疑難排解。

## 發佈更新非常慢


如果在特定電腦上發佈重新整理所需的時間比預期更長，且如果用戶端設定為使用**IconSourceRoot**設定，請判斷**IconSourceRoot**是否包含不正確 URL。 不完整的 URL 會在發佈重新整理時產生很長的延遲。

## 使用者無法連線到伺服器並進入中斷連接的操作模式


當您使用以 RTSPS 通訊協定設定的 App-v 管理伺服器時，如果使用者無法連線並進入中斷連接的操作模式，請判斷在伺服器上使用的憑證是否有效。 不正確憑證會防止使用者連線，並會導致使用者進入斷開連接的操作模式。

## <a href="" id="users-experience-slow-performance-when-applications-are-not-fully-cached-"></a>當應用程式未完全緩存時，使用者遇到效能降低的問題


當應用程式不完全快取時，使用者在啟動或使用應用程式時，有時候可能會遇到暫時緩慢或斷斷續續的效能。 有幾個可能的原因，例如，當 App-v 用戶端正在自動載入應用程式的程式中，或正在處理不連續的要求時，就會發生這種情況。 當應用程式完全緩存時，這些問題就不會再發生。

## <a href="" id="error-displayed-after-an-update-is-removed-"></a>移除更新後顯示錯誤


您必須使用正確的 Windows Installer 3.1 命令格式，才能從應用程式 V 用戶端移除更新，如下所示：

`Msiexec /I {F82584A0-D706-4D2D-9BC1-7E6D8BE3BB0F} MSIPATCHREMOVE={BE3DD018-9A1F-40FD-9538-C0A995CBD254} /qb /l*v "Uninstall.log"`

使用較舊的命令格式時，會 `msiexec /package <GUID> /uninstall <GUID>` 導致錯誤6003「Application Virtualization 用戶端無法啟動」。

## 當您嘗試啟動應用程式時，發生錯誤碼 0A-0000E01E


錯誤碼 0A-0000E01E 表示順序式應用程式套件可能已損毀。 解決方案是 resequence 套件。

## 使用者無法存取他們在 Q：磁片磁碟機上建立的檔案


如果使用者將檔案儲存到**Q：** 磁片磁碟機，他們就無法取得磁片磁碟機的讀取權限。 使用者不應該將檔案儲存至**Q：** 磁片磁碟機。

## 出現1D1 錯誤的使用者


當檔案流式 URL 在開啟的軟體描述項（OSD）檔案中設定不正確時，App-v 用戶端會傳回1d1 錯誤，而不是「找不到檔案」錯誤。 此錯誤表示應用程式啟動失敗，且使用者已強制進入中斷線上作業模式。 修正檔案流式處理 URL。

## 與某些應用程式相關聯的不正確圖示


若要在發佈作業中使用圖示，App-v 用戶端首先會判斷它是否已有圖示的快取複本，方法是在圖示快取中，查看原始來源路徑符合發佈作業所提供之圖示路徑的專案。 如果 App-v 用戶端找到一個相符的專案，則會使用已緩存的圖示;否則，它會將新的圖示下載到快取中。 如果圖示的路徑是臨時目錄，或是在新的圖示或套件中重複使用，則在快取中的查閱可能會從先前的操作中挑選錯誤的圖示。

## 啟動應用程式時，系統會提示使用者輸入認證


如果使用者嘗試啟動的虛擬應用程式是系統管理員限制存取權，使用者可能會收到輸入認證的提示。 使用者應該輸入擁有啟動該應用程式許可權的帳戶的使用者名稱和密碼，然後按 ENTER。

## 將 App-v 用戶端升級到版本4.5 之後，發佈更新失敗


如果使用者資料目錄之前放在非標準位置（%*AllUsersProfile*%\\Documents\\SoftGrid Client\\Users\\%*username*%），在電腦上沒有系統管理員許可權的使用者將會發現發佈更新在升級 app-v 用戶端後失敗。 在升級期間，App-V 用戶端全域資料目錄及其所有子目錄都是以系統管理員的限制存取權進行設定。 您可以在升級前變更使用者資料目錄，讓它不是全域資料目錄的子目錄，來避免這個問題。

## 安裝失敗後需要重新開機


如果用戶端安裝因任何原因而失敗，而且後續嘗試安裝用戶端也失敗，請檢查 Windows 安裝程式記錄檔，看看是否顯示「sftplay 失敗，error = 1072」錯誤。 如果是，請在再次嘗試安裝用戶端之前重新開機電腦。

## 修復損毀的虛擬應用程式


如果由於任何原因使用 Windows 安裝程式套件（MSI）檔案安裝的虛擬應用程式套件遭到損毀，請重新安裝套件。 Windows Installer 中提供的修復函數將不會更新使用者的磁片量。

## 相關主題


[Application Virtualization Client 參考資料](application-virtualization-client-reference.md)

 

 





