---
title: 'Lync Server 2013: командлеты голосовой маршрутизации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice routing cmdlets
ms:assetid: 8f05b25e-cc62-4d85-a5d8-4ed56f28dfbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416494(v=OCS.15)
ms:contentKeyID: 48184821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1d32ef285c30229510e0ff28ac978a8230fd01b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="fe770-102">Командлеты голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe770-102">Voice routing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe770-103">_**Тема последнего изменения:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="fe770-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="fe770-104">Голосовые маршруты содержат инструкции, которые сообщают Microsoft Lync Server 2013 о том, как перенаправлять звонки от пользователей голосовой почты на номера телефонов в коммутируемой телефонной сети (КТСОП) или в частной среде обмена филиалами (АТС).</span><span class="sxs-lookup"><span data-stu-id="fe770-104">Voice routes contain instructions that tell Microsoft Lync Server 2013 how to route calls from Enterprise Voice users to phone numbers on the public switched telephone network (PSTN) or a private branch exchange (PBX).</span></span>

<div>

## <a name="voice-routing-cmdlets"></a><span data-ttu-id="fe770-105">Командлеты голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="fe770-105">Voice Routing Cmdlets</span></span>

<span data-ttu-id="fe770-106">Используйте следующие командлеты для настройки голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="fe770-106">Use the following cmdlets to configure voice routes.</span></span>

<span data-ttu-id="fe770-107">**Маршрутизация голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="fe770-107">**Voice Routing**</span></span>

  - <span></span>  
    <span data-ttu-id="fe770-108">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-108">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe770-109">[New-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-109">[New-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe770-110">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-110">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe770-111">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-111">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fe770-112">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-112">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe770-113">[New-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-113">[New-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe770-114">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-114">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe770-115">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-115">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe770-116">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-116">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="fe770-117">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204940(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-117">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204940(v=OCS.15))</span></span>

  - <span data-ttu-id="fe770-118">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205141(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-118">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205141(v=OCS.15))</span></span>

  - <span data-ttu-id="fe770-119">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-119">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205135(v=OCS.15))</span></span>

  - <span data-ttu-id="fe770-120">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204799(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-120">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204799(v=OCS.15))</span></span>

  - <span data-ttu-id="fe770-121">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205313(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-121">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205313(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fe770-122">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-122">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe770-123">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe770-123">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe770-124">См. также</span><span class="sxs-lookup"><span data-stu-id="fe770-124">See Also</span></span>


[<span data-ttu-id="fe770-125">Командлеты для корпоративных голосовых команд в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe770-125">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  
[<span data-ttu-id="fe770-126">Командлеты подключения PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe770-126">PSTN connectivity cmdlets in Lync Server 2013</span></span>](lync-server-2013-pstn-connectivity-cmdlets.md)  


[<span data-ttu-id="fe770-127">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe770-127">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

