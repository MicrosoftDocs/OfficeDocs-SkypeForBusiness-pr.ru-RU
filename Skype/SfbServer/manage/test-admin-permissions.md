---
title: Тестирование разрешений администратора в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Тестирование разрешений администратора в Skype для бизнеса Server
ms.openlocfilehash: 27ae50cca0018985ad59dbc4487dd3630cb5cf87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800099"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="ab4c4-103">Тестирование разрешений администратора в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ab4c4-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="ab4c4-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="ab4c4-104">Verification schedule</span></span>|<span data-ttu-id="ab4c4-105">После начального развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="ab4c4-106">При необходимости, если возникают проблемы, связанные с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="ab4c4-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="ab4c4-107">Testing tool</span></span>|<span data-ttu-id="ab4c4-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab4c4-108">Windows PowerShell</span></span>|
|<span data-ttu-id="ab4c4-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="ab4c4-109">Permissions required</span></span>|<span data-ttu-id="ab4c4-110">При локальном запуске с помощью оболочки управления Skype для бизнеса Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="ab4c4-111">При запуске с помощью удаленного экземпляра Windows PowerShell пользователю должна быть назначена роль RBAC с разрешением на Test-CsOUPermission управления доступом.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="ab4c4-112">Чтобы увидеть список всех ролей RBAC, которые могут использовать этот командлет, в командной Windows PowerShell командной Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ab4c4-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="ab4c4-113">Get-CsAdminRole Where-Object \| {$_. Командлеты -match "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="ab4c4-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="ab4c4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ab4c4-114">Description</span></span>

<span data-ttu-id="ab4c4-115">При установке Skype для бизнеса Server одна из задач, выполняемых программой установки, предоставляет группе RTCUniversalUserAdmins разрешения Active Directory, необходимые для управления пользователями, компьютерами, контактами, контактами приложений и пользователями InetOrg.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="ab4c4-116">Если вы отключили наследование разрешений в Active Directory, установка не сможет назначить эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="ab4c4-117">В результате члены группы RTCUniversalUserAdmins не смогут управлять объектами Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="ab4c4-118">Эти права управления будут доступны только администраторам домена.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="ab4c4-119">Этот Test-CsOUPermission проверяет, установлены ли необходимые разрешения для управления пользователями, компьютерами и другими объектами в контейнере Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="ab4c4-120">Если эти разрешения не заданы, эту проблему можно устранить с помощью [запускалета Grant-CsOUPermission.](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)</span><span class="sxs-lookup"><span data-stu-id="ab4c4-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="ab4c4-121">Обратите вниманиеGrant-CsOUPermission что разрешения можно назначать только членам группы RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="ab4c4-122">Этот cmdlet нельзя использовать для предоставления разрешений произвольному пользователю или группе.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="ab4c4-123">Если вы хотите, чтобы разрешения на управление пользователями были у другого пользователя или группы, следует добавить этого пользователя (или группу) в группу RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="ab4c4-124">Запуск теста</span><span class="sxs-lookup"><span data-stu-id="ab4c4-124">Running the test</span></span>

<span data-ttu-id="ab4c4-125">Чтобы проверить, установлены ли разрешения управления для контейнера, запустите Test-CsOUPermission, за которым следует различающийся имя контейнера и тип проверяемого разрешения.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="ab4c4-126">Например, эта команда проверяет, установлены ли разрешения пользователя для OU=Redmond,dc=litwareinc,dc=com:</span><span class="sxs-lookup"><span data-stu-id="ab4c4-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="ab4c4-127">Чтобы проверить несколько разрешений с помощью одной команды, заключив каждый тип разрешений в кавычках, разделять эти типы запятой.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="ab4c4-128">Например, эта команда проверяет разрешения пользователей, компьютеров и контактов:</span><span class="sxs-lookup"><span data-stu-id="ab4c4-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="ab4c4-129">Дополнительные сведения см. в разделе [справки по Test-CsOUPermission.](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)</span><span class="sxs-lookup"><span data-stu-id="ab4c4-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ab4c4-130">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="ab4c4-130">Determining success or failure</span></span>

<span data-ttu-id="ab4c4-131">Если необходимые разрешения уже установлены, Test-CsOUPermission возвращает ответ из одного слова:</span><span class="sxs-lookup"><span data-stu-id="ab4c4-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="ab4c4-132">Верно</span><span class="sxs-lookup"><span data-stu-id="ab4c4-132">True</span></span>

<span data-ttu-id="ab4c4-133">Если необходимые разрешения не задаются, Test-CsOUPermission возвращает значение False.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="ab4c4-134">Возможно, вам придется найти это значение в течение времени.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="ab4c4-135">Как правило, он внедряется в несколько сопутствующих предупреждений.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="ab4c4-136">Например:</span><span class="sxs-lookup"><span data-stu-id="ab4c4-136">For example:</span></span>

<span data-ttu-id="ab4c4-137">ПРЕДУПРЕЖДЕНИЕ: запись управления доступом (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Потомки; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="ab4c4-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="ab4c4-138">ПРЕДУПРЕЖДЕНИЕ. Элементы управления доступом (AES) в объекте "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" не готовы.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="ab4c4-139">False</span><span class="sxs-lookup"><span data-stu-id="ab4c4-139">False</span></span> 

<span data-ttu-id="ab4c4-140">ПРЕДУПРЕЖДЕНИЕ: обработка Test-CsOUPermission завершена с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="ab4c4-141">Во время этого запуска были записаны предупреждения "2".</span><span class="sxs-lookup"><span data-stu-id="ab4c4-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="ab4c4-142">ПРЕДУПРЕЖДЕНИЕ. Подробные результаты можно найти по C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ab4c4-143">Причины, по которым мог произойть сбой теста</span><span class="sxs-lookup"><span data-stu-id="ab4c4-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="ab4c4-144">Если Test-CsOUPermission происходит сбой, это обычно означает, что указанное разрешение не было назначено группе RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="ab4c4-145">Эту проблему можно устранить и назначить необходимые разрешения с помощью Grant-CsOUPermission управления.</span><span class="sxs-lookup"><span data-stu-id="ab4c4-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="ab4c4-146">Например, эта команда предоставляет группе RTCUniversalUserAdmins разрешения для пользователей, контактов и inetOrgPersons:</span><span class="sxs-lookup"><span data-stu-id="ab4c4-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="ab4c4-147">Дополнительные сведения см. в разделе [справки по Test-CsOUPermission.](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)</span><span class="sxs-lookup"><span data-stu-id="ab4c4-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>
