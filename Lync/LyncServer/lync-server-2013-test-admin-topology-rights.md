---
title: 'Lync Server 2013: Проверка прав топологии администратора'
description: 'Lync Server 2013: Проверка прав топологии администратора.'
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
ms.openlocfilehash: 22d713297d0e944c7acbc5efcb11b21ea1b26639
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568565"
---
# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="b9475-103">Проверка прав топологии администратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9475-103">Test admin topology rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9475-104">_**Последнее изменение темы:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="b9475-104">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9475-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="b9475-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b9475-106">После первоначального развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9475-106">After initial Lync Server deployment.</span></span> <span data-ttu-id="b9475-107">При необходимости, если возникают проблемы, связанные с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="b9475-107">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9475-108">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="b9475-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b9475-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9475-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9475-110">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="b9475-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b9475-111">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b9475-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b9475-112">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="b9475-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="b9475-113">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b9475-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b9475-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b9475-114">Description</span></span>

<span data-ttu-id="b9475-115">По умолчанию только администраторы домена могут включать топологию Lync Server и вносить значительные изменения в инфраструктуру Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9475-115">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="b9475-116">Это не проблема, если администраторы домена и администраторы сервера Lync являются одним и тем же. Во многих организациях администраторы сервера Lync Server не хранят права администратора для всего домена.</span><span class="sxs-lookup"><span data-stu-id="b9475-116">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="b9475-117">По умолчанию это означает, что эти администраторы (определенные как члены группы RTCUniversalServerAdmins) не могут вносить изменения в топологию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9475-117">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="b9475-118">Чтобы предоставить членам группы RTCUniversalServerAdmins право на внесение изменений в топологию, необходимо назначить необходимые разрешения Active Directory с помощью командлета [Grant – CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="b9475-118">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="b9475-119">Командлет Test-CsSetupPermission проверяет, настроены ли необходимые разрешения, необходимые для установки Lync Server или одного из его компонентов, в указанном контейнере Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9475-119">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="b9475-120">Если разрешения не назначены, можно запустить командлет Grant-CsSetupPermission, чтобы предоставить членам группы RTCUniversalServerAdmins право на установку и включение Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9475-120">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9475-121">Подробный список разрешений, назначаемых Grant – CsSetupPermission, можно узнать в блоге <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">granting — CsSetupPermission и Grant/CsOUPermission</A>.</span><span class="sxs-lookup"><span data-stu-id="b9475-121">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b9475-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="b9475-122">Running the test</span></span>

<span data-ttu-id="b9475-123">Чтобы определить, назначены ли разрешения на установку для контейнера Active Directory, вызовите командлет Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="b9475-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="b9475-124">Укажите различающееся имя контейнера, который необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="b9475-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="b9475-125">Например, эта команда проверяет разрешения программы установки для контейнера OU = Кссерверс, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="b9475-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="b9475-126">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="b9475-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b9475-127">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="b9475-127">Determining success or failure</span></span>

<span data-ttu-id="b9475-128">Если Test-CsSetupPermission определяет, что необходимые разрешения для контейнера Active Directory уже заданы, командлет возвращает значение true:</span><span class="sxs-lookup"><span data-stu-id="b9475-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="b9475-129">Верно</span><span class="sxs-lookup"><span data-stu-id="b9475-129">True</span></span>

<span data-ttu-id="b9475-130">Если разрешения не заданы, то Test-CsSetupPermission возвращает значение false.</span><span class="sxs-lookup"><span data-stu-id="b9475-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="b9475-131">Обратите внимание, что это значение, как правило, будет заключено во множество предупреждающих сообщений.</span><span class="sxs-lookup"><span data-stu-id="b9475-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="b9475-132">Например:</span><span class="sxs-lookup"><span data-stu-id="b9475-132">For example:</span></span>

<span data-ttu-id="b9475-133">Предупреждение: запись управления доступом (ACE) ATL-CS-001 \\ RTCUniversalServerAdmins; Разрешить Екстендедригхт; Видим Видим 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="b9475-133">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="b9475-134">Предупреждение: записи управления доступом (ACE) для объекта "CN = Computers, DC = litwareinc, DC = com" не готовы.</span><span class="sxs-lookup"><span data-stu-id="b9475-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="b9475-135">False</span><span class="sxs-lookup"><span data-stu-id="b9475-135">False</span></span>

<span data-ttu-id="b9475-136">Предупреждение: "Test-CsSetupPermission" обработка завершена с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="b9475-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="b9475-137">во время этого запуска было записано предупреждение 2.</span><span class="sxs-lookup"><span data-stu-id="b9475-137">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="b9475-138">Предупреждение: подробные результаты можно найти на сайте "C: \\ Users \\ Admin \\ AppData \\ Local \\ temp \\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span><span class="sxs-lookup"><span data-stu-id="b9475-138">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b9475-139">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="b9475-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="b9475-140">Несмотря на то, что в Test-CsSetupPermission возникает редкие исключения, обычно это означает, что разрешения программы установки не назначены указанному контейнеру Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9475-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="b9475-141">Эти разрешения могут быть назначены с помощью командлета Grant-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="b9475-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="b9475-142">Например, эта команда предоставляет разрешения на установку контейнера Computers в домене litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="b9475-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="b9475-143">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="b9475-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

