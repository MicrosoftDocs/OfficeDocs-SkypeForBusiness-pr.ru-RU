---
title: Тестирование разрешений администратора в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Проверка разрешений администратора в Skype для бизнеса Server
ms.openlocfilehash: 1e06c87dcf0e436d72c510a2bc8d9f2aa2051620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030162"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="fdc56-103">Тестирование разрешений администратора в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fdc56-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="fdc56-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="fdc56-104">Verification schedule</span></span>|<span data-ttu-id="fdc56-105">После первоначального развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fdc56-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="fdc56-106">При необходимости, если возникают проблемы, связанные с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="fdc56-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="fdc56-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="fdc56-107">Testing tool</span></span>|<span data-ttu-id="fdc56-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fdc56-108">Windows PowerShell</span></span>|
|<span data-ttu-id="fdc56-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="fdc56-109">Permissions required</span></span>|<span data-ttu-id="fdc56-110">При локальном запуске с помощью командной консоли Skype для бизнеса Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fdc56-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="fdc56-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="fdc56-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="fdc56-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fdc56-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="fdc56-113">Get – CsAdminRole \| Where – Object {$ _. Командлеты-ПОИСКПОЗ "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="fdc56-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="fdc56-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fdc56-114">Description</span></span>

<span data-ttu-id="fdc56-115">При установке Skype для бизнеса Server одна из задач, которая выполнялась программой установки, предоставляет группе RTCUniversalUserAdmins разрешения Active Directory, необходимые для управления пользователями, компьютерами, контактами, контактами приложений и Инеторг. Person.</span><span class="sxs-lookup"><span data-stu-id="fdc56-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="fdc56-116">Если вы отключили наследование разрешений в Active Directory, программа установки не сможет назначить эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="fdc56-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="fdc56-117">В результате участники группы RTCUniversalUserAdmins не смогут управлять сущностями Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fdc56-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="fdc56-118">Эти привилегии управления будут доступны только администраторам домена.</span><span class="sxs-lookup"><span data-stu-id="fdc56-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="fdc56-119">Командлет Test-CsOUPermission проверяет, что для контейнера Active Directory установлены необходимые разрешения, необходимые для управления пользователями, компьютерами и другими объектами.</span><span class="sxs-lookup"><span data-stu-id="fdc56-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="fdc56-120">Если эти разрешения не заданы, можно устранить эту проблему, выполнив [командлет Grant – CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission).</span><span class="sxs-lookup"><span data-stu-id="fdc56-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="fdc56-121">Обратите внимание, что Grant – CsOUPermission может назначать разрешения только членам группы RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="fdc56-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="fdc56-122">Вы не можете использовать этот командлет для предоставления разрешений произвольному пользователю или группе.</span><span class="sxs-lookup"><span data-stu-id="fdc56-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="fdc56-123">Если вы хотите, чтобы другой пользователь или группа применялись к разрешениям управления пользователями, необходимо добавить этого пользователя (или группу) в группу RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="fdc56-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="fdc56-124">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="fdc56-124">Running the test</span></span>

<span data-ttu-id="fdc56-125">Чтобы проверить, установлены ли для контейнера разрешения на управление, запустите командлет Test-CsOUPermission, а затем различающееся имя контейнера и тип проверяемых разрешений.</span><span class="sxs-lookup"><span data-stu-id="fdc56-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="fdc56-126">Например, эта команда проверяет, установлены ли разрешения пользователя для подразделения OU = Redmond, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="fdc56-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="fdc56-127">Чтобы проверить несколько разрешений с помощью одной команды, заключите каждый тип разрешения в кавычки, а затем разделите эти типы с помощью запятых.</span><span class="sxs-lookup"><span data-stu-id="fdc56-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="fdc56-128">Например, одна команда проверяет разрешения пользователя, компьютера и контакта:</span><span class="sxs-lookup"><span data-stu-id="fdc56-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="fdc56-129">Для получения дополнительных сведений обратитесь к [разделу "Справка" для командлета Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="fdc56-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fdc56-130">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="fdc56-130">Determining success or failure</span></span>

<span data-ttu-id="fdc56-131">Если необходимые разрешения уже заданы, Test-CsOUPermission возвратит ответ из одного слова:</span><span class="sxs-lookup"><span data-stu-id="fdc56-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="fdc56-132">Верно</span><span class="sxs-lookup"><span data-stu-id="fdc56-132">True</span></span>

<span data-ttu-id="fdc56-133">Если необходимые разрешения не заданы, Test-CsOUPermission будет возвращать значение false.</span><span class="sxs-lookup"><span data-stu-id="fdc56-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="fdc56-134">Вам может потребоваться найти это значение в течение некоторого времени.</span><span class="sxs-lookup"><span data-stu-id="fdc56-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="fdc56-135">Как правило, она обычно внедряется в несколько соответствующих предупреждений.</span><span class="sxs-lookup"><span data-stu-id="fdc56-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="fdc56-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="fdc56-136">For example:</span></span>

<span data-ttu-id="fdc56-137">Предупреждение: элемент управления доступом (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; разрешить Реадпроперти; Контаинеринхерит; Потомки bf967aba-0de6-11d0-00aa003049e2; d819615a — 3b9b – 4738 — b47e – f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="fdc56-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="fdc56-138">Предупреждение: записи управления доступом (ACE) для объекта "OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com" не готовы.</span><span class="sxs-lookup"><span data-stu-id="fdc56-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="fdc56-139">False</span><span class="sxs-lookup"><span data-stu-id="fdc56-139">False</span></span> 

<span data-ttu-id="fdc56-140">Предупреждение: "Test-CsOUPermission" обработка завершена с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="fdc56-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="fdc56-141">во время этого запуска было записано предупреждение 2.</span><span class="sxs-lookup"><span data-stu-id="fdc56-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="fdc56-142">Предупреждение: подробные результаты можно найти по адресу "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="fdc56-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fdc56-143">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="fdc56-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="fdc56-144">Если Test-CsOUPermission завершается с ошибкой, обычно это означает, что указанное разрешение не было назначено группе RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="fdc56-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="fdc56-145">Эту проблему можно решить и назначить необходимые разрешения с помощью командлета Grant – CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="fdc56-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="fdc56-146">Например, эта команда предоставляет разрешения OU для пользователей, контактов и Инеторгперсонс группе RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="fdc56-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="fdc56-147">Для получения дополнительных сведений обратитесь к [разделу "Справка" для командлета Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="fdc56-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>
