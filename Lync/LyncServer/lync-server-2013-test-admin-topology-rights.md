---
title: 'Lync Server 2013: Проверка прав топологии администратора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e17b4a4e3550ea5af665c78b40039dcbd56facdc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519366"
---
# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Проверка прав топологии администратора в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-12-08_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>После первоначального развертывания Lync Server. При необходимости, если возникают проблемы, связанные с разрешениями.</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsSetupPermission. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

По умолчанию только администраторы домена могут включать топологию Lync Server и вносить значительные изменения в инфраструктуру Lync Server. Это не проблема, если администраторы домена и администраторы сервера Lync являются одним и тем же. Во многих организациях администраторы сервера Lync Server не хранят права администратора для всего домена. По умолчанию это означает, что эти администраторы (определенные как члены группы RTCUniversalServerAdmins) не могут вносить изменения в топологию Lync Server. Чтобы предоставить членам группы RTCUniversalServerAdmins право на внесение изменений в топологию, необходимо назначить необходимые разрешения Active Directory с помощью командлета [Grant – CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .

Командлет Test-CsSetupPermission проверяет, настроены ли необходимые разрешения, необходимые для установки Lync Server или одного из его компонентов, в указанном контейнере Active Directory. Если разрешения не назначены, можно запустить командлет Grant-CsSetupPermission, чтобы предоставить членам группы RTCUniversalServerAdmins право на установку и включение Lync Server.

<div>


> [!NOTE]  
> Подробный список разрешений, назначаемых Grant – CsSetupPermission, можно узнать в блоге <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">granting — CsSetupPermission и Grant/CsOUPermission</A>.



</div>

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Чтобы определить, назначены ли разрешения на установку для контейнера Active Directory, вызовите командлет Test-CsSetupPermission. Укажите различающееся имя контейнера, который необходимо проверить. Например, эта команда проверяет разрешения программы установки для контейнера OU = Кссерверс, DC = litwareinc, DC = com:

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если Test-CsSetupPermission определяет, что необходимые разрешения для контейнера Active Directory уже заданы, командлет возвращает значение true:

Верно

Если разрешения не заданы, то Test-CsSetupPermission возвращает значение false. Обратите внимание, что это значение, как правило, будет заключено во множество предупреждающих сообщений. Например:

Предупреждение: запись управления доступом (ACE) ATL-CS-001 \\ RTCUniversalServerAdmins; Разрешить Екстендедригхт; Видим Видим 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

Предупреждение: записи управления доступом (ACE) для объекта "CN = Computers, DC = litwareinc, DC = com" не готовы.

False

Предупреждение: "Test-CsSetupPermission" обработка завершена с предупреждениями. во время этого запуска было записано предупреждение 2.

Предупреждение: подробные результаты можно найти на сайте "C: \\ Users \\ Admin \\ AppData \\ Local \\ temp \\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Несмотря на то, что в Test-CsSetupPermission возникает редкие исключения, обычно это означает, что разрешения программы установки не назначены указанному контейнеру Active Directory. Эти разрешения могут быть назначены с помощью командлета Grant-CsSetupPermission. Например, эта команда предоставляет разрешения на установку контейнера Computers в домене litwareinc.com:

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

