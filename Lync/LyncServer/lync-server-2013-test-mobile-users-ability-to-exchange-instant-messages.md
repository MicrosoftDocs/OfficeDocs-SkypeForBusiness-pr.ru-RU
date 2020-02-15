---
title: 'Lync Server 2013: Протестируйте мобильные пользователи возможность обмениваться мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84e4a79f511247b3c335872b7a1ec31fb9f2201e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Проверка возможности мобильных пользователей обмениваться мгновенными сообщениями в Lync Server 2013

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
<td><p>Monthly Channel</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsMcxP2PIM. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Служба Mobility Service позволяет пользователям мобильных устройств выполнять такие действия, как:

1.  Обмен мгновенными сообщениями и сведениями о присутствии Exchange.

2.  Храните и извлекать голосовую почту внутренне, а не со своего поставщика услуг беспроводной связи.

3.  Используйте возможности Lync Server, такие как вызов с помощью конференц-связи по работе и удаленному доступу.

Командлет Test-CsMxcP2PIM предоставляет простой и простой способ проверки того, что пользователи могут использовать службу Mobility Service для обмена мгновенными сообщениями.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Чтобы выполнить этот тест, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи. Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsMcxP2PIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если два тестовых пользователя могут обмениваться мгновенными сообщениями с помощью службы Mobility Service, то Test-CsMcxP2PIM будет возвращать результат теста Success:

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Целевой URI:http://atl-cs-001.litwareinc.com:443/mcx

Результат: успешное выполнение

Задержка: 00:00:00

Сообщение об ошибке:

Диагност

В противном случае результат будет настроен на сбой, и будет выведено подробное сообщение об ошибке и диагностика:

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Целевой URI:https://atl-cs-001.litwareinc.com:443/mcx

Результат: сбой

Задержка: 00:00:00

Сообщение об ошибке: нет ответа, полученного для службы веб-билета.

Внутреннее исключение: запрос ХХТП не авторизован для

Схема согласования клиента "NTLM". Проверка подлинности

заголовку, полученному от сервера, является "Negotiate, NTLM".

Внутреннее исключение: удаленный сервер вернул ошибку:

(401) авторизация недоступна.

Диагност

Внутренняя диагностика: X – MS $ Server – Фкдб: ATL – CS —

001.litwareinc.com

Cache — Control: Private

Content-Type: Text/HTML; charset = UTF – 8.

Сервер: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

Питание от X: ASP.NET

X — Content – Type — параметры: параметр "пассивный прослушивание"

Дата: среда, 28 мая 2014 19:16:05 GMT

Content — Length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Если Test-CsMcxP2PIM не удается выполнить первый шаг, необходимо убедиться, что служба Mobility Service работает и работает. Это можно сделать с помощью веб-браузера, чтобы проверить, что можно получить доступ к URL-адресу службы Mobility пула Lync Server. Например, эта команда проверяет URL-адрес пула atl-cs-001.litwareinc.com:

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Если служба Mobility Service работает, убедитесь, что у двух тестовых пользователей есть действительные учетные записи Lync Server. Вы можете получить сведения об учетной записи с помощью следующей команды:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Если свойство Enabled имеет значение, не равное true, или если команда завершается с ошибкой, то это означает, что у пользователя нет допустимой учетной записи Lync Server.

Кроме того, необходимо убедиться, что для пользователя включена поддержка мобильных устройств. Для этого сначала определите политику мобильности, назначенную учетной записи:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Зная имя политики, используйте командлет Get-CsMobilityPolicy, чтобы убедиться, что рассматриваемая политика (например, Редмондмобилитиполици) имеет свойство Енаблемобилити со значением true:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Если отображается сообщение об ошибке с заголовками проверки подлинности, это часто означает, что вы не указали допустимую учетную запись пользователя. Проверьте имя пользователя и пароль, а затем повторите проверку. Если вы убеждены, что учетная запись пользователя действительна, используйте командлет Get-CsWebServiceConfiguration и проверьте значение свойства Усевиндовсаус. , Покажет, какие методы проверки подлинности включены в вашей организации. Дополнительные советы по устранению неполадок в службе Mobility Service можно найти в статье блог [Устранение неполадок, связанных с подключением внешних мобильных устройств Lync, с](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)пошаговым выполнением.

</div>

</div>

<span> </span>

</div>

</div>

</div>

