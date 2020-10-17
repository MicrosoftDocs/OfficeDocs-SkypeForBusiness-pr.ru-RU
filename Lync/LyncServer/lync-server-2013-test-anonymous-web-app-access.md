---
title: 'Lync Server 2013: Проверка анонимного доступа веб-приложения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a3d90d3de8624f9965b04990ad996d9c04a954f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519316"
---
# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>Проверка анонимного доступа веб-приложения в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Monthly</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsWebAppAnonymous. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsWebAppAnonymous проверяет, что анонимный пользователь может присоединиться к конференциям Lync Server с помощью веб-приложения Lync. При запуске командлета Test-CsWebAppAnonymous связывается со службой веб-билета для получения веб-билета анонимного пользователя. Если командлету удалось получить этот билет, Test-CsWebAppAnonymous будет обращаться к Lync Server и пытаться установить отдельные конференции для обмена мгновенными сообщениями, общего доступа к приложениям и совместной работы с данными.

Обратите внимание, что Test-CsWebAppAnonymous только проверяет интерфейсы API и подключения, используемые для создания этих конференций. В действительности командлет не создает и не проводит никакие Конференции.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsWebAppAnonymous можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей или учетных записей двух пользователей, для которых включен Lync Server. Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server. Например:

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных командной консоли Lync Server (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи. Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-Ксвебаппанонимаус:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета Test-CsWebAppAnonymous. Обратите внимание, что Test-CsWebAppAnonymous не рекомендуется использовать в Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если Test-CsWebAppAnonymous может присоединиться к конференциям для анонимного пользователя, командлет вернет результат теста Success:

Целевое полное доменное имя:

Результат: успешное выполнение

Задержка: 00:00:00

Сообщение об ошибке:

Диагност

Если анонимный пользователь не может присоединиться к необходимым конференциям, результат теста будет помечен как сбой. Как правило, Test-CsWebAppAnonymous также будет сообщать о подробном сообщении об ошибке и диагностике:

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:05.9746266

Сообщение об ошибке: нет ответа, полученного для службы Web-Ticket

Диагностика: несанкционированный HTTP-запрос для клиента

Схема проверки подлинности "NTLM". Проверка подлинности

заголовку, полученному от сервера, является "Negotiate, NTLM".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Test-CsWebAppAnonymous ошибки обычно связаны с ошибками проверки подлинности пользователей: необходимо выполнить тест с использованием действительной учетной записи пользователя, несмотря на то, что командлет проверяет возможность подключения анонимного пользователя к Lync Server. В случае сбоя Test-CsWebAppAnonymous необходимо убедиться, что указанный пользователь имеет действительную учетную запись пользователя Lync Server. Вы можете получить сведения об учетной записи Lync Server с помощью следующей команды:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Если свойство Enabled имеет значение, не равное true, или если команда завершается с ошибкой, то это означает, что у пользователя нет допустимой учетной записи Lync Server.

Кроме того, необходимо убедиться, что пароль, который вы задали при выполнении командлета, является допустимым паролем.

Проблемы с конфигурацией сервера Office Web Apps также могут привести к сбою Test-CsWebAppAnonymous; Это часто случается, если вы получаете следующую диагностику:

HTTP-запрос не авторизован с помощью схемы проверки подлинности клиента "NTLM". В заголовке проверки подлинности, полученной от сервера, получено значение "Negotiate, NTLM".

Дополнительные сведения об устранении неполадок сервера Office Web Apps и их устранении см. в статье блог [Office Web Apps server 2013-Machines posts (сведения о неисправности)](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).

</div>

</div>

<span> </span>

</div>

</div>

</div>

