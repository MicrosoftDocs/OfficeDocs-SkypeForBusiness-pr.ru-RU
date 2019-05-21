---
title: Рекомендации по присоединению к домену для системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: В этом разделе описывается присоединение к домену ПК с системой комнат Skype.
ms.openlocfilehash: 934b39a0375085e9b8c18022a4526c76a970aca9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293615"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="18f0a-103">Рекомендации по присоединению к домену для системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="18f0a-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="18f0a-104">В этом разделе описывается присоединение к домену ПК с системой комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="18f0a-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="18f0a-105">Рекомендации по присоединению к домену</span><span class="sxs-lookup"><span data-stu-id="18f0a-105">Domain joining considerations</span></span>

<span data-ttu-id="18f0a-106">Вы можете присоединиться к компьютеру управляющего устройства Skype Rooms в домен Active Directory или оставить его в Рабочей группе.</span><span class="sxs-lookup"><span data-stu-id="18f0a-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="18f0a-107">Consider the following points before making this decision:</span><span class="sxs-lookup"><span data-stu-id="18f0a-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="18f0a-108">Домен: присоединение к компьютеру управляющего устройства в системе комнат Skype поможет вам импортировать цепочку сертификатов частной корневой папки организации автоматически.</span><span class="sxs-lookup"><span data-stu-id="18f0a-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="18f0a-109">Domain (подключение к домену). присоединение к компьютеру управляющего устройства из комнаты Skype позволяет предоставить пользователям домена и группам права администратора.</span><span class="sxs-lookup"><span data-stu-id="18f0a-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="18f0a-110">By doing so, you will not have to remember the local machine level administrator account password.</span><span class="sxs-lookup"><span data-stu-id="18f0a-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="18f0a-111">Когда вы присоединяетесь к домену системное устройство для помещения в Skype на компьютер, необходимо создать отдельное подразделение (OU), чтобы вы могли предоставлять исключения объектов групповой политики (GPO) для подразделения, где находятся все объекты компьютера, на котором установлена система Skype для комнаты.</span><span class="sxs-lookup"><span data-stu-id="18f0a-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="18f0a-112">После этого создайте объекты компьютера в подразделении, прежде чем присоединиться к домену с помощью устройства управления системой комнаты для помещения Skype на компьютер.</span><span class="sxs-lookup"><span data-stu-id="18f0a-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="18f0a-113">Во многих организациях есть следующие объекты групповой политики, которые влияют на функции ПК в системе управления комнатой Skype.</span><span class="sxs-lookup"><span data-stu-id="18f0a-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="18f0a-114">Убедитесь, что вы переопределяете или блокируете наследование этих GPO в подразделении системы помещения в Skype.</span><span class="sxs-lookup"><span data-stu-id="18f0a-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="18f0a-115">Время ожидания для сеансов входа (автоматическая блокировка)</span><span class="sxs-lookup"><span data-stu-id="18f0a-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="18f0a-116">Политики, связанные с управлением питанием</span><span class="sxs-lookup"><span data-stu-id="18f0a-116">Power management related policies</span></span>
    
  - <span data-ttu-id="18f0a-117">Необходимость дополнительных действий для проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="18f0a-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="18f0a-118">Отказ в доступе к локальным дискам</span><span class="sxs-lookup"><span data-stu-id="18f0a-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="18f0a-119">Отображение подсказок при низкой скорости сетевого подключения</span><span class="sxs-lookup"><span data-stu-id="18f0a-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="18f0a-120">Запуск определенной программы при входе</span><span class="sxs-lookup"><span data-stu-id="18f0a-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="18f0a-121">Создание еще одной учетной записи пользователя домена на всех компьютерах, присоединенных к домену</span><span class="sxs-lookup"><span data-stu-id="18f0a-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="18f0a-122">Принудительное обновление Windows для системы помещения в Skype</span><span class="sxs-lookup"><span data-stu-id="18f0a-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="18f0a-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span><span class="sxs-lookup"><span data-stu-id="18f0a-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="18f0a-124">Как и в клиенте Skype для бизнеса для настольных компьютеров, для этого требуется вручную импортировать цепочку корневых сертификатов на устройстве с устройством системы комнатной помощи Skype.</span><span class="sxs-lookup"><span data-stu-id="18f0a-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="18f0a-125">Если развертывание Skype для бизнеса использует общедоступный сертификат (например, Ентруст, VeriSign и т. д.), вам не нужно импортировать корневую цепочку сертификатов.</span><span class="sxs-lookup"><span data-stu-id="18f0a-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="18f0a-126">Если вы планируете присоединиться к домену с системными машинами Skype, не присоединяясь к системным машинам Skype на непреднамеренном подразделении, не подключаясь к ним, убедитесь, что вы присоединитесь к нужному подразделению.</span><span class="sxs-lookup"><span data-stu-id="18f0a-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="18f0a-127">Вы можете использовать следующий командлет с компьютера, на котором есть система для помещения Skype, чтобы присоединиться в подходящую подразделении и не получал ни одной политики, которая может блокировать функцию ЛРС.</span><span class="sxs-lookup"><span data-stu-id="18f0a-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="18f0a-128">Contact your system administrator or OEM partner to run these cmdlet:</span><span class="sxs-lookup"><span data-stu-id="18f0a-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="18f0a-129">Даже если создано отдельное подразделение и наследование заблокировано, некоторые политики могут привести к возникновению проблем на более высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="18f0a-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="18f0a-130">Групповая политика с параметром "Без переопределения" имеет приоритет над подразделением с параметром блокировки наследования политики.</span><span class="sxs-lookup"><span data-stu-id="18f0a-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="18f0a-131">Дополнительные сведения можно найти в статье " [не перекрывать" в соответствии с блокированием наследования политик](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) в документации по групповой политике.</span><span class="sxs-lookup"><span data-stu-id="18f0a-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="18f0a-132">You may have multiple approaches to solving these problems.</span><span class="sxs-lookup"><span data-stu-id="18f0a-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="18f0a-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span><span class="sxs-lookup"><span data-stu-id="18f0a-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="18f0a-134">Рекомендуется включить качество обслуживания (QoS) для системных устройств Skype для комнаты.</span><span class="sxs-lookup"><span data-stu-id="18f0a-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="18f0a-135">См. также</span><span class="sxs-lookup"><span data-stu-id="18f0a-135">See also</span></span>
  
[<span data-ttu-id="18f0a-136">Конфигурация устройств: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="18f0a-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="18f0a-137">Управление качеством обслуживания</span><span class="sxs-lookup"><span data-stu-id="18f0a-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
