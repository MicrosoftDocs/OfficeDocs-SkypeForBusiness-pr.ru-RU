---
title: 'Lync Server 2013: Проверка возможности пользователя войти на сервер Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6cae2899d08765faf5d605ea20ae111f395ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Проверка возможности пользователя войти на сервер Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Ежедневно</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Требуемые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</p>
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксрегистратион. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-Ксрегистратион позволяет удостовериться, что пользователи в вашей организации могут войти на сервер Lync Server. При запуске test-Ксрегистратион командлет пытается войти в тестовый пользователь на Lync Server, а затем, если он успешно завершает работу, с помощью которого тестовый пользователь будет отключен от системы. Все это происходит без взаимодействия с пользователем и без воздействия каких – либо реальных пользователей. Например, предположим, что проверка учетной записи sip:kenmyer@litwareinc.comа с реальным пользователем, у которого есть учетная запись сервера Lync Server. В этом случае тест будет проводиться без перерывов в работе Кен мер. Когда Кен мер тестовая учетная запись выходит из системы, Кен мер человека останется на входе.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-Ксрегистратион можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи пользователя, который включен для Lync Server. Для выполнения этой проверки с помощью тестовой учетной записи необходимо указать полное доменное имя для тестируемого пула регистраторов Lync Server. Например:

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, содержащий имя учетной записи и пароль. Затем необходимо добавить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-Ксрегистратион:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Дополнительные сведения можно найти в справочной документации по командлету [Test-ксрегистратион](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Если указанный пользователь может войти на сервер Lync Server (а затем выйти из него), вы получите вывод примерно так, чтобы его свойство Result пометило как **успешное.**

Таржетфкдн: atl-cs-001.litwareinc.com

Результат: успех

Задержка: 00:00:06.8630376

Ошибки

Диагностик

Если указанному пользователю не удается войти в систему или выйти из нее, результат будет показан в виде ошибки, а дополнительные сведения будут записаны в свойствах Error и диагноз.

Таржетфкдн: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: 404, не найдена

Диагностика: ErrorCode = 1003, источник = ATL-CS-001. плана litwareinc. com, Reason = User

не существует

Microsoft. RTC. SignalR. Диагностичеадер

Например, в предыдущем выводе говорится, что тест завершился сбоем, так как указанный пользователь не найден. Вы можете определить, является ли адрес SIP допустимым (и назначен ли пользователю этот адрес SIP для Lync Server), выполнив следующую команду:

    Get-CsUser "sip:kenmyer@litwareinc.com"

Если при выполнении теста-Ксрегистратион происходит сбой, может потребоваться повторный запуск теста, в том числе параметр подробно:

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

При включенном параметре "подробный" функция Test-Ксрегистратион будет возвращать пошаговые инструкции для каждого действия, которое он пытался войти на сервер Lync Server. Например:

ПОДРОБНЫЕ сведения: начато действие "регистрация".

Отправка запроса на регистрацию:

Целевое полное доменное имя = atl-cs-011.litwareinc.com

SIP адрес пользователя = sip:kenmyer@litwareinc.com

Порт регистратора = 5061.

Выбран тип проверки подлинности "Trusted".

Исключение "конечная точка не может зарегистрироваться. Просмотрите код ошибки для конкретной причины "произошла ошибка" во время выполнения рабочего процесса Microsoft. RTC. Синсетиктрансактионс. Workflow. Стрегистрерворкфлов.

Стек вызовов исключений: в Microsoft. RTC. SignalR. SipAsyncResult'1. ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Ксрегистратион:

  - Вы указали неверную учетную запись пользователя. Для проверки существования учетной записи пользователя можно выполнить следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя верна, но в настоящее время учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если для свойства Enabled задано значение false, это означает, что пользователь в настоящее время не поддерживает Lync Server.

  - Вы указали неправильный пул регистраторов. Вы можете вернуть полные доменные имена для пулов регистратора с помощью этой команды:
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - Пул регистраторов в настоящее время недоступен. Попробуйте выполнить команду ping для пула, чтобы узнать, отвечает ли он.
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

