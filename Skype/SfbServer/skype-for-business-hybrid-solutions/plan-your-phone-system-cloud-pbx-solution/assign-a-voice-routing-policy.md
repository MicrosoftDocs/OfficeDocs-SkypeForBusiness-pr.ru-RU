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
description: Сводка. Ознакомьтесь с этой темой, чтобы узнать, как назначить голосовую политику для пользователей, использующих телефонную систему с локальной подключением PSTN.
ms.openlocfilehash: 43e2b560cc0886bacd6faaec6c113ee1f237eff7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092967"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="5e4ab-103">Назначение политики маршрутизация голосовой связи</span><span class="sxs-lookup"><span data-stu-id="5e4ab-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="5e4ab-104">Skype для бизнеса Online будет отменен 31 июля 2021 г., после чего служба будет больше недоступна.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="5e4ab-105">Кроме того, подключение PSTN между локальной средой, будь то Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online, больше не будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="5e4ab-106">Узнайте, как подключить сеть локальной телефонии к Teams с помощью [прямого маршрутного маршрутинга.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="5e4ab-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="5e4ab-107">**Сводка:** Ознакомьтесь с этой темой, чтобы узнать, как назначить голосовую политику пользователям, использующим телефонную систему с локальной возможностью подключения к PSTN.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="5e4ab-108">После подключения пользователя к Skype для бизнеса в Интернете и использования телефонной системы с локальной подключением КСТН к ним будут применяться две политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="5e4ab-109">Одна из них — это локальное политика маршрутинга голосовой маршрутики, которую вы назначите в помещении.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="5e4ab-110">Эта политика может быть глобальной или пользовательской и определяет, какие записи использования PSTN связаны с пользователем.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="5e4ab-111">В этом разделе объясняется назначение этой политики.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="5e4ab-112">Другая политика голосовой политики определяет, какие функции вызова доступны пользователю; эта политика голосовой связи определяется Корпорацией Майкрософт и идентична для всех пользователей подключения к сети PSTN для всех телефонных систем.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="5e4ab-113">Он автоматически назначен пользователям телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="5e4ab-114">**Пользователь локальной сети**</span><span class="sxs-lookup"><span data-stu-id="5e4ab-114">**On-premises user**</span></span>|<span data-ttu-id="5e4ab-115">**Телефонная система с локальной пользователем подключения PSTN**</span><span class="sxs-lookup"><span data-stu-id="5e4ab-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5e4ab-116">Функции вызова, определенные в</span><span class="sxs-lookup"><span data-stu-id="5e4ab-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="5e4ab-117">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="5e4ab-117">Voice policy</span></span>  <br/> |<span data-ttu-id="5e4ab-118">Заранее определенные политики голосовой связи, назначенной автоматически, когда пользователь имеет лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="5e4ab-119">Записи использования PSTN, связанные с</span><span class="sxs-lookup"><span data-stu-id="5e4ab-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="5e4ab-120">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="5e4ab-120">Voice policy</span></span>  <br/> |<span data-ttu-id="5e4ab-121">Политика маршрутивки голосовых данных, назначенная в то время как пользователь по-прежнему находится в локальном помещении.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="5e4ab-122">Выполните следующие действия, используя локальное развертывание, в то время как пользователь по-прежнему находится в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="5e4ab-123">Использование глобальной политики маршрутинга голосовой почты</span><span class="sxs-lookup"><span data-stu-id="5e4ab-123">Using a global voice routing policy</span></span>

<span data-ttu-id="5e4ab-124">Перед использованием глобальной политики маршрутичности голосовой связи для телефонной системы с пользователями подключения к сети PSTN необходимо добавить записи об использовании PSTN в политику.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="5e4ab-125">Назначение записей использования PSTN глобальной политике маршрутинга голосовых данных</span><span class="sxs-lookup"><span data-stu-id="5e4ab-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="5e4ab-126">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5e4ab-127">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="5e4ab-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5e4ab-128">Добавьте записи использования PSTN в политику:</span><span class="sxs-lookup"><span data-stu-id="5e4ab-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="5e4ab-129">Например:</span><span class="sxs-lookup"><span data-stu-id="5e4ab-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="5e4ab-130">Создание новой политики маршрутивки голосовой почты</span><span class="sxs-lookup"><span data-stu-id="5e4ab-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="5e4ab-131">Создание новой политики маршрутивки голосовой почты</span><span class="sxs-lookup"><span data-stu-id="5e4ab-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="5e4ab-132">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5e4ab-133">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="5e4ab-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5e4ab-134">Создайте новую политику маршрутинга голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="5e4ab-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="5e4ab-135">Например:</span><span class="sxs-lookup"><span data-stu-id="5e4ab-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="5e4ab-136">В этом примере создается новая политика маршрутизов голосовой маршрутики под названием HybridVoice, которая имеет два использования PSTN, связанных с ней.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="5e4ab-137">Назначение политики маршрутивки голосовой почты</span><span class="sxs-lookup"><span data-stu-id="5e4ab-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="5e4ab-138">Независимо от того, используете ли вы глобальную политику маршрутивки голосовой маршрутики или только для пользователей, используйте следующие действия для назначения политики пользователю.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="5e4ab-139">Назначение политики маршрутики голосовой почты</span><span class="sxs-lookup"><span data-stu-id="5e4ab-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="5e4ab-140">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5e4ab-141">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="5e4ab-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5e4ab-142">Назначьте существующую политику голосовой связи пользователю:</span><span class="sxs-lookup"><span data-stu-id="5e4ab-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="5e4ab-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e4ab-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="5e4ab-144">В этом примере пользователю с именем Bob Kelly назначена ранее созданная голосовая политика с именем HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="5e4ab-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="5e4ab-145">Дополнительные сведения о политиках маршрутизации голосовых данных см. в материале Create or modify a voice [policy and configure PSTN use records in Skype for Business 2015,](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)и [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5e4ab-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
