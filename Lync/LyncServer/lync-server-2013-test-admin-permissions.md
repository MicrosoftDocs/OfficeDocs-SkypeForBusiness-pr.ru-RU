---
title: 'Lync Server 2013: Проверка разрешений администратора'
description: 'Lync Server 2013: Проверка разрешений администратора.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e15be288ed31afe9303d91ce3e623d19822428
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568525"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a>Проверка разрешений администратора в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-08-18_


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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsOUPermission. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

При установке Lync Server 2013 1 задач, выполненных программой установки, Группа RTCUniversalUserAdmins предоставляет разрешения Active Directory, необходимые для управления пользователями, компьютерами, контактами, контактами приложения и Инеторг лицами. Если вы отключили наследование разрешений в программе установки Active Directory, ему не удастся назначить эти разрешения. В результате участники группы RTCUniversalUserAdmins не смогут управлять сущностями Lync Server. Эти привилегии управления будут доступны только администраторам домена.

Командлет Test-CsOUPermission проверяет, что необходимые разрешения, необходимые для управления пользователями, компьютерами и другими объектами, установлены в контейнере Active Directory. Если эти разрешения не заданы, можно устранить эту проблему, выполнив командлет [Grant – CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .

Обратите внимание, что Grant-CsOUPermission могут назначать разрешения только участникам группы RTCUniversalUserAdmins. Вы не можете использовать этот командлет для предоставления разрешений произвольному пользователю или группе. Если вы хотите, чтобы другой пользователь или группа применялись к разрешениям управления пользователями, необходимо добавить этого пользователя (или группу) в группу RTCUniversalUserAdmins.

Дополнительные сведения о разрешениях для подразделений содержатся в статье [разрешения наследования разрешений отключены для компьютеров, пользователей и контейнеров inetOrgPerson в Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Чтобы убедиться в том, что для контейнера заданы разрешения на управление, выполните командлет Test-CsOUPermission, а затем различающееся имя контейнера и тип проверяемых разрешений. Например, эта команда проверяет, установлены ли разрешения пользователя для подразделения OU = Redmond, DC = litwareinc, DC = com:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

Чтобы проверить несколько разрешений с помощью одной команды, заключите каждый тип разрешения в кавычки, а затем разделите эти типы с помощью запятых. Например, одна команда проверяет разрешения пользователя, компьютера и контакта:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если необходимые разрешения уже заданы, Test-CsOUPermission возвратит ответ из одного слова:

Верно

Если необходимые разрешения не заданы, Test-CsOUPermission вернет значение false. Вам может потребоваться найти это значение в течение некоторого времени. Как правило, она обычно внедряется в несколько соответствующих предупреждений. Например:

Предупреждение: запись управления доступом (ACE) ATL-CS-001 \\ RTCUniversalUserReadOnlyGroup; Allow; Реадпроперти; Контаинеринхерит; Потомки bf967aba-0de6-11d0-00aa003049e2; d819615a — 3b9b – 4738 — b47e – f1bd8ee3aea4

Предупреждение: записи управления доступом (ACE) для объекта "OU = NorthAmerica, DC = ATL-CS-001 \\ DC = litwareinc, DC = com" не готовы.

False

Предупреждение: "Test-CsOUPermission" обработка завершена с предупреждениями. во время этого запуска было записано предупреждение 2.

Предупреждение: подробные результаты можно найти на сайте "C: \\ Users \\ Admin \\ AppData \\ Local \\ temp \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Если Test-CsOUPermission завершается с ошибкой, обычно это означает, что указанное разрешение не назначено группе RTCUniversalUserAdmins. Эту проблему можно решить и назначить необходимые разрешения с помощью командлета Grant-CsOUPermission. Например, эта команда предоставляет разрешения OU для пользователей, контактов и Инеторгперсонс группе RTCUniversalUserAdmins:

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета Grant-CsOUPermission.

</div>

</div>

<span> </span>

</div>

</div>

</div>

