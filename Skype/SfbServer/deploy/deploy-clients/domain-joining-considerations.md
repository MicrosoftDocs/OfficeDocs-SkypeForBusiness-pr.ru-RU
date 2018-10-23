---
title: Рекомендации по присоединению к домену для системы комнат Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: В этом разделе описывается присоединение к домену ПК с системой комнат Skype.
ms.openlocfilehash: 3a457e73b3509967043b1ef11d1e5017f2190434
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699597"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="02192-103">Рекомендации по присоединению к домену для системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="02192-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="02192-104">В этом разделе описывается присоединение к домену ПК с системой комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="02192-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="02192-105">Рекомендации по присоединению к домену</span><span class="sxs-lookup"><span data-stu-id="02192-105">Domain joining considerations</span></span>

<span data-ttu-id="02192-106">Можно присоединиться к appliance системы комнаты Скайп ПК в домен Active Directory или оставьте его в рабочую группу.</span><span class="sxs-lookup"><span data-stu-id="02192-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="02192-107">Consider the following points before making this decision:</span><span class="sxs-lookup"><span data-stu-id="02192-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="02192-108">Присоединение домена appliance системы комнаты Скайп ПК позволяет автоматически Импорт цепочки сертификатов частный корневой вашей организации.</span><span class="sxs-lookup"><span data-stu-id="02192-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="02192-109">Присоединение домена appliance системы комнаты Скайп ПК позволяет предоставить административные права групп и пользователей домена.</span><span class="sxs-lookup"><span data-stu-id="02192-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="02192-110">By doing so, you will not have to remember the local machine level administrator account password.</span><span class="sxs-lookup"><span data-stu-id="02192-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="02192-111">При подключении устройства системы комнаты Скайп ПК к домену, это необходимо создать отдельные организационному подразделению (OU), таким образом, можно обеспечить исключения для объекта групповой политики (GPO) для Подразделения, в которой размещаются все объекты Скайп комнаты системы компьютера.</span><span class="sxs-lookup"><span data-stu-id="02192-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="02192-112">При этом создание объектов компьютера в Подразделении перед присоединением appliance системы комнаты Скайп ПК к домену.</span><span class="sxs-lookup"><span data-stu-id="02192-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="02192-113">Многие организации имеют следующие объекты групповой политики, которые могут повлиять на системные комнаты Скайп appliance ПК функции.</span><span class="sxs-lookup"><span data-stu-id="02192-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="02192-114">Убедитесь, что переопределить или блокировка наследования эти объекты групповой политики в Подразделении Скайп комнаты системы:</span><span class="sxs-lookup"><span data-stu-id="02192-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="02192-115">Время ожидания для сеансов входа (автоматическая блокировка)</span><span class="sxs-lookup"><span data-stu-id="02192-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="02192-116">Политики, связанные с управлением питанием</span><span class="sxs-lookup"><span data-stu-id="02192-116">Power management related policies</span></span>
    
  - <span data-ttu-id="02192-117">Необходимость дополнительных действий для проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="02192-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="02192-118">Отказ в доступе к локальным дискам</span><span class="sxs-lookup"><span data-stu-id="02192-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="02192-119">Отображение подсказок при низкой скорости сетевого подключения</span><span class="sxs-lookup"><span data-stu-id="02192-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="02192-120">Запуск определенной программы при входе</span><span class="sxs-lookup"><span data-stu-id="02192-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="02192-121">Создание еще одной учетной записи пользователя домена на всех компьютерах, присоединенных к домену</span><span class="sxs-lookup"><span data-stu-id="02192-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="02192-122">Push-комнаты Скайп системе центра обновления Windows</span><span class="sxs-lookup"><span data-stu-id="02192-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="02192-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span><span class="sxs-lookup"><span data-stu-id="02192-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="02192-124">Как на рабочий стол Скайп для клиента Business этого необходимо вручную Импорт цепочки корневого сертификата на устройстве системы комнаты Скайп ПК.</span><span class="sxs-lookup"><span data-stu-id="02192-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="02192-125">В случае не требуется импортировать цепочки сертификатов корневого, если ваше Скайп по развертыванию использует общедоступный сертификат (например, Entrust VeriSign и т. п.).</span><span class="sxs-lookup"><span data-stu-id="02192-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="02192-126">Если вы планируете присоединение к домену машины Скайп комнаты системы, во избежание соединение Скайп комнаты системы компьютера случайно to случайных Подразделения, которая не может быть от объектов групповой политики, убедитесь, что присоединиться к правильный Подразделения.</span><span class="sxs-lookup"><span data-stu-id="02192-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="02192-127">Можно использовать следующий командлет с компьютера Скайп комнаты системы для присоединения к правильный подразделения и не получает объекты групповой политики, которые могут блокировать LRS функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="02192-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="02192-128">Contact your system administrator or OEM partner to run these cmdlet:</span><span class="sxs-lookup"><span data-stu-id="02192-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="02192-129">Даже если создано отдельное подразделение и наследование заблокировано, некоторые политики могут привести к возникновению проблем на более высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="02192-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="02192-130">Групповая политика с параметром "Без переопределения" имеет приоритет над подразделением с параметром блокировки наследования политики.</span><span class="sxs-lookup"><span data-stu-id="02192-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="02192-131">Для получения дополнительных сведений обратитесь к статье, [Не перекрывать по сравнению с блокировать наследование политики](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) в документации по групповой политики.</span><span class="sxs-lookup"><span data-stu-id="02192-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="02192-132">You may have multiple approaches to solving these problems.</span><span class="sxs-lookup"><span data-stu-id="02192-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="02192-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span><span class="sxs-lookup"><span data-stu-id="02192-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="02192-134">Рекомендуется включить качество обслуживания (QoS) для устройств Скайп комнаты системы.</span><span class="sxs-lookup"><span data-stu-id="02192-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="02192-135">См. также</span><span class="sxs-lookup"><span data-stu-id="02192-135">See also</span></span>
  
[<span data-ttu-id="02192-136">Конфигурация устройств: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="02192-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="02192-137">Управление качеством обслуживания</span><span class="sxs-lookup"><span data-stu-id="02192-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
