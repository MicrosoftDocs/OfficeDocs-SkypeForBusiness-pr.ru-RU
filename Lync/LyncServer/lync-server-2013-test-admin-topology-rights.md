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
ms.openlocfilehash: 3681a3328f0e1e659377947919bbfc782f1fea7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="6e01a-102">Проверка прав топологии администратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e01a-102">Test admin topology rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e01a-103">_**Тема последнего изменения:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="6e01a-103">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e01a-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="6e01a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6e01a-105">После первоначального развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e01a-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="6e01a-106">По мере необходимости, если возникают проблемы, связанные с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="6e01a-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e01a-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="6e01a-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6e01a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e01a-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e01a-109">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="6e01a-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6e01a-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="6e01a-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6e01a-111">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Кссетуппермиссион.</span><span class="sxs-lookup"><span data-stu-id="6e01a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="6e01a-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6e01a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6e01a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6e01a-113">Description</span></span>

<span data-ttu-id="6e01a-114">По умолчанию только администраторы домена могут включать топологию сервера Lync и вносить большие изменения в инфраструктуру Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e01a-114">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="6e01a-115">Это не является проблемой, пока Администраторы домена и администраторы сервера Lync находятся в одной и той же папке. Во многих организациях администраторы сервера Lync Server не хранят права администратора для всего домена.</span><span class="sxs-lookup"><span data-stu-id="6e01a-115">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="6e01a-116">По умолчанию, это означает, что администраторы, определенные как члены группы Рткуниверсалсерверадминс, не могут вносить изменения в топологию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e01a-116">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="6e01a-117">Чтобы предоставить участникам группы Рткуниверсалсерверадминс право вносить изменения в топологию, необходимо назначить необходимые разрешения Active Directory с помощью командлета [Grant-кссетуппермиссион](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="6e01a-117">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="6e01a-118">Командлет Test-Кссетуппермиссион удостоверяется в том, что необходимые разрешения, необходимые для установки Lync Server или одного из его компонентов, настроены в указанном контейнере Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6e01a-118">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="6e01a-119">Если разрешения не назначены, можно запустить командлет Grant-Кссетуппермиссион, чтобы предоставить участникам группы Рткуниверсалсерверадминс право на установку и включение Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e01a-119">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e01a-120">Подробный список разрешений, назначенных Grant-Кссетуппермиссион, можно найти в блоге <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-кссетуппермиссион и Grant-ксаупермиссион</A>.</span><span class="sxs-lookup"><span data-stu-id="6e01a-120">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6e01a-121">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="6e01a-121">Running the test</span></span>

<span data-ttu-id="6e01a-122">Чтобы определить, назначены ли разрешения на установку для контейнера Active Directory, вызовите командлет Test-Кссетуппермиссион.</span><span class="sxs-lookup"><span data-stu-id="6e01a-122">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="6e01a-123">Укажите различающееся имя контейнера, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="6e01a-123">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="6e01a-124">Например, эта команда проверяет разрешения на установку в контейнере OU = Кссерверс, DC = плана litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="6e01a-124">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="6e01a-125">Дополнительные сведения можно найти в разделе справки по командлету [Test-кссетуппермиссион](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="6e01a-125">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6e01a-126">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="6e01a-126">Determining success or failure</span></span>

<span data-ttu-id="6e01a-127">Если в параметре test-Кссетуппермиссион определено, что необходимые разрешения уже установлены для контейнера Active Directory, командлет вернет значение true:</span><span class="sxs-lookup"><span data-stu-id="6e01a-127">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="6e01a-128">Верно</span><span class="sxs-lookup"><span data-stu-id="6e01a-128">True</span></span>

<span data-ttu-id="6e01a-129">Если разрешения не заданы, Test-Кссетуппермиссион вернет значение false.</span><span class="sxs-lookup"><span data-stu-id="6e01a-129">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="6e01a-130">Обратите внимание, что это значение обычно заключается на множество предупреждающих сообщений.</span><span class="sxs-lookup"><span data-stu-id="6e01a-130">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="6e01a-131">Например:</span><span class="sxs-lookup"><span data-stu-id="6e01a-131">For example:</span></span>

<span data-ttu-id="6e01a-132">Предупреждение: элемент управления доступом (ACE) ATL-CS-001\\рткуниверсалсерверадминс; Пуск Екстендедригхт; Ничего Ничего 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="6e01a-132">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="6e01a-133">Предупреждение: элементы управления доступом (ACE) для объекта "CN = Computers, DC = плана litwareinc, DC = com" не готовы.</span><span class="sxs-lookup"><span data-stu-id="6e01a-133">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="6e01a-134">False</span><span class="sxs-lookup"><span data-stu-id="6e01a-134">False</span></span>

<span data-ttu-id="6e01a-135">Предупреждение: обработка "Test-Кссетуппермиссион" завершена с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="6e01a-135">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="6e01a-136">во время этого запуска записано предупреждение "2".</span><span class="sxs-lookup"><span data-stu-id="6e01a-136">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="6e01a-137">Предупреждение: подробные результаты можно найти на странице "C:\\\\Users\\admin\\AppData\\Local\\Temp Test-кссетуппермиссион-1da99ba6-abe2-45e4-8b16-dfd244763118. HTML".</span><span class="sxs-lookup"><span data-stu-id="6e01a-137">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6e01a-138">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="6e01a-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="6e01a-139">Несмотря на то, что при выполнении теста-Кссетуппермиссион возникает редкие исключения, обычно это означает, что для определенного контейнера Active Directory разрешения на установку не назначены.</span><span class="sxs-lookup"><span data-stu-id="6e01a-139">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="6e01a-140">Эти разрешения можно назначить с помощью командлета Grant-Кссетуппермиссион.</span><span class="sxs-lookup"><span data-stu-id="6e01a-140">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="6e01a-141">Например, эта команда предоставляет разрешения на установку контейнера Computers в litwareinc.com домена.</span><span class="sxs-lookup"><span data-stu-id="6e01a-141">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="6e01a-142">Дополнительные сведения можно найти в разделе справки по командлету [Test-кссетуппермиссион](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="6e01a-142">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

