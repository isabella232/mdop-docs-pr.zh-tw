---
title: 如何保護 MBAM 網站的規劃
description: 如何保護 MBAM 網站的規劃
author: dansimp
ms.assetid: aea1d137-62cf-4da4-9989-541e0b5ad8d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 223c9397ad7933e11051c289c3dbcab63940fbc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810905"
---
# <span data-ttu-id="e130e-103">如何保護 MBAM 網站的規劃</span><span class="sxs-lookup"><span data-stu-id="e130e-103">Planning How to Secure the MBAM Websites</span></span>


<span data-ttu-id="e130e-104">本主題描述下列方法，以保護 Microsoft BitLocker 管理與監控（MBAM）2.5 的管理與監控網站與自助式入口網站：</span><span class="sxs-lookup"><span data-stu-id="e130e-104">This topic describes the following methods for securing the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Administration and Monitoring Website and Self-Service Portal:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e130e-105">方法</span><span class="sxs-lookup"><span data-stu-id="e130e-105">Method</span></span></th>
<th align="left"><span data-ttu-id="e130e-106">必要或選擇性嗎？</span><span class="sxs-lookup"><span data-stu-id="e130e-106">Required or optional?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-107">使用憑證來保護 MBAM 網站</span><span class="sxs-lookup"><span data-stu-id="e130e-107">Using certificates to secure MBAM websites</span></span></p></td>
<td align="left"><p><span data-ttu-id="e130e-108">選擇性，但強烈建議</span><span class="sxs-lookup"><span data-stu-id="e130e-108">Optional, but highly recommended</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e130e-109">註冊應用程式池帳戶的服務主體名稱（SPN）</span><span class="sxs-lookup"><span data-stu-id="e130e-109">Registering Service Principal Names (SPN) for the application pool account</span></span></p></td>
<td align="left"><p><span data-ttu-id="e130e-110">必要</span><span class="sxs-lookup"><span data-stu-id="e130e-110">Required</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="e130e-111">如需如何保護 MBAM 部署的詳細資訊，請參閱[MBAM 2.5 安全考慮](mbam-25-security-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="e130e-111">For more information about how to secure your MBAM deployment, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md).</span></span>

## <span data-ttu-id="e130e-112">使用憑證來保護 MBAM 網站</span><span class="sxs-lookup"><span data-stu-id="e130e-112">Using certificates to secure MBAM websites</span></span>


<span data-ttu-id="e130e-113">我們建議您使用憑證來保護下列各專案間的通訊：</span><span class="sxs-lookup"><span data-stu-id="e130e-113">We recommend that you use a certificate to secure the communication between the:</span></span>

-   <span data-ttu-id="e130e-114">MBAM 用戶端和 web 服務</span><span class="sxs-lookup"><span data-stu-id="e130e-114">MBAM Client and the web services</span></span>

-   <span data-ttu-id="e130e-115">瀏覽器以及管理和監控網站與自助入口網站</span><span class="sxs-lookup"><span data-stu-id="e130e-115">Browser and the Administration and Monitoring Website and the Self-Service Portal websites</span></span>

