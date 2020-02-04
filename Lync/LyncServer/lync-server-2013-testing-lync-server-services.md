---
title: 'Lync Server 2013: Проверка служб Lync Server'
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
ms.openlocfilehash: bdafd84f5a8edd21d6e62433d028ed735e37a37d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a>Тестирование служб Lync Server в Lync Server 2013

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
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Кскомпутер. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Test-Кскомпутер проверяет состояние всех служб Lync Server 2013, запущенных на локальном компьютере. (Test-Кскомпутер можно выполнять только локально, и его невозможно запустить из удаленного экземпляра Windows PowerShell.) Командлет также проверяет, открыты ли на компьютере соответствующие порты брандмауэра, и определяет, были ли группы Active Directory, созданные при установке сервера Lync Server 2013, добавлены в соответствующие локальные группы. Например, с помощью теста-Кскомпутер вы увидите, что группа Active Directory Рткуниверсалусерадминс была добавлена в группу "Администраторы".

Дополнительные сведения можно найти в справочной документации по командлету [Test-кскомпутер](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-Кскомпутер можно запускать только на локальном компьютере, но вы не можете вызвать Test-Кскомпутер из удаленного экземпляра Windows PowerShell. По умолчанию в режиме Test-Кскомпутер отображается очень мало вывода на экран, а данные, возвращаемые командлетом, записываются в HTML-файл. По этой причине мы рекомендуем включать параметр подробных данных и параметр отчета каждый раз при запуске test-Кскомпутер. Параметр verbose обеспечивает немного более подробный вывод на экран во время выполнения командлета. Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-Кскомпутер. Если параметр отчета не указан, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь такое имя, как: ce84964a-c4da-4622-ad34-c54ff3ed361f. HTML.

В следующем образце команды запускается Test-Кскомпутер и сохраняются выходные данные в файле с именем C:\\Logs\\компутертест. HTML.

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

Дополнительные сведения можно найти в справочной документации по командлету [Test-кскомпутер](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Из-за количества выполняемых проверок тестов и Кскомпутер не сообщается о том, что проверка **выполнена успешно** или **нет, тест завершился сбоем**. Вместо этого вам нужно будет просмотреть созданный HTML-файл с помощью Internet Explorer, чтобы определить успешность или сбой каждого теста.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Кскомпутер:

  - Тестовый компьютер может быть недоступен для использования с сервером Lync Server. Это может произойти, если вы изменили серверные службы Lync или серверные роли на компьютере, а командлет Enable-Кскомпутер не был запущен. Чтобы устранить эту проблему, выполните следующую команду:
    
        Enable-CsComputer

  - Репликация может быть не актуальна на тестовом компьютере. Вы можете проверить текущее состояние репликации для компьютера, выполнив командлет Get-Ксманажементсторерепликатионстатус:
    
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

