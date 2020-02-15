---
title: 'Lync Server 2013: Проверка сеанса конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d83d3c3fe933a4538d9c2508668497af42c3340
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>Проверка сеанса конференц-связи с телефонным подключением в Lync Server 2013

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
<td><p>Daily (Ежедневный)</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsDialInConferencing. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsDialInConferencing проверяет, может ли пользователь участвовать в конференции с телефонным подключением. Test-CsDialInConferencing работает, пытаясь записать тестового пользователя в систему. Если вход выполнен успешно, командлет затем использует учетные данные пользователя и разрешения, чтобы попробовать все доступные номера доступа к конференц-связи с телефонным подключением. Успешное или неудачное завершение каждой попытки проверки подлинности. После этого тестовый пользователь будет выполнен выход из Lync Server. Test-CsDialInConferencing только проверяет, могут ли быть выполнены соответствующие подключения. В действительности он не выполняет никакие телефонные звонки и не создает никаких конференций с телефонным подключением, к которым могли бы присоединиться другие пользователи.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsDialInConferencing можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server. Чтобы выполнить эту проверку с помощью тестовой учетной записи, достаточно указать полное доменное имя тестируемого пула Lync Server. Пример:

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи. Затем необходимо добавить этот объект учетных данных и SIP-адрес учетной записи, вызывающей Test-CsDialInConferencing:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанный пользователь может войти в систему Lync Server и установить подключение, используя один из доступных номеров доступа к конференц-связи с телефонным подключением, будет получен результат, подобный следующему, при этом свойство Result помечается как **успешное:**

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.8630376

Ошибкой

Диагност

Если указанный пользователь не может сделать это подключение, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: при входе в систему было отказано. Убедитесь, что правильные учетные данные

используется, и учетная запись активна.

Внутреннее исключение: сбой НеготиатесекуритяссоЦиатион, ошибка: —

2146893044

Диагност

Приведенные выше выходные данные показывают, что тестовый пользователь отклонил доступ к серверу Lync Server. Обычно это означает, что учетные данные пользователя, переданные в Test-CsDialInConferencing, являются недопустимыми. В свою очередь, необходимо повторно создать объект учетных данных Windows PowerShell. Несмотря на то, что вы можете получить пароль для учетной записи пользователя, вы можете проверить SIP адрес, выполнив следующую команду:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsDialInConferencing:

  - Указана недопустимая учетная запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.

  - Возможно, у вас неверный номер доступа к конференц-связи с телефонным подключением. С помощью этой команды можно возвратить список номеров доступа для конференц-связи с телефонным подключением, настроенный в текущий момент:
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

