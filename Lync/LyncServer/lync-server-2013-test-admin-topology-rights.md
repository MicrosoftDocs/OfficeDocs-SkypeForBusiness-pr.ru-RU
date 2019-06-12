---
title: 'Lync Server 2013: Проверка прав топологии администратора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 365c879678ff3fd51dcaaf89d4b2593eccf645f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Проверка прав топологии администратора в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-12-08_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>После первоначального развертывания Lync Server. По мере необходимости, если возникают проблемы, связанные с разрешениями.</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Требуемые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</p>
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Кссетуппермиссион. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

По умолчанию только администраторы домена могут включать топологию сервера Lync и вносить большие изменения в инфраструктуру Lync Server. Это не является проблемой, пока Администраторы домена и администраторы сервера Lync находятся в одной и той же папке. Во многих организациях администраторы сервера Lync Server не хранят права администратора для всего домена. По умолчанию, это означает, что администраторы, определенные как члены группы Рткуниверсалсерверадминс, не могут вносить изменения в топологию Lync Server. Чтобы предоставить участникам группы Рткуниверсалсерверадминс право вносить изменения в топологию, необходимо назначить необходимые разрешения Active Directory с помощью командлета [Grant-кссетуппермиссион](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .

Командлет Test-Кссетуппермиссион удостоверяется в том, что необходимые разрешения, необходимые для установки Lync Server или одного из его компонентов, настроены в указанном контейнере Active Directory. Если разрешения не назначены, можно запустить командлет Grant-Кссетуппермиссион, чтобы предоставить участникам группы Рткуниверсалсерверадминс право на установку и включение Lync Server.

<div>


> [!NOTE]  
> Подробный список разрешений, назначенных Grant-Кссетуппермиссион, можно найти в блоге <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-кссетуппермиссион и Grant-ксаупермиссион</A>.



</div>

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Чтобы определить, назначены ли разрешения на установку для контейнера Active Directory, вызовите командлет Test-Кссетуппермиссион. Укажите различающееся имя контейнера, который нужно проверить. Например, эта команда проверяет разрешения на установку в контейнере OU = Кссерверс, DC = плана litwareinc, DC = com:

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

Дополнительные сведения можно найти в разделе справки по командлету [Test-кссетуппермиссион](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Если в параметре test-Кссетуппермиссион определено, что необходимые разрешения уже установлены для контейнера Active Directory, командлет вернет значение true:

True

Если разрешения не заданы, Test-Кссетуппермиссион вернет значение false. Обратите внимание, что это значение обычно заключается на множество предупреждающих сообщений. Например:

Предупреждение: элемент управления доступом (ACE) ATL-CS-001\\рткуниверсалсерверадминс; Пуск Екстендедригхт; Ничего Ничего 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

Предупреждение: элементы управления доступом (ACE) для объекта "CN = Computers, DC = плана litwareinc, DC = com" не готовы.

False

Предупреждение: обработка "Test-Кссетуппермиссион" завершена с предупреждениями. во время этого запуска записано предупреждение "2".

Предупреждение: подробные результаты можно найти на странице "C:\\\\Users\\admin\\AppData\\Local\\Temp Test-кссетуппермиссион-1da99ba6-abe2-45e4-8b16-dfd244763118. HTML".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Несмотря на то, что при выполнении теста-Кссетуппермиссион возникает редкие исключения, обычно это означает, что для определенного контейнера Active Directory разрешения на установку не назначены. Эти разрешения можно назначить с помощью командлета Grant-Кссетуппермиссион. Например, эта команда предоставляет разрешения на установку контейнера Computers в litwareinc.com домена.

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

Дополнительные сведения можно найти в разделе справки по командлету [Test-кссетуппермиссион](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

