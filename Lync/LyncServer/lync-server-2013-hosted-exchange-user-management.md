---
title: 'Lync Server 2013: Управление пользователями размещенного сервера Exchange'
description: 'Lync Server 2013: Управление пользователями размещенного сервера Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ceda9352fc627fc7b762b5995d788ffafa159ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550115"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Управление пользователями размещенного сервера Exchange в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-18_

Для предоставления служб голосовой почты для пользователей Lync Server 2013, чьи почтовые ящики расположены в размещенной службе Exchange, необходимо включить учетные записи пользователей для размещенной голосовой почты.

<div>


> [!NOTE]  
> Прежде чем можно будет включить поддержку размещенной голосовой почты для пользователя Lync Server 2013, необходимо развернуть политику размещенной голосовой почты, которая применяется к соответствующей учетной записи пользователя. Эта политика может задаваться на глобальном уровне, на уровне сайта или на уровне пользователя и применяться к пользователю, которому требуется предоставить голосовую почту. Дополнительные сведения см. <A href="lync-server-2013-hosted-voice-mail-policies.md">в разделе политики размещенной голосовой почты в Lync Server 2013</A>.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>Атрибут msExchUCVoiceMailSettings

Lync Server 2013 представляет новый атрибут пользователя с именем **msExchUCVoiceMailSettings**, который создается в рамках подготовки схемы Lync Server 2013 Active Directory. Этот многозначный атрибут содержит параметры голосовой почты, которые являются общими для Lync Server 2013 и размещенной службы Exchange.

Размещенная служба Exchange может в некоторых случаях устанавливать значение атрибута msExchUCVoiceMailSettings в процессе включения единой системы обмена сообщениями Exchange или в процессе переноса почтовых ящиков на размещенный Exchange Server. Если этот атрибут не задан Exchange, администратор Lync Server 2013 должен задать его, выполнив командлет Set-CsUser, как описано ранее в этой статье.

В следующей таблице показаны пары "ключ-значение" для этого атрибута и их авторы.

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>Пары "ключ-значение" атрибута msExchUCVoiceMailSettings

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Значение</th>
<th>Автор</th>
<th>Смысл</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server предоставил пользователю доступ к размещенной единой системе обмена сообщениями. Приложение маршрутизации единой системы обмена сообщениями Exchange будет проверять политику размещенной голосовой почты пользователя для сведений о маршрутизации.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server запретил пользователю доступ к размещенной единой системе обмена сообщениями.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>Для пользователя включен доступ к размещенной единой системе обмена сообщениями в Lync Server 2013. Приложение Lync Server 2013 ExUM Routing будет проверять политику размещенной голосовой почты пользователя для сведений о маршрутизации.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>Пользователь отключил доступ к размещенной единой системе обмена сообщениями в Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Если атрибут уже содержит значения, отличные от пар "ключ-значение" в Lync Server 2013 (CSHostedVoiceMail = 0 или CSHostedVoiceMail = 1), то предупреждение будет указывать на то, что этот атрибут может управляться другим приложением. Например, предупреждение отображается в том случае, если пара "ключ-значение" ExchangeHostedVoiceMail=0 или ExchangeHostedVoiceMail=1 уже существует. В таком случае можно изменить это значение в Active Directory или выполнить следующий командлет, чтобы установить значение NULL:<BR>Set-CsUser –identity user –HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>Предоставление пользователям размещенной голосовой почты

Чтобы обеспечить перенаправление вызовов голосовой почты пользователя в размещенную единую систему обмена сообщениями Exchange, необходимо выполнить командлет Set-CsUser для установки значения параметра *HostedVoiceMail*. Этот параметр также сигнализирует Lync Server 2013, чтобы получить индикатор "позвонить голосовой почте".

  - В следующем примере учетной записи пользователя Пилар Акерман (Pilar Ackerman) предоставляется размещенная голосовая почта:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    Этот командлет проверяет, применяется ли к этому пользователю политика маршрутизации размещенной голосовой почты (глобально, на уровне сайта или на уровне пользователя). Если политика не применяется, то командлет завершается неудачно.

  - В следующем примере учетная запись пользователя Пилар Акерман (Pilar Ackerman) отключается от размещенной голосовой почты:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    Этот командлет проверяет, применяется ли к этому пользователю политика маршрутизации размещенной голосовой почты (глобально, на уровне сайта или на уровне пользователя). Если политика применяется, то командлет завершается неудачно.

Дополнительные сведения об использовании командлета Set-CsUser см в документации по консоли управления Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

