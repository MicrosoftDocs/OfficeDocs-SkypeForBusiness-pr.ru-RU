---
title: Тестирование прав топологии администратора в Skype для бизнеса Server
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
description: Проверка прав на топологию в Skype для бизнеса Server
ms.openlocfilehash: de2f5752bdcd9096a47595fd7ffd10a3ab799d9c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030152"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="e9456-103">Тестирование прав топологии администратора в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e9456-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="e9456-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="e9456-104">Verification schedule</span></span>|<span data-ttu-id="e9456-105">После первоначального развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e9456-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="e9456-106">При необходимости, если возникают проблемы, связанные с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="e9456-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="e9456-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="e9456-107">Testing tool</span></span>|<span data-ttu-id="e9456-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9456-108">Windows PowerShell</span></span>|
|<span data-ttu-id="e9456-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="e9456-109">Permissions required</span></span>|<span data-ttu-id="e9456-110">При локальном запуске с помощью командной консоли Skype для бизнеса Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e9456-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="e9456-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="e9456-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="e9456-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e9456-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="e9456-113">Get – CsAdminRole \| Where – Object {$ _. Командлеты-ПОИСКПОЗ "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="e9456-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="e9456-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e9456-114">Description</span></span>

<span data-ttu-id="e9456-115">По умолчанию только администраторы домена могут включать топологию сервера Skype для бизнеса Server и вносить значительные изменения в инфраструктуру Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e9456-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="e9456-116">Это не проблема, так как Администраторы домена и администраторы Skype для бизнеса Server относятся к одному и тому же.</span><span class="sxs-lookup"><span data-stu-id="e9456-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="e9456-117">Во многих организациях администраторы Skype для бизнеса Server не хранят права администратора для всего домена.</span><span class="sxs-lookup"><span data-stu-id="e9456-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="e9456-118">По умолчанию это означает, что эти администраторы (определенные как члены группы RTCUniversalServerAdmins) не могут выполнять изменения топологии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e9456-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="e9456-119">Чтобы предоставить членам группы RTCUniversalServerAdmins право на внесение изменений в топологию, необходимо назначить необходимые разрешения Active Directory с помощью командлета [Grant – CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="e9456-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="e9456-120">Командлет Test-CsSetupPermission проверяет, настроены ли необходимые разрешения, необходимые для установки Skype для бизнеса Server или одного из его компонентов, в указанном контейнере Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e9456-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="e9456-121">Если разрешения не назначены, можно запустить командлет Grant-CsSetupPermission, чтобы предоставить членам группы RTCUniversalServerAdmins право на установку и включение Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e9456-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="e9456-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="e9456-122">Running the test</span></span>

<span data-ttu-id="e9456-123">Чтобы определить, назначены ли разрешения на установку для контейнера Active Directory, вызовите командлет Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="e9456-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="e9456-124">Укажите различающееся имя контейнера, который необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="e9456-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="e9456-125">Например, эта команда проверяет разрешения программы установки для контейнера OU = Кссерверс, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="e9456-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="e9456-126">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="e9456-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e9456-127">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="e9456-127">Determining success or failure</span></span>

<span data-ttu-id="e9456-128">Если Test-CsSetupPermission определяет, что необходимые разрешения для контейнера Active Directory уже установлены, командлет вернет значение true:</span><span class="sxs-lookup"><span data-stu-id="e9456-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="e9456-129">Верно</span><span class="sxs-lookup"><span data-stu-id="e9456-129">True</span></span> 

<span data-ttu-id="e9456-130">Если разрешения не заданы, Test-CsSetupPermission будет возвращать значение false.</span><span class="sxs-lookup"><span data-stu-id="e9456-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="e9456-131">Обратите внимание, что это значение, как правило, будет заключено во множество предупреждающих сообщений.</span><span class="sxs-lookup"><span data-stu-id="e9456-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="e9456-132">Пример:</span><span class="sxs-lookup"><span data-stu-id="e9456-132">For example:</span></span>

<span data-ttu-id="e9456-133">Предупреждение: элемент управления доступом (ACE) atl-cs-001\RTCUniversalServerAdmins; Разрешить Екстендедригхт; Видим Видим 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="e9456-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="e9456-134">Предупреждение: записи управления доступом (ACE) для объекта "CN = Computers, DC = litwareinc, DC = com" не готовы.</span><span class="sxs-lookup"><span data-stu-id="e9456-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="e9456-135">False</span><span class="sxs-lookup"><span data-stu-id="e9456-135">False</span></span> 

<span data-ttu-id="e9456-136">Предупреждение: "Test-CsSetupPermission" обработка завершена с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="e9456-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="e9456-137">во время этого запуска было записано предупреждение 2.</span><span class="sxs-lookup"><span data-stu-id="e9456-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="e9456-138">Предупреждение: подробные результаты можно найти по адресу "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span><span class="sxs-lookup"><span data-stu-id="e9456-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e9456-139">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="e9456-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="e9456-140">Несмотря на то, что в Test-CsSetupPermission возникает редкие исключения, которые обычно означают, что разрешения программы установки для указанного контейнера Active Directory не назначены.</span><span class="sxs-lookup"><span data-stu-id="e9456-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="e9456-141">Эти разрешения могут быть назначены с помощью командлета Grant – CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="e9456-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="e9456-142">Например, эта команда предоставляет разрешения на установку контейнера Computers в домене litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="e9456-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="e9456-143">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="e9456-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
