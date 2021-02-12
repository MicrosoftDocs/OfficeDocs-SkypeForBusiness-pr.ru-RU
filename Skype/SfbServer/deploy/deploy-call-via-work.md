---
title: Развертывание вызова с помощью работы в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: Сводка. Узнайте, как развернуть call Via Work в Skype для бизнеса Server для некоторых или всех пользователей.
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825009"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="dc0b6-103">Развертывание вызова с помощью работы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="dc0b6-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="dc0b6-104">**Сводка:** Узнайте, как развернуть call Via Work в Skype для бизнеса Server для некоторых или всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="dc0b6-105">Используйте эти действия для развертывания call Via Work для пользователей.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="dc0b6-106">Вопросы планирования обсуждаются в плане ["Позвонить с работы" в Skype для бизнеса Server.](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)</span><span class="sxs-lookup"><span data-stu-id="dc0b6-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="dc0b6-107">В предыдущих версиях удаленного управления вызовами Lync Server была возможностью, которая позволяла пользователям управлять телефонами УАЦ с помощью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="dc0b6-108">В Skype для бизнеса Server эта функция заменена функцией "Позвонить с работы".</span><span class="sxs-lookup"><span data-stu-id="dc0b6-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="dc0b6-109">Необходимые условия для вызова с помощью работы</span><span class="sxs-lookup"><span data-stu-id="dc0b6-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="dc0b6-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Server.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="dc0b6-111">Чтобы включить для пользователей возможность "Позвонить с помощью работы", необходимо также иметь следующие необходимые условия:</span><span class="sxs-lookup"><span data-stu-id="dc0b6-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="dc0b6-112">Сервер-посредник должен быть развернут как в составе сервера переднего плана, так и в качестве автономных ролей.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="dc0b6-113">Необходимо также развернуть шлюз IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="dc0b6-114">Все пользователи, которым будет включена возможность вызова с помощью работы, должны иметь прямой включаемой набор (DID) в телефонной системе УАЙЛ.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="dc0b6-115">Необходимо включить для всех пользователей call Via Work Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="dc0b6-116">При этом необходимо настроить для каждого пользователя номер DID Skype для бизнеса на соответствующий номер DID для соответствующей телефонной системы УАТС.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="dc0b6-117">Для всех пользователей, которые будут  использовать функцию "Позвонить с работы", в клиенте Skype для бизнеса должна быть выбрана автоматическая настройка дополнительных подключений. </span><span class="sxs-lookup"><span data-stu-id="dc0b6-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="dc0b6-118">Это позволяет клиенту обнаружить URL-адреса UCWA.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="dc0b6-119">**Автоматическая настройка** — это выбор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="dc0b6-120">Для каждого пользователя «Позвонить с помощью работы».</span><span class="sxs-lookup"><span data-stu-id="dc0b6-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="dc0b6-121">Убедитесь, что для каждого пользователя "Позвонить с помощью работы" включена возможность телефонного и телефонного звонка.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="dc0b6-122">Это позволяет этим пользователям получать доступ к конференциям Skype для бизнеса и выход из них.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="dc0b6-123">Убедитесь, что делегирования, групповые вызовы и группы ответа отключены для каждого пользователя "Позвонить с работы".</span><span class="sxs-lookup"><span data-stu-id="dc0b6-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="dc0b6-124">Развертывание функции вызовов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="dc0b6-124">Deploy Call Via Work</span></span>

<span data-ttu-id="dc0b6-125">После создания необходимых условий сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="dc0b6-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="dc0b6-126">Создайте глобальный номер телефона для развертывания, который Skype для бизнеса отображает в ИД вызываемого УАТБ пользователя, который звонит с помощью работы.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="dc0b6-127">Создание одной или более политик "Позвонить с помощью работы"</span><span class="sxs-lookup"><span data-stu-id="dc0b6-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="dc0b6-128">Назначение политики "Позвонить с помощью работы" каждому пользователю, для которого будет включена возможность вызова с помощью работы</span><span class="sxs-lookup"><span data-stu-id="dc0b6-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="dc0b6-129">Создание глобального номера телефона "Позвонить с помощью работы"</span><span class="sxs-lookup"><span data-stu-id="dc0b6-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="dc0b6-130">Введите следующий cmdlet</span><span class="sxs-lookup"><span data-stu-id="dc0b6-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="dc0b6-131">Например, следующий cmdlet задает глобальный номер телефона 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="dc0b6-132">Создание политики "Позвонить с помощью работы"</span><span class="sxs-lookup"><span data-stu-id="dc0b6-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="dc0b6-133">Введите следующий cmdlet</span><span class="sxs-lookup"><span data-stu-id="dc0b6-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="dc0b6-134">Например, следующий cmdlet создает политику call Via Work под названием ContosoUser1CvWP, требует от пользователя использования номера вызова администратора и устанавливает для этого номера вызова 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="dc0b6-135">Назначение пользователю политики "Позвонить с помощью работы"</span><span class="sxs-lookup"><span data-stu-id="dc0b6-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="dc0b6-136">Введите следующий cmdlet</span><span class="sxs-lookup"><span data-stu-id="dc0b6-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="dc0b6-137">Например, следующий cmdlet назначает политику Call Via Work "ContosoUser1CvWP" пользователю с именем **ContosoUser1.**</span><span class="sxs-lookup"><span data-stu-id="dc0b6-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="dc0b6-138">См. также</span><span class="sxs-lookup"><span data-stu-id="dc0b6-138">See also</span></span>

[<span data-ttu-id="dc0b6-139">Планирование звонков с помощью работы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="dc0b6-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