<span data-ttu-id="e130e-116">如需有關要求及安裝憑證的資訊，請參閱設定[網際網路伺服器憑證](https://technet.microsoft.com/library/cc731977.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e130e-116">For information about requesting and installing a certificate, see [Configuring Internet Server Certificates](https://technet.microsoft.com/library/cc731977.aspx).</span></span>

**<span data-ttu-id="e130e-117">注意</span><span class="sxs-lookup"><span data-stu-id="e130e-117">Note</span></span>**  
<span data-ttu-id="e130e-118">只有在您使用 Windows PowerShell 時，才能在不同的伺服器上設定網站和 web 服務。</span><span class="sxs-lookup"><span data-stu-id="e130e-118">You can configure the websites and web services on different servers only if you are using Windows PowerShell.</span></span> <span data-ttu-id="e130e-119">如果您使用 MBAM 伺服器設定向導來設定網站，您必須在同一個伺服器上設定網站和 web 服務。</span><span class="sxs-lookup"><span data-stu-id="e130e-119">If you use the MBAM Server Configuration wizard to configure the websites, you must configure the websites and the web services on the same server.</span></span>



<span data-ttu-id="e130e-120">為了保護 web 服務與資料庫之間的通訊，我們也建議您在 SQL Server 中強制執行加密。</span><span class="sxs-lookup"><span data-stu-id="e130e-120">To secure the communication between the web services and the databases, we also recommend that you force encryption in SQL Server.</span></span> <span data-ttu-id="e130e-121">如需加強所有連線至 SQL Server 連線的相關資訊（包括 web 服務與 SQL Server 之間的通訊），請參閱[MBAM 2.5 安全性考慮](mbam-25-security-considerations.md#bkmk-secure-databases)。</span><span class="sxs-lookup"><span data-stu-id="e130e-121">For information about securing all connections to SQL Server, including communication between the web services and SQL Server, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-secure-databases).</span></span>

## <span data-ttu-id="e130e-122">為應用程式池帳戶註冊 Spn</span><span class="sxs-lookup"><span data-stu-id="e130e-122">Registering SPNs for the application pool account</span></span>


<span data-ttu-id="e130e-123">若要讓 MBAM 伺服器從管理和監控網站和自助服務入口網站驗證通訊，您必須在您用於 web 應用程式池的網域帳戶下，為主機名稱註冊服務主要名稱（SPN）。</span><span class="sxs-lookup"><span data-stu-id="e130e-123">To enable the MBAM Servers to authenticate communication from the Administration and Monitoring Website and the Self-Service Portal, you must register a Service Principal Name (SPN) for the host name under the domain account that you are using for the web application pool.</span></span>

<span data-ttu-id="e130e-124">本主題包含如何針對下列類型的主機名稱註冊 Spn 的指示：</span><span class="sxs-lookup"><span data-stu-id="e130e-124">This topic contains instructions on how to register SPNs for the following types of host names:</span></span>

-   <span data-ttu-id="e130e-125">完全合格的功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="e130e-125">Fully qualified domain name</span></span>

-   <span data-ttu-id="e130e-126">NetBIOS 名稱</span><span class="sxs-lookup"><span data-stu-id="e130e-126">NetBIOS name</span></span>

-   <span data-ttu-id="e130e-127">虛擬名稱</span><span class="sxs-lookup"><span data-stu-id="e130e-127">Virtual name</span></span>

### <span data-ttu-id="e130e-128">在建立初始 MBAM 安裝的 Spn 之前</span><span class="sxs-lookup"><span data-stu-id="e130e-128">Before you create SPNs for an initial MBAM installation</span></span>

<span data-ttu-id="e130e-129">開始建立 Spn 之前，請先查看下表中的資訊。</span><span class="sxs-lookup"><span data-stu-id="e130e-129">Review the information in the following table before you start creating SPNs.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e130e-130">任務或專案</span><span class="sxs-lookup"><span data-stu-id="e130e-130">Task or item</span></span></th>
<th align="left"><span data-ttu-id="e130e-131">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e130e-131">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-132">在 Active Directory 網域服務（AD DS）中建立服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="e130e-132">Create a service account in Active Directory Domain Services (AD DS).</span></span></p></td>
<td align="left"><p><span data-ttu-id="e130e-133">服務帳戶是您在 AD DS 中建立的使用者帳戶，可提供 MBAM 網站的安全性。</span><span class="sxs-lookup"><span data-stu-id="e130e-133">The service account is a user account that you create in AD DS to provide security for the MBAM websites.</span></span> <span data-ttu-id="e130e-134">MBAM 網站會在應用程式池中執行，其身分識別為服務帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="e130e-134">The MBAM websites run under an application pool, whose identity is the name of the service account.</span></span> <span data-ttu-id="e130e-135">然後，系統會在應用程式池帳戶中註冊 Spn。</span><span class="sxs-lookup"><span data-stu-id="e130e-135">The SPNs are then registered in the application pool account.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="e130e-136">注意</span><span class="sxs-lookup"><span data-stu-id="e130e-136">Note</span></span></strong><br/><p><span data-ttu-id="e130e-137">您必須針對所有的 web 伺服器使用相同的應用程式池帳戶。</span><span class="sxs-lookup"><span data-stu-id="e130e-137">You must use the same application pool account for all web servers.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e130e-138">確認 IIS IUSRS 群群組帳戶或應用程式池帳戶已獲授與所需的權利。</span><span class="sxs-lookup"><span data-stu-id="e130e-138">Verify that either the IIS-IUSRS group account or the application pool account has been granted the necessary rights.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e130e-139">若要檢查這一點，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e130e-139">To check this, follow these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="e130e-140">開啟 [ <strong> 本機安全性原則編輯器] </strong> ，然後展開 [ <strong> 本機原則] </strong> 節點。</span><span class="sxs-lookup"><span data-stu-id="e130e-140">Open the <strong>Local Security Policy editor</strong> and expand the <strong>Local Policies</strong> node.</span></span></p></li>
<li><p><span data-ttu-id="e130e-141">選取 [ <strong> 使用者權利指派] </strong> 節點，然後按兩下 [在 <strong> 驗證之後類比用戶端 </strong> ]，然後 <strong> </strong> 在右窗格中以批次工作群組原則設定登入。</span><span class="sxs-lookup"><span data-stu-id="e130e-141">Select the <strong>User Rights Assignment</strong> node, and double-click the <strong>Impersonate a client after authentication</strong> and <strong>Log on as a batch job</strong> Group Policy settings in the right pane.</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-142">如果您使用網域系統管理帳戶來設定 MBAM 網站，MBAM 會為您建立 Spn。</span><span class="sxs-lookup"><span data-stu-id="e130e-142">If you configure the MBAM websites by using a domain administrative account, MBAM will create the SPNs for you.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e130e-143">如果您使用網域系統管理帳戶來設定 MBAM 網站，請依照本主題中的步驟，手動登錄您所使用之主機名稱類型的 Spn。</span><span class="sxs-lookup"><span data-stu-id="e130e-143">If you configure the MBAM websites by using a domain administrative account, follow the steps in this topic to register SPNs manually for the type of host name that you are using.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="e130e-144">當您使用完整的網域主機名稱稱時，註冊 Spn</span><span class="sxs-lookup"><span data-stu-id="e130e-144">Registering SPNs when you use a fully qualified domain host name</span></span>

<span data-ttu-id="e130e-145">如果您在設定 MBAM 時使用完整的功能變數名稱主機名稱，就必須只註冊一個 SPN，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="e130e-145">If you use a fully qualified domain host name when you configure MBAM, you have to register only one SPN, as shown in the following example.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e130e-146">您需要執行的動作</span><span class="sxs-lookup"><span data-stu-id="e130e-146">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="e130e-147">範例及詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e130e-147">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-148">針對完全合格的功能變數名稱註冊 SPN。</span><span class="sxs-lookup"><span data-stu-id="e130e-148">Register an SPN for the fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mybitlockerrecovery.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="e130e-149">完整的主機名稱是 <strong> mybitlockerrecovery.contoso.com </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e130e-149">The fully qualified host name is <strong>mybitlockerrecovery.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e130e-150">針對您針對應用程式池帳戶所註冊的 SPN，設定受限制的委派。</span><span class="sxs-lookup"><span data-stu-id="e130e-150">Configure constrained delegation for the SPN that you are registering for the application pool account.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)"><span data-ttu-id="e130e-151">設定受限制的委派</span><span class="sxs-lookup"><span data-stu-id="e130e-151">Configuring Constrained Delegation</span></span></a></p>
<p><span data-ttu-id="e130e-152">這個需求只適用于 MBAM 2.5;MBAM 2.5 SP1 中並無需這麼做。</span><span class="sxs-lookup"><span data-stu-id="e130e-152">This requirement only applies to MBAM 2.5; it is not necessary in MBAM 2.5 SP1.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="e130e-153">當您使用 NetBIOS 主機名稱時，註冊 Spn</span><span class="sxs-lookup"><span data-stu-id="e130e-153">Registering SPNs when you use a NetBIOS host name</span></span>

<span data-ttu-id="e130e-154">如果您在設定 MBAM 時使用 NetBIOS 主機名稱，請為 NetBIOS 名稱註冊一個 SPN，然後針對完整功能變數名稱登錄另一個 SPN，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="e130e-154">If you use a NetBIOS host name when you configure MBAM, register one SPN for the NetBIOS name, and another SPN for the fully qualified domain name, as shown in the following examples.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e130e-155">您需要執行的動作</span><span class="sxs-lookup"><span data-stu-id="e130e-155">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="e130e-156">範例及詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e130e-156">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-157">針對 NetBIOS 主機名稱註冊 SPN。</span><span class="sxs-lookup"><span data-stu-id="e130e-157">Register an SPN for the NetBIOS host name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/nbname01 contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="e130e-158">NetBIOS 主機名稱是 <strong> nbname01 </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e130e-158">The NetBIOS host name is <strong>nbname01</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e130e-159">針對完全合格的功能變數名稱註冊 SPN。</span><span class="sxs-lookup"><span data-stu-id="e130e-159">Register an SPN for the fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn –s http/nbname01.corp.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="e130e-160">完整的功能變數名稱是 <strong> nbname01.contoso.com </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e130e-160">The fully qualified domain name is <strong>nbname01.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-161">針對您為應用程式池帳戶所註冊的 Spn，設定受限制的委派。</span><span class="sxs-lookup"><span data-stu-id="e130e-161">Configure constrained delegation for the SPNs that you are registering for the application pool account.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)"><span data-ttu-id="e130e-162">設定受限制的委派</span><span class="sxs-lookup"><span data-stu-id="e130e-162">Configuring Constrained Delegation</span></span></a></p>
<p><span data-ttu-id="e130e-163">這個需求只適用于 MBAM 2.5;MBAM 2.5 SP1 中並無需這麼做。</span><span class="sxs-lookup"><span data-stu-id="e130e-163">This requirement only applies to MBAM 2.5; it is not necessary in MBAM 2.5 SP1.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-regvirtualspn"></a><span data-ttu-id="e130e-164">當您使用虛擬主機名稱稱時，註冊 Spn</span><span class="sxs-lookup"><span data-stu-id="e130e-164">Registering SPNs when you use a virtual host name</span></span>

<span data-ttu-id="e130e-165">如果您使用是完整功能變數名稱的虛擬主機名稱來設定 MBAM，請只針對虛擬主機名稱註冊一個 SPN。</span><span class="sxs-lookup"><span data-stu-id="e130e-165">If you configure MBAM with a virtual host name that is a fully qualified domain name, register only one SPN for the virtual host name.</span></span> <span data-ttu-id="e130e-166">如果您設定的虛擬主機名稱不是完整的功能變數名稱，您必須建立第二個 SPN 來指定完整的功能變數名稱，如下列範例所述。</span><span class="sxs-lookup"><span data-stu-id="e130e-166">If the virtual host name that you configure is not a fully qualified domain name, you must create a second SPN that specifies the fully qualified domain name, as described in the following examples.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e130e-167">您需要執行的動作</span><span class="sxs-lookup"><span data-stu-id="e130e-167">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="e130e-168">範例及詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e130e-168">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-169">如果您的虛擬主機名稱是完整的功能變數名稱，就像在這個範例中一樣，只註冊一個 SPN。</span><span class="sxs-lookup"><span data-stu-id="e130e-169">If your virtual host name is a fully qualified domain name, as in this example, register only one SPN.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="e130e-170">在這個範例中，虛擬主機名稱是 <strong> mbamvirtual.contoso.com </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e130e-170">In the example, the virtual host name is <strong>mbamvirtual.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e130e-171">如果您的虛擬主機名稱不是完整的功能變數名稱，請註冊這個額外的 SPN。</span><span class="sxs-lookup"><span data-stu-id="e130e-171">Register this additional SPN if your virtual host name is not a fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="e130e-172">在這個範例中，虛擬主機名稱是 <strong> mbamvirtual </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e130e-172">In the example, the virtual host name is <strong>mbamvirtual</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-173">如果您的虛擬主機名稱不是完整的功能變數名稱，請註冊這個額外的 SPN。</span><span class="sxs-lookup"><span data-stu-id="e130e-173">Register this additional SPN if your virtual host name is not a fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="e130e-174">在這個範例中，虛擬主機名稱是 <strong> mbamvirtual.contoso.com </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e130e-174">In the example, the virtual host name is <strong>mbamvirtual.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e130e-175">在功能變數名稱伺服器（DNS）伺服器上，建立自訂主機名稱的 "A 記錄"，並將其指向 web 伺服器或負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="e130e-175">On the Domain Name Server (DNS) server, create an “A record” for the custom host name and point it to a web server or a load balancer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e130e-176">請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=394337" data-raw-source="[Configure DNS Host Records](https://go.microsoft.com/fwlink/?LinkId=394337)"> 設定 Dns 主機記錄中的「設定 Dns 主機 A 記錄」一節 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e130e-176">See the “To configure DNS Host A Records” section in <a href="https://go.microsoft.com/fwlink/?LinkId=394337" data-raw-source="[Configure DNS Host Records](https://go.microsoft.com/fwlink/?LinkId=394337)">Configure DNS Host Records</a>.</span></span></p>
<p><span data-ttu-id="e130e-177">我們建議您使用記錄，而不是 CNAMES。</span><span class="sxs-lookup"><span data-stu-id="e130e-177">We recommend that you use A records instead of CNAMES.</span></span> <span data-ttu-id="e130e-178">如果您使用 CNAMES 指向網域位址，您也必須在應用程式池帳戶中註冊 web 伺服器名稱的 Spn。</span><span class="sxs-lookup"><span data-stu-id="e130e-178">If you use CNAMES to point to the domain address, you must also register SPNs for the web server name in the application pool account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-179">針對您為應用程式池帳戶所註冊的 Spn，設定受限制的委派。</span><span class="sxs-lookup"><span data-stu-id="e130e-179">Configure constrained delegation for the SPNs that you are registering for the application pool account.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)"><span data-ttu-id="e130e-180">設定受限制的委派</span><span class="sxs-lookup"><span data-stu-id="e130e-180">Configuring Constrained Delegation</span></span></a></p>
<p><span data-ttu-id="e130e-181">這個需求只適用于 MBAM 2.5;MBAM 2.5 SP1 中並無需這麼做。</span><span class="sxs-lookup"><span data-stu-id="e130e-181">This requirement only applies to MBAM 2.5; it is not necessary in MBAM 2.5 SP1.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-registerspn"></a><span data-ttu-id="e130e-182">從舊版 MBAM 升級時註冊 SPN</span><span class="sxs-lookup"><span data-stu-id="e130e-182">Registering an SPN when you upgrade from previous versions of MBAM</span></span>

<span data-ttu-id="e130e-183">只有在您想要的情況下，才能完成本節中的步驟：</span><span class="sxs-lookup"><span data-stu-id="e130e-183">Complete the steps in this section only if you want to:</span></span>

-   <span data-ttu-id="e130e-184">從舊版本的 MBAM 升級。</span><span class="sxs-lookup"><span data-stu-id="e130e-184">Upgrade from a previous version of MBAM.</span></span>

-   <span data-ttu-id="e130e-185">在負載平衡或分散式設定中執行 MBAM 2.5 中的網站，而且您目前正在執行的設定不是負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e130e-185">Run the websites in MBAM 2.5 in a load-balanced or distributed configuration, and you are currently running in a configuration that is not load balanced.</span></span>

<span data-ttu-id="e130e-186">如果您已在電腦帳戶上註冊 Spn，而不是在應用程式池帳戶中登錄，MBAM 會使用現有的 Spn，而且您無法在負載平衡或散佈配置中設定網站。</span><span class="sxs-lookup"><span data-stu-id="e130e-186">If you already registered SPNs on the machine account rather than in an application pool account, MBAM uses the existing SPNs, and you cannot configure the websites in a load-balanced or distributed configuration.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e130e-187">您需要執行的動作</span><span class="sxs-lookup"><span data-stu-id="e130e-187">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="e130e-188">範例及詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e130e-188">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-189">在 Active Directory 網域服務（AD DS）中建立應用程式池帳戶。</span><span class="sxs-lookup"><span data-stu-id="e130e-189">Create an application pool account in Active Directory Domain Services (AD DS).</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e130e-190">移除目前已安裝的網站和 web 服務。</span><span class="sxs-lookup"><span data-stu-id="e130e-190">Remove the currently installed websites and web services.</span></span></p></td>
<td align="left"><p><a href="removing-mbam-server-features-or-software.md" data-raw-source="[Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md)"><span data-ttu-id="e130e-191">移除 MBAM 伺服器功能或軟體</span><span class="sxs-lookup"><span data-stu-id="e130e-191">Removing MBAM Server Features or Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-192">從電腦帳戶移除 Spn。</span><span class="sxs-lookup"><span data-stu-id="e130e-192">Remove SPNs from the machine account.</span></span></p></td>
<td align="left"><p><code>Setspn –d http/mbamwebserver mbamwebserver</code></p>
<p><code>Setspn –d http/mbamwebserver.contoso.com mbamwebserver</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e130e-193">在應用程式池帳戶中註冊 Spn。</span><span class="sxs-lookup"><span data-stu-id="e130e-193">Register SPNs in the application pool account.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e130e-194"><a href="#bkmk-regvirtualspn" data-raw-source="[Registering SPNs when you use a virtual host name](#bkmk-regvirtualspn)">當您使用虛擬主機名稱稱時，請遵循註冊 spn 的步驟 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e130e-194">Follow the steps for <a href="#bkmk-regvirtualspn" data-raw-source="[Registering SPNs when you use a virtual host name](#bkmk-regvirtualspn)">Registering SPNs when you use a virtual host name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e130e-195">重新設定 web 應用程式和 web 服務。</span><span class="sxs-lookup"><span data-stu-id="e130e-195">Reconfigure the web applications and web services.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="e130e-196">如何設定 MBAM 2.5 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="e130e-196">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e130e-197">視您用於設定的方法而定，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e130e-197">Do one of the following, depending on the method you use for the configuration:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e130e-198">方法</span><span class="sxs-lookup"><span data-stu-id="e130e-198">Method</span></span></th>
<th align="left"><span data-ttu-id="e130e-199">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e130e-199">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e130e-200">MBAM Server 設定精靈</span><span class="sxs-lookup"><span data-stu-id="e130e-200">MBAM Server Configuration wizard</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e130e-201">在 [ <strong> Web 服務應用程式池] 的 [網域帳戶] 欄位中，輸入應用程式池帳戶 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e130e-201">Enter the application pool account in the <strong>Web service application pool domain account</strong> field.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><code>Enable-MbamWebApplication</code> <span data-ttu-id="e130e-202">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e130e-202">Windows PowerShell cmdlet</span></span></p></td>
<td align="left"><p><span data-ttu-id="e130e-203">在參數中輸入帳戶 <code>WebServiceApplicationPoolCredential</code> 。</span><span class="sxs-lookup"><span data-stu-id="e130e-203">Enter the account in the <code>WebServiceApplicationPoolCredential</code> parameter.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="e130e-204">重要</span><span class="sxs-lookup"><span data-stu-id="e130e-204">Important</span></span></strong><br/><p><span data-ttu-id="e130e-205">您輸入的主機名稱必須與您要為其建立 Spn 的虛擬主機名稱名稱相同。</span><span class="sxs-lookup"><span data-stu-id="e130e-205">The host name that you enter must be the same name as the virtual host name for which you are creating the SPNs.</span></span> <span data-ttu-id="e130e-206">此外，在您的網路群中，主機名稱和應用程式池認證在您要設定的每個伺服器上都必須是相同的。</span><span class="sxs-lookup"><span data-stu-id="e130e-206">Also, in your web farm, the host names and the application pool credentials must be the same on every server that you are configuring.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="e130e-207">當 MBAM 設定 web 應用程式時，它會嘗試為您註冊 Spn，但只有在您要安裝 MBAM 的伺服器上有網域系統管理員許可權時，才能這麼做。</span><span class="sxs-lookup"><span data-stu-id="e130e-207">When MBAM configures the web applications, it will try to register the SPNs for you, but it can do so only if you have Domain Admin rights on the server on which you are installing MBAM.</span></span> <span data-ttu-id="e130e-208">如果您沒有這些許可權，您可以完成設定，但您必須在設定 MBAM 之前或之後設定 Spn。</span><span class="sxs-lookup"><span data-stu-id="e130e-208">If you do not have these rights, you can complete the configuration, but you will have to set the SPNs before or after you configure MBAM.</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="e130e-209">必要的要求篩選設定</span><span class="sxs-lookup"><span data-stu-id="e130e-209">Required Request Filtering Settings</span></span>

 <span data-ttu-id="e130e-210">應用程式需要「允許未列出的檔案名副檔名」才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="e130e-210">'Allow unlisted file name extensions' is required for the application to operate as expected.</span></span>  <span data-ttu-id="e130e-211">若要找到此功能，請流覽至 [Microsoft BitLocker 管理與監視]-> 要求篩選-> 編輯功能設定]。</span><span class="sxs-lookup"><span data-stu-id="e130e-211">This can be found by navigating to the 'Microsoft BitLocker Administration and Monitoring' -> Request Filtering -> Edit Feature Settings.</span></span>


## <span data-ttu-id="e130e-212">相關主題</span><span class="sxs-lookup"><span data-stu-id="e130e-212">Related topics</span></span>


[<span data-ttu-id="e130e-213">MBAM 2.5 的環境準備</span><span class="sxs-lookup"><span data-stu-id="e130e-213">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="e130e-214">MBAM 2.5 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="e130e-214">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)





## <span data-ttu-id="e130e-215">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="e130e-215">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e130e-216">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="e130e-216">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="e130e-217">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="e130e-217">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>



