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
ms.openlocfilehash: 3ae10fa68703393459a72eaab7236f214502a614
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508556"
---
# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Проверка веб-запроса адресной книги в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsAddressBookWebQuery. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsAddressBookWebQuery позволяет администраторам проверить, могут ли пользователи использовать службу веб-запросов адресной книги для поиска определенного контакта. При запуске командлета Test-CsAddressBookWebQuery будет сначала подключаться к службе веб-билетов, чтобы пройти проверку подлинности. Если проверка подлинности прошла успешно, командлет будет подключаться к службе веб-запросов адресной книги и искать указанного контакта. При нахождении контакта командлет попытается вернуть данные на локальный компьютер. Тест будет помечен как успешный, только если все эти действия можно выполнить.

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsAddressBookWebQuery можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server. Чтобы выполнить эту проверку с помощью тестовой учетной записи, необходимо указать полное доменное имя пула Lync Server и SIP-адрес пользователя, выступающего в качестве целевого объекта поиска. Например:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо создать объект учетных данных Windows PowerShell, который содержит действительное имя пользователя и пароль. Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, когда код вызывает Test-CsAddressBookWebQuery:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанный пользователь может подключаться к службе адресной книги и получать целевой адрес пользователя, будет выведен результат, подобный следующему, с свойством Result, помеченным как успешно:

TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.2611356

Ошибкой

Диагност

Если указанный пользователь не может подключиться или не удается получить целевой адрес пользователя, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:

TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: сбой запроса веб-службы адресной книги с кодом отклика

Ноентрифаунд.

Диагност

Предыдущие выходные данные почтовых состояний не пройдены, так как целевой пользователь не найден. Можно определить, был ли действительный SIP адрес передан Test-CsAddressBookWebQuery, выполнив команду, аналогичную следующей:

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

Если Test-CsAddressBookWebQuery завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Если включен параметр Verbose, Test-CsAddressBookWebQuery будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server. Например, эти выходные данные указывают на то, что Test-CsAddressBookWebQuery удалось подключиться к службе адресной книги, но ей не удалось определить конечный SIP адрес:

Начато действие "Куеряддрессбуквебсервице".

Служба веб-запросов к адресной книге вызовов. URL-АДРЕС АБВС =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Исключение запроса адресной книги: сбой запроса веб-службы адресной книги с кодом отклика Ноентрифаунд.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsAddressBookWebQuery:

  - Вы указали недопустимую учетную запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя действительна, но в настоящее время эта учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если для свойства Enabled задано значение false, то в данный момент пользователь не включен для Lync Server.

  - Целевой пользователь может отсутствовать в адресной книге.

  - Возможно, адресная книга не полностью обновлена и не была реплицирована. Вы можете принудительно обновить все серверы адресной книги в Организации, выполнив следующую команду:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

