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
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359325"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="61a2a-103">Назначение политики маршрутизация голосовой связи</span><span class="sxs-lookup"><span data-stu-id="61a2a-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="61a2a-104">Skype для бизнеса Online будет прекращен до 31 июля, 2021 после чего служба станет недоступна.</span><span class="sxs-lookup"><span data-stu-id="61a2a-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="61a2a-105">Кроме того, связь по протоколу PSTN между локальной средой и в Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online больше не будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="61a2a-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="61a2a-106">Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="61a2a-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="61a2a-107">**Сводка:** В этом разделе рассказывается, как назначить политику голосовой связи для пользователей, использующих телефонную систему с локальной сетью PSTN.</span><span class="sxs-lookup"><span data-stu-id="61a2a-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="61a2a-108">Когда пользователь входит в Skype для бизнеса Online и использует телефонную систему с локальной связью PSTN, к ним применяются две политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="61a2a-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="61a2a-109">Одна локальная политика маршрутизации голосовой связи, которая будет назначена локальной.</span><span class="sxs-lookup"><span data-stu-id="61a2a-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="61a2a-110">Эта политика может быть глобальной или определенной пользователем и определяет, какие записи об использовании PSTN связаны с пользователем.</span><span class="sxs-lookup"><span data-stu-id="61a2a-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="61a2a-111">В этом разделе объясняется, как назначить эту политику.</span><span class="sxs-lookup"><span data-stu-id="61a2a-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="61a2a-112">Другая политика голосовой связи определяет, какие функции звонков доступны для пользователя; Эта политика голосовой связи определена корпорацией Майкрософт и идентична для всех телефонных систем с локальными пользователями подключения PSTN.</span><span class="sxs-lookup"><span data-stu-id="61a2a-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="61a2a-113">Он автоматически назначается пользователям телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="61a2a-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="61a2a-114">**Локальный пользователь**</span><span class="sxs-lookup"><span data-stu-id="61a2a-114">**On-premises user**</span></span>|<span data-ttu-id="61a2a-115">**Телефонная система с локальным пользователем подключения PSTN**</span><span class="sxs-lookup"><span data-stu-id="61a2a-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="61a2a-116">Функции вызова, определенные в</span><span class="sxs-lookup"><span data-stu-id="61a2a-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="61a2a-117">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="61a2a-117">Voice policy</span></span>  <br/> |<span data-ttu-id="61a2a-118">Предварительно определенная политика голосовой связи, назначаемая автоматически при лицензировании пользователя для телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="61a2a-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="61a2a-119">Записи использования PSTN, связанные с</span><span class="sxs-lookup"><span data-stu-id="61a2a-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="61a2a-120">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="61a2a-120">Voice policy</span></span>  <br/> |<span data-ttu-id="61a2a-121">Политика маршрутизации голосовой связи, назначенная, когда пользователь по-прежнему размещен в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="61a2a-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="61a2a-122">Выполните следующие действия, используя локальное развертывание, в то время как пользователь по-прежнему размещается в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="61a2a-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="61a2a-123">Использование глобальной политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="61a2a-123">Using a global voice routing policy</span></span>

<span data-ttu-id="61a2a-124">Прежде чем использовать глобальную политику маршрутизации голосовых вызовов для телефонной системы с локальными пользователями подключения к сети PSTN, необходимо добавить в политику записи об использовании PSTN.</span><span class="sxs-lookup"><span data-stu-id="61a2a-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="61a2a-125">Назначение записей использования PSTN глобальной политике маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="61a2a-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="61a2a-126">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="61a2a-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="61a2a-127">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="61a2a-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="61a2a-128">Добавьте в политику записи об использовании PSTN.</span><span class="sxs-lookup"><span data-stu-id="61a2a-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="61a2a-129">Например:</span><span class="sxs-lookup"><span data-stu-id="61a2a-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="61a2a-130">Создание новой политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="61a2a-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="61a2a-131">Создание новой политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="61a2a-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="61a2a-132">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="61a2a-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="61a2a-133">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="61a2a-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="61a2a-134">Создание новой политики маршрутизации голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="61a2a-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="61a2a-135">Например:</span><span class="sxs-lookup"><span data-stu-id="61a2a-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="61a2a-136">В этом примере создается новая политика маршрутизации голосовой связи с именем HybridVoice, с которой связаны две использованные PSTN.</span><span class="sxs-lookup"><span data-stu-id="61a2a-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="61a2a-137">Назначение политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="61a2a-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="61a2a-138">Независимо от того, используется глобальная политика маршрутизации голосовой связи или пользовательские, выполните следующие действия, чтобы назначить политику пользователю.</span><span class="sxs-lookup"><span data-stu-id="61a2a-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="61a2a-139">Назначение политики маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="61a2a-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="61a2a-140">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="61a2a-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="61a2a-141">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="61a2a-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="61a2a-142">Назначьте существующую политику голосовой связи пользователю:</span><span class="sxs-lookup"><span data-stu-id="61a2a-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="61a2a-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="61a2a-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="61a2a-144">В этом примере пользователю с отображаемым именем Bob Kelly назначается ранее созданная политика голосовой связи с именем HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="61a2a-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="61a2a-145">Дополнительные сведения о политиках маршрутизации голосовой связи приведены [в статье Создание или изменение политики голосовой связи и настройка записей использования PSTN в Skype для бизнеса 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)и [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="61a2a-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

