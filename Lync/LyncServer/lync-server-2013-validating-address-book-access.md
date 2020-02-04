---
title: 'Lync Server 2013: Проверка доступа к адресной книге'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96fe45f1491ca518a6985b0c15f8bcc229bd7f8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>Проверка доступа к адресной книге в Lync Server 2013

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
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксаддрессбуксервице. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-Ксаддрессбуксервице позволяет удостовериться, что пользователь может подключаться к веб-службе загрузки адресной книги. При выполнении командлета Test-Ксаддрессбуксервице подключается к веб-службе загрузки адресной книги в указанном пуле и запрашивает расположение файлов из адресной книги. Если веб-служба загрузки адресной книги предоставляет это расположение, проверка считается успешной. Если запрос отвергнут, проверка считается неудачной.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-Ксаддрессбуксервице можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи пользователя, который был включен для Lync Server. Для выполнения этой проверки с помощью тестовой учетной записи все, что вам нужно, — это указать полное доменное имя (FQDN) для тестируемого пула Lync Server. Например:

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, содержащий имя учетной записи и пароль. Затем необходимо добавить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-Ксаддрессбуксервице:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Дополнительные сведения можно найти в справочной документации по командлету [Test-ксаддрессбуксервице](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Если указанный пользователь может подключаться к службе адресной книги, вы получите обратное вывод, как показано ниже, и свойство Result помечается как **успешное**.

Таржетури:https://lync-se.fabrikam.com:443/abs/handler

Таржетфкдн: atl-cs-001.litwareinc.com

Результат: успех

Задержка: 00:00:06.2260399

Ошибки

Диагностик

Если указанный пользователь не может установить это подключение, результат будет показан как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз.

Таржетури:

Таржетфкдн: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Диагностика: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,

Reason = универсальный код ресурса (URI) назначения не включен для SIP либо не

Существует.

Microsoft. RTC. SignalR. Диагностичеадер

Например, предшествующее выходное состояние не удалось выполнить тест, так как указанный пользователь (то есть "конечный URI") не существует или не включен для Lync Server. Вы можете проверить, является ли учетная запись пользователя действительной, и убедиться, что вы указали правильный SIP-адрес, выполнив команду, например следующую:

Get-CsUser-Identity "sip:kenmyer@litwareinc.com" | Select-Object Сипаддресс, Enabled

Если при выполнении теста-Ксаддрессбуксервице происходит сбой, может потребоваться повторное выполнение теста, на этот раз включая параметр подробно:

Test-Ксаддрессбуксервице-Таржетфкдн "atl-cs-001.litwareinc.com"-подробный

При включенном параметре "подробный" — Ксаддрессбуксервице возвращает пошаговые учетные записи для каждого действия, которое оно пытается выполнить для проверки возможности входа на сервер Lync Server для указанного пользователя. Например, этот образец выходных данных показывает, что Ксаддрессбуксервице, по крайней мере, в этом примере, удалось загрузить файл адресной книги:

Отправка HTTP-запроса GET.

Путь к файлу =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

Номер попытки = 1

Таймаут (мсек) = 60000

Файл в формате ABS успешно скачанhttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Ксаддрессбуксервице:

  - Вы указали недопустимую учетную запись пользователя. Для проверки существования учетной записи пользователя можно выполнить следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя верна, но в настоящее время эта учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если для свойства Enabled задано значение false, это означает, что пользователь в данный момент не включен для Lync Server.

</div>

<div>

## <a name="see-also"></a>См. также


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

