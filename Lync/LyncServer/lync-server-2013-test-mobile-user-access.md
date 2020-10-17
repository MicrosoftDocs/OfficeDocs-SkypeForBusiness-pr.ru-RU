---
title: 'Lync Server 2013: Проверка доступа мобильных пользователей'
description: 'Lync Server 2013: Проверка доступа мобильных пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99a05e6ef9fe925126026452823e5edcc100ede
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541875"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a>Проверка доступа пользователей мобильных устройств в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Monthly</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsMcxConference. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Служба Mobility Service позволяет пользователям мобильных устройств выполнять такие действия, как:

1.  Обмен мгновенными сообщениями и сведениями о присутствии Exchange.

2.  Храните и извлекать голосовую почту внутренне, а не со своего поставщика услуг беспроводной связи.

3.  Используйте возможности Lync Server, такие как вызов с помощью конференц-связи по работе и удаленному доступу. Командлет Test-CsMcxConference предоставляет быстрый и простой способ проверки того, что пользователи могут присоединяться к конференциям Lync Server и участвовать в них с помощью мобильного устройства.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Чтобы выполнить эту проверку, необходимо создать три объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи. Затем необходимо включить эти объекты учетных данных и адреса SIP этих учетных записей при вызове Test-CsMcxConference, как показано в следующем примере:

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если проверка прошла успешно, Test-CsMcxConference сообщит результат теста "успех":

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Целевой URI: http://atl-cs-001.litwareinc.com:443/mcx

Результат: успешное выполнение

Задержка: 00:00:00

Сообщение об ошибке:

Диагност

Если проверка неуспешна Test-CsMcxConference будет сообщать о результатах сбоя. Этот результат проверки обычно сопровождается подробным сообщением об ошибке и диагностикой. Например:

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Целевой URI: https://atl-cs-001.litwareinc.com:443/mcx

Результат: сбой

Задержка: 00:00:00

Сообщение об ошибке: нет ответа, полученного для службы Web-Ticket.

Внутреннее исключение: запрос ХХТП не авторизован для клиента

Схема согласования "NTLM". Полученный заголовок проверки подлинности

с сервера было "согласование".

Внутреннее исключение: удаленный сервер вернул ошибку: (401)

Доступ.

Диагност

Внутренняя диагностика: X — MS $ Server – Фкдб: atl-cs-001.litwareinc.com

Cache-Control: Private

Content-Type: Text/HTML; charset = UTF – 8.

Сервер: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

Питание от X: ASP.NET

X — Content – Type — параметры: параметр "пассивный прослушивание"

Дата: среда, 28 мая 2014 19:22:19 GMT

Content — Length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Если Test-CsMcxConference не удастся, сначала убедитесь, что служба Mobility Service запущена и доступна. Это можно сделать с помощью веб-браузера, чтобы проверить, что можно получить доступ к URL-адресу службы Mobility пула Lync Server. Например, эта команда проверяет URL-адрес пула atl-cs-001.litwareinc.com:

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

Если вы можете получить доступ к службе Mobility Service, убедитесь, что тестовые пользователи имеют действительные учетные записи Lync Server. Вы можете получить сведения об учетной записи с помощью следующей команды:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Если свойство Enabled имеет значение, не равное true, или если команда завершается с ошибкой, то это означает, что у пользователя нет допустимой учетной записи Lync Server. Кроме того, необходимо убедиться, что для каждой учетной записи пользователя включена поддержка мобильных устройств. Для этого сначала определите политику мобильности, назначенную учетной записи:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Зная имя политики, используйте командлет Get-CsMobilityPolicy, чтобы убедиться в том, что в рассматриваемой политике (например, Редмондмобилитиполици) свойство Енаблемобилити имеет значение true:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

При получении сообщения об ошибке "заголовок проверки подлинности" при запуске Test-CsMcxConference, что часто означает, что вы не указали допустимую учетную запись пользователя, проверьте имя пользователя и пароль, а затем повторите проверку. Если вы убеждены, что учетная запись пользователя действительна, используйте командлет Get-CsWebServiceConfiguration и проверьте значение свойства Усевиндовсаус. , Покажет, какие методы проверки подлинности включены в вашей организации.

Дополнительные советы по устранению неполадок в службе Mobility Service можно найти в статье блог [Устранение неполадок, связанных с подключением внешних мобильных устройств Lync, с](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)пошаговым выполнением.

</div>

</div>

<span> </span>

</div>

</div>

</div>

