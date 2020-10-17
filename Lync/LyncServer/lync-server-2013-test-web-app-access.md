---
title: 'Lync Server 2013: тестирование доступа веб-приложения'
description: 'Lync Server 2013: тестирование доступа веб-приложения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc3bbc8008df4fe47fc5a39571356383fe5a6035
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560835"
---
# <a name="test-web-app-access-in-lync-server-2013"></a>Проверка доступа веб-приложения в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsWebApp. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsWebApp проверяет, могут ли пользователи, прошедшие проверку подлинности, присоединиться к конференциям Lync Server с помощью веб-приложения Lync. При запуске командлета Test-CsWebApp связывается со службой веб-билета для получения веб-билетов для указанных пользователей. Эти билеты эффективно действуют как "билеты на допуску" для конференции Lync Server. Если можно получить билеты и проверить подлинность пользователей, Test-CsWebApp будет обращаться к Lync Server и пытаться установить отдельные конференции для обмена мгновенными сообщениями, общего доступа к приложениям и совместной работы с данными.

Обратите внимание, что Test-CsWebApp просто проверяет интерфейсы API и подключения, используемые для создания этих конференций. Командлет позволяет убедиться в том, что Lync Web App можно использовать для создания конференций и присоединения к ним. Однако он не создает и не проводит конференц-связи.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsWebApp можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей или учетных записей двух пользователей, для которых включен Lync Server. Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server. Например:

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи. Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-Ксвебапп:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-ксвебапп](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) . Обратите внимание, что Test-CsWebApp было признано нерекомендуемым для использования в Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если Test-CsWebApp можете присоединиться к конференциям, командлет вернет результат теста Success:

Целевое полное доменное имя:

Результат: успешное выполнение

Задержка: 00:00:00

Сообщение об ошибке:

Диагност

Если пользователи не могут присоединиться к необходимым конференциям, результат теста будет помечен как сбой. Как правило, Test-CsWebApp также будет сообщать о подробном сообщении об ошибке и диагностике:

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Сообщение об ошибке: нет ответа, полученного для службы Web-Ticket

Диагностика: несанкционированный HTTP-запрос для клиента

Схема проверки подлинности "NTLM". Проверка подлинности

заголовку, полученному от сервера, является "Negotiate, NTLM".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ошибки Test-CsWebApp обычно включают ошибки проверки подлинности пользователей. В случае сбоя Test-CsWebApp сначала необходимо убедиться, что указанные пользователи имеют действительные учетные записи пользователей и включены для Lync Server. Вы можете получить сведения об учетной записи с помощью следующей команды:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Если свойство Enabled имеет значение, не равное true, или если команда завершается с ошибкой, то это означает, что у пользователя нет допустимой учетной записи Lync Server. Кроме того, необходимо убедиться, что указанные в командлете пароли действительны.

</div>

</div>

<span> </span>

</div>

</div>

</div>

