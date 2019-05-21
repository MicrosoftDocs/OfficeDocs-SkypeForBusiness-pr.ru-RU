---
title: Развертывание звонка через Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Сводка: сведения о том, как развертывать звонки через Skype для бизнеса Server для некоторых или всех пользователей.'
ms.openlocfilehash: a2d4783f39ca19fd751295f4725f686d843f8d5b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286392"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="7370c-103">Развертывание звонка через Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7370c-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="7370c-104">**Сводка:** Сведения о том, как развертывать звонки через Skype для бизнеса Server для некоторых или всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="7370c-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="7370c-105">Выполните эти действия, чтобы развернуть звонок с помощью работы для пользователей.</span><span class="sxs-lookup"><span data-stu-id="7370c-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="7370c-106">Вопросы планирования обсуждаются в разделе [планирование звонков с помощью Skype для бизнеса Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="7370c-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="7370c-107">В предыдущих версиях Lync Server удаленное управление звонками – это функция, с помощью которой пользователи смогут управлять телефонной АТС в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7370c-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="7370c-108">В Skype для бизнеса Server эта функция заменена на "звонок через Work".</span><span class="sxs-lookup"><span data-stu-id="7370c-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="7370c-109">Предварительные условия для звонков через Work</span><span class="sxs-lookup"><span data-stu-id="7370c-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="7370c-110">"Звонок через работу" использует веб-API единой системы обмена сообщениями (УКВА), который автоматически устанавливается на все серверы переднего плана Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7370c-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="7370c-111">Чтобы пользователи могли звонить через работу, необходимо также установить следующие необходимые компоненты:</span><span class="sxs-lookup"><span data-stu-id="7370c-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="7370c-112">Сервер-посредник должен быть развернут либо как часть сервера переднего плана, либо как самостоятельная роль.</span><span class="sxs-lookup"><span data-stu-id="7370c-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="7370c-113">Также необходимо развернуть шлюз IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="7370c-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="7370c-114">Все пользователи, которым будет разрешено звонить через работу, должны иметь прямой набор номера в телефонной системе УАТС.</span><span class="sxs-lookup"><span data-stu-id="7370c-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="7370c-115">Необходимо включить все звонки с помощью рабочих пользователей для корпоративного голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7370c-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="7370c-116">В этом случае необходимо настроить для каждого пользователя номер в Skype для бизнеса на соответствующий номер для соответствующей телефонной системы УАТС.</span><span class="sxs-lookup"><span data-stu-id="7370c-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="7370c-117">Для всех пользователей, которые будут использовать функцию "звонок через работу", необходимо выбрать **автоматическую настройку** подключений в их **дополнительных подключениях** в клиенте Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7370c-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="7370c-118">Это позволяет клиенту найти URL-адреса УКВА.</span><span class="sxs-lookup"><span data-stu-id="7370c-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="7370c-119">Значение **Автоматическая настройка** выбрано по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7370c-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="7370c-120">Для каждого звонка с рабочего пользователя Включите переадресацию звонков и одновременный звонок.</span><span class="sxs-lookup"><span data-stu-id="7370c-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="7370c-121">Для каждого звонка с рабочего пользователя убедитесь в том, что на Конференц-связь с телефонным подключением и конференц-связь включена.</span><span class="sxs-lookup"><span data-stu-id="7370c-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="7370c-122">Это позволит этим пользователям получать и исполнять конференции в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7370c-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="7370c-123">Убедитесь, что делегирование, вызов команды и группа ответа отключены для каждого звонка с помощью рабочего пользователя.</span><span class="sxs-lookup"><span data-stu-id="7370c-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="7370c-124">Развертывание функции вызовов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="7370c-124">Deploy Call Via Work</span></span>

<span data-ttu-id="7370c-125">Реализовав обязательные условия, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7370c-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="7370c-126">Создайте глобальный телефонный номер для развертывания, который будет отображаться в Skype для бизнеса в идентификации вызывающего абонента УАТС для пользователей, которые совершают звонки по рабочим звонкам.</span><span class="sxs-lookup"><span data-stu-id="7370c-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="7370c-127">Создание одного или нескольких звонков с помощью рабочих политик</span><span class="sxs-lookup"><span data-stu-id="7370c-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="7370c-128">Назначение рабочей политики для звонка каждому пользователю, который будет активироваться с помощью работы</span><span class="sxs-lookup"><span data-stu-id="7370c-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="7370c-129">Создание глобального номера телефона для функции "Позвонить с рабочего"</span><span class="sxs-lookup"><span data-stu-id="7370c-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="7370c-130">Введите следующий командлет</span><span class="sxs-lookup"><span data-stu-id="7370c-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="7370c-131">Например, указанный ниже командлет задает глобальный номер телефона 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="7370c-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="7370c-132">Создание политики для функции "Позвонить с рабочего"</span><span class="sxs-lookup"><span data-stu-id="7370c-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="7370c-133">Введите следующий командлет</span><span class="sxs-lookup"><span data-stu-id="7370c-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="7370c-134">Например, следующий командлет создает вызов с помощью рабочей политики, именуемой ContosoUser1CvWP, требует, чтобы пользователь использовал номер обратного вызова для администратора, и устанавливает для него номер обратного вызова в 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="7370c-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="7370c-135">Назначение пользователю вызова с помощью рабочей политики</span><span class="sxs-lookup"><span data-stu-id="7370c-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="7370c-136">Введите следующий командлет</span><span class="sxs-lookup"><span data-stu-id="7370c-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="7370c-137">Например, следующий командлет назначает вызов с помощью рабочей политики "ContosoUser1CvWP" для пользователя с именем **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="7370c-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="7370c-138">См. также</span><span class="sxs-lookup"><span data-stu-id="7370c-138">See also</span></span>

[<span data-ttu-id="7370c-139">Планирование звонков с помощью Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7370c-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

