---
title: 'Lync Server 2013: тестирование публикации и подписки на присутствие пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335ad014595f855c1ccefab363f3cf34ad7c282b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503856"
---
# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a>Тестирование публикации и подписки на присутствие пользователей в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Ежедневное</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsPresence. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Test-CsPresence используется, чтобы определить, может ли пользователь, который является членом теста, войти в Lync Server, а затем получить сведения о присутствии Exchange. Сначала командлет выполняет вход в систему от имени этих пользователей. Если удается выполнить оба входа, первый тестовый пользователь запрашивает сведения о присутствии у второго пользователя. Второй пользователь публикует эти сведения, а командлет Test-CsPresence проверяет, что они успешно переданы первому пользователю. После обмена сведениями о присутствии два тестовых пользователя после выхода из Lync Server выводятся из Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsPresence можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей (см. Настройка тестовых учетных записей для запуска тестов Lync Server) или учетных записей двух пользователей, для которых включен Lync Server. Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server. Например:

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи. Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsPresence:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанные пользователи могут обмениваться сведениями о присутствии, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success.**

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.3280315

Ошибкой

Диагност

Если два пользователя не могут обмениваться сведениями о присутствии, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: 404, не найдена

Диагностика: ErrorCode = 4005, Source = ATL – CS – 001.litwareinc.com,

Reason = конечный URI либо не включен для SIP, либо не

есть.

Microsoft. RTC. Signal. Диагностичеадер

Например, предыдущее выходное состояние не удалось выполнить тест, так как по крайней мере одна из двух учетных записей пользователей является недопустимой: либо учетная запись не существует, либо она не была включена для Lync Server. Вы можете убедиться, что учетные записи существуют, и определить, включены ли они для Lync Server, выполнив следующую команду:

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

Если Test-CsPresence завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Если включен параметр Verbose, Test-CsPresence будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server. Например:

Попадание в запрос на регистрацию для неизвестного

Действие ' Register ' завершено в ' 0,0345791 ' сек.

Начато действие "Селфсубскрибеактивити".

Действие ' Селфсубскрибеактивити ' завершено в ' 0,0041174 ' сек.

Начато действие "Субскрибепресенце".

Действие ' Субскрибепресенце ' завершено в ' 0,0038764 ' сек.

Начато действие "Публишпресенце".

Уведомление о присутствии не получается в течение 25 сек. произошла ошибка руинг рабочего процесса Microsoft. RTC. SyntheticTransactions. Workflows. Стпресенцеворкфлов Execution.

Тот факт, что уведомление о присутствии не было получено в течение 25 секунд, может означать, что проблемы с сетью препятствуют обмену данными.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsPresence:

  - Вы указали неправильную учетную запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если для свойства Enabled задано значение false, то в настоящее время у пользователя не включена поддержка Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

