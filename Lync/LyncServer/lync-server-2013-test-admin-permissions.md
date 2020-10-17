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
# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="fe4f5-103">Проверка разрешений администратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe4f5-103">Test admin permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe4f5-104">_**Последнее изменение темы:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="fe4f5-104">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe4f5-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="fe4f5-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fe4f5-106">После первоначального развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-106">After initial Lync Server deployment.</span></span> <span data-ttu-id="fe4f5-107">При необходимости, если возникают проблемы, связанные с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-107">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe4f5-108">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="fe4f5-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fe4f5-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe4f5-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe4f5-110">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="fe4f5-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fe4f5-111">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fe4f5-112">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="fe4f5-113">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fe4f5-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fe4f5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fe4f5-114">Description</span></span>

<span data-ttu-id="fe4f5-115">При установке Lync Server 2013 1 задач, выполненных программой установки, Группа RTCUniversalUserAdmins предоставляет разрешения Active Directory, необходимые для управления пользователями, компьютерами, контактами, контактами приложения и Инеторг лицами.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-115">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="fe4f5-116">Если вы отключили наследование разрешений в программе установки Active Directory, ему не удастся назначить эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-116">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="fe4f5-117">В результате участники группы RTCUniversalUserAdmins не смогут управлять сущностями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="fe4f5-118">Эти привилегии управления будут доступны только администраторам домена.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-118">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="fe4f5-119">Командлет Test-CsOUPermission проверяет, что необходимые разрешения, необходимые для управления пользователями, компьютерами и другими объектами, установлены в контейнере Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-119">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="fe4f5-120">Если эти разрешения не заданы, можно устранить эту проблему, выполнив командлет [Grant – CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="fe4f5-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="fe4f5-121">Обратите внимание, что Grant-CsOUPermission могут назначать разрешения только участникам группы RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="fe4f5-122">Вы не можете использовать этот командлет для предоставления разрешений произвольному пользователю или группе.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="fe4f5-123">Если вы хотите, чтобы другой пользователь или группа применялись к разрешениям управления пользователями, необходимо добавить этого пользователя (или группу) в группу RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="fe4f5-124">Дополнительные сведения о разрешениях для подразделений содержатся в статье [разрешения наследования разрешений отключены для компьютеров, пользователей и контейнеров inetOrgPerson в Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span><span class="sxs-lookup"><span data-stu-id="fe4f5-124">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fe4f5-125">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="fe4f5-125">Running the test</span></span>

<span data-ttu-id="fe4f5-126">Чтобы убедиться в том, что для контейнера заданы разрешения на управление, выполните командлет Test-CsOUPermission, а затем различающееся имя контейнера и тип проверяемых разрешений.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-126">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="fe4f5-127">Например, эта команда проверяет, установлены ли разрешения пользователя для подразделения OU = Redmond, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="fe4f5-127">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="fe4f5-128">Чтобы проверить несколько разрешений с помощью одной команды, заключите каждый тип разрешения в кавычки, а затем разделите эти типы с помощью запятых.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-128">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="fe4f5-129">Например, одна команда проверяет разрешения пользователя, компьютера и контакта:</span><span class="sxs-lookup"><span data-stu-id="fe4f5-129">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="fe4f5-130">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="fe4f5-130">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fe4f5-131">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="fe4f5-131">Determining success or failure</span></span>

<span data-ttu-id="fe4f5-132">Если необходимые разрешения уже заданы, Test-CsOUPermission возвратит ответ из одного слова:</span><span class="sxs-lookup"><span data-stu-id="fe4f5-132">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="fe4f5-133">Верно</span><span class="sxs-lookup"><span data-stu-id="fe4f5-133">True</span></span>

<span data-ttu-id="fe4f5-134">Если необходимые разрешения не заданы, Test-CsOUPermission вернет значение false.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-134">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="fe4f5-135">Вам может потребоваться найти это значение в течение некоторого времени.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-135">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="fe4f5-136">Как правило, она обычно внедряется в несколько соответствующих предупреждений.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-136">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="fe4f5-137">Например:</span><span class="sxs-lookup"><span data-stu-id="fe4f5-137">For example:</span></span>

<span data-ttu-id="fe4f5-138">Предупреждение: запись управления доступом (ACE) ATL-CS-001 \\ RTCUniversalUserReadOnlyGroup; Allow; Реадпроперти; Контаинеринхерит; Потомки bf967aba-0de6-11d0-00aa003049e2; d819615a — 3b9b – 4738 — b47e – f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="fe4f5-138">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="fe4f5-139">Предупреждение: записи управления доступом (ACE) для объекта "OU = NorthAmerica, DC = ATL-CS-001 \\ DC = litwareinc, DC = com" не готовы.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-139">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="fe4f5-140">False</span><span class="sxs-lookup"><span data-stu-id="fe4f5-140">False</span></span>

<span data-ttu-id="fe4f5-141">Предупреждение: "Test-CsOUPermission" обработка завершена с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-141">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="fe4f5-142">во время этого запуска было записано предупреждение 2.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-142">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="fe4f5-143">Предупреждение: подробные результаты можно найти на сайте "C: \\ Users \\ Admin \\ AppData \\ Local \\ temp \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="fe4f5-143">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fe4f5-144">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="fe4f5-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="fe4f5-145">Если Test-CsOUPermission завершается с ошибкой, обычно это означает, что указанное разрешение не назначено группе RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-145">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="fe4f5-146">Эту проблему можно решить и назначить необходимые разрешения с помощью командлета Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-146">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="fe4f5-147">Например, эта команда предоставляет разрешения OU для пользователей, контактов и Инеторгперсонс группе RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="fe4f5-147">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="fe4f5-148">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-148">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

