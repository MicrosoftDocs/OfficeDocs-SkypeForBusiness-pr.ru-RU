---
title: 'Lync Server 2013: Проверка аудио-и видеоконференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0bfeef1abcf7b5859c365b7c64b4fcc84f49ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503706"
---
# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>Проверка аудио-и видеоконференций в Lync Server 2013

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
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Расписание проверки</p></td>
<td><p>Ежедневное</p></td>
</tr>
<tr class="odd">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsAVConference. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsAVConference проверяет, могут ли два тестовых пользователя участвовать в аудио-или видеоконференции (A/V). Когда командлет запускается, два пользователя входят в систему. После успешного входа в систему первый пользователь создает конференцию аудио-и видеосвязи, а затем ждет, пока второй пользователь присоединяется к этой Конференции. После короткого обмена данными конференция удаляется и два тестовых пользователя выходят из системы.

Обратите внимание на то, что Test-CsAVConference не выполняет собственно видеоконференцию A/V между двумя тестовыми пользователями. Вместо этого командлет проверяет, могут ли два пользователя выполнить все подключения, необходимые для проведения такой конференции.

Дальнейшие примеры для этой команды можно найти на странице [Test-ксавконференце](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsAVConference можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей (см. Настройка тестовых учетных записей для запуска тестов Lync Server) или учетных записей двух пользователей, для которых включен Lync Server. Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server. Например:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи. Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-Ксавконференце:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Дополнительные сведения можно найти в справочной документации по командлету [Test-ксавконференце](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанные пользователи могут успешно завершить аудио-или видеоконференцию, вы получите результат, аналогичный приведенному ниже, и свойство Result помечено как **Success.**

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:02.6841765

Ошибкой

Диагност

Если пользователи не могут выполнить конференц-связи, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: 404, не найдена

Диагностика: ErrorCode = 4005, Source = ATL – CS – 001.litwareinc.com,

Reason = конечный URI либо не включен для SIP, либо не

есть.

Microsoft. RTC. Signal. Диагностичеадер

Например, предыдущие выходные данные появлялись, так как по крайней мере одна из двух учетных записей пользователей была недействительной из-за того, что учетная запись не существует или учетная запись не включена для Lync Server. Можно проверить наличие двух тестовых учетных записей и включить ли они для Lync Server, выполнив команду, аналогичную следующей:

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

Если Test-CsAVConference завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Если включен параметр Verbose, Test-CsAVConference будет возвращать пошаговые учетные записи каждого действия, которое он попытался проверить, сможет участвовать в конференции с помощью AV. Например, предположим, что тест завершается сбоем и вы получаете следующую диагностику:

ErrorCode = 1008, Source = акцесспрокси. litwareinc. com, Reason = не удается разрешить запись SRV DNS

Если вы повторно перезапустите тест с параметром verbose, возвращаемые сведения о пошаговых шагах будут иметь следующий результат:

VERBOSE: начато действие "Register".

Отправка запроса на регистрацию:

Целевое полное доменное имя = atl-cs-001.litwareinc.com

SIP адрес пользователя = sip:davidlongmire@litwareinc.com

Порт регистратора = 5061.

Выбран тип проверки подлинности "доверенный".

Начато действие Register.

Отправка запроса на регистрацию:

Целевое полное доменное имя = atl-cs-001.litwareinc.com

SIP адрес пользователя = sip:kenmyer@litwareinc.com

Порт регистратора = 5061.

Выбран тип проверки подлинности "доверенный".

Исключение "не удалось зарегистрировать конечную точку. Обратитесь к разделу ErrorCode по определенному причине. При выполнении рабочего процесса

Последняя строка этого результата показывает, что пользователь sip:kenmyer@litwareinc.com не смог зарегистрироваться в Lync Server. Это означает, что необходимо убедиться, что адрес SIP sip:kenmyer@litwareinc.com является допустимым и что связанный пользователь включен для Lync Server.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsAVConference:

  - Указана недопустимая учетная запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
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

