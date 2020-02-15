---
title: 'Lync Server 2013: тестирование разрешений на активацию служб и групп'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8df9373088e29259ff95de1342000446d0d43d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Тестирование разрешений на активацию служб и групп в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsTopology. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsTopology позволяет убедиться, что Lync Server 2013 правильно работает в глобальной области. По умолчанию командлет проверяет всю инфраструктуру Lync Server, проверяя, что необходимые службы запущены и установлены ли соответствующие разрешения для этих служб, а также для универсальных групп безопасности, создаваемых при установке Lync Server. .

Кроме проверки допустимости установки Lync Server, Test-CsTopology также позволяет проверить допустимость определенной службы. Например, эта команда проверяет состояние сервера аудио-и видеоконференций в пуле atl-cs-001.litwareinc.com:

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

По умолчанию test-CsTopology отображает очень маленький вывод на экран. Вместо этого сведения, возвращаемые командлетом, записываются в HTML-файл. Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-CsTopology. Если не включить параметр отчета, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь имя, аналогичное следующему: ce84964a-c4da-4622-ad34-c54ff3ed361f. HTML.

Приведенный ниже пример команды выполняет командлет Test-CsTopology и сохраняет выходные данные в файл с именем C:\\Logs\\компутертест. HTML:

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

В отличие от большинства командлетов тестирования, Test-CsTopology отправляет отчет об успешном выполнении или сбое. Частично это вызвано большим количеством проверок, которые командлет должен выполнять при каждом запуске. Вместо этого данные сохраняются в HTML-отчете, который можно просмотреть с помощью Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsTopology:

  - Репликация может быть неактуальной на тестовом компьютере. Вы можете проверить текущее состояние репликации для компьютера, выполнив командлет Get – CsManagementStoreReplicationStatus:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Если состояние репликации устарело, можно вручную выполнить репликацию с помощью следующей команды:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - Возможно, топология включена. При изменении топологии Lync Server (изменений, которые могут повлиять на локальный компьютер) необходимо включить новую топологию. Вы можете включить топологию в любое время, выполнив следующую команду:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

