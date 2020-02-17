---
title: 'Lync Server 2013: Проверка проверки подлинности клиента Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efc07ff877d5692c2871a8b0481233d3bd8c58b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Тестирование проверки подлинности клиента Lync в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsClientAuth. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsClientAuth позволяет определить, может ли пользователь войти на сервер Lync с помощью сертификата клиента, можно запустить командлет Test-CsClientAuth. После вызова командлета Test-CsClientAuth командлет свяжется со службой подготовки сертификатов и загрузит копию всех клиентских сертификатов для указанного пользователя. Если сертификат клиента можно найти и скачать, Test-CsClientAuth будет пытаться войти в систему с помощью этого сертификата. Если вход выполнен успешно, то Test-CsClientAuth выйдет из системы и сообщит о том, что тест успешно выполнен. Если сертификат клиента не удается обнаружить или загрузить, или командлет не может войти с его помощью в систему, Test-CsClientAuth сообщает о неудачном завершении проверки.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsClientAuth запускается с помощью учетной записи любого пользователя, для которого включен Lync Server. Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи. Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, когда система вызывает Test-CsClientAuth:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsClientAuth](http://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанный пользователь может войти на сервер Lync Server с помощью клиентского сертификата, будет выведен результат, подобный следующему, при этом свойство Result помечается как **успешное:**

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.8630376

Ошибкой

Диагност

Если указанный пользователь не может выполнить вход в систему, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:03.3645259

Ошибка: не удалось скачать сертификат CS для данного пользователя. Проверка наличия

предоставлены правильные URI и учетные данные.

Диагност

Например, в предыдущем выходном состоянии не удалось выполнить тест, так как не удалось найти действительный сертификат клиента для указанного пользователя. Вы можете получить список сертификатов клиентов, выданных пользователю, выполнив команду следующим образом:

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Если Test-CsClientAuth завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Если включен параметр Verbose, командлет Test-CsClientAuth возвращает пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server. Например:

Попытка скачать сертификат CS для пользователя: kenmyer@litwareinc.com конечная точка: Степид

URL-адрес веб-службы:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

Не удалось скачать сертификат CS из веб-службы.

ПРОВЕРЯТЬ

\-URL-адрес веб-службы является допустимым, а веб-службы функционируют

\-Если для проверки\\\\подлинности используется ПИН-код фонено, убедитесь, что они совпадают с URI пользователя.

\-При использовании проверки\\подлинности NTLM Kerberos убедитесь, что вы предоставили действительные учетные данные.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsClientAuth:

  - Указана недопустимая учетная запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.

  - Тестовый пользователь может не иметь действительный сертификат клиента. Сведения о сертификатах клиентов, назначенных пользователю, можно получить с помощью следующей команды:
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

