---
title: Вопросы присоединения к домену Системы номеров Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Ознакомьтесь с этой темой, чтобы узнать, как присоединиться к компьютеру устройства skype Room System к вашему домену.
ms.openlocfilehash: cf98f98a7294ead0920b3d6b07b00879cbfe15f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093573"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="8883e-103">Вопросы присоединения к домену Системы номеров Skype</span><span class="sxs-lookup"><span data-stu-id="8883e-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="8883e-104">Ознакомьтесь с этой темой, чтобы узнать, как присоединиться к компьютеру устройства skype Room System к вашему домену.</span><span class="sxs-lookup"><span data-stu-id="8883e-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="8883e-105">Сведения о присоединении к домену</span><span class="sxs-lookup"><span data-stu-id="8883e-105">Domain joining considerations</span></span>

<span data-ttu-id="8883e-106">Вы можете присоединиться к компьютеру устройства Skype Room System к домену Active Directory или оставить его в workgroup.</span><span class="sxs-lookup"><span data-stu-id="8883e-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="8883e-107">Перед принятием этого решения рассмотрите следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="8883e-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="8883e-108">Присоединение домена к компьютеру устройства skype Room System помогает автоматически импортировать частную корневую цепочку сертификатов организации.</span><span class="sxs-lookup"><span data-stu-id="8883e-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="8883e-109">Присоединение домена к компьютеру устройства Skype Room System позволяет предоставлять пользователям домена и группам административные права.</span><span class="sxs-lookup"><span data-stu-id="8883e-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="8883e-110">Таким образом, вам не придется запоминать пароль учетной записи администратора локального уровня компьютера.</span><span class="sxs-lookup"><span data-stu-id="8883e-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="8883e-111">При подстройке компьютера-устройства Skype Room System к домену необходимо создать отдельное организационное подразделение (OU), чтобы вы могли предоставлять исключения объектов групповой политики (GPO) в OU, где находятся все объекты системы номеров Skype.</span><span class="sxs-lookup"><span data-stu-id="8883e-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="8883e-112">При этом создайте машинные объекты в OU перед присоединением к домену компьютера устройства Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="8883e-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="8883e-113">Во многих организациях имеются следующие GPOs, которые влияют на функции ПК устройства Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="8883e-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="8883e-114">Убедитесь, что вы переопределяют или блокируете наследование этих GPOs в OU системы номеров Skype:</span><span class="sxs-lookup"><span data-stu-id="8883e-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="8883e-115">Периодику сеансов логотипа (автоматическая блокировка)</span><span class="sxs-lookup"><span data-stu-id="8883e-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="8883e-116">Политики управления питанием</span><span class="sxs-lookup"><span data-stu-id="8883e-116">Power management related policies</span></span>
    
  - <span data-ttu-id="8883e-117">Требуются дополнительные действия проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="8883e-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="8883e-118">Отказ в доступе к локальным дискам</span><span class="sxs-lookup"><span data-stu-id="8883e-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="8883e-119">Запрос пользователей для медленных подключений к сети</span><span class="sxs-lookup"><span data-stu-id="8883e-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="8883e-120">Запуск определенной программы в logon</span><span class="sxs-lookup"><span data-stu-id="8883e-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="8883e-121">Создайте другую учетную запись пользователя домена на всех компьютерах, присоединив к домену.</span><span class="sxs-lookup"><span data-stu-id="8883e-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="8883e-122">Push Windows Update to Skype Room System</span><span class="sxs-lookup"><span data-stu-id="8883e-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="8883e-123">Кроме того, вы можете оставить компьютер устройства в группе.</span><span class="sxs-lookup"><span data-stu-id="8883e-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="8883e-124">Как и для настольного клиента Skype для бизнеса, для этого необходимо вручную импортировать корневую цепочку сертификатов на компьютере устройства Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="8883e-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="8883e-125">Импорт корневой цепочки сертификатов не требуется, если развертывание Skype для бизнеса использует общедоступный сертификат (например, Entrust, VeriSign и так далее).</span><span class="sxs-lookup"><span data-stu-id="8883e-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="8883e-126">Если вы планируете присоединиться к компьютерам системы skype Room System к домену, чтобы избежать случайного присоединения к компьютеру Skype Room System к непреднамеренным OU, который может быть не свободен от GPOs, убедитесь, что вы присоединитесь к правильному OU.</span><span class="sxs-lookup"><span data-stu-id="8883e-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="8883e-127">Чтобы присоединиться к правильному OU, можно использовать следующий cmdlet из машины Skype Room System и не получать GPOs, которые могут блокировать функции LRS.</span><span class="sxs-lookup"><span data-stu-id="8883e-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="8883e-128">Свяжитесь с системным администратором или партнером OEM для запуска этих групп:</span><span class="sxs-lookup"><span data-stu-id="8883e-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="8883e-129">Даже если вы создаете отдельный OU и блокируете наследование, существуют политики, которые могут вызвать проблемы на более высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="8883e-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="8883e-130">Групповая политика без параметра Переопределения бьет OU с параметром Наследования политик блока.</span><span class="sxs-lookup"><span data-stu-id="8883e-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="8883e-131">Дополнительные сведения см. в статье [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span><span class="sxs-lookup"><span data-stu-id="8883e-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="8883e-132">У вас может быть несколько подходов к решению этих проблем.</span><span class="sxs-lookup"><span data-stu-id="8883e-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="8883e-133">Мы советуем вам проконсультироваться со специалистами Active Directory, чтобы убедиться, что у вас есть соответствующие параметры GPO или, по крайней мере, OU, в котором ранее описанные политики не существуют.</span><span class="sxs-lookup"><span data-stu-id="8883e-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="8883e-134">Рекомендуется включить службы качества (QoS) для устройств Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="8883e-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="8883e-135">См. также</span><span class="sxs-lookup"><span data-stu-id="8883e-135">See also</span></span>
  
[<span data-ttu-id="8883e-136">Конфигурация устройств: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="8883e-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="8883e-137">Управление качеством обслуживания</span><span class="sxs-lookup"><span data-stu-id="8883e-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)