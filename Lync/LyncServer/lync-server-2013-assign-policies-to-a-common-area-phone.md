---
title: 'Lync Server 2013: назначение политик для телефонного телефона с общим регионом'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b792d6ae14ee13fd1d95761d2a0d6b0af7bbdfae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a>Назначение политик в Lync Server 2013 на стандартном телефоне

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

После создания политики для обычных телефонов (Дополнительные сведения см. [в разделе Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)) можно назначить политику для обычного телефона с помощью Windows PowerShell и соответствующего **гранта (CS). **командлета. Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a>Назначение политики единому телефону с общим регионом

  - Следующая команда назначает политику голосовой связи "на пользователя", Редмондвоице на общем телефоне с телефонным подключением, у которого установлен номер 14 зал здания.
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a>Назначение политики для нескольких распространенных телефонных областей

  - В этом примере политика голосовой связи "на пользователя" Редмондвоице назначается всем телефонам с общим диапазоном, настроенным для использования в Организации.
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

Подробности можно найти в статьях справки для [Grant-ксвоицеполици](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).

</div>

<div>

## <a name="see-also"></a>См. также


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

