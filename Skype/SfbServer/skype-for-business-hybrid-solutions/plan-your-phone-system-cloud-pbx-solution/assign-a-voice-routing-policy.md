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
description: Сводка. В этом разделе вы узнаете, как назначить политику голосовой связи пользователям, использующим телефонную систему с локальной связью через STN.
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359325"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="b7879-103">Назначение политики маршрутизация голосовой связи</span><span class="sxs-lookup"><span data-stu-id="b7879-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="b7879-104">Skype для бизнеса Online будет отменен 31 июля 2021 г., после чего служба станет недоступна.</span><span class="sxs-lookup"><span data-stu-id="b7879-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="b7879-105">Кроме того, подключение по STN между локальной средой через Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online больше не будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="b7879-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="b7879-106">Узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутки.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="b7879-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="b7879-107">**Сводка:** В этом разделе вы узнаете, как назначить политику голосовой связи пользователям, использующим телефонную систему с локальной связью через STN.</span><span class="sxs-lookup"><span data-stu-id="b7879-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="b7879-108">После того как пользователь подключается к Skype для бизнеса Online и использует телефонную систему с локальной связью через STN, к ним будут применяться две политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b7879-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="b7879-109">Один из них — это политика маршрутистики локальной голосовой почты, которую вы будете назначать локально.</span><span class="sxs-lookup"><span data-stu-id="b7879-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="b7879-110">Эта политика может быть глобальной или пользовательской и определяет, какие записи использования STN связаны с пользователем.</span><span class="sxs-lookup"><span data-stu-id="b7879-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="b7879-111">В этом разделе объясняется, как назначить эту политику.</span><span class="sxs-lookup"><span data-stu-id="b7879-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="b7879-112">Другая политика голосовой почты определяет, какие функции звонков доступны пользователю; Эта политика голосовой связи определяется корпорацией Майкрософт и идентична для всех пользователей телефонной системы с локальной связью по STN.</span><span class="sxs-lookup"><span data-stu-id="b7879-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="b7879-113">Она автоматически назначена пользователям телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="b7879-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="b7879-114">**Пользователь локальной сети**</span><span class="sxs-lookup"><span data-stu-id="b7879-114">**On-premises user**</span></span>|<span data-ttu-id="b7879-115">**Телефонная система с пользователем локального подключения к STN**</span><span class="sxs-lookup"><span data-stu-id="b7879-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7879-116">Функции звонков, определенные в</span><span class="sxs-lookup"><span data-stu-id="b7879-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="b7879-117">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="b7879-117">Voice policy</span></span>  <br/> |<span data-ttu-id="b7879-118">Предопределяемая политика голосовой связи, назначенная автоматически, когда у пользователя есть лицензия на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="b7879-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="b7879-119">Записи использования PSTN, связанные с</span><span class="sxs-lookup"><span data-stu-id="b7879-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="b7879-120">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="b7879-120">Voice policy</span></span>  <br/> |<span data-ttu-id="b7879-121">Политика маршрутов голосовой почты, назначенная, когда пользователь по-прежнему находится в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="b7879-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="b7879-122">Выполните следующие действия с использованием локального развертывания, пока пользователь по-прежнему находится в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="b7879-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="b7879-123">Использование глобальной политики маршрутов голосовой почты</span><span class="sxs-lookup"><span data-stu-id="b7879-123">Using a global voice routing policy</span></span>

<span data-ttu-id="b7879-124">Перед использованием глобальной политики маршрутки голосовой связи для телефонной системы с пользователями локальной сети ЗВОНКОВ необходимо добавить в политику записи об использовании ЗВОНКОВ.</span><span class="sxs-lookup"><span data-stu-id="b7879-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="b7879-125">Назначение записей использования PSTN глобальной политике маршрутки голосовой почты</span><span class="sxs-lookup"><span data-stu-id="b7879-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="b7879-126">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b7879-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b7879-127">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="b7879-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b7879-128">Добавьте записи использования PSTN в политику:</span><span class="sxs-lookup"><span data-stu-id="b7879-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="b7879-129">Пример:</span><span class="sxs-lookup"><span data-stu-id="b7879-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="b7879-130">Создание новой политики маршрутки голосовой почты</span><span class="sxs-lookup"><span data-stu-id="b7879-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="b7879-131">Создание новой политики маршрутки голосовой почты</span><span class="sxs-lookup"><span data-stu-id="b7879-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="b7879-132">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b7879-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b7879-133">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="b7879-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b7879-134">Создайте новую политику маршрутов голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="b7879-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="b7879-135">Пример:</span><span class="sxs-lookup"><span data-stu-id="b7879-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="b7879-136">В этом примере создается новая политика маршрутики голосовых данных HybridVoice с двумя связанными с ней вариантами работы с STN.</span><span class="sxs-lookup"><span data-stu-id="b7879-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="b7879-137">Назначение политики маршрутной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="b7879-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="b7879-138">Независимо от того, используете ли вы глобальную политику маршрутинга голосовой почты или политику для отдельных пользователей, для назначения политики пользователю используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b7879-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="b7879-139">Назначение политики маршрутки голосовой почты</span><span class="sxs-lookup"><span data-stu-id="b7879-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="b7879-140">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b7879-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b7879-141">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="b7879-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b7879-142">Назначьте существующую политику голосовой связи пользователю:</span><span class="sxs-lookup"><span data-stu-id="b7879-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="b7879-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="b7879-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="b7879-144">В этом примере пользователю с отображаемым именем Bob Kelly назначена ранее созданная политика голосовой связи с именем HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="b7879-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="b7879-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015,](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b7879-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

