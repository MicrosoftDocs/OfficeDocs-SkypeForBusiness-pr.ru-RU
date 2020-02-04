---
title: 'Lync Server 2013: Проверка веб-запроса адресной книги'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d6a38c0c1d8a67977f9dd66da2a94b51a4f9ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Проверка веб-запроса адресной книги в Lync Server 2013

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
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксаддрессбуквебкуери. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-Ксаддрессбуквебкуери позволяет администраторам удостовериться в том, что пользователи могут использовать службу веб-запросов адресной книги для поиска определенного контакта. При запуске командлета Test-Ксаддрессбуквебкуери сначала подключится к службе веб-билета для проверки подлинности. Если проверка подлинности прошла успешно, командлет подключится к службе веб-запросов адресной книги и проведет поиск по указанному контакту. Если этот контакт будет найден, командлет попытается вернуть эти данные на локальный компьютер. Тест помечается успешно, только если все эти действия можно выполнить.

Дополнительные сведения можно найти в справочной документации по командлету [Test-ксаддрессбуквебкуери](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-Ксаддрессбуквебкуери можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи пользователя, который включен для Lync Server. Для выполнения этой проверки с помощью тестовой учетной записи необходимо указать полное доменное имя пула сервера Lync Server и адрес SIP пользователя, который действует как цель поиска. Например:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

Для выполнения этой проверки с использованием реальной учетной записи пользователя необходимо создать объект учетных данных Windows PowerShell, содержащий действительное имя пользователя и пароль. Затем необходимо добавить этот объект учетных данных и адрес SIP, назначенный учетной записи, когда код вызывает Test-Ксаддрессбуквебкуери:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Дополнительные сведения можно найти в справочной документации по командлету [Test-ксаддрессбуквебкуери](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Если указанный пользователь может подключаться к службе адресной книги и извлекать конечный адрес пользователя, вы вернете вывод, аналогичный этому, с помощью свойства Result, помеченного как успешно.

Таржетури:https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Таржетфкдн: atl-cs-001.litwareinc.com

Результат: успех

Задержка: 00:00:06.2611356

Ошибки

Диагностик

Если указанному пользователю не удается подключиться или не удается получить целевой адрес пользователя, результат будет показан в виде ошибки, а дополнительные сведения будут записаны в свойствах Error и диагноз.

Таржетури:https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Таржетфкдн: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: не удалось выполнить запрос веб-службы адресной книги с кодом ответа

Ноентрифаунд.

Диагностик

В предыдущем выводе говорится, что тест завершился сбоем, так как целевой пользователь не найден. Вы можете определить, был ли допустимый SIP-адрес передан в тест — Ксаддрессбуквебкуери, выполнив команду, подобную следующей:

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

Если при выполнении теста-Ксаддрессбуквебкуери происходит сбой, может потребоваться повторный запуск теста, в том числе параметр подробно:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

При включенном параметре "подробный" функция Test-Ксаддрессбуквебкуери возвращает пошаговые учетные записи каждого действия, которое он пытался выполнить, при проверке возможности входа на сервер Lync Server. Например, эти выходные данные указывают на то, что тест-Ксаддрессбуквебкуери смог подключиться к службе адресной книги, но ему не удалось найти адрес SIP Target.

Начато действие "Куеряддрессбуквебсервице".

Служба веб-запросов из адресной книги телефонной связи. URL-АДРЕС АБВС =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Исключение запроса в адресную книгу: запрос веб-службы адресной книги не удался с кодом ответа Ноентрифаунд.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Ксаддрессбуквебкуери:

  - Вы указали недопустимую учетную запись пользователя. Для проверки существования учетной записи пользователя можно выполнить следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя верна, но в настоящее время эта учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если для свойства Enabled задано значение false, это означает, что пользователь в данный момент не включен для Lync Server.

  - Конечный пользователь может отсутствовать в адресной книге.

  - Возможно, адресная книга не полностью обновлена и не была реплицирована. Вы можете принудительно обновить все серверы адресной книги в вашей организации, выполнив следующую команду:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

