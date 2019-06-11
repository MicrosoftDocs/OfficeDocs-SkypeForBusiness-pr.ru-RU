---
title: 'Lync Server 2013: Проверка возможности обмена мгновенными сообщениями с пользователями мобильных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7fd19f6ef2f4a44a61d56848b4bf845c79736ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Тестирование возможности мобильных пользователей обмениваться мгновенными сообщениями в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Ежемесячно</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Требуемые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</p>
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsMcxP2PIM. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Служба Mobility Service позволяет пользователям мобильных устройств выполнять такие действия, как:

1.  Обмен мгновенными сообщениями и сведениями о присутствии.

2.  Храните и изменяйте голосовую почту внутренне, а не с поставщиком услуг беспроводной связи.

3.  Пользуйтесь возможностями Lync Server, такими как звонки через Конференц-связь с телефонным подключением.

Командлет Test-CsMxcP2PIM предоставляет быстрый и простой способ проверки того, что пользователи могут использовать службу Mobility Service для обмена мгновенными сообщениями.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Чтобы выполнить этот тест, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи. После вызова Test-CsMcxP2PIM вы должны добавить эти объекты учетных данных и адреса SIP для двух учетных записей.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

Дополнительные сведения можно найти в разделе справки по командлету [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Если два тестовых пользователя могут обмениваться мгновенными сообщениями с помощью службы Mobility Service, при использовании команды Test-CsMcxP2PIM будут возвращены результаты проверки.

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Конечный URI:http://atl-cs-001.litwareinc.com:443/mcx

Результат: успех

Задержка: 00:00:00

Сообщение об ошибке:

Диагностик

В противном случае результат будет настроен на сбой, и на экране появится подробное сообщение об ошибке и диагностика.

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Конечный URI:https://atl-cs-001.litwareinc.com:443/mcx

Результат: сбой

Задержка: 00:00:00

Сообщение об ошибке: ни одного ответа не получено для службы веб-билета.

Внутреннее исключение: запрос ХХТП не разрешен

Клиентская схема согласования "NTLM". Проверка подлинности

заголовку, полученному от сервера, является "Negotiate, NTLM".

Внутреннее исключение: удаленный сервер вернул ошибку:

(401) от несанкционированного доступа.

Диагностик

Внутренняя диагностика: X-MS-Server-Фкдб: ATL-CS-

001.litwareinc.com

Cache-Control: Private

Content-Type: Text/HTML; charset = UTF-8.

Сервер: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

X — с питанием от: ASP.NET

X-Content-Types-параметры: onпрослушивание

Дата: СР. 28 мая 2014 19:16:05 GMT

Content-Length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Если при использовании команды Test-CsMcxP2PIM происходит сбой, необходимо убедиться в том, что служба Mobility Service работает. Это можно сделать с помощью веб-браузера, чтобы убедиться, что вы можете получить доступ к URL-адресу службы Mobility Service для пула Lync Server. Например, эта команда проверяет URL-адрес для пула atl-cs-001.litwareinc.com:

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Если служба Mobility Service работает, убедитесь в том, что у ваших двух тестовых пользователей есть действительные учетные записи Lync Server. Вы можете получить сведения об учетной записи с помощью следующей команды:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Если свойство Enabled не равно true или если команда не выполнена, это означает, что у пользователя нет действительной учетной записи Lync Server.

Кроме того, необходимо убедиться, что у пользователя включена поддержка мобильных устройств. Для этого сначала определите политику мобильности, назначенную учетной записи:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

После того как вы узнаете имя политики, используйте командлет Get-Ксмобилитиполици, чтобы убедиться, что для политики (например, Редмондмобилитиполици) задано значение true для свойства Енаблемобилити.

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Если появляется сообщение об ошибке с заголовком проверки подлинности, это часто означает, что вы не указали действительной учетной записи пользователя. Проверьте имя пользователя и пароль, а затем повторите проверку. Если вы убедились в том, что учетная запись пользователя верна, используйте командлет Get-Ксвебсервицеконфигуратион и проверьте значение свойства Усевиндовсаус. С помощью которого вы узнаете, какие методы проверки подлинности включены в вашей организации. Дополнительные советы по устранению неполадок со службой Mobility Service можно найти в статье пошаговые инструкции [по устранению неполадок, связанных с подключением к блогу внешних мобильных устройств Lync](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

