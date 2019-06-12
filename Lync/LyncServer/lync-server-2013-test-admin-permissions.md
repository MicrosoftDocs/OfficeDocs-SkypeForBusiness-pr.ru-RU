---
title: 'Lync Server 2013: Проверка разрешений администратора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3da940b30822a5cfcc1fed302ff3db1f34bd8380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="e9394-102">Проверка разрешений администратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9394-102">Test admin permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9394-103">_**Тема последнего изменения:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="e9394-103">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9394-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="e9394-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e9394-105">После первоначального развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9394-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="e9394-106">По мере необходимости, если возникают проблемы, связанные с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="e9394-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9394-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="e9394-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e9394-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9394-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9394-109">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="e9394-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e9394-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="e9394-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e9394-111">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксаупермиссион.</span><span class="sxs-lookup"><span data-stu-id="e9394-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="e9394-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e9394-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e9394-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e9394-113">Description</span></span>

<span data-ttu-id="e9394-114">При установке Lync Server 2013 1 для задач, выполненных программой установки, группе Рткуниверсалусерадминс предоставляются разрешения Active Directory, необходимые для управления пользователями, компьютерами, контактами, контактами приложения и Инеторг лицами.</span><span class="sxs-lookup"><span data-stu-id="e9394-114">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="e9394-115">Если вы отключили наследование разрешений в службе каталогов Active Directory, вам не удастся назначить эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="e9394-115">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="e9394-116">В результате участники группы Рткуниверсалусерадминс не смогут управлять сущностями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9394-116">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="e9394-117">Эти права на управление будут доступны только администраторам домена.</span><span class="sxs-lookup"><span data-stu-id="e9394-117">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="e9394-118">Командлет Test-Ксаупермиссион подтверждает, что необходимые разрешения, необходимые для управления пользователями, компьютерами и другими объектами, задаются в контейнере Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e9394-118">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="e9394-119">Если эти разрешения не заданы, вы можете устранить эту проблему, выполнив командлет [Grant-ксаупермиссион](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="e9394-119">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="e9394-120">Обратите внимание, что Grant-Ксаупермиссион может назначать разрешения только участникам группы Рткуниверсалусерадминс.</span><span class="sxs-lookup"><span data-stu-id="e9394-120">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="e9394-121">Вы не можете использовать этот командлет, чтобы предоставить разрешения для произвольного пользователя или группы.</span><span class="sxs-lookup"><span data-stu-id="e9394-121">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="e9394-122">Если вы хотите, чтобы другой пользователь или группа имели разрешения на управление пользователями, вы должны добавить этого пользователя (или группу) в группу Рткуниверсалусерадминс.</span><span class="sxs-lookup"><span data-stu-id="e9394-122">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="e9394-123">Дополнительные сведения о разрешениях для подразделений можно найти в статье [отключение наследования разрешений для пользователей и контейнеров inetOrgPerson в Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span><span class="sxs-lookup"><span data-stu-id="e9394-123">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e9394-124">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="e9394-124">Running the test</span></span>

<span data-ttu-id="e9394-125">Чтобы убедиться в том, что для контейнера заданы разрешения на управление, выполните командлет Test-Ксаупермиссион, а затем — различающееся имя контейнера и тип проверяемых разрешений.</span><span class="sxs-lookup"><span data-stu-id="e9394-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="e9394-126">Например, эта команда проверяет, заданы ли разрешения пользователей на подразделение OU = Redmond, DC = плана litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="e9394-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="e9394-127">Для проверки нескольких разрешений с помощью одной команды заключите все типы разрешений в кавычки, а затем разделите их с помощью запятых.</span><span class="sxs-lookup"><span data-stu-id="e9394-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="e9394-128">Например, одна из этих команд проверяет разрешения пользователей, компьютеров и контактов.</span><span class="sxs-lookup"><span data-stu-id="e9394-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="e9394-129">Дополнительные сведения можно найти в разделе справки по командлету [Test-ксаупермиссион](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="e9394-129">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e9394-130">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="e9394-130">Determining success or failure</span></span>

<span data-ttu-id="e9394-131">Если необходимые разрешения уже установлены, Test-Ксаупермиссион возвратит ответ из одного слова:</span><span class="sxs-lookup"><span data-stu-id="e9394-131">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="e9394-132">True</span><span class="sxs-lookup"><span data-stu-id="e9394-132">True</span></span>

<span data-ttu-id="e9394-133">Если требуемые разрешения не заданы, Test-Ксаупермиссион вернет значение false.</span><span class="sxs-lookup"><span data-stu-id="e9394-133">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="e9394-134">Может потребоваться найти это значение в течение некоторого времени.</span><span class="sxs-lookup"><span data-stu-id="e9394-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="e9394-135">Как правило, он встраивается в несколько соответствующих предупреждений.</span><span class="sxs-lookup"><span data-stu-id="e9394-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="e9394-136">Например:</span><span class="sxs-lookup"><span data-stu-id="e9394-136">For example:</span></span>

<span data-ttu-id="e9394-137">Предупреждение: элемент управления доступом (ACE) ATL-CS-001\\рткуниверсалусерреадонлиграуп; Пуск Реадпроперти; Контаинеринхерит; Потомки; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="e9394-137">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="e9394-138">Предупреждение: элементы управления доступом (ACE) для объекта "OU = Норсамерика, DC = ATL-CS-001\\DC = плана LITWAREINC, DC = com" не готовы.</span><span class="sxs-lookup"><span data-stu-id="e9394-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="e9394-139">False</span><span class="sxs-lookup"><span data-stu-id="e9394-139">False</span></span>

<span data-ttu-id="e9394-140">Предупреждение: обработка "Test-Ксаупермиссион" завершена с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="e9394-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="e9394-141">во время этого запуска записано предупреждение "2".</span><span class="sxs-lookup"><span data-stu-id="e9394-141">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="e9394-142">Предупреждение: подробные результаты можно найти на странице "C:\\\\Users\\admin\\AppData\\Local\\Temp Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de. HTML".</span><span class="sxs-lookup"><span data-stu-id="e9394-142">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e9394-143">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="e9394-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="e9394-144">Если при выполнении теста-Ксаупермиссион это обычно означает, что указанное разрешение не назначено группе Рткуниверсалусерадминс.</span><span class="sxs-lookup"><span data-stu-id="e9394-144">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="e9394-145">Вы можете устранить эту проблему и назначить необходимые разрешения с помощью командлета Grant-Ксаупермиссион.</span><span class="sxs-lookup"><span data-stu-id="e9394-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="e9394-146">Например, эта команда предоставляет разрешения на доступ к подразделению для пользователей, контактов и Инеторгперсонс группе Рткуниверсалусерадминс:</span><span class="sxs-lookup"><span data-stu-id="e9394-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="e9394-147">Дополнительные сведения можно найти в разделе справки о командлете Grant-Ксаупермиссион.</span><span class="sxs-lookup"><span data-stu-id="e9394-147">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

