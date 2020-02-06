---
title: Назначение политики маршрутизации голосовой связи
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Аннотация: Ознакомьтесь с этой статьей, чтобы научиться назначать политику голосовой связи для пользователей, использующих телефонную систему в Office 365 с локальным подключением КТСОП.'
ms.openlocfilehash: 0e9a39fba8d1db7b70f0422e71223d49917716ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803999"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="997a0-103">Назначение политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="997a0-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="997a0-104">**Сводка:** В этой статье рассказывается о том, как назначить политику голосовой связи для пользователей, использующих телефонную систему в Office 365 с локальным подключением КТСОП.</span><span class="sxs-lookup"><span data-stu-id="997a0-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="997a0-105">После того как пользователь входит в Skype для бизнеса Online и использует телефонную систему в Office 365 с локальным подключением PSTN, к ним применяются две политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="997a0-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="997a0-106">One — это локальная политика голосовой маршрутизации, которая будет назначаться локально.</span><span class="sxs-lookup"><span data-stu-id="997a0-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="997a0-107">Этот параметр может быть глобальным или конкретным пользователем и определяет, какие записи об использовании PSTN связаны с пользователем.</span><span class="sxs-lookup"><span data-stu-id="997a0-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="997a0-108">This topic explains how to assign this policy.</span><span class="sxs-lookup"><span data-stu-id="997a0-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="997a0-109">Другая политика голосовой связи определяет доступные для пользователя функции звонка; Эта политика голосовой связи определена корпорацией Майкрософт и идентична для всех телефонных систем в Office 365 с локальными пользователями сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="997a0-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="997a0-110">Она автоматически назначается телефонной системе пользователям Office 365.</span><span class="sxs-lookup"><span data-stu-id="997a0-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="997a0-111">**Локальный пользователь**</span><span class="sxs-lookup"><span data-stu-id="997a0-111">**On-premises user**</span></span>|<span data-ttu-id="997a0-112">**Телефонная система в Office 365 с локальным пользовательским подключением PSTN**</span><span class="sxs-lookup"><span data-stu-id="997a0-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="997a0-113">Функции вызовов, определенные в</span><span class="sxs-lookup"><span data-stu-id="997a0-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="997a0-114">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="997a0-114">Voice policy</span></span>  <br/> |<span data-ttu-id="997a0-115">Предварительно определенная политика голосовой связи, назначаемая автоматически, когда пользователь лицензируется для телефонной системы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="997a0-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="997a0-116">Записи использования ТСОП, связанные с</span><span class="sxs-lookup"><span data-stu-id="997a0-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="997a0-117">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="997a0-117">Voice policy</span></span>  <br/> |<span data-ttu-id="997a0-118">Политика маршрутизации голосовой связи, назначенная, когда пользователь размещен в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="997a0-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="997a0-119">Для выполнения описанных ниже действий используйте локальное развертывание, в то время как пользователь по-прежнему входит в локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="997a0-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="997a0-120">Использование политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="997a0-120">Using a global voice routing policy</span></span>

<span data-ttu-id="997a0-121">Перед использованием глобальной политики голосовой маршрутизации для телефонной системы в Office 365 с локальными пользователями подключения к глобальной сети (КТСОП) необходимо добавить в политику записи об использовании PSTN.</span><span class="sxs-lookup"><span data-stu-id="997a0-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="997a0-122">Назначение записей использования ТСОП глобальной политике маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="997a0-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="997a0-123">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="997a0-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="997a0-124">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="997a0-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="997a0-125">Добавьте в политику записи об использовании КТСОП.</span><span class="sxs-lookup"><span data-stu-id="997a0-125">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="997a0-126">Например:</span><span class="sxs-lookup"><span data-stu-id="997a0-126">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="997a0-127">Создание новой политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="997a0-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="997a0-128">Создание новой политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="997a0-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="997a0-129">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="997a0-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="997a0-130">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="997a0-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="997a0-131">Создание новой политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="997a0-131">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="997a0-132">Например:</span><span class="sxs-lookup"><span data-stu-id="997a0-132">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="997a0-133">В этом примере создается новая политика маршрутизации голосовой связи HybridVoice, с которой связаны две записи использования ТСОП.</span><span class="sxs-lookup"><span data-stu-id="997a0-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="997a0-134">Назначение политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="997a0-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="997a0-135">Независимо от того, какая политика маршрутизации голосовой связи используется — глобальная или пользовательская, используйте следующие действия для назначения политики пользователю.</span><span class="sxs-lookup"><span data-stu-id="997a0-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="997a0-136">Назначение политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="997a0-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="997a0-137">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="997a0-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="997a0-138">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="997a0-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="997a0-139">Назначьте существующую политику голосовой связи пользователю:</span><span class="sxs-lookup"><span data-stu-id="997a0-139">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="997a0-140">Например:</span><span class="sxs-lookup"><span data-stu-id="997a0-140">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="997a0-141">В этом примере пользователю с отображаемым именем Bob Kelly назначается ранее созданная политика голосовой связи с именем HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="997a0-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="997a0-142">Дополнительные сведения о политиках голосовой маршрутизации можно найти [в разделе Создание или изменение политики голосовой связи и настройка записей использования PSTN в Skype для бизнеса 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-ксвоицераутингполици](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)и [Grant-ксвоицеполици](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="997a0-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

