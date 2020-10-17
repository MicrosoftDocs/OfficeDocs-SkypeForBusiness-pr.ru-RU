---
title: 'Lync Server 2013: Настройка служб федерации Active Directory (AD FS 2,0)'
description: 'Lync Server 2013: Настройка служб федерации Active Directory (AD FS 2,0).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc21500273d8576f54f6110783e61764ec9723a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567845"
---
# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="df306-103">Настройка служб федерации Active Directory (AD FS 2,0) для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df306-103">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df306-104">_**Последнее изменение темы:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="df306-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="df306-105">В следующем разделе описано, как настроить службы федерации Active Directory (AD FS 2,0) для поддержки многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="df306-105">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="df306-106">Сведения о том, как установить AD FS 2,0, можно найти в статье AD FS 2,0 пошаговые инструкции и руководства по [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374) .</span><span class="sxs-lookup"><span data-stu-id="df306-106">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="df306-107">При установке служб федерации Active Directory 2,0 не используйте Диспетчер Windows Server для добавления роли служб федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df306-107">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="df306-108">Вместо этого скачайте и установите пакет RTW 2,0 служб федерации Active Directory на сайте <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A> .</span><span class="sxs-lookup"><span data-stu-id="df306-108">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="df306-109">**Настройка AD FS для двухфакторной проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="df306-109">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="df306-110">Выполните вход на компьютер с AD FS 2,0 с помощью учетной записи администратора домена.</span><span class="sxs-lookup"><span data-stu-id="df306-110">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="df306-111">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df306-111">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="df306-112">В командной строке Windows PowerShell выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="df306-112">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="df306-113">Установите связь с каждым сервером Lync Server 2013 с накопительными обновлениями для Lync Server 2013: Июль 2013 директор, корпоративный пул и сервер Standard Edition, для которых будет включена пассивная проверка подлинности с помощью следующей команды: замена имени сервера, относящегося к развертыванию:</span><span class="sxs-lookup"><span data-stu-id="df306-113">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="df306-114">В меню Администрирование откройте консоль управления AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="df306-114">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="df306-115">Разверните узел **отношения доверия** отношения \> **доверия с проверяющей стороной**.</span><span class="sxs-lookup"><span data-stu-id="df306-115">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="df306-116">Убедитесь, что для Lync Server 2013 с накопительными пакетами обновления для Lync Server 2013 создано новое отношение доверия: Июль 2013 Корпоративный пул или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="df306-116">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="df306-117">Создайте и назначьте правило авторизации выдачи для отношения доверия с проверяющей стороной с помощью Windows PowerShell, выполнив следующие команды:</span><span class="sxs-lookup"><span data-stu-id="df306-117">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="df306-118">Создайте и назначьте правило преобразования выдачи для отношения доверия с проверяющей стороной с помощью Windows PowerShell, выполнив следующие команды:</span><span class="sxs-lookup"><span data-stu-id="df306-118">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="df306-119">В консоли управления AD FS 2,0 щелкните правой кнопкой мыши отношение доверия с проверяющей стороной и выберите команду **изменить правила утверждений**.</span><span class="sxs-lookup"><span data-stu-id="df306-119">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="df306-120">Выберите вкладку **правила авторизации выдачи** и убедитесь, что новое правило авторизации было успешно создано.</span><span class="sxs-lookup"><span data-stu-id="df306-120">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="df306-121">Перейдите на вкладку **правила преобразования выдачи** и убедитесь, что новое правило преобразования успешно создано.</span><span class="sxs-lookup"><span data-stu-id="df306-121">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

