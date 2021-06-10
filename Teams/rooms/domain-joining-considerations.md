---
title: Рекомендации по присоединению к домену для системы комнат Skype
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: Администратор может узнать, как присоединиться к компьютеру с устройством Skype Room System в домен Active Directory, а также о том, как это сделать.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117557"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="7ea25-103">Рекомендации по присоединению к домену для системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="7ea25-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="7ea25-104">В этом разделе описывается присоединение к домену ПК с системой комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="7ea25-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="7ea25-105">Рекомендации по присоединению к домену</span><span class="sxs-lookup"><span data-stu-id="7ea25-105">Domain joining considerations</span></span>

<span data-ttu-id="7ea25-106">Вы можете присоединиться к Skype компьютера-устройства Room System к домену Active Directory или оставить его в группе.</span><span class="sxs-lookup"><span data-stu-id="7ea25-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="7ea25-107">Consider the following points before making this decision:</span><span class="sxs-lookup"><span data-stu-id="7ea25-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="7ea25-108">Присоединение домена к компьютеру с устройством Skype Room System помогает автоматически импортировать цепочку частных корневых сертификатов вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7ea25-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="7ea25-109">Присоединение домена к компьютеру Skype Room System позволяет предоставлять пользователям домена и группам права администратора.</span><span class="sxs-lookup"><span data-stu-id="7ea25-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="7ea25-110">By doing so, you will not have to remember the local machine level administrator account password.</span><span class="sxs-lookup"><span data-stu-id="7ea25-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="7ea25-111">Когда вы присоединяете к домену устройство Skype Room System, необходимо создать отдельное подразделение, чтобы исключить объект групповой политики (GPO) в подразделении, где находятся все объекты Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="7ea25-111">When you join a Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="7ea25-112">При этом создавайте объекты в ОУ, прежде чем присоединяться к Skype устройства Room System к домену.</span><span class="sxs-lookup"><span data-stu-id="7ea25-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="7ea25-113">Во многих организациях есть следующие GOS, которые влияют на Skype устройства для компьютера с комнатами.</span><span class="sxs-lookup"><span data-stu-id="7ea25-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="7ea25-114">Переопределять или блокировать наследование этих GOS в Skype Room System OU:</span><span class="sxs-lookup"><span data-stu-id="7ea25-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="7ea25-115">Время ожидания для сеансов входа (автоматическая блокировка)</span><span class="sxs-lookup"><span data-stu-id="7ea25-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="7ea25-116">Политики, связанные с управлением питанием</span><span class="sxs-lookup"><span data-stu-id="7ea25-116">Policies related to power management</span></span>
  - <span data-ttu-id="7ea25-117">Необходимость дополнительных действий для проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="7ea25-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="7ea25-118">Отказ в доступе к локальным дискам</span><span class="sxs-lookup"><span data-stu-id="7ea25-118">Denying access to local drives</span></span>
  - <span data-ttu-id="7ea25-119">Отображение подсказок при низкой скорости сетевого подключения</span><span class="sxs-lookup"><span data-stu-id="7ea25-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="7ea25-120">Запуск определенной программы при входе</span><span class="sxs-lookup"><span data-stu-id="7ea25-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="7ea25-121">Создание еще одной учетной записи пользователя домена на всех компьютерах, присоединенных к домену</span><span class="sxs-lookup"><span data-stu-id="7ea25-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="7ea25-122">Push-Windows обновления для Skype комнаты</span><span class="sxs-lookup"><span data-stu-id="7ea25-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="7ea25-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span><span class="sxs-lookup"><span data-stu-id="7ea25-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="7ea25-124">Как и в клиенте Microsoft Teams или Skype для бизнеса, необходимо вручную импортировать корневую цепочку сертификатов на компьютере с устройством Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="7ea25-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="7ea25-125">Вам не нужно импортировать корневую цепочку сертификатов, если в развертывании используется общедоступный сертификат (например, Заверять, VeriSign и другие).</span><span class="sxs-lookup"><span data-stu-id="7ea25-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="7ea25-126">Если вы планируете присоединиться к домену компьютеры Skype Room System, чтобы избежать случайного присоединения компьютера Skype Room System к случайному агенту, который может быть недоступен в GOS, убедитесь, что вы присоединились к правильному OU.</span><span class="sxs-lookup"><span data-stu-id="7ea25-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="7ea25-127">Вы можете использовать следующий Skype-компьютер с системой комнат, чтобы присоединиться к правильному проекту и не получать GGPOs, которые могут блокировать функции LRS.</span><span class="sxs-lookup"><span data-stu-id="7ea25-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="7ea25-128">Обратитесь к системного администратора или партнеру OEM, чтобы выполнить эти cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7ea25-128">Contact your system administrator or OEM partner to run these cmdlets:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="7ea25-129">Даже если вы создаете отдельное ОО и блокируете наследование, существуют некоторые политики, которые могут вызывать проблемы более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="7ea25-129">Even if you create a separate OU and block inheritance, there are some policies that could cause issues at a higher level.</span></span> <span data-ttu-id="7ea25-130">Групповая политика с параметром "Без переопределения" имеет приоритет над подразделением с параметром блокировки наследования политики.</span><span class="sxs-lookup"><span data-stu-id="7ea25-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="7ea25-131">Дополнительные сведения см. в [документе Групповая](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) политика без переопределения по сравнению с наследованием блокирования политики.</span><span class="sxs-lookup"><span data-stu-id="7ea25-131">For more information, see [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="7ea25-132">You may have multiple approaches to solving these problems.</span><span class="sxs-lookup"><span data-stu-id="7ea25-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="7ea25-133">Мы советуем обратиться к экспертам Active Directory, чтобы убедиться, что у вас есть ОО, у которого есть соответствующие параметры GPO, или по крайней мере один из них, в котором ранее описанные политики не существуют.</span><span class="sxs-lookup"><span data-stu-id="7ea25-133">We advise you to consult with your Active Directory experts to ensure that you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="7ea25-134">Мы советуем обеспечить качество обслуживания (QoS) для Skype система комнат.</span><span class="sxs-lookup"><span data-stu-id="7ea25-134">We advise to enabling Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7ea25-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7ea25-135">Related topics</span></span>
  
[<span data-ttu-id="7ea25-136">Конфигурация устройств: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="7ea25-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="7ea25-137">Управление качеством обслуживания</span><span class="sxs-lookup"><span data-stu-id="7ea25-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)