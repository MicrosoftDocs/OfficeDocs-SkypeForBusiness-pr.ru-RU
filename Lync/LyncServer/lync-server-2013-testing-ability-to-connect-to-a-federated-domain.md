---
title: 'Lync Server 2013: Проверка возможности подключения к Федеративной домену'
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
ms.openlocfilehash: f18a8c703b085fe559b3a979ac72d9c0b0dfe38f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Тестирование возможности подключения к Федеративной домену из Lync Server 2013

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
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксфедератедпартнер. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Test-Ксфедератедпартнер проверяет возможность подключения к домену федеративного партнера. Чтобы проверить подключение к домену, этот домен должен быть указан в коллекции разрешенных (Федеративных) доменов. Вы можете получить список доменов из списка разрешенных доменов, выполнив следующую команду:

    Get-CsAllowedDomain

Дополнительные сведения можно найти в справочной документации по командлету [Test-ксфедератедпартнер](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлету Test-Федератедпартнер требуется два фрагмента данных: полное доменное имя пограничного сервера и полное доменное имя федеративного партнера. Например, эта команда проверяет возможность подключения к домену contoso.com:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Эта команда позволяет проверить подключения ко всем доменам, которые в настоящее время находятся в списке разрешенных доменов:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Дополнительные сведения можно найти в справочной документации по командлету [Test-ксфедератедпартнер](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Если вы можете связаться с указанным доменом, вы получите вывод, аналогичный этому, с помощью свойства Result, помеченного как **успешно.**

Таржетфкдн: atl-cs-001.litwareinc.com

Результат: успех

Задержка: 00:00:00

Ошибки

Диагностик

Если указанному домену невозможно обратиться, результат будет показан в виде ошибки, а дополнительные сведения будут записаны в свойствах Error и диагноз.

Таржетфкдн: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: 504, время ожидания сервера

Диагностика: ErrorCode = 2, источник = ATL-CS-001. плана litwareinc. com, Reason = см.

код ответа и фраза с основанием.

Microsoft. RTC. SignalR. Диагностичеадер

Например, в предыдущем выводе говорится о том, что тест завершился сбоем из-за ошибки времени ожидания сервера. Как правило, это указывает на проблемы с подключением к сети или на проблемы с соединением пограничного сервера.

Если при выполнении теста-Ксфедератедпартнер происходит сбой, может потребоваться повторный запуск теста, в том числе параметр подробно:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Ксфедератедпартнер:

  - Сервер граничного сервера может быть недоступен. Полные доменные имена для пограничного сервера можно использовать с помощью этой команды:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    После этого вы сможете проверить связь с каждым пограничным сервером, чтобы убедиться, что он доступен по сети. Например:
    
        ping atl-edge-001.litwareinc.com

  - Указанный домен может не отображаться в списке разрешенные домены. Чтобы проверить, какие домены были добавлены в список разрешенных доменов, используйте следующую команду:
    
        Get-CsAllowedDomain
    
    Если вы хотите просмотреть список доменов, с которыми пользователи блокировали связь, а затем выполните следующую команду:
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

