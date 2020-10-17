---
title: 'Lync Server 2013: создание политик расположения'
description: 'Lync Server 2013: создание политик расположения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 464ea9893890ab6185f180434e2dad13818123d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562265"
---
# <a name="create-location-policies-in-lync-server-2013"></a>Создание политик расположения в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-11_

Lync Server использует политику расположения для включения клиентов Lync для E9 – 1 — 1 во время регистрации клиента. Политика расположения содержит параметры, которые определяют порядок внедрения E9-1-1..

Глобальную политику расположения можно редактировать, кроме того, можно создавать новые именованные политики расположения. Клиент получает глобальную политику, если он расположен не в подсети, для которой имеется связанная локальная политика, или если локальная политика не назначена ему напрямую. Именованные политики назначаются подсетям или пользователям.

Чтобы создать политику расположения, следует использовать учетную запись, являющуюся членом группы RTCUniversalServerAdmins или административной роли CsVoiceAdministrator или обладает эквивалентными правами и разрешениями администратора.

Полное описание политик расположения приведено [в разделе Определение политики расположения для Lync Server 2013](lync-server-2013-defining-the-location-policy.md). Командлеты в этой процедуре используют заданную политику расположения и приведенные ниже значения.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Элемент</th>
<th>Значение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>енханцедемерженцисервицесенаблед</p></td>
<td><p><strong>True</strong></p></td>
</tr>
<tr class="even">
<td><p>локатионрекуиред</p></td>
<td><p><strong>Заявление об отказе от ответственности</strong></p></td>
</tr>
<tr class="odd">
<td><p>енханцедемерженцисервицедисклаимер</p></td>
<td><p>Политика вашей компании требует задать расположение. В противном случае в экстренной ситуации соответствующие службы не смогут определить ваше расположение. Задайте расположение.</p></td>
</tr>
<tr class="even">
<td><p>Параметра uselocationfore911only установлено</p></td>
<td><p><strong>False</strong></p></td>
</tr>
<tr class="odd">
<td><p>Параметра pstnusage</p></td>
<td><p><strong>емерженциусаже</strong></p></td>
</tr>
<tr class="even">
<td><p>емерженцидиалстринг</p></td>
<td><p><strong>911</strong></p></td>
</tr>
<tr class="odd">
<td><p>EmergencyDialMask</p></td>
<td><p><strong>112</strong></p></td>
</tr>
<tr class="even">
<td><p>нотификатионури</p></td>
<td><p><strong>sip:security@litwareinc.com</strong></p></td>
</tr>
<tr class="odd">
<td><p>конференцеури</p></td>
<td><p><strong>sip:+14255550123@litwareinc.com</strong></p></td>
</tr>
<tr class="even">
<td><p>конференцемоде</p></td>
<td><p><strong>TwoWay</strong></p></td>
</tr>
<tr class="odd">
<td><p>локатионрефрешинтервал</p></td>
<td><p><strong>2</strong></p></td>
</tr>
</tbody>
</table>


Для получения подробных сведений о работе с политиками расположения обратитесь к документации по командной консоли Lync Server для следующих командлетов:

  - New-CsLocationPolicy

  - Get-CsLocationPolicy

  - Set-CsLocationPolicy

  - Remove-CsLocationPolicy

  - Grant-CsLocationPolicy

<div>

## <a name="to-create-location-policies"></a>Создание политик расположения

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.
    
    <div>
    

    > [!NOTE]  
    > Командлет CsLocationPolicy завершится с ошибкой, если значение для параметра <STRONG>PstnUsage</STRONG> не будет содержаться в глобальном списке параметров PstnUsage.

    
    </div>

2.  Чтобы изменить глобальную политику расположения, можно дополнительно выполнить следующий командлет:
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  Выполните следующие действия, чтобы создать именованную политику расположения.
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  Выполните следующий командлет, чтобы применить именованную политику расположения, созданную в шаге 3, к политике пользователя.
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

