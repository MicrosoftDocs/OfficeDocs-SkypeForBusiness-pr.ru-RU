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
ms.openlocfilehash: 97db574803b575d484240e7339d56603ae5432da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817190"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="9afbb-103">Тестирование разрешений администратора в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9afbb-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="9afbb-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="9afbb-104">Verification schedule</span></span>|<span data-ttu-id="9afbb-105">После первоначального развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9afbb-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="9afbb-106">По мере необходимости, если возникают проблемы, связанные с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="9afbb-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="9afbb-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="9afbb-107">Testing tool</span></span>|<span data-ttu-id="9afbb-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9afbb-108">Windows PowerShell</span></span>|
|<span data-ttu-id="9afbb-109">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="9afbb-109">Permissions required</span></span>|<span data-ttu-id="9afbb-110">При локальном запуске с помощью командной консоли Skype для бизнеса Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="9afbb-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="9afbb-111">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксаупермиссион.</span><span class="sxs-lookup"><span data-stu-id="9afbb-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="9afbb-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9afbb-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="9afbb-113">Get-Ксадминроле \| Where-Object {$ _. Командлеты-Match "Test-Ксаупермиссион"}</span><span class="sxs-lookup"><span data-stu-id="9afbb-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="9afbb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9afbb-114">Description</span></span>

<span data-ttu-id="9afbb-115">При установке Skype для бизнеса Server одной из задач, выполненных программой установки, выводится группа Рткуниверсалусерадминс с разрешениями Active Directory, необходимыми для управления пользователями, компьютерами, контактами, контактами приложений и Инеторг людей.</span><span class="sxs-lookup"><span data-stu-id="9afbb-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="9afbb-116">Если вы отключили наследование разрешений в Active Directory, программа установки не сможет назначить эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="9afbb-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="9afbb-117">В результате участники группы Рткуниверсалусерадминс не смогут управлять сущностями Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9afbb-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="9afbb-118">Эти права на управление будут доступны только администраторам домена.</span><span class="sxs-lookup"><span data-stu-id="9afbb-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="9afbb-119">Командлет Test-Ксаупермиссион удостоверяется в том, что необходимые разрешения, необходимые для управления пользователями, компьютерами и другими объектами, задаются в контейнере Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9afbb-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="9afbb-120">Если эти разрешения не заданы, вы можете устранить эту проблему, выполнив [командлет Grant-ксаупермиссион](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span><span class="sxs-lookup"><span data-stu-id="9afbb-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="9afbb-121">Обратите внимание, что Grant-Ксаупермиссион может назначать разрешения только участникам группы Рткуниверсалусерадминс.</span><span class="sxs-lookup"><span data-stu-id="9afbb-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="9afbb-122">Вы не можете использовать этот командлет, чтобы предоставить разрешения для произвольного пользователя или группы.</span><span class="sxs-lookup"><span data-stu-id="9afbb-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="9afbb-123">Если вы хотите, чтобы другой пользователь или группа имели разрешения на управление пользователями, вы должны добавить этого пользователя (или группу) в группу Рткуниверсалусерадминс.</span><span class="sxs-lookup"><span data-stu-id="9afbb-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="9afbb-124">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="9afbb-124">Running the test</span></span>

<span data-ttu-id="9afbb-125">Чтобы убедиться в том, что для контейнера заданы разрешения на управление, выполните командлет Test-Ксаупермиссион, а затем — различающееся имя контейнера и тип проверяемых разрешений.</span><span class="sxs-lookup"><span data-stu-id="9afbb-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="9afbb-126">Например, эта команда проверяет, заданы ли разрешения пользователей на подразделение OU = Redmond, DC = плана litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="9afbb-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="9afbb-127">Для проверки нескольких разрешений с помощью одной команды заключите все типы разрешений в кавычки, а затем разделите их с помощью запятых.</span><span class="sxs-lookup"><span data-stu-id="9afbb-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="9afbb-128">Например, одна из этих команд проверяет разрешения пользователей, компьютеров и контактов.</span><span class="sxs-lookup"><span data-stu-id="9afbb-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="9afbb-129">Дополнительные сведения можно найти в [разделе справки по командлету Test-ксаупермиссион](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="9afbb-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9afbb-130">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="9afbb-130">Determining success or failure</span></span>

<span data-ttu-id="9afbb-131">Если необходимые разрешения уже установлены, тест-Ксаупермиссион возвратит ответ из одного слова:</span><span class="sxs-lookup"><span data-stu-id="9afbb-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="9afbb-132">Верно</span><span class="sxs-lookup"><span data-stu-id="9afbb-132">True</span></span>

<span data-ttu-id="9afbb-133">Если не заданы необходимые разрешения, Test-Ксаупермиссион возвратит значение false.</span><span class="sxs-lookup"><span data-stu-id="9afbb-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="9afbb-134">Может потребоваться найти это значение в течение некоторого времени.</span><span class="sxs-lookup"><span data-stu-id="9afbb-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="9afbb-135">Как правило, он встраивается в несколько соответствующих предупреждений.</span><span class="sxs-lookup"><span data-stu-id="9afbb-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="9afbb-136">Например:</span><span class="sxs-lookup"><span data-stu-id="9afbb-136">For example:</span></span>

<span data-ttu-id="9afbb-137">Предупреждение: элемент управления доступом (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; Пуск Реадпроперти; Контаинеринхерит; Потомки; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="9afbb-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="9afbb-138">Предупреждение: элементы управления доступом (ACE) для объекта "OU = Норсамерика, DC = atl-cs-001\DC = плана litwareinc, DC = com" не готовы.</span><span class="sxs-lookup"><span data-stu-id="9afbb-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="9afbb-139">False</span><span class="sxs-lookup"><span data-stu-id="9afbb-139">False</span></span> 

<span data-ttu-id="9afbb-140">Предупреждение: обработка "Test-Ксаупермиссион" завершена с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="9afbb-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="9afbb-141">во время этого запуска записано предупреждение "2".</span><span class="sxs-lookup"><span data-stu-id="9afbb-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="9afbb-142">Предупреждение: подробные результаты можно найти по адресу "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="9afbb-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9afbb-143">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="9afbb-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="9afbb-144">Если при выполнении теста-Ксаупермиссион происходит сбой, это означает, что указанное разрешение не было назначено группе Рткуниверсалусерадминс.</span><span class="sxs-lookup"><span data-stu-id="9afbb-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="9afbb-145">Вы можете устранить эту проблему и назначить необходимые разрешения с помощью командлета Grant-Ксаупермиссион.</span><span class="sxs-lookup"><span data-stu-id="9afbb-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="9afbb-146">Например, эта команда предоставляет разрешения на доступ к подразделению для пользователей, контактов и Инеторгперсонс группе Рткуниверсалусерадминс:</span><span class="sxs-lookup"><span data-stu-id="9afbb-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="9afbb-147">Дополнительные сведения можно найти в [разделе справки по командлету Test-ксаупермиссион](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="9afbb-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>
