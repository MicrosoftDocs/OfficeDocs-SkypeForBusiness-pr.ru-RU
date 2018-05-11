---
title: Назначение политики маршрутизации голосовой связи
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Сводка: Прочтите этот раздел, чтобы узнать, как назначение политики голосовой связи для пользователей, использующих с телефонной системой в Office 365 с помощью подключения к ТСОП в локальной.'
ms.openlocfilehash: 0699e4c4da94c680f86ec607950a1c3b42b5690a
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="71b6b-103">Назначение политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="71b6b-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="71b6b-104">**Сводка:** Прочтите этот раздел, чтобы узнать, как назначение политики голосовой связи для пользователей с помощью телефонной системой в Office 365 с помощью локального подключения к ТСОП.</span><span class="sxs-lookup"><span data-stu-id="71b6b-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="71b6b-105">Когда пользователь разговаривает по Скайп для бизнеса в Интернет и использование системы телефона в Office 365 с помощью подключения к ТСОП в локальной, два политик голосовой связи будет применяться к их.</span><span class="sxs-lookup"><span data-stu-id="71b6b-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="71b6b-106">Один является локальной политики маршрутизации голосовых данных, который будут использоваться для назначения локально.</span><span class="sxs-lookup"><span data-stu-id="71b6b-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="71b6b-107">Эта политика может быть глобальной или пользовательская и определяет, какие записи использования ТСОП связаны с этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="71b6b-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="71b6b-108">В этом разделе объясняется, как назначить эту политику.</span><span class="sxs-lookup"><span data-stu-id="71b6b-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="71b6b-109">Политика голосовой связи определяет, какие вызова функции, доступные для пользователя; политики голосовой связи определяется корпорацией Майкрософт и идентична для всех телефонной системой в Office 365 с локальными пользователями подключения к ТСОП.</span><span class="sxs-lookup"><span data-stu-id="71b6b-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="71b6b-110">Он автоматически назначается телефонной системой в пользователей Office 365.</span><span class="sxs-lookup"><span data-stu-id="71b6b-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="71b6b-111">**Локальный пользователь**</span><span class="sxs-lookup"><span data-stu-id="71b6b-111">**On-premises user**</span></span>|<span data-ttu-id="71b6b-112">**Система телефона в Office 365 с помощью подключения к ТСОП локального пользователя**</span><span class="sxs-lookup"><span data-stu-id="71b6b-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="71b6b-113">Функции вызовов, определенные в</span><span class="sxs-lookup"><span data-stu-id="71b6b-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="71b6b-114">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="71b6b-114">Voice policy</span></span>  <br/> |<span data-ttu-id="71b6b-115">Заранее определенные политики голосовой связи, назначенные автоматически, когда у пользователя лицензии для телефонной системой в Office 365.</span><span class="sxs-lookup"><span data-stu-id="71b6b-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="71b6b-116">Записи использования ТСОП, связанные с</span><span class="sxs-lookup"><span data-stu-id="71b6b-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="71b6b-117">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="71b6b-117">Voice policy</span></span>  <br/> |<span data-ttu-id="71b6b-118">Политика маршрутизации голосовой связи, назначенная, когда пользователь размещен в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="71b6b-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="71b6b-119">Выполните следующие действия, используя локальное развертывание, пока пользователь по-прежнему размещенный в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="71b6b-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="71b6b-120">Использование политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="71b6b-120">Using a global voice routing policy</span></span>

<span data-ttu-id="71b6b-121">Прежде чем использовать политику маршрутизации голосовой связи глобальной для телефонной системой в Office 365 с локальными пользователями подключения к ТСОП, необходимо добавить записи использования ТСОП в политике.</span><span class="sxs-lookup"><span data-stu-id="71b6b-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="71b6b-122">Назначение записей использования ТСОП глобальной политике маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="71b6b-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="71b6b-123">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="71b6b-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="71b6b-124">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="71b6b-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="71b6b-125">Добавление записей использования ТСОП в политике:</span><span class="sxs-lookup"><span data-stu-id="71b6b-125">Add the PSTN usage records to the policy:</span></span>
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 

  ```

    <span data-ttu-id="71b6b-126">Например:</span><span class="sxs-lookup"><span data-stu-id="71b6b-126">For example:</span></span>
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 

  ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="71b6b-127">Создание новой политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="71b6b-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="71b6b-128">Создание новой политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="71b6b-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="71b6b-129">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="71b6b-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="71b6b-130">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="71b6b-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="71b6b-131">Создание новой политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="71b6b-131">Create a new voice routing policy:</span></span>
    
  ```
  New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
  ```

    <span data-ttu-id="71b6b-132">Например:</span><span class="sxs-lookup"><span data-stu-id="71b6b-132">For example:</span></span>
    
  ```
  New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
  ```

<span data-ttu-id="71b6b-133">В этом примере создается новая политика маршрутизации голосовой связи HybridVoice, с которой связаны две записи использования ТСОП.</span><span class="sxs-lookup"><span data-stu-id="71b6b-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="71b6b-134">Назначение политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="71b6b-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="71b6b-135">Независимо от того, какая политика маршрутизации голосовой связи используется — глобальная или пользовательская, используйте следующие действия для назначения политики пользователю.</span><span class="sxs-lookup"><span data-stu-id="71b6b-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="71b6b-136">Назначение политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="71b6b-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="71b6b-137">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="71b6b-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="71b6b-138">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="71b6b-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="71b6b-139">Назначьте существующую политику голосовой связи пользователю:</span><span class="sxs-lookup"><span data-stu-id="71b6b-139">Assign an existing voice policy to a user:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
  ```

    <span data-ttu-id="71b6b-140">Например:</span><span class="sxs-lookup"><span data-stu-id="71b6b-140">For example:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
  ```

<span data-ttu-id="71b6b-141">В этом примере пользователю с отображаемым именем Bob Kelly назначается ранее созданная политика голосовой связи с именем HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="71b6b-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="71b6b-142">Дополнительные сведения о политиках маршрутизации голосовых данных в разделе [Создание или изменение политики голосовой связи и Настройка записей использования ТСОП в Скайп для бизнеса 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)и [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="71b6b-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

