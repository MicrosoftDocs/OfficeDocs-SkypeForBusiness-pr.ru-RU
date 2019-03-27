---
title: Тестирование разрешения администратора в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Проверка разрешений администратора в Скайп для Business Server
ms.openlocfilehash: 3f3f649ea01f974cf0462cabb7784bedc7a6df4f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873361"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="b83d0-103">Тестирование разрешения администратора в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="b83d0-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="b83d0-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="b83d0-104">Verification schedule</span></span>|<span data-ttu-id="b83d0-105">После первоначальной Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="b83d0-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="b83d0-106">При необходимости в случае возникновения проблем, связанных с разрешением.</span><span class="sxs-lookup"><span data-stu-id="b83d0-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="b83d0-107">Средства тестирования</span><span class="sxs-lookup"><span data-stu-id="b83d0-107">Testing tool</span></span>|<span data-ttu-id="b83d0-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b83d0-108">Windows PowerShell</span></span>|
|<span data-ttu-id="b83d0-109">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="b83d0-109">Permissions required</span></span>|<span data-ttu-id="b83d0-110">При запуске локально с помощью Скайп для консоли Business Server, пользователи должны быть членами группы RTCUniversalServerAdmins безопасности.</span><span class="sxs-lookup"><span data-stu-id="b83d0-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="b83d0-111">При запуске с помощью удаленной оболочки Windows PowerShell, пользователям необходимо назначить роль RBAC, которая имеет разрешение на запуск командлета Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="b83d0-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="b83d0-112">Чтобы просмотреть список всех ролей RBAC, можно с помощью этого командлета, выполните следующую команду в командной строке Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b83d0-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="b83d0-113">Get-CsAdminRole \| Where-Object {$_. Командлеты-match «Test-CsOUPermission»}</span><span class="sxs-lookup"><span data-stu-id="b83d0-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="b83d0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b83d0-114">Description</span></span>

<span data-ttu-id="b83d0-115">При установке Скайп для Business Server одной из задач, выполняемого программой установки предоставляет группе RTCUniversalUserAdmins разрешения Active Directory, которые требуются для управления пользователями, компьютеров, контактов, контактов приложения и InetOrg лица.</span><span class="sxs-lookup"><span data-stu-id="b83d0-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="b83d0-116">Если вы отключили наследование разрешений в Active Directory, программа установки не сможет назначать разрешения.</span><span class="sxs-lookup"><span data-stu-id="b83d0-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="b83d0-117">В результате члены группы RTCUniversalUserAdmins не сможет управлять Скайп для сущностей Business Server.</span><span class="sxs-lookup"><span data-stu-id="b83d0-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="b83d0-118">Эти права управления доступна только для администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="b83d0-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="b83d0-119">Командлет Test-CsOUPermission проверяет, что для контейнера Active Directory установлены требуемые разрешения, необходимые для управления пользователями, компьютеры и другие объекты.</span><span class="sxs-lookup"><span data-stu-id="b83d0-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="b83d0-120">Если эти разрешения не заданы, можно устранить эту проблему, выполнив [командлет Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span><span class="sxs-lookup"><span data-stu-id="b83d0-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="b83d0-121">Обратите внимание на то, что Grant-CsOUPermission могут быть назначены только разрешений членам группы RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="b83d0-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="b83d0-122">Этот командлет нельзя использовать для предоставления разрешений на произвольного пользователя или группы.</span><span class="sxs-lookup"><span data-stu-id="b83d0-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="b83d0-123">Если необходимо иметь разрешения на управление пользователями другого пользователя или группы, следует добавить в группу RTCUniversalUserAdmins этого пользователя (или группы).</span><span class="sxs-lookup"><span data-stu-id="b83d0-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="b83d0-124">Тест</span><span class="sxs-lookup"><span data-stu-id="b83d0-124">Running the test</span></span>

<span data-ttu-id="b83d0-125">Чтобы убедиться, что установлены разрешения управления в контейнере, запустите командлет Test-CsOUPermission, затем по различающееся имя контейнера и по типу разрешения, которые проверяются.</span><span class="sxs-lookup"><span data-stu-id="b83d0-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="b83d0-126">Например, эта команда проверяет установил ли разрешения пользователя на подразделение OU = Redmond, dc = litwareinc, dc = com:</span><span class="sxs-lookup"><span data-stu-id="b83d0-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="b83d0-127">Чтобы проверить несколько разрешений с помощью одной команды, заключите каждый тип разрешения, заключенной в кавычки, а затем разделяются запятыми этих типов.</span><span class="sxs-lookup"><span data-stu-id="b83d0-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="b83d0-128">Например один проверяется пользователей и компьютеров контакт разрешения:</span><span class="sxs-lookup"><span data-stu-id="b83d0-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="b83d0-129">Для получения дополнительных сведений см [раздел справки для командлета Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="b83d0-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b83d0-130">Определение успешное или неудачное</span><span class="sxs-lookup"><span data-stu-id="b83d0-130">Determining success or failure</span></span>

<span data-ttu-id="b83d0-131">Если уже были установлены соответствующие разрешения, Test-CsOUPermission возвращает ответа одного слова:</span><span class="sxs-lookup"><span data-stu-id="b83d0-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="b83d0-132">True</span><span class="sxs-lookup"><span data-stu-id="b83d0-132">True</span></span>

<span data-ttu-id="b83d0-133">Если заданы соответствующие разрешения, Test-CsOUPermission возвращает значение False.</span><span class="sxs-lookup"><span data-stu-id="b83d0-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="b83d0-134">Может потребоваться поиск некоторое время найти это значение.</span><span class="sxs-lookup"><span data-stu-id="b83d0-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="b83d0-135">Оно обычно внедряться в несколько сопутствующий предупреждения.</span><span class="sxs-lookup"><span data-stu-id="b83d0-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="b83d0-136">Например:</span><span class="sxs-lookup"><span data-stu-id="b83d0-136">For example:</span></span>

<span data-ttu-id="b83d0-137">Предупреждение: доступ к управления доступом atl-cs-001\RTCUniversalUserReadOnlyGroup; Разрешить; ReadProperty; ContainerInherit; Потомки; 0 bf967aba-0de6 - 11d-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="b83d0-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="b83d0-138">Предупреждение: Записи управления доступом (ACE) на объекте «OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com» еще не готово.</span><span class="sxs-lookup"><span data-stu-id="b83d0-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="b83d0-139">False</span><span class="sxs-lookup"><span data-stu-id="b83d0-139">False</span></span> 

<span data-ttu-id="b83d0-140">Предупреждение: «Test-CsOUPermission» обработка выполнена с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="b83d0-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="b83d0-141">«2» предупреждений, зарегистрированных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b83d0-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="b83d0-142">Предупреждение: Подробные результаты, можно найти в «C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html».</span><span class="sxs-lookup"><span data-stu-id="b83d0-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b83d0-143">Причины, почему не удалось теста</span><span class="sxs-lookup"><span data-stu-id="b83d0-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="b83d0-144">Если Test-CsOUPermission не удается, это обычно означает, что указанное разрешение не был назначен группе RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="b83d0-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="b83d0-145">Можно устранить неполадки и назначить требуемые разрешения с помощью командлета Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="b83d0-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="b83d0-146">Например эта команда предоставляет разрешения Подразделения для пользователей, контактов и inetOrgPersons в группу RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="b83d0-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="b83d0-147">Для получения дополнительных сведений см [раздел справки для командлета Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="b83d0-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>
