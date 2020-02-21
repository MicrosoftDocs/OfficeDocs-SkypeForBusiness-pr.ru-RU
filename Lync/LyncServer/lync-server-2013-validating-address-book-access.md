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
ms.openlocfilehash: 665ee384afd85c4be5c82182691953e1c78c9659
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>Проверка доступа к адресной книге в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsAddressBookService. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsAddressBookService предоставляет способ проверки возможности подключения пользователя к веб-службе загрузки адресной книги. При выполнении командлета Test-CsAddressBookService подключается к веб-службе загрузки адресной книги в указанном пуле и запрашивает расположение файлов адресной книги. Если веб-служба загрузки адресной книги предоставляет это расположение, проверка считается успешной. Если такой запрос отклоняется, то тест считается непройденным.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsAddressBookService можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, который был включен для Lync Server. Для выполнения этой проверки с помощью тестовой учетной записи все, что необходимо сделать, — указать полное доменное имя (FQDN) тестируемого пула Lync Server. Например:

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи. Затем необходимо добавить этот объект учетных данных и адрес SIP, назначенный учетной записи при вызове Test-CsAddressBookService:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанный пользователь может подключаться к службе адресной книги, будет выведен результат, подобный следующему, при этом свойство Result помечается как **успешное**:

TargetUrihttps://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.2260399

Ошибкой

Диагност

Если указанный пользователь не может сделать это подключение, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Диагностика: ErrorCode = 4005, Source = ATL – CS – 001.litwareinc.com,

Reason = конечный URI либо не включен для SIP, либо не

есть.

Microsoft. RTC. Signal. Диагностичеадер

Например, предыдущие выходные состояния не удалось выполнить тест, так как указанный пользователь (то есть "конечный URI") не существует или не включен для Lync Server. Вы можете проверить, является ли учетная запись пользователя допустимой, и убедиться, что указан правильный SIP-адрес, выполнив команду, подобную следующей:

Get – CsUser — Identity "sip:kenmyer@litwareinc.com" | Select — объект SipAddress, включен

Если не удается выполнить команду Test-CsAddressBookService, вам может потребоваться повторить проверку, в том числе параметр verbose:

Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-verbose

Если параметр verbose включен, командлет Test-CsAddressBookService возвращает пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server. Например, в приведенном ниже примере показана проверка того, что в этом примере кода CsAddressBookService, по крайней мере, в этом примере была возможность скачать файл адресной книги:

Отправка HTTP-запроса GET.

Путь к файлу =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

Номер попытки = 1

Время ожидания (МС) = 60000

Файл ABS успешно скачанhttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsAddressBookService:

  - Вы указали недопустимую учетную запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя действительна, но в настоящее время эта учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если для свойства Enabled задано значение false, то в данный момент пользователь не включен для Lync Server.

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

