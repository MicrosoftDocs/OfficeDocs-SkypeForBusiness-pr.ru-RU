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
description: Администратор может узнать о том, как присоединиться к устройству с устройством системы комнат Skype в домене Active Directory, а также о том, как это сделать.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfcee1421c25903a5ec8deb2f66871ed1d57ef1c
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905441"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="a2dc7-103">Рекомендации по присоединению к домену для системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="a2dc7-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="a2dc7-104">В этом разделе описывается присоединение к домену ПК с системой комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="a2dc7-105">Рекомендации по присоединению к домену</span><span class="sxs-lookup"><span data-stu-id="a2dc7-105">Domain joining considerations</span></span>

<span data-ttu-id="a2dc7-106">Вы можете присоединиться к домену Active Directory с помощью устройства Skype Room System или оставить его в "Workgroup".</span><span class="sxs-lookup"><span data-stu-id="a2dc7-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="a2dc7-107">Consider the following points before making this decision:</span><span class="sxs-lookup"><span data-stu-id="a2dc7-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="a2dc7-108">Присоединение домена к компьютеру-устройству Skype Room System помогает автоматически импортировать цепочку частных корневых сертификатов вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="a2dc7-109">Присоединение домена к компьютеру-устройству Skype Room System позволяет предоставлять пользователям домена и группам права администратора.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="a2dc7-110">By doing so, you will not have to remember the local machine level administrator account password.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="a2dc7-111">Когда вы присоединяете к домену устройство системы комнат Skype, необходимо создать отдельный подразделение, чтобы исключить объект групповой политики (GPO) в подразделении, где находятся все объекты системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="a2dc7-112">При этом создавайте объекты компьютера в системе управления объектами, прежде чем присоединяться к устройству системы комнат Skype в домене.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="a2dc7-113">Во многих организациях есть следующие GOS, которые влияют на функции устройства Скайп-комнатной системы.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="a2dc7-114">Переопределять или блокировать наследование этих GGPOs в системе комнат Skype:</span><span class="sxs-lookup"><span data-stu-id="a2dc7-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="a2dc7-115">Время ожидания для сеансов входа (автоматическая блокировка)</span><span class="sxs-lookup"><span data-stu-id="a2dc7-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="a2dc7-116">Политики, связанные с управлением питанием</span><span class="sxs-lookup"><span data-stu-id="a2dc7-116">Power management related policies</span></span>
  - <span data-ttu-id="a2dc7-117">Необходимость дополнительных действий для проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a2dc7-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="a2dc7-118">Отказ в доступе к локальным дискам</span><span class="sxs-lookup"><span data-stu-id="a2dc7-118">Denying access to local drives</span></span>
  - <span data-ttu-id="a2dc7-119">Отображение подсказок при низкой скорости сетевого подключения</span><span class="sxs-lookup"><span data-stu-id="a2dc7-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="a2dc7-120">Запуск определенной программы при входе</span><span class="sxs-lookup"><span data-stu-id="a2dc7-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="a2dc7-121">Создание еще одной учетной записи пользователя домена на всех компьютерах, присоединенных к домену</span><span class="sxs-lookup"><span data-stu-id="a2dc7-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="a2dc7-122">Push-обновление Windows до Skype Room System</span><span class="sxs-lookup"><span data-stu-id="a2dc7-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="a2dc7-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="a2dc7-124">Как и в клиенте Для настольных систем Microsoft Teams или Skype для бизнеса, вам необходимо вручную импортировать корневую цепочку сертификатов на компьютере с устройством Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="a2dc7-125">Вам не нужно импортировать корневую цепочку сертификатов, если в развертывании используется общедоступный сертификат (например, "Доверить", "VeriSign" и другие).</span><span class="sxs-lookup"><span data-stu-id="a2dc7-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="a2dc7-126">Если вы планируете присоединить компьютеры с комнатами Skype в домене, чтобы избежать случайного присоединения к системным помещениям Skype для непредусмотренного OU, который может быть недоступен для GOS, убедитесь, что вы присоединились к правильному OU.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="a2dc7-127">Вы можете использовать следующий cmdlet с компьютера Skype Room System, чтобы присоединиться к правильному OU и не получать GOS, которые могут блокировать функции LRS.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="a2dc7-128">Contact your system administrator or OEM partner to run these cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a2dc7-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="a2dc7-129">Даже если создано отдельное подразделение и наследование заблокировано, некоторые политики могут привести к возникновению проблем на более высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="a2dc7-130">Групповая политика с параметром "Без переопределения" имеет приоритет над подразделением с параметром блокировки наследования политики.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="a2dc7-131">Дополнительные сведения см. в статье ["Сравнение](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) с наследованием политик блокировки" в документации групповой политики.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="a2dc7-132">You may have multiple approaches to solving these problems.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="a2dc7-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="a2dc7-134">Рекомендуется включить качество обслуживания (QoS) для устройств с системой комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="a2dc7-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2dc7-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a2dc7-135">Related topics</span></span>
  
[<span data-ttu-id="a2dc7-136">Конфигурация устройств: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="a2dc7-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="a2dc7-137">Управление качеством обслуживания</span><span class="sxs-lookup"><span data-stu-id="a2dc7-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
