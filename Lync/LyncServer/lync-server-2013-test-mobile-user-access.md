---
title: 'Lync Server 2013: Проверка доступа пользователей мобильных устройств'
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
ms.openlocfilehash: 628fd3aae4f66316627176c3af025eb63202bafb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a>Проверка доступа пользователей мобильных устройств в Lync Server 2013

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
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксмкксконференце. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Служба Mobility Service позволяет пользователям мобильных устройств выполнять такие действия, как:

1.  Обмен мгновенными сообщениями и сведениями о присутствии.

2.  Храните и изменяйте голосовую почту внутренне, а не с поставщиком услуг беспроводной связи.

3.  Пользуйтесь возможностями Lync Server, такими как звонки через Конференц-связь с телефонным подключением. Командлет Test-Ксмкксконференце предоставляет быстрый и простой способ убедиться, что пользователи могут присоединяться к конференции Lync Server и принимать участие в них, используя мобильное устройство.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Для выполнения этой проверки необходимо создать три объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи. При вызове теста-Ксмкксконференце, как показано в следующем примере, необходимо добавить эти объекты учетных данных и адреса SIP для двух учетных записей.

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

Дополнительные сведения можно найти в разделе справки по командлету [Test-ксмкксконференце](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Если проверка пройдет успешно, тест-Ксмкксконференце сообщит результат теста "успешно".

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Конечный URI:http://atl-cs-001.litwareinc.com:443/mcx

Результат: успех

Задержка: 00:00:00

Сообщение об ошибке:

Диагностик

Если проверка не пройдет успешно, Ксмкксконференце сообщит результаты теста о сбое. Этот результат проверки обычно сопровождается подробным сообщением об ошибке и диагностикой. Например:

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Конечный URI:https://atl-cs-001.litwareinc.com:443/mcx

Результат: сбой

Задержка: 00:00:00

Сообщение об ошибке: ни одного ответа не получено для службы веб-билета.

Внутреннее исключение: запрос ХХТП не разрешен клиентом

Схема согласования "NTLM". Полученный заголовок проверки подлинности

с сервера: "согласование".

Внутреннее исключение: удаленный сервер вернул ошибку (401).

Прошедшим.

Диагностик

Внутренняя диагностика: X-MS-Server-Фкдб: atl-cs-001.litwareinc.com

Cache-Control: Private

Content-Type: Text/HTML; charset = UTF-8.

Сервер: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

X — с питанием от: ASP.NET

X-Content-Types-параметры: onпрослушивание

Дата: СР. 28 мая 2014 19:22:19 GMT

Content-Length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Если при выполнении теста-Ксмкксконференце возникла ошибка, убедитесь в том, что служба Mobility Service запущена и доступ к ней возможен. Это можно сделать с помощью веб-браузера, чтобы убедиться, что вы можете получить доступ к URL-адресу службы Mobility Service для пула Lync Server. Например, эта команда проверяет URL-адрес для пула atl-cs-001.litwareinc.com:

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

Если вы можете получить доступ к службе Mobility Service, вы должны убедиться, что у ваших тестовых пользователей есть действительные учетные записи Lync Server. Вы можете получить сведения об учетной записи с помощью следующей команды:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Если свойство Enabled не равно true или если команда не выполнена, это означает, что у пользователя нет действительной учетной записи Lync Server. Кроме того, необходимо убедиться в том, что для каждой учетной записи пользователя включена поддержка мобильных устройств. Для этого сначала определите политику мобильности, назначенную учетной записи:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

После того как вы узнаете имя политики, используйте командлет Get-Ксмобилитиполици, чтобы убедиться, что для политики (например, Редмондмобилитиполици) задано значение true для свойства Енаблемобилити.

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Если при запуске test-Ксмкксконференце появляется сообщение об ошибке "заголовок для проверки подлинности", которое часто означает, что вы не указали действительную учетную запись пользователя, проверьте имя пользователя и пароль, а затем повторите проверку. Если вы убедились в том, что учетная запись пользователя верна, используйте командлет Get-Ксвебсервицеконфигуратион и проверьте значение свойства Усевиндовсаус. С помощью которого вы узнаете, какие методы проверки подлинности включены в вашей организации.

Дополнительные советы по устранению неполадок со службой Mobility Service можно найти в [статье пошаговые инструкции по устранению неполадок, связанных с подключением к блогу внешних мобильных устройств Lync](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

