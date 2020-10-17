---
title: 'Lync Server 2013: тестирование однорангового аудио-и видеозвонка'
description: 'Lync Server 2013: тестирование однорангового аудио-и видеозвонка.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03bab69d926a99c091a510ce64b78dbf505d4cbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556295"
---
# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Тестирование однорангового аудио-и видеозвонка в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsP2PAV. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Test-CsP2PAV используется для определения того, может ли пользователь иметь возможность участвовать в одноранговой беседе A/V. Чтобы протестировать этот сценарий, командлет начинает с ведения журнала для двух пользователей в Lync Server. Предположим, что вход обоих пользователей выполнен успешно, а первый пользователь приглашает второго пользователя в аудио-видео беседу. Второй пользователь принимает приглашение, проверяется подключение между двумя пользователями, а затем вызов завершается, а тестовые пользователи выходят из системы.

Test-CsP2PAV на самом деле не проводит функцию "аудио" или "V". Обмен мультимедийными данными между тестовыми пользователями не осуществляется. Вместо этого командлет проверяет, могут ли быть выполнены соответствующие подключения, и могут ли два пользователя совершать такой вызов.

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsP2PAV можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей (см. Настройка тестовых учетных записей для запуска тестов Lync Server) или учетных записей двух пользователей, для которых включен Lync Server. Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server. Например:

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных Lync Server (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи. Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsP2PAV:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если два тестовых пользователя могут выполнить одноранговый вызов A/V, вы получите выходные данные, аналогичные приведенным ниже, со свойством Result, помеченным как **Success.**

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.8630376

Ошибкой

Диагност

Если тестовые пользователи не могут выполнить вызов, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: 480, временно недоступна

Диагностика: ErrorCode = 15030, Source = ATL-CS-001. litwareinc. com, Reason = Failed

порядок маршрутизации в Exchange Server

Microsoft. RTC. Signal. Диагностичеадер

Например, предыдущие выходные данные почтовых состояний завершились сбоем, так как не удалось связаться с сервером Microsoft Exchange. Это сообщение об ошибке обычно указывает на проблему, связанную с настройкой единой системы обмена сообщениями Exchange.

В случае сбоя Test-CsP2PAV вы можете повторно выполнить тест, на этот раз включая параметр verbose:

Test-CsP2PAV TargetFqdn "atl-cs-001.litwareinc.com" — подробные сведения

Если включен параметр Verbose, Test-CsP2PAV будет возвращать пошаговые учетные записи каждого выполняемого действия, так как он проверил возможность входа в систему на Lync Server для указанного пользователя. Например, предположим, что тест завершился со следующей диагностикой:

ErrorCode = 6003, Source = ATL-CS-001. litwareinc. com, Reason = не поддерживается в диалоговом окне запроса

Если вы перезапустите Test-CsP2PAV и включите параметр Verbose, вы получите результат, подобный следующему:

VERBOSE: начато действие "Register".

Отправка запроса на регистрацию:

Целевое полное доменное имя = atl-cs-011.litwareinc.com

SIP адрес пользователя = sip:kenmyer@litwareinc.com

Порт регистратора = 5062.

Выбран тип проверки подлинности "Ива".

Исключение "не удалось зарегистрировать конечную точку. Обратитесь к разделу ErrorCode по определенному причине. возникла во время выполнения рабочего процесса Microsoft. RTC. SyntheticTransactions. Workflows. STP2PAVWorkflow.

Несмотря на то, что в результате анализа результатов может быть непросто очевидно, вы увидите, что был указан недопустимый порт регистратора (порт 5062). В свою очередь это привело к сбою теста.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsP2PAV:

  - Указана недопустимая учетная запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
    Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

