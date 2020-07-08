---
title: 關於 App-V 封裝加速器 (App-V 4.6 SP1)
description: 關於 App-V 封裝加速器 (App-V 4.6 SP1)
author: manikadhiman
ms.assetid: fc2d2375-8f17-4a6d-b374-771cb947cb8c
ms.reviewer: ''
manager: dansimp
ms.author: v-madhi
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cb7b8e6fa9482838283257843caf4b291c03bf2d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802478"
---
# 關於 App-V 封裝加速器 (App-V 4.6 SP1)


您可以使用 App-v 封裝加速器來自動序列化大型、複雜的應用程式。 此外，當您套用 app-v 套件加速器時，您不一定必須手動安裝應用程式，才能建立虛擬應用程式套件。

**記事** 在某些情況下，系統會提示您在執行 App-v 排序器的電腦上本機安裝應用程式，然後才能使用套件加速器。 如果您必須安裝應用程式，您必須安裝應用程式至應用程式的預設位置。 App-v 排序器不會監視此安裝。 建立 App-v 套件加速器時，套件加速器的作者決定是否需要在本機安裝應用程式。

 

App-v 排序器會從 App-v 套件加速器和相關安裝媒體提取所需的檔案，以建立虛擬套件，而不需要監視應用程式的安裝。

**重要** 免責聲明： Microsoft Application Virtualization Sequencer 不會提供您用來建立套件加速器之軟體應用程式的授權權利。 您必須遵守此類應用程式的所有使用者授權合約。 您有責任確認軟體應用程式的授權條款可讓您使用 Application Virtualization 排序器建立套件加速器。

 

App-v 和專案範本彼此不同。 套件加速器是特定于應用程式的。 [專案範本] 可讓使用者儲存組織專用的常用設定，並將它們套用至多個應用程式。 您也可以在命令提示字元中建立專案範本，而相反地，您必須使用 App-v 排序器主控台來建立套件加速器。 此外，不支援使用套件加速器建立套件及套用專案範本。

## 共用 app-v 套件加速器


本節提供有關如何共用套件加速器的最佳做法資訊。 如果您打算共用套件加速器，諸如電腦名稱稱、使用者帳戶資訊等資訊，以及相關聯應用程式的相關資訊，都可能包含在套件加速器中。下列清單說明您在建立套件加速器時應考慮的方法：

-   [**使用者名稱**]。 當您登入執行 App-v 排序器的電腦時，您應該使用一般的使用者帳戶，例如管理電腦/網域的內建**管理員**帳戶。 您不應該使用以現有的使用者名稱為基礎的帳戶。

-   [**電腦名稱稱**]。 指定執行排序器之電腦的一般、非鑒別名稱。

-   **伺服器 URL**。 在 Sequencer 主控台的 [**部署**] 索引標籤上，使用伺服器 URL 設定資訊的預設設定。

-   **應用程式**。 如果您不想在建立套件加速器時共用執行 Sequencer 之電腦上所安裝的應用程式清單，您必須刪除**appv\_manifest.xml**檔案。 此檔案位於虛擬應用程式套件的套件根目錄中。

您也應該檢查與虛擬應用程式套件相關聯的任何設定或設定檔，以確保應用程式不包含任何個人資訊。

## 保護 App-v 套件加速器


在網路上的安全位置，請務必將 app-v 封裝快速鍵及任何關聯的安裝媒體儲存在網路上，以保護 App-v 套件加速器以及安裝檔案不受損害或遭到損毀。 因為套件加速器也可以包含密碼和使用者專用的資訊，所以您必須將 App-v 套件加速器儲存在安全的位置，而且您必須在建立套件加速器之後進行數位簽章，以便在應用套件加速器時驗證發行者。 如需數位簽章的詳細資訊，請參閱[常見準則安全性的數位簽章慣例的應用程式指導方針](https://go.microsoft.com/fwlink/?LinkId=204705)（ https://go.microsoft.com/fwlink/?LinkId=204705) 。

## 相關主題


[如何建立 App-V 封裝加速器 (App-V 4.6 SP1)](how-to-create-app-v-package-accelerators--app-v-46-sp1-.md)

[如何套用套件加速器以建立虛擬應用程式套件（App-v 4.6 SP1）](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)

 

 





