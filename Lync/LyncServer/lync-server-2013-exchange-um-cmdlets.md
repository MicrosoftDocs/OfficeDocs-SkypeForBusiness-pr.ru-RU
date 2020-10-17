---
title: 'Lync Server 2013: командлеты Exchange единой системы обмена сообщениями'
description: 'Lync Server 2013: Командлеты единой системы обмена сообщениями Exchange.'
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
ms.openlocfilehash: 272e791969508b488efb0aaa2db10fb645ddd81c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564825"
---
# <a name="exchange-um-cmdlets-in-lync-server-2013"></a><span data-ttu-id="60186-103">Командлеты единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60186-103">Exchange UM cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60186-104">_**Последнее изменение темы:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="60186-104">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="60186-105">Microsoft Lync Server 2013 работает вместе с единой системой обмена сообщениями Exchange для реализации автосекретаря и абонентского доступа для размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="60186-105">Microsoft Lync Server 2013 works together with Exchange Unified Messaging (UM) to implement Auto Attendant and Subscriber Access for hosted voice mail.</span></span> <span data-ttu-id="60186-106">Управление этими возможностями осуществляется с помощью командлетов в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="60186-106">These features can be managed through cmdlets in the Lync Server Management Shell.</span></span>

<div>

## <a name="exchange-um-cmdlets"></a><span data-ttu-id="60186-107">Командлеты единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="60186-107">Exchange UM Cmdlets</span></span>

<span data-ttu-id="60186-108">Для управления единой системой обмена сообщениями Exchange можно использовать следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="60186-108">The following cmdlets can be used to manage Exchange UM</span></span>

<span data-ttu-id="60186-109">**единой системы обмена сообщениями Exchange**</span><span class="sxs-lookup"><span data-stu-id="60186-109">**Exchange UM**</span></span>

  - <span></span>  
    <span data-ttu-id="60186-110">[Get — CsExUmContact](https://technet.microsoft.com/library/Gg412725(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-110">[Get-CsExUmContact](https://technet.microsoft.com/library/Gg412725(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60186-111">[Move — CsExUmContact](https://technet.microsoft.com/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-111">[Move-CsExUmContact](https://technet.microsoft.com/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60186-112">[New — CsExUmContact](https://technet.microsoft.com/library/Gg398139(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-112">[New-CsExUmContact](https://technet.microsoft.com/library/Gg398139(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60186-113">[Remove — CsExUmContact](rehttps://technet.microsoft.com/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-113">[Remove-CsExUmContact](rehttps://technet.microsoft.com/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60186-114">[Set — CsExUmContact](https://technet.microsoft.com/library/Gg412944(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-114">[Set-CsExUmContact](https://technet.microsoft.com/library/Gg412944(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="60186-115">[Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-115">[Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="60186-116">[Test-CsExStorageNotification](https://technet.microsoft.com/library/JJ205331(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-116">[Test-CsExStorageNotification](https://technet.microsoft.com/library/JJ205331(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="60186-117">[Test-CsExUMConnectivity](https://technet.microsoft.com/library/JJ204784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-117">[Test-CsExUMConnectivity](https://technet.microsoft.com/library/JJ204784(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="60186-118">[Test-CsExUMVoiceMail](https://technet.microsoft.com/library/JJ205058(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-118">[Test-CsExUMVoiceMail](https://technet.microsoft.com/library/JJ205058(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60186-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398348(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398348(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60186-120">[Granting — CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-120">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60186-121">[New — CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398653(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-121">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398653(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60186-122">[Remove — CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398211(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-122">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398211(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60186-123">[Set — CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-123">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412722(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60186-124">[Get — Ксвоицемаилрераутингконфигуратион](https://technet.microsoft.com/library/Gg425732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-124">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425732(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60186-125">[New — Ксвоицемаилрераутингконфигуратион](https://technet.microsoft.com/library/Gg425849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-125">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425849(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60186-126">[Remove — Ксвоицемаилрераутингконфигуратион](https://technet.microsoft.com/library/Gg398573(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-126">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg398573(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60186-127">[Set — Ксвоицемаилрераутингконфигуратион](https://technet.microsoft.com/library/Gg412948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60186-127">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg412948(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60186-128">См. также</span><span class="sxs-lookup"><span data-stu-id="60186-128">See Also</span></span>


[<span data-ttu-id="60186-129">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="60186-129">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

