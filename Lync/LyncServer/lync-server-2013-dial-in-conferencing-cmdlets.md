---
title: 'Lync Server 2013: командлеты конференц-связи с телефонным подключением'
description: 'Lync Server 2013: командлеты конференц-связи с телефонным подключением.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing cmdlets
ms:assetid: 0718f82a-91c4-466f-8443-a85002deaa48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415630(v=OCS.15)
ms:contentKeyID: 48183320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b19cc8a022f8d86e0b3bdd22a93f8df692404171
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576205"
---
# <a name="dial-in-conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="702cd-103">Командлеты конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="702cd-103">Dial-in conferencing cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="702cd-104">_**Последнее изменение темы:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="702cd-104">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="702cd-105">Конференц-связь с телефонным подключением позволяет пользователям использовать обычный телефон (то есть устройство в телефонной сети общего пользования), чтобы присоединиться к звуковой части Конференции.</span><span class="sxs-lookup"><span data-stu-id="702cd-105">Dial-in conferencing provides a way for users to use a "regular" telephone (that is, a device on the public switched telephone network) to join the audio portion of a conference.</span></span>

<div>

## <a name="dial-in-conferencing-cmdlets"></a><span data-ttu-id="702cd-106">Dial-In Conferencing Cmdlets</span><span class="sxs-lookup"><span data-stu-id="702cd-106">Dial-In Conferencing Cmdlets</span></span>

<span data-ttu-id="702cd-107">Если вы не хотите разрешить Конференц-связь с телефонным подключением, эту возможность можно отключить с помощью командлета Set-CsConferencingPolicy и задав для свойства ЕнабледиалинконференЦинг значение false.</span><span class="sxs-lookup"><span data-stu-id="702cd-107">If you do not want to allow dial-in conferencing you can disable this capability by using the Set-CsConferencingPolicy cmdlet and setting the EnableDialInConferencing property to False.</span></span> <span data-ttu-id="702cd-108">По умолчанию всем пользователям разрешается размещать собрания, которые включают конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="702cd-108">By default, all users are allowed to host meetings that include dial-in conferencing.</span></span>

<span data-ttu-id="702cd-109">**Конференц-связь с телефонным подключением**</span><span class="sxs-lookup"><span data-stu-id="702cd-109">**Dial-In Conferencing**</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-110">[Get — CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-110">[Get-CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-111">[Move — CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-111">[Move-CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-112">[New — CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-112">[New-CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-113">[Remove — CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-113">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="702cd-114">[Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-114">[Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="702cd-115">[Get — CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-115">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-116">[New — CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-116">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-117">[Remove — CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-117">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-118">[Set — CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-118">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="702cd-119">[Get — CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-119">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-120">[New — CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-120">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-121">[Remove — CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-121">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-122">[Set — CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-122">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="702cd-123">[Get — CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-123">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-124">[New — CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-124">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-125">[Remove — CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-125">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="702cd-126">[Set — CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-126">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="702cd-127">[Get — CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="702cd-127">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="702cd-128">См. также</span><span class="sxs-lookup"><span data-stu-id="702cd-128">See Also</span></span>


[<span data-ttu-id="702cd-129">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="702cd-129">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

