---
title: Назначение политики маршрутизация голосовой связи
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
description: Сводка. Ознакомьтесь с этой статьей, чтобы узнать, как назначить политику голосовой связи для пользователей, использующих телефонную систему с локальной сетью PSTN.
ms.openlocfilehash: 141d3cca560201df921fb4195db55ac60103a3d6
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221863"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="1a571-103">Назначение политики маршрутизация голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1a571-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="1a571-104">**Сводка:** В этом разделе рассказывается, как назначить политику голосовой связи для пользователей, использующих телефонную систему с локальной сетью PSTN.</span><span class="sxs-lookup"><span data-stu-id="1a571-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="1a571-105">Когда пользователь входит в Skype для бизнеса Online и использует телефонную систему с локальной связью PSTN, к ним применяются две политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="1a571-105">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="1a571-106">Одна локальная политика маршрутизации голосовой связи, которая будет назначена локальной.</span><span class="sxs-lookup"><span data-stu-id="1a571-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="1a571-107">Эта политика может быть глобальной или определенной пользователем и определяет, какие записи об использовании PSTN связаны с пользователем.</span><span class="sxs-lookup"><span data-stu-id="1a571-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="1a571-108">В этом разделе объясняется, как назначить эту политику.</span><span class="sxs-lookup"><span data-stu-id="1a571-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="1a571-109">Другая политика голосовой связи определяет, какие функции звонков доступны для пользователя; Эта политика голосовой связи определена корпорацией Майкрософт и идентична для всех телефонных систем с локальными пользователями подключения PSTN.</span><span class="sxs-lookup"><span data-stu-id="1a571-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="1a571-110">Он автоматически назначается пользователям телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="1a571-110">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="1a571-111">**Локальный пользователь**</span><span class="sxs-lookup"><span data-stu-id="1a571-111">**On-premises user**</span></span>|<span data-ttu-id="1a571-112">**Телефонная система с локальным пользователем подключения PSTN**</span><span class="sxs-lookup"><span data-stu-id="1a571-112">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1a571-113">Функции вызова, определенные в</span><span class="sxs-lookup"><span data-stu-id="1a571-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="1a571-114">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1a571-114">Voice policy</span></span>  <br/> |<span data-ttu-id="1a571-115">Предварительно определенная политика голосовой связи, назначаемая автоматически при лицензировании пользователя для телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="1a571-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="1a571-116">Записи использования PSTN, связанные с</span><span class="sxs-lookup"><span data-stu-id="1a571-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="1a571-117">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1a571-117">Voice policy</span></span>  <br/> |<span data-ttu-id="1a571-118">Политика маршрутизации голосовой связи, назначенная, когда пользователь по-прежнему размещен в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="1a571-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="1a571-119">Выполните следующие действия, используя локальное развертывание, в то время как пользователь по-прежнему размещается в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="1a571-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="1a571-120">Использование глобальной политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1a571-120">Using a global voice routing policy</span></span>

<span data-ttu-id="1a571-121">Прежде чем использовать глобальную политику маршрутизации голосовых вызовов для телефонной системы с локальными пользователями подключения к сети PSTN, необходимо добавить в политику записи об использовании PSTN.</span><span class="sxs-lookup"><span data-stu-id="1a571-121">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="1a571-122">Назначение записей использования PSTN глобальной политике маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1a571-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="1a571-123">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1a571-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1a571-124">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="1a571-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1a571-125">Добавьте в политику записи об использовании PSTN.</span><span class="sxs-lookup"><span data-stu-id="1a571-125">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="1a571-126">Например:</span><span class="sxs-lookup"><span data-stu-id="1a571-126">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="1a571-127">Создание новой политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1a571-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="1a571-128">Создание новой политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1a571-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="1a571-129">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1a571-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1a571-130">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="1a571-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1a571-131">Создание новой политики маршрутизации голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="1a571-131">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="1a571-132">Например:</span><span class="sxs-lookup"><span data-stu-id="1a571-132">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="1a571-133">В этом примере создается новая политика маршрутизации голосовой связи с именем HybridVoice, с которой связаны две использованные PSTN.</span><span class="sxs-lookup"><span data-stu-id="1a571-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="1a571-134">Назначение политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1a571-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="1a571-135">Независимо от того, используется глобальная политика маршрутизации голосовой связи или пользовательские, выполните следующие действия, чтобы назначить политику пользователю.</span><span class="sxs-lookup"><span data-stu-id="1a571-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="1a571-136">Назначение политики маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="1a571-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="1a571-137">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1a571-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1a571-138">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="1a571-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1a571-139">Назначьте существующую политику голосовой связи пользователю:</span><span class="sxs-lookup"><span data-stu-id="1a571-139">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="1a571-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="1a571-140">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="1a571-141">В этом примере пользователю с отображаемым именем Bob Kelly назначается ранее созданная политика голосовой связи с именем HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="1a571-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="1a571-142">Дополнительные сведения о политиках маршрутизации голосовой связи приведены [в статье Создание или изменение политики голосовой связи и настройка записей использования PSTN в Skype для бизнеса 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)и [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1a571-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

