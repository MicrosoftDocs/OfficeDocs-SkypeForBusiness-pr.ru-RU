---
title: 'Lync Server 2013: командлеты конференц-связи'
description: 'Lync Server 2013: командлеты конференц-связи.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing cmdlets
ms:assetid: 7ff94637-6319-4c45-9230-be34e8d81ede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398641(v=OCS.15)
ms:contentKeyID: 48184640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b7cd9843c971d5bf8611c4e64548b2ff608f1b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561185"
---
# <a name="conferencing-cmdlets-in-lync-server-2013"></a>Командлеты конференц-связи в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-09_

Microsoft Lync Server 2013 позволяет пользователям присоединяться к конференциям двумя различными способами: с помощью приложения для конференц-связи, например Lync 2013, или с помощью телефонного соединения. Пользователи с телефонным подключением не смогут выполнять такие действия, как просмотр слайдов или обмен мгновенными сообщениями, но они смогут полностью участвовать а звуковой части конференции.

<div>

## <a name="conferencing-cmdlets"></a>Командлеты конференц-связи

Командлеты **CsDialInConferencing** используются для настройки всех свойств конференц-связи с телефонным подключением, от указания телефонных номеров, которые могут набирать пользователи для присоединения к конференции, до команд, которые набираются с клавиатуры и становятся доступны пользователям после того, как они присоединятся к конференции (например, нажатие клавиши 6 для включения или отключения телефонного микрофона). Управление большинством других функций конференции (таких как возможность пользователей записывать конференции, общий доступ к приложениям во время конференции и т.п.) осуществляется с помощью командлетов **CsConferencingPolicy**.

**[Командлеты конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-cmdlets.md)**

  - <span></span>  
    [Get — CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))

  - <span></span>  
    [Move — CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - <span></span>  
    [New — CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))

  - <span></span>  
    [Remove — CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))

  - <span></span>  
    [New — CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))

  - <span></span>  
    [Remove — CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))

  - <span></span>  
    [Set — CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))

  - <span></span>  
    [New — CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))

  - <span></span>  
    [Remove — CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))

  - <span></span>  
    [Set — CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))

  - <span></span>  
    [New — CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))

  - <span></span>  
    [Remove — CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))

  - <span></span>  
    [Set — CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))

**[Командлеты веб-конференций в Lync Server 2013](lync-server-2013-web-conferencing-cmdlets.md)**

  - <span></span>  
    [Get — CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))

  - <span></span>  
    [Remove — CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))

  - <span></span>  
    [Set — CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set — Ксконференцесервер](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))

  - <span></span>  
    [New — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))

  - <span></span>  
    [Remove — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))

  - <span></span>  
    [Set — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))

  - <span></span>  
    [Granting — CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))

  - <span></span>  
    [New — CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))

  - <span></span>  
    [Remove — CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))

  - <span></span>  
    [Set — CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))

  - <span></span>  
    [New — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))

  - <span></span>  
    [Remove — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))

  - <span></span>  
    [Set — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))

<!-- end list -->

  - [Disable — CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))

  - [Enable — CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))

  - [Get — CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))

  - [Move — CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))

  - [Set — CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))

  - <span></span>  
    [Test-Ксавконференце](https://technet.microsoft.com/library/Gg412749(v=OCS.15))

  - <span></span>  
    [Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))

  - <span></span>  
    [Test-Ксвебапп](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - <span></span>  
    [Test-Ксвебаппанонимаус](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

  - <span></span>  
    [Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>См. также


[Блог Lync Server PowerShell](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

