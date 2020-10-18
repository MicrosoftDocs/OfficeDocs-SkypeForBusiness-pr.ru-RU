---
title: 'Lync Server 2013: тестирование служб Lync Server'
description: 'Lync Server 2013: тестирование служб Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f04cf5e0c098c671b6fb126d4607f3cdba107712
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575225"
---
# <a name="testing-lync-server-services-in-lync-server-2013"></a>Тестирование служб Lync Server в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsComputer. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Test-CsComputer проверяет состояние всех служб Lync Server 2013, запущенных на локальном компьютере. (Test-CsComputer можно запускать только локально, его нельзя запустить из удаленного экземпляра Windows PowerShell.) Командлет также проверяет, открыты ли на компьютере соответствующие порты брандмауэра, и определяет, были ли группы Active Directory, созданные при установке Lync Server 2013, добавлены в соответствующие локальные группы. Например, Test-CsComputer будет проверять, была ли группа Active Directory RTCUniversalUserAdmins добавлена в группу администраторов.

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsComputer можно запускать только на локальном компьютере, вы не можете вызывать Test-CsComputer из удаленного экземпляра Windows PowerShell. По умолчанию Test-CsComputer отображает очень маленький вывод на экран, а данные, возвращаемые командлетом, записываются в HTML-файл. Из-за этого мы рекомендуем включить параметр Verbose и параметр отчета каждый раз при запуске test-CsComputer. Параметр verbose предоставит немного более подробный вывод на экран при выполнении командлета. Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-CsComputer. Если не включить параметр отчета, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь имя, аналогичное следующему: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.

В приведенном ниже примере команда выполняет Test-CsComputer и сохраняет выходные данные в файл с именем C: \\ Logs \\ComputerTest.html:

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Из-за количества проверок, выполняемых для проверки, Test-CsComputer не сообщает о простом **Да, тест успешно выполнен** или **нет, тест завершился ошибкой**. Вместо этого необходимо просмотреть созданный HTML-файл с помощью Internet Explorer, чтобы определить успешность или неудачу каждого теста.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsComputer:

  - Тестовый компьютер не может быть включен для использования с сервером Lync Server. Это может произойти, если на компьютере были изменены серверные службы или роли сервера Lync, а командлет Enable-CsComputer не был запущен. Для устранения этой неполадки выполните следующую команду.
    
        Enable-CsComputer

  - Репликация может быть не актуальна на тестовом компьютере. Вы можете проверить текущее состояние репликации для компьютера, выполнив командлет Get-CsManagementStoreReplicationStatus:
    
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

