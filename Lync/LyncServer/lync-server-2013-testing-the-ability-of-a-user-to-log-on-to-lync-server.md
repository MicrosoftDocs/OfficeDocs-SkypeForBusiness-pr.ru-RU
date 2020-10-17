---
title: 'Lync Server 2013: Проверка возможности входа пользователя на Lync Server'
description: 'Lync Server 2013: тестирование возможности входа пользователя на Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b86ae3e490af0b361799ed5fb3f56ed4de42c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556215"
---
# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Проверка возможности входа пользователя в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsRegistration. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsRegistration позволяет убедиться, что пользователи в организации могут входить в систему на сервере Lync Server. При выполнении командлета Test-CsRegistration командлет пытается войти в тестовый пользователь в Lync Server, а затем, если он был успешным, отсоединяется тестовый пользователь от системы. Все это происходит без вмешательства пользователя и без влияния на фактических пользователей. Например, предположим, что тестовая учетная запись sip:kenmyer@litwareinc.com соответствует реальному пользователю с действительной учетной записью Lync Server. В этом случае тест будет проводиться без какого-либо вмешательства в работу реального пользователя Ken Myer. Когда тестовая учетная запись Ken Myer выйдет из системы, личная учетная запись Ken Myer останется в системе.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsRegistration можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server. Чтобы выполнить эту проверку с помощью тестовой учетной записи, необходимо указать полное доменное имя тестируемого пула регистратора Lync Server. Например:

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи. Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-CsRegistration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанный пользователь может войти в систему, а затем выйти из нее с сервера Lync Server, будет выведен результат, подобный следующему, с помощью свойства Result, помеченного как **успешное:**

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.8630376

Ошибкой

Диагност

Если указанный пользователь не может войти в систему или выйти из нее, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения.

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: 404, не найдена

Диагностика: ErrorCode = 1003, Source = ATL-CS-001. litwareinc. com, Reason = пользователь выполняет

не существует

Microsoft. RTC. Signal. Диагностичеадер

Например, предыдущие выходные данные почтовых состояний не пройдены, так как не удалось найти указанного пользователя. Вы можете определить, является ли адрес SIP допустимым (и ли пользователь, которому назначен SIP-адрес, включен для Lync Server), выполнив следующую команду:

    Get-CsUser "sip:kenmyer@litwareinc.com"

Если Test-CsRegistration завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Если включен параметр Verbose, Test-CsRegistration будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server. Например:

VERBOSE: начато действие "Register".

Отправка запроса на регистрацию:

Целевое полное доменное имя = atl-cs-011.litwareinc.com

SIP адрес пользователя = sip:kenmyer@litwareinc.com

Порт регистратора = 5061.

Выбран тип проверки подлинности "доверенный".

Не удается зарегистрировать исключение "конечная точка не может быть зарегистрирована". Просмотрите код ошибки для конкретной причины "при выполнении рабочего процесса Microsoft. RTC. SyntheticTransactions. Workflow. Стрегистрерворкфлов.

Стек вызовов исключения: в Microsoft. RTC. SignalR. SipAsyncResult'1. Сровиффаилед ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsRegistration:

  - Вы указали неправильную учетную запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.

  - Указан недопустимый пул регистратора. С помощью этой команды можно получить полные доменные имена пулов регистратора.
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - В настоящее время пул регистратора недоступен. Попробуйте выполнить команду ping для пула, чтобы узнать, отвечает ли он:
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

