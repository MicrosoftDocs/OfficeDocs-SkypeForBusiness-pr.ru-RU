---
title: Вопросы присоединения к домену системы комнат Skype
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
description: В этом разделе вы узнаете, как присоединить компьютер устройства системы комнат Skype к домену.
ms.openlocfilehash: 6d6decf689b1a38615851911b42676050a823e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805919"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="8f790-103">Вопросы присоединения к домену системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="8f790-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="8f790-104">В этом разделе вы узнаете, как присоединить компьютер устройства системы комнат Skype к домену.</span><span class="sxs-lookup"><span data-stu-id="8f790-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="8f790-105">Сведения о присоединении к домену</span><span class="sxs-lookup"><span data-stu-id="8f790-105">Domain joining considerations</span></span>

<span data-ttu-id="8f790-106">Компьютер устройства системы комнат Skype можно присоединить к домену Active Directory или оставить в группе.</span><span class="sxs-lookup"><span data-stu-id="8f790-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="8f790-107">Прежде чем принимать решение, рассмотрите следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="8f790-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="8f790-108">Присоединение к домену компьютера устройства системы комнат Skype помогает автоматически импортировать частную корневую цепочку сертификатов вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8f790-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="8f790-109">Присоединение к домену компьютера устройства системы комнат Skype позволяет предоставить пользователям домена и группам права администратора.</span><span class="sxs-lookup"><span data-stu-id="8f790-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="8f790-110">Таким образом, вам не придется запоминать пароль учетной записи администратора локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="8f790-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="8f790-111">При подстройке компьютера устройства системы комнат Skype к домену необходимо создать отдельное подразделение, чтобы можно было предоставлять исключения объектов групповой политики (GPO) подразделению, в котором находятся все объекты компьютера системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="8f790-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="8f790-112">В этом случае создайте объекты компьютера в этом OU перед присоединением компьютера устройства системы комнат Skype к домену.</span><span class="sxs-lookup"><span data-stu-id="8f790-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="8f790-113">Во многих организациях имеются следующие GOS, которые влияют на функции ПК системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="8f790-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="8f790-114">Убедитесь, что вы переопределяли или блокировали наследование этих GOS в OU системы комнат Skype:</span><span class="sxs-lookup"><span data-stu-id="8f790-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="8f790-115">Время аута сеансов для работы с логотипом (автоматическая блокировка)</span><span class="sxs-lookup"><span data-stu-id="8f790-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="8f790-116">Политики, связанные с управлением питанием</span><span class="sxs-lookup"><span data-stu-id="8f790-116">Power management related policies</span></span>
    
  - <span data-ttu-id="8f790-117">Требование дополнительных действий проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="8f790-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="8f790-118">Запрет доступа к локальным дискам</span><span class="sxs-lookup"><span data-stu-id="8f790-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="8f790-119">Запрос медленных сетевых подключений для пользователей</span><span class="sxs-lookup"><span data-stu-id="8f790-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="8f790-120">Запуск определенной программы при ее запуске</span><span class="sxs-lookup"><span data-stu-id="8f790-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="8f790-121">Создайте еще одну учетную запись пользователя домена на всех компьютерах, которые присоединились к домену.</span><span class="sxs-lookup"><span data-stu-id="8f790-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="8f790-122">Push Windows Update to Skype Room System</span><span class="sxs-lookup"><span data-stu-id="8f790-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="8f790-123">Кроме того, можно оставить компьютер устройства в группе.</span><span class="sxs-lookup"><span data-stu-id="8f790-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="8f790-124">Как и для настольного клиента Skype для бизнеса, для этого необходимо вручную импортировать корневую цепочку сертификатов на компьютер устройства системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="8f790-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="8f790-125">Импортировать корневую цепочку сертификатов не требуется, если в развертывании Skype для бизнеса используется общедоступный сертификат (например, "Пособная", "VeriSign" и так далее).</span><span class="sxs-lookup"><span data-stu-id="8f790-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="8f790-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span><span class="sxs-lookup"><span data-stu-id="8f790-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="8f790-127">Можно использовать следующий cmdlet с компьютера системы комнат Skype, чтобы присоединиться к правильному OU и не получать GOS, которые могут блокировать функции LRS.</span><span class="sxs-lookup"><span data-stu-id="8f790-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="8f790-128">Обратитесь к системным администраторам или партнерам по OEM, чтобы выполнить указанные ниже данные.</span><span class="sxs-lookup"><span data-stu-id="8f790-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="8f790-129">Даже при создании отдельного OU и блокировки наследования существуют некоторые политики, которые могут вызывать проблемы на более высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="8f790-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="8f790-130">Групповая политика без параметра переопределения обыгрывает OU с параметром наследования заблокированной политики.</span><span class="sxs-lookup"><span data-stu-id="8f790-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="8f790-131">Дополнительные сведения см. в статье No [Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span><span class="sxs-lookup"><span data-stu-id="8f790-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="8f790-132">У вас может быть несколько подходов к решению этих проблем.</span><span class="sxs-lookup"><span data-stu-id="8f790-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="8f790-133">Мы рекомендуем проконсультироваться со специалистами По Active Directory, чтобы убедиться, что у вас есть соответствующее параметров GPO или по крайней мере такое, в котором ранее описанные политики не существуют.</span><span class="sxs-lookup"><span data-stu-id="8f790-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="8f790-134">Рекомендуется включить качество обслуживания (QoS) для устройств системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="8f790-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f790-135">См. также</span><span class="sxs-lookup"><span data-stu-id="8f790-135">See also</span></span>
  
[<span data-ttu-id="8f790-136">Конфигурация устройств: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="8f790-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="8f790-137">Управление качеством обслуживания</span><span class="sxs-lookup"><span data-stu-id="8f790-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
