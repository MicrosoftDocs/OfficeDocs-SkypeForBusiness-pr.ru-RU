---
title: 'Lync Server 2013: командлеты UM Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange UM cmdlets
ms:assetid: 32922b9f-590d-41cc-ba57-9ed5f1caa814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415642(v=OCS.15)
ms:contentKeyID: 48183786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cc9d63189d66e6e5255ca7c0d34a717cc2eb514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-um-cmdlets-in-lync-server-2013"></a><span data-ttu-id="b3fef-102">Командлеты единой системы обмена сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3fef-102">Exchange UM cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3fef-103">_**Тема последнего изменения:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="b3fef-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="b3fef-104">Microsoft Lync Server 2013 работает вместе с единой системой обмена сообщениями Exchange (UM) для реализации автосекретаря и абонентского доступа для размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="b3fef-104">Microsoft Lync Server 2013 works together with Exchange Unified Messaging (UM) to implement Auto Attendant and Subscriber Access for hosted voice mail.</span></span> <span data-ttu-id="b3fef-105">Эти возможности можно управлять с помощью командлетов в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3fef-105">These features can be managed through cmdlets in the Lync Server Management Shell.</span></span>

<div>

## <a name="exchange-um-cmdlets"></a><span data-ttu-id="b3fef-106">Командлеты Exchange UM</span><span class="sxs-lookup"><span data-stu-id="b3fef-106">Exchange UM Cmdlets</span></span>

<span data-ttu-id="b3fef-107">Для управления UM Exchange можно использовать следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="b3fef-107">The following cmdlets can be used to manage Exchange UM</span></span>

<span data-ttu-id="b3fef-108">**обмена сообщениями Exchange**</span><span class="sxs-lookup"><span data-stu-id="b3fef-108">**Exchange UM**</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-109">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-109">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-110">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-110">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-111">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-111">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-112">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-112">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-113">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-113">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="b3fef-114">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-114">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="b3fef-115">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-115">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="b3fef-116">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-116">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="b3fef-117">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-117">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b3fef-118">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-118">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-119">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-119">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-120">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-120">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-121">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-121">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-122">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-122">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b3fef-123">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-123">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-124">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-124">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-125">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-125">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b3fef-126">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b3fef-126">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3fef-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b3fef-127">See Also</span></span>


[<span data-ttu-id="b3fef-128">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3fef-128">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

