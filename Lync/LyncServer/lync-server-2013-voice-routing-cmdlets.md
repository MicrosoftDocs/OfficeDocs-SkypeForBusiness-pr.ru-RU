---
title: 'Lync Server 2013: командлеты маршрутизации голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routing cmdlets
ms:assetid: 8f05b25e-cc62-4d85-a5d8-4ed56f28dfbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416494(v=OCS.15)
ms:contentKeyID: 48184821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: deb3a54494d70b54325e6bc64f3b3facc0ec2a8f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535466"
---
# <a name="voice-routing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f9549-102">Командлеты маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9549-102">Voice routing cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9549-103">_**Последнее изменение темы:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="f9549-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="f9549-104">Маршруты голосовых вызовов содержат инструкции, которые сообщают Microsoft Lync Server 2013 о маршрутизации вызовов от пользователей корпоративной голосовой связи на телефонные номера в телефонной сети общего пользования (PSTN) или УАТС.</span><span class="sxs-lookup"><span data-stu-id="f9549-104">Voice routes contain instructions that tell Microsoft Lync Server 2013 how to route calls from Enterprise Voice users to phone numbers on the public switched telephone network (PSTN) or a private branch exchange (PBX).</span></span>

<div>

## <a name="voice-routing-cmdlets"></a><span data-ttu-id="f9549-105">Командлеты маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="f9549-105">Voice Routing Cmdlets</span></span>

<span data-ttu-id="f9549-106">Для настройки маршрутизации голосовой связи используйте следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="f9549-106">Use the following cmdlets to configure voice routes.</span></span>

<span data-ttu-id="f9549-107">**Маршрутизация голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="f9549-107">**Voice Routing**</span></span>

  - <span></span>  
    <span data-ttu-id="f9549-108">[Get — Ксраутингконфигуратион](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-108">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f9549-109">[New — Ксраутингконфигуратион](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-109">[New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f9549-110">[Remove — Ксраутингконфигуратион](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-110">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f9549-111">[Set — Ксраутингконфигуратион](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-111">[Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f9549-112">[Get — Ксвоицерауте](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-112">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f9549-113">[New — Ксвоицерауте](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-113">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f9549-114">[Remove — Ксвоицерауте](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-114">[Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f9549-115">[Set — Ксвоицерауте](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-115">[Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f9549-116">[Test-Ксвоицерауте](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-116">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f9549-117">[Get — CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-117">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span></span>

  - <span data-ttu-id="f9549-118">[Granting — CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-118">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span></span>

  - <span data-ttu-id="f9549-119">[New — CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-119">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span></span>

  - <span data-ttu-id="f9549-120">[Remove — CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-120">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span></span>

  - <span data-ttu-id="f9549-121">[Set — CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-121">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f9549-122">[Get — Кспстнусаже](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-122">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f9549-123">[Set — Кспстнусаже](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9549-123">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9549-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f9549-124">See Also</span></span>


[<span data-ttu-id="f9549-125">Командлеты корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9549-125">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  
[<span data-ttu-id="f9549-126">Командлеты подключения PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9549-126">PSTN connectivity cmdlets in Lync Server 2013</span></span>](lync-server-2013-pstn-connectivity-cmdlets.md)  


[<span data-ttu-id="f9549-127">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9549-127">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

