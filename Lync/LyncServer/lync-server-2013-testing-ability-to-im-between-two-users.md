---
title: 'Lync Server 2013: тестирование возможности обмена мгновенными сообщениями между двумя пользователями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08627842b5a58a72801a018e8e8da49fcdeb249
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42015372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Возможность тестирования обмена мгновенными сообщениями между двумя пользователями в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsIM. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsIM проверяет, могут ли две тестовых пользователя обмениваться мгновенными сообщениями. При вызове командлет Test-CsIM начинает работу, пытаясь войти в систему на сервере Lync Server с помощью учетной записи пользователя. При условии, что два входа успешно выполнены, командлет запускает сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями. (Пользователь 1 приглашает пользователя 2 в сеанс обмена мгновенными сообщениями, а пользователь 2 принимает приглашение.) После проверки того, что сообщения могут обмениваться между двумя пользователями, Test-CsIM завершает сеанс обмена мгновенными сообщениями и записывает в систему обоих пользователей.

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsIM можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетных записей двух пользователей с включенной поддержкой Lync Server. Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server. Пример:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи. Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если два пользователя могут выполнить сеанс обмена мгновенными сообщениями, будет выведен результат, подобный следующему, при этом свойство Result помечается как **успешное:**

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.6630911

Ошибкой

Диагност

Если тестовые пользователи не могут завершить сеанс, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: 504, время ожидания сервера

Диагностика: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, Reason = видите

код отклика и фраза причины.

Microsoft. RTC. Signal. Диагностичеадер

Например, предыдущие выходные данные почтовых состояний не пройдены, так как не удалось найти указанного пользователя. Можно определить, является ли адрес SIP допустимым (и ли пользователь, которому был назначен SIP-адрес, включен для Lync Server), выполнив следующую команду:

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Если Test-CsIM завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Если включен параметр Verbose, Test-CsIM будет возвращать пошаговое выполнение каждого действия, выполняемого при проверке того, что два тестовых пользователя участвуют в сеансе обмена мгновенными сообщениями. Например, приведенный ниже пример выходных данных, возникающих при наличии неправильного набора учетных данных пользователя (в данном случае, неправильного пароля), предоставляется для Test-CsIM:

Отправка запроса на регистрацию:

Целевое полное доменное имя = atl-cs-011.litwareinc.com

SIP адрес пользователя = sip:kenmyer@litwareinc.com

Порт регистратора = 5061

Выбран тип проверки подлинности "Ива".

Регистрация с использованием SIP/ATL-CS-001. litwareinc. com

Действие ' Register ' завершено в ' 0,0601795 ' сек.

Исключение "при входе в систему было отклонено. Убедитесь, что используются правильные учетные данные, а учетная запись активна. " При выполнении рабочего процесса.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsIM:

  - Указана недопустимая учетная запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если для свойства Enabled задано значение false, то в настоящее время у пользователя не включена поддержка Lync Server.

  - Служба обмена мгновенными сообщениями может быть недоступна. С помощью Lync Server можно настроить систему таким образом, чтобы мгновенные сообщения не были доступны, если не удается получить доступ к базе данных архивации. Это можно проверить, выполнив команду, аналогичную следующей:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Если для Блокконарчивефаилуре задано значение true, то следует определить, доступна ли база данных архивации. Вы можете вернуть расположения баз данных архивации с помощью следующей команды:
    
        Get-CsService -ArchivingDatabase

  - Сервер архивации может быть недоступен. С помощью этой команды можно получить полное доменное имя серверов архивации:
    
        Get-CsService -ArchivingServer
    
    После этого вы можете проверить связь с соответствующим сервером, чтобы убедиться, что он доступен. Пример:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

