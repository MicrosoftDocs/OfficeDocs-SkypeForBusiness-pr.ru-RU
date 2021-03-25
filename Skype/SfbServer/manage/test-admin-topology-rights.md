---
title: Тестирование прав топологии администратора в Skype для бизнеса Server
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
description: Тестирование прав топологии в Skype для бизнеса Server
ms.openlocfilehash: d9c0ec5560dcb6f1a6872f0b38f2930e46b2364c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122393"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="1b314-103">Тестирование прав топологии администратора в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1b314-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="1b314-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="1b314-104">Verification schedule</span></span>|<span data-ttu-id="1b314-105">После начального развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1b314-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="1b314-106">При необходимости, если возникают проблемы, связанные с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="1b314-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="1b314-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="1b314-107">Testing tool</span></span>|<span data-ttu-id="1b314-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b314-108">Windows PowerShell</span></span>|
|<span data-ttu-id="1b314-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="1b314-109">Permissions required</span></span>|<span data-ttu-id="1b314-110">При локальном запуске с помощью оболочки управления серверами Skype для бизнеса пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1b314-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="1b314-111">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, которая имеет разрешение на запуск Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="1b314-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="1b314-112">Чтобы увидеть список всех ролей RBAC, которые могут использовать этот командлет, запустите следующую команду из Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1b314-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="1b314-113">Get-CsAdminRole Where-Object \| {$_. Командлеты -match "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="1b314-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="1b314-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1b314-114">Description</span></span>

<span data-ttu-id="1b314-115">По умолчанию только администраторы доменов могут включить топологию Skype для бизнеса Server и внести большие изменения в инфраструктуру Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1b314-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="1b314-116">Это не будет проблемой до тех пор, пока администраторы домена и администраторы Skype для бизнеса Server будут одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="1b314-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="1b314-117">Во многих организациях администраторы Skype для бизнеса Server не имеют административных прав на весь домен.</span><span class="sxs-lookup"><span data-stu-id="1b314-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="1b314-118">По умолчанию это означает, что эти администраторы (определенные как члены группы RTCUniversalServerAdmins) не могут вносить изменения в топологию Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1b314-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="1b314-119">Чтобы дать членам группы RTCUniversalServerAdmins право вносить изменения в топологию, необходимо назначить необходимые разрешения Active Directory с помощью команды [Grant-CsSetupPermission.](/powershell/module/skype/Grant-CsSetupPermission)</span><span class="sxs-lookup"><span data-stu-id="1b314-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="1b314-120">Этот Test-CsSetupPermission проверяет, что необходимые разрешения, необходимые для установки Skype для бизнес-сервера или одного из его компонентов, настраиваются в указанном контейнере Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1b314-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="1b314-121">Если разрешения не назначены, можно запустить Grant-CsSetupPermission, чтобы предоставить участникам группы RTCUniversalServerAdmins право устанавливать и включить Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1b314-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="1b314-122">Запуск теста</span><span class="sxs-lookup"><span data-stu-id="1b314-122">Running the test</span></span>

<span data-ttu-id="1b314-123">Чтобы определить, назначены ли разрешения на установку для контейнера Active Directory, позвоните в Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="1b314-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="1b314-124">Укажите отличительное имя проверяемого контейнера.</span><span class="sxs-lookup"><span data-stu-id="1b314-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="1b314-125">Например, эта команда проверяет разрешения установки на контейнере ou=CsServers,dc=litwareinc,dc=com:</span><span class="sxs-lookup"><span data-stu-id="1b314-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="1b314-126">Дополнительные сведения см. в разделе Справка для [cmdlet Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)</span><span class="sxs-lookup"><span data-stu-id="1b314-126">For more information, see the help topic for the [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1b314-127">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="1b314-127">Determining success or failure</span></span>

<span data-ttu-id="1b314-128">Если Test-CsSetupPermission определяет, что необходимые разрешения уже установлены в контейнере Active Directory, то в этом случае в этот код возвращается значение True:</span><span class="sxs-lookup"><span data-stu-id="1b314-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="1b314-129">Верно</span><span class="sxs-lookup"><span data-stu-id="1b314-129">True</span></span> 

<span data-ttu-id="1b314-130">Если разрешения не установлены, Test-CsSetupPermission возвращает значение False.</span><span class="sxs-lookup"><span data-stu-id="1b314-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="1b314-131">Обратите внимание, что это значение обычно будет заключено во многих предупреждающих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="1b314-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="1b314-132">Например:</span><span class="sxs-lookup"><span data-stu-id="1b314-132">For example:</span></span>

<span data-ttu-id="1b314-133">ВНИМАНИЕ. Запись управления доступом (ACE) atl-cs-001\RTCUniversalServerAdmins; Разрешить; ExtendedRight; Нет; Нет; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="1b314-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="1b314-134">ВНИМАНИЕ. Записи управления доступом (ACEs) на объекте "CN=Computers,DC=litwareinc,DC=com" не готовы.</span><span class="sxs-lookup"><span data-stu-id="1b314-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="1b314-135">False</span><span class="sxs-lookup"><span data-stu-id="1b314-135">False</span></span> 

<span data-ttu-id="1b314-136">ВНИМАНИЕ. Обработка "Test-CsSetupPermission" завершена с помощью предупреждений.</span><span class="sxs-lookup"><span data-stu-id="1b314-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="1b314-137">Во время этого запуска были записаны предупреждения "2".</span><span class="sxs-lookup"><span data-stu-id="1b314-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="1b314-138">ВНИМАНИЕ. Подробные результаты можно найти на "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span><span class="sxs-lookup"><span data-stu-id="1b314-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1b314-139">Причины сбой теста</span><span class="sxs-lookup"><span data-stu-id="1b314-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="1b314-140">Хотя существуют редкие исключения, если Test-CsSetupPermission сбой, что обычно означает, что разрешения на установку не назначены для указанного контейнера Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1b314-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="1b314-141">Эти разрешения могут быть назначены с помощью Grant-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="1b314-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="1b314-142">Например, эта команда предоставляет разрешения на установку контейнеру Computers в домене litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="1b314-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="1b314-143">Дополнительные сведения см. в разделе Справка для [cmdlet Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)</span><span class="sxs-lookup"><span data-stu-id="1b314-143">For more information, see the help topic for the [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>