---
title: 'Lync Server 2013: тестирование возможности подключения к федеративного домена'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82c44cf7cff78fc93054679ae1bc4c66bc6b4c40
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Тестирование возможности подключения к федеративного домена из Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsFederatedPartner. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Test-CsFederatedPartner проверяет возможность подключения к домену федеративного партнера. Чтобы проверить подключение к домену, этот домен должен быть указан в коллекции разрешенных (Федеративных) доменов. С помощью этой команды можно получить список доменов из списка разрешенных доменов:

    Get-CsAllowedDomain

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Для командлета Test-Федератедпартнер требуются два фрагмента информации: полное доменное имя пограничного сервера и полное доменное имя федеративного партнера. Например, эта команда проверяет возможность подключения к домену contoso.com:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Эта команда позволяет проверить подключения ко всем доменам, которые в настоящее время находятся в списке разрешенных доменов:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если к указанному домену можно обратиться, вы получите выходные данные, аналогичные приведенным ниже, с свойством Result, помеченным как **успешное:**

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:00

Ошибкой

Диагност

Если не удается связаться с указанным доменом, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: 504, время ожидания сервера

Диагностика: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, Reason = видите

код отклика и фраза причины.

Microsoft. RTC. Signal. Диагностичеадер

Например, предыдущие выходные данные погрешностей о том, что тест завершился сбоем из-за ошибки времени ожидания сервера. Как правило, это свидетельствует о проблемах с подключением к сети или проблемах связи с пограничным сервером.

Если Test-CsFederatedPartner завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsFederatedPartner:

  - Пограничный сервер может быть недоступен. Полные доменные имена пограничных серверов можно выполнить с помощью следующей команды:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    После этого можно выполнить обмен пакетами с каждым пограничным сервером, чтобы убедиться, что к ним возможен доступ через сеть. Пример:
    
        ping atl-edge-001.litwareinc.com

  - Указанный домен может не отображаться в списке разрешенных доменов. Чтобы проверить домены, добавленные в список разрешенных доменов, выполните следующую команду:
    
        Get-CsAllowedDomain
    
    Если вы хотите просмотреть список доменов, с которыми пользователи блокировали связь с, выполните следующую команду:
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

