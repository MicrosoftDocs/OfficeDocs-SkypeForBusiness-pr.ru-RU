---
title: Развертывание функции вызовов с рабочего телефона в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Сводка: Узнайте, как развертывание звонок через работу в Скайп для Business Server 2015 для некоторых или всех пользователей.'
ms.openlocfilehash: e101cf39daedb8d94879b6cf99cd0c7b4ae00e8d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-via-work-in-skype-for-business-server-2015"></a><span data-ttu-id="9532f-103">Развертывание функции вызовов с рабочего телефона в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="9532f-103">Deploy Call Via Work in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9532f-104">**Сводка:** Сведения о развертывании звонок через работу в Скайп для Business Server 2015 для некоторых или всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="9532f-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server 2015 for some or all of your users.</span></span>
  
<span data-ttu-id="9532f-105">Используйте следующие действия для развертывания звонок с помощью рабочих для пользователей.</span><span class="sxs-lookup"><span data-stu-id="9532f-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="9532f-106">В [Планирование для звонков с помощью Скайп для Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)рассматриваются вопросы планирования.</span><span class="sxs-lookup"><span data-stu-id="9532f-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="9532f-107">В предыдущих версиях Lync Server удаленного вызова элемент управления был функции, которая позволяет пользователям управлять телефонах УАТС с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9532f-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="9532f-108">В Скайп Business Server этот компонент был заменен звонок с помощью рабочих.</span><span class="sxs-lookup"><span data-stu-id="9532f-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="9532f-109">Необходимые условия для позвонить с рабочего</span><span class="sxs-lookup"><span data-stu-id="9532f-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="9532f-110">Звонок с помощью рабочих использует Unified Communications Web API (UCWA), который автоматически устанавливается на всех Скайп для серверов переднего плана Business Server.</span><span class="sxs-lookup"><span data-stu-id="9532f-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="9532f-111">Чтобы включить пользователей для звонков с помощью рабочих, также требуются следующие необходимые компоненты на месте:</span><span class="sxs-lookup"><span data-stu-id="9532f-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="9532f-112">Необходимо иметь на сервер-посредник развернут, как часть сервера переднего плана или отдельных ролей.</span><span class="sxs-lookup"><span data-stu-id="9532f-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="9532f-113">Также необходимо развернуть шлюз IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="9532f-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="9532f-114">Все пользователи, которые будут использоваться для звонков с помощью рабочих должны иметь прямого входного набора (DID) на телефонной системы УАТС.</span><span class="sxs-lookup"><span data-stu-id="9532f-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="9532f-115">Всех вызовов с помощью рабочих пользователей необходимо включить для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9532f-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="9532f-116">При этом необходимо настроить Скайп для бизнеса БЫЛИ номер для каждого пользователя на соответствующий номер DID для соответствующего телефонной системы УАТС.</span><span class="sxs-lookup"><span data-stu-id="9532f-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="9532f-117">Все пользователи, которые будут применять звонок с помощью рабочих должны иметь **Автоматической настройки** , выбранной в их параметр **Дополнительные подключения** в их Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="9532f-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="9532f-118">Это позволяет клиентам обнаруживать URL-адреса, UCWA.</span><span class="sxs-lookup"><span data-stu-id="9532f-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="9532f-119">Значение **Автоматическая настройка** выбрано по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9532f-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="9532f-120">Для каждого пользователя звонок с помощью рабочих включите переадресацию звонков и одновременных звонков.</span><span class="sxs-lookup"><span data-stu-id="9532f-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="9532f-121">Для каждого пользователя звонок с помощью рабочих убедитесь включено конференц-связь и конференц-связи по телефону.</span><span class="sxs-lookup"><span data-stu-id="9532f-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="9532f-122">Эти пользователи могут получить в и выход из нее Скайп для конференций бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9532f-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="9532f-123">Убедитесь, что делегирование, групповой звонок и группы ответа отключены для каждого пользователя, звонок с помощью рабочих.</span><span class="sxs-lookup"><span data-stu-id="9532f-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="9532f-124">Развертывание функции вызовов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="9532f-124">Deploy Call Via Work</span></span>

<span data-ttu-id="9532f-125">Реализовав обязательные условия, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9532f-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="9532f-126">Создание глобального телефон для вашего развертывания, которое отображает Скайп для бизнеса на Звонящего УАТС, пользователей, которые имеются вызовы звонок с помощью рабочих.</span><span class="sxs-lookup"><span data-stu-id="9532f-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="9532f-127">Создайте одну или несколько политик звонок с помощью рабочих</span><span class="sxs-lookup"><span data-stu-id="9532f-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="9532f-128">Назначение политики звонок с помощью рабочих для каждого пользователя, который будет включен для звонков с помощью рабочих</span><span class="sxs-lookup"><span data-stu-id="9532f-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="9532f-129">Создание глобального номера телефона для функции "Позвонить с рабочего"</span><span class="sxs-lookup"><span data-stu-id="9532f-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="9532f-130">Введите следующий командлет</span><span class="sxs-lookup"><span data-stu-id="9532f-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="9532f-131">Например, указанный ниже командлет задает глобальный номер телефона 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="9532f-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="9532f-132">Создание политики для функции "Позвонить с рабочего"</span><span class="sxs-lookup"><span data-stu-id="9532f-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="9532f-133">Введите следующий командлет</span><span class="sxs-lookup"><span data-stu-id="9532f-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber
    <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

  ```

    <span data-ttu-id="9532f-134">К примеру следующий командлет создается политика звонков с помощью рабочих называется ContosoUser1CvWP, пользователь может использовать один номер обратного вызова admin и задает этот номер обратного вызова 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="9532f-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="9532f-135">Назначение политики звонок с помощью рабочих для пользователя</span><span class="sxs-lookup"><span data-stu-id="9532f-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="9532f-136">Введите следующий командлет</span><span class="sxs-lookup"><span data-stu-id="9532f-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="9532f-137">Например следующий командлет, назначает политику звонок с помощью рабочих «ContosoUser1CvWP» пользователя с именем **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="9532f-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="9532f-138">См. также</span><span class="sxs-lookup"><span data-stu-id="9532f-138">See also</span></span>

#### 

[<span data-ttu-id="9532f-139">Планирование позвонить с рабочего в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9532f-139">Plan for Call Via Work in Skype for Business Server 2015</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

