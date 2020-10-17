---
title: 'Lync Server 2013: тестирование возможности использования расширения групп'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8c12d687d6c23c7c7bdc2bf2d8046038154c871
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520746"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Тестирование возможности использования расширения групп в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsGroupExpansion. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsGroupExpansion позволяет определить, работает ли расширение группы в Организации. Если включено расширение группы, пользователи настраивают группы рассылки как контакты. Это означает, что эти пользователи могут отправить одно и то же мгновенное сообщение всем участникам группы, отправляя сообщение в группу, а не отдельные участники этой группы. Углубление в группы позволяет быстро и просто увидеть всех членов группы и их текущее состояние.

С помощью командлета Test-CsGroupExpansion вы указываете группу рассылки Active Directory с помощью электронного адреса группы. В Test-CsGroupExpansion затем используется расширение группы для получения сведений о членстве в группах и сравнения полученного списка с членством в указанном адресе электронной почты группы. Если эти два списка совпадают, то значит углубление в группы работает правильно. Обратите внимание, что вы можете протестировать расширение группы двумя способами: Протестируйте саму службу или протестируйте связанную веб-службу.

Дополнительные сведения можно найти в справочной документации по командлету [Test-ксграупекспансион](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsGroupExpansion можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, который был включен для Lync Server. Чтобы выполнить эту проверку с помощью тестовой учетной записи, необходимо указать полное доменное имя тестируемого пула Lync Server и адрес электронной почты для действительной группы рассылки. Например:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Lync Server, содержащий имя учетной записи и пароль. Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, когда система вызывает Test-Ксграупекспансион:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Дополнительные сведения можно найти в справочной документации по командлету [Test-ксграупекспансион](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанный пользователь может использовать расширение группы, будет выведен результат, подобный следующему, с свойством Result, помеченным как **успешное:**

TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:01.1234976

Ошибкой

Диагност

Если указанный пользователь не может использовать расширение группы, то результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:

TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибкой

Диагност

Test-CsGroupExpansion: не удалось зарегистрировать конечную точку. Обратитесь к разделу ErrorCode по определенному причине.

Предыдущие выходные данные появлялись, что не удалось выполнить проверку, так как указанный пользователь не смог зарегистрироваться в Lync Server. Обычно это происходит, если тестовая учетная запись не существует или не включена для Lync Server. Вы можете убедиться, что учетная запись существует, и определить, включена ли учетная запись для NM-OCS-14-3, выполнив команду, аналогичную следующей:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Если Test-CsGroupExpansion завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Если включен параметр Verbose, Test-CsGroupExpansion будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server. Например, эти выходные данные указывают на то, что не удалось найти указанную группу рассылки:

Попытка получить веб-билет.

URL-адрес веб-службы: https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

Использование проверки подлинности NTLM/Kerbtray.

Жетвебтиккетактивити завершен.

Начато действие "Верифидистрибутионлист".

Состояние ответа веб-службы ДЛКС: Нотфаунд.

Действие ' Верифидистрибутионлист ' завершено в ' 0,2597923 ' сек.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsGroupExpansion:

  - Вы указали недопустимую учетную запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server. Чтобы убедиться, что учетная запись пользователя была включена для Lync Server, выполните команду, аналогичную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.

  - Расширение группы может быть отключено. Можно отключить расширение группы. Если расширение группы было отключено, командлет Test-CsGroupExpansion завершится с ошибками. Чтобы определить, включено ли расширение группы, используйте команду, аналогичную следующей:
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

