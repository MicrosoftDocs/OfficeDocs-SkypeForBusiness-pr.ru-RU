---
title: 'Lync Server 2013: Проверка разрешений на активацию служб и групп'
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
ms.openlocfilehash: ef22928f9506c4ec67acd3de6bad80274f8c0f12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Проверка разрешений на активацию служб и групп в Lync Server 2013

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
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Кстопологи. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-Кстопологи позволяет проверить, правильно ли работает Lync Server 2013 в глобальной области. По умолчанию командлет проверяет всю инфраструктуру сервера Lync, убедившись в том, что необходимые службы запущены и установлены соответствующие разрешения для этих служб, а также для универсальных групп безопасности, которые создаются при установке Lync Server. .

Помимо проверки действительности установки Lync Server, Test-Кстопологи также позволяет проверить правильность определенной службы. Например, эта команда проверяет состояние сервера конференц-связи A/V в пуле atl-cs-001.litwareinc.com:

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

По умолчанию в режиме Test-Кстопологи отображается очень мало вывода на экран. Вместо этого данные, возвращаемые командлетом, записываются в HTML-файл. Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-Кстопологи. Если параметр отчета не указан, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь такое имя, как: ce84964a-c4da-4622-ad34-c54ff3ed361f. HTML.

В следующем образце команды запускается Test-Кстопологи и сохраняются выходные данные в файле с именем C:\\Logs\\компутертест. HTML.

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

Дополнительные сведения можно найти в справочной документации по командлету [Test-кстопологи](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

В отличие от большинства командлетов теста, Test-Кстопологи сообщает об успешном завершении или сбое. Частично, это связано с большим количеством проверок, которое командлет должен выполнять каждый раз при запуске. Вместо этого данные сохраняются в отчете в формате HTML, который затем можно просматривать с помощью Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Кстопологи:

  - Репликация может быть неактуальной на тестовом компьютере. Вы можете проверить текущее состояние репликации для компьютера, выполнив командлет Get-Ксманажементсторерепликатионстатус:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Если состояние репликации не устарело, вы можете вручную выполнить принудительную репликацию с помощью следующей команды:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - Возможно, требуется включить топологию. Если вы измените топологию Lync Server (изменения, которые могут повлиять на локальный компьютер), необходимо включить новую топологию. Вы можете включить топологию в любое время, выполнив следующую команду:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

