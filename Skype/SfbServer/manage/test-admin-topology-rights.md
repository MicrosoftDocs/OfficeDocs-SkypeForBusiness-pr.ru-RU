---
title: Тестирование прав администратора топологии в Skype для бизнеса Server
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
ms.openlocfilehash: a6bbebd44387911fdb69679a16ab052c673f0b10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832849"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="d924a-103">Тестирование прав администратора топологии в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d924a-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="d924a-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="d924a-104">Verification schedule</span></span>|<span data-ttu-id="d924a-105">После начального развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d924a-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="d924a-106">При необходимости, если возникают проблемы, связанные с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="d924a-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="d924a-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="d924a-107">Testing tool</span></span>|<span data-ttu-id="d924a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d924a-108">Windows PowerShell</span></span>|
|<span data-ttu-id="d924a-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="d924a-109">Permissions required</span></span>|<span data-ttu-id="d924a-110">При локальном запуске с помощью оболочки управления Skype для бизнеса Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d924a-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="d924a-111">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, которая имеет разрешение на запуск Test-CsSetupPermission управления.</span><span class="sxs-lookup"><span data-stu-id="d924a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="d924a-112">Чтобы увидеть список всех ролей RBAC, которые могут использовать этот командлет, в командной Windows PowerShell командной Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d924a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="d924a-113">Get-CsAdminRole Where-Object \| {$_. Командлеты -match "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="d924a-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="d924a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d924a-114">Description</span></span>

<span data-ttu-id="d924a-115">По умолчанию только администраторы домена могут включить топологию Skype для бизнеса Server и внести существенные изменения в инфраструктуру Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d924a-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="d924a-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span><span class="sxs-lookup"><span data-stu-id="d924a-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="d924a-117">Во многих организациях администраторы Skype для бизнеса Server не имеют административных прав на весь домен.</span><span class="sxs-lookup"><span data-stu-id="d924a-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="d924a-118">По умолчанию это означает, что эти администраторы (определенные как участники группы RTCUniversalServerAdmins) не могут вносить изменения в топологию Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d924a-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="d924a-119">Чтобы предоставить участникам группы RTCUniversalServerAdmins право на внесение изменений в топологию, необходимо назначить необходимые разрешения Active Directory с помощью команды [Grant-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)</span><span class="sxs-lookup"><span data-stu-id="d924a-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="d924a-120">Этот Test-CsSetupPermission проверяет, настроены ли необходимые разрешения для установки Skype для бизнеса Server или одного из его компонентов в указанном контейнере Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d924a-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="d924a-121">Если разрешения не назначены, можно запустить Grant-CsSetupPermission, чтобы предоставить участникам группы RTCUniversalServerAdmins право на установку и разрешение Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d924a-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="d924a-122">Запуск теста</span><span class="sxs-lookup"><span data-stu-id="d924a-122">Running the test</span></span>

<span data-ttu-id="d924a-123">Чтобы определить, назначены ли разрешения на установку для контейнера Active Directory, вызовите Test-CsSetupPermission управления.</span><span class="sxs-lookup"><span data-stu-id="d924a-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="d924a-124">Укажите различающейся имя проверяемого контейнера.</span><span class="sxs-lookup"><span data-stu-id="d924a-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="d924a-125">Например, эта команда проверяет разрешения на установку для контейнера ou=CsServers,dc=litwareinc,dc=com:</span><span class="sxs-lookup"><span data-stu-id="d924a-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="d924a-126">Дополнительные сведения см. в разделе справки по [cmdlet Test-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)</span><span class="sxs-lookup"><span data-stu-id="d924a-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d924a-127">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="d924a-127">Determining success or failure</span></span>

<span data-ttu-id="d924a-128">Если Test-CsSetupPermission, что необходимые разрешения уже установлены для контейнера Active Directory, то он возвращает значение True:</span><span class="sxs-lookup"><span data-stu-id="d924a-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="d924a-129">Верно</span><span class="sxs-lookup"><span data-stu-id="d924a-129">True</span></span> 

<span data-ttu-id="d924a-130">Если разрешения не за установлены, Test-CsSetupPermission возвращает значение False.</span><span class="sxs-lookup"><span data-stu-id="d924a-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="d924a-131">Обратите внимание, что это значение обычно заключено во множество предупреждений.</span><span class="sxs-lookup"><span data-stu-id="d924a-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="d924a-132">Пример:</span><span class="sxs-lookup"><span data-stu-id="d924a-132">For example:</span></span>

<span data-ttu-id="d924a-133">ПРЕДУПРЕЖДЕНИЕ: запись управления доступом (ACE) atl-cs-001\RTCUniversalServerAdmins; Разрешить; ExtendedRight; Нет; Нет; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="d924a-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="d924a-134">ПРЕДУПРЕЖДЕНИЕ. Элементы управления доступом (AES) в объекте "CN=Computers,DC=litwareinc,DC=com" не готовы.</span><span class="sxs-lookup"><span data-stu-id="d924a-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="d924a-135">Неверно</span><span class="sxs-lookup"><span data-stu-id="d924a-135">False</span></span> 

<span data-ttu-id="d924a-136">ПРЕДУПРЕЖДЕНИЕ: обработка Test-CsSetupPermission завершена с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="d924a-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="d924a-137">Во время этого запуска были записаны предупреждения "2".</span><span class="sxs-lookup"><span data-stu-id="d924a-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="d924a-138">ПРЕДУПРЕЖДЕНИЕ. Подробные результаты можно найти по C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html.</span><span class="sxs-lookup"><span data-stu-id="d924a-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d924a-139">Причины, по которым мог произойть сбой теста</span><span class="sxs-lookup"><span data-stu-id="d924a-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="d924a-140">Хотя существуют редкие исключения, Test-CsSetupPermission не удается, что обычно означает, что разрешения на установку не назначены для указанного контейнера Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d924a-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="d924a-141">Эти разрешения могут быть назначены с помощью Grant-CsSetupPermission управления.</span><span class="sxs-lookup"><span data-stu-id="d924a-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="d924a-142">Например, эта команда предоставляет разрешения на установку контейнеру Computers в домене litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="d924a-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="d924a-143">Дополнительные сведения см. в разделе справки по [cmdlet Test-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)</span><span class="sxs-lookup"><span data-stu-id="d924a-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
