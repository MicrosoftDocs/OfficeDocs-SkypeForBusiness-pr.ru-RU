---
title: 'Lync Server 2013: Настройка служб федерации Active Directory (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924f9c1b6e7fe64186eeee6a34364417d497866b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="5ebe9-102">Настройка служб федерации Active Directory (AD FS 2,0) для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ebe9-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ebe9-103">_**Тема последнего изменения:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="5ebe9-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="5ebe9-104">В этом разделе рассматривается настройка служб федерации Active Directory (AD FS 2.0) для поддержки многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="5ebe9-105">Сведения о том, как установить AD FS 2,0, приведены пошаговые инструкции для AD FS 2,0 и инструкции по [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span><span class="sxs-lookup"><span data-stu-id="5ebe9-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="5ebe9-106">При установке AD FS 2.0 не добавляйте роль службы федерации Active Directory с помощью диспетчера серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="5ebe9-107">Вместо этого загрузите и установите пакет служб федерации Active Directory 2,0 RTW at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="5ebe9-108">**Настройка AD FS для двухфакторной проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="5ebe9-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="5ebe9-109">Войдите в систему на компьютере с AD FS 2.0 с помощью учетной записи администратора домена.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="5ebe9-110">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="5ebe9-111">Введите в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5ebe9-111">From the Windows PowerShell command-line, run the following command:</span></span>
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  <span data-ttu-id="5ebe9-112">Установите связь с каждым сервером Lync Server 2013 с накопительными обновлениями для Lync Server 2013: Июль 2013 режиссер, корпоративный пул и сервер Standard Edition, для которых будет включена пассивная проверка подлинности, выполнив указанную ниже команду, заменив имя сервера, относящееся к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  <span data-ttu-id="5ebe9-113">Запустите консоль управления AD FS 2.0 в меню "Средства администрирования".</span><span class="sxs-lookup"><span data-stu-id="5ebe9-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="5ebe9-114">Разверните элемент \> **доверия проверяющей стороны** **отношений доверия** .</span><span class="sxs-lookup"><span data-stu-id="5ebe9-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="5ebe9-115">Убедитесь в том, что для Lync Server 2013 установлены новые доверительные отношения с накопительными обновлениями для Lync Server 2013: Июль 2013 корпоративным пулом или Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="5ebe9-116">С помощью Windows PowerShell и следующих команд создайте и назначьте для отношения доверия с проверяющей стороны правило утверждения авторизации:</span><span class="sxs-lookup"><span data-stu-id="5ebe9-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="5ebe9-117">С помощью Windows PowerShell и следующих команд создайте и назначьте для отношения доверия с проверяющей стороны правило утверждения преобразования:</span><span class="sxs-lookup"><span data-stu-id="5ebe9-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="5ebe9-118">В консоли управления AD FS 2.0 щелкните отношение доверия с проверяющей стороной правой кнопкой мыши и выберите команду **редактирования правил утверждений**.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="5ebe9-119">Перейдите на вкладку **правил разрешения выпуска** и убедитесь в том, что новое правило разрешения успешно создано.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="5ebe9-120">Перейдите на вкладку **правил преобразования выпуска** и убедитесь в том, что новое правило преобразования успешно создано.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

