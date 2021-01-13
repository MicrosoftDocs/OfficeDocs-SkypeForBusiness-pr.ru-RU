---
title: Настройка телефонной сети в Skype для бизнеса Server
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
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: Сводка. В этом разделе вы узнаете, как настроить в Skype для бизнеса Server возможность телефонной связи.
ms.openlocfilehash: 92c282c87576e3d46353dabd8235521fe0097c11
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820729"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="252d4-103">Настройка телефонной сети в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="252d4-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="252d4-104">**Сводка:** В этом разделе вы узнаете, как настроить в Skype для бизнеса Server возможность телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="252d4-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="252d4-105">После создания топологии, включаемой в рабочие нагрузки и выбранных функций для телефонного номера, необходимо выполнить дополнительные действия по настройке функции телефонной комконференции.</span><span class="sxs-lookup"><span data-stu-id="252d4-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="252d4-106">Перед прочтение этой темы ознакомьтесь с планом для телефонной связи в Skype для бизнеса [Server,](../../plan-your-deployment/conferencing/dial-in-conferencing.md)требованиями к оборудованию и программному обеспечению для работы с этой услугой в Skype для бизнеса [Server,](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)а также с потоком развертывания и контрольным списком для телефонной [связи.](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)</span><span class="sxs-lookup"><span data-stu-id="252d4-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="252d4-107">Чтобы настроить функцию телефонной комконференции, необходимо выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="252d4-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="252d4-108">Настройка абонентских групп</span><span class="sxs-lookup"><span data-stu-id="252d4-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="252d4-109">Настройка областей для телефонной комконференции</span><span class="sxs-lookup"><span data-stu-id="252d4-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="252d4-110">Настройка номеров доступа по телефонной линии</span><span class="sxs-lookup"><span data-stu-id="252d4-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="252d4-111">Настройка политик конфигурации</span><span class="sxs-lookup"><span data-stu-id="252d4-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="252d4-112">Назначение строки URI учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="252d4-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="252d4-113">Кроме того, можно выполнить следующие необязательные задачи.</span><span class="sxs-lookup"><span data-stu-id="252d4-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="252d4-114">Дополнительные сведения об этих необязательных задачах см. в под управлением функции "Управление телефонным доступом" [в Skype для бизнеса Server.](../../manage/conferencing/dial-in-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="252d4-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="252d4-115">Управление политиками ПИН-кодов для телефонной видеоконференции</span><span class="sxs-lookup"><span data-stu-id="252d4-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="252d4-116">Управление сопоставлением клавиш для команд DTMF</span><span class="sxs-lookup"><span data-stu-id="252d4-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="252d4-117">Создание каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="252d4-117">Create conference directories</span></span>
    
- <span data-ttu-id="252d4-118">Управление объявлениями о подступах к конференции и отправляемой из нее</span><span class="sxs-lookup"><span data-stu-id="252d4-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="252d4-119">Тестирование параметров телефонной комференции</span><span class="sxs-lookup"><span data-stu-id="252d4-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="252d4-120">Отправка приветствия пользователям с телефонным номером</span><span class="sxs-lookup"><span data-stu-id="252d4-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="252d4-121">Настройка абонентских групп</span><span class="sxs-lookup"><span data-stu-id="252d4-121">Configure dial plans</span></span>
<span data-ttu-id="252d4-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="252d4-122"><a name="BKMK_ConfigureDialPlans"> </a></span></span>

<span data-ttu-id="252d4-123">При развертывании конференц-связи с телефонным подключением требуется создать или изменить одну абонентскую группу или несколько таких групп для маршрутизации номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="252d4-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="252d4-124">Необходимо также убедиться, что каждая телефонная плана содержит хотя бы одно правило нормализации — правило, которое преобразует телефонные расширения в полные телефонные номера в формате E.164.</span><span class="sxs-lookup"><span data-stu-id="252d4-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="252d4-125">Пользователи конференц-связи с телефонным подключением присоединяются к конференциям в качестве пользователей предприятия, прошедших проверку подлинности, путем ввода ПИН-кода и номера телефона.</span><span class="sxs-lookup"><span data-stu-id="252d4-125">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="252d4-126">Для преобразования добавочных номеров в полные номера телефонов требуется правило нормализации, поэтому пользователи могут проходить проверку подлинности только с помощью добавочного номера.</span><span class="sxs-lookup"><span data-stu-id="252d4-126">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="252d4-127">Чтобы настроить dial plans for dial-in conferencing:</span><span class="sxs-lookup"><span data-stu-id="252d4-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="252d4-128">Независимо от того, развертывается ли Корпоративная голосовая связь, измените глобальную телефонную систему, чтобы добавить регион для телефонного доступа и убедиться, что правило нормализации точно преобразует номера доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="252d4-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="252d4-129">Подробные инструкции см. в описании создания или изменения телефонной [плана в Skype для бизнеса Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="252d4-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="252d4-130">Если вы не развернули Корпоративная голосовая связь, создайте телефонные планы для номеров доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="252d4-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="252d4-131">Не забудьте добавить регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="252d4-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="252d4-132">Подробные инструкции см. в описании создания или изменения телефонной [плана в Skype для бизнеса Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="252d4-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="252d4-133">Если вы развернули Корпоративная голосовая связь, измените Корпоративная голосовая связь, чтобы они включали регионы и использовали соответствующие правила нормализации для номеров доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="252d4-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="252d4-134">Кроме того, вы также можете создать выделенные абонентские группы, которые используются только для номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="252d4-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="252d4-135">Подробные инструкции см. в описании создания или изменения телефонной [плана в Skype для бизнеса Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="252d4-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="252d4-136">Дополнительные сведения о создании правил нормализации см. в теме "Создание или изменение правила нормализации [в Skype для бизнеса".](../../deploy/deploy-enterprise-voice/normalization-rules.md)</span><span class="sxs-lookup"><span data-stu-id="252d4-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="252d4-137">Настройка областей для телефонной комконференции</span><span class="sxs-lookup"><span data-stu-id="252d4-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="252d4-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="252d4-138"><a name="BKMK_ConfigureDialInRegions"> </a></span></span>

<span data-ttu-id="252d4-139">При настройке абонентской группы вы указываете применяемый к ней регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="252d4-139">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="252d4-140">Регион для телефонной связи связывает номера доступа к этой телефонной связи с соответствующей телефонной картой.</span><span class="sxs-lookup"><span data-stu-id="252d4-140">The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="252d4-141">При создании номера доступа для телефонного подключения выбираются те области, которые связывают этот номер доступа с соответствующими абонентскими группами.</span><span class="sxs-lookup"><span data-stu-id="252d4-141">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="252d4-142">Поскольку важно указать регион для всех телефонных планов, мы рекомендуем проверить, есть ли регионы для всех телефонных планов.</span><span class="sxs-lookup"><span data-stu-id="252d4-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="252d4-143">Чтобы проверить, настроен ли регион для всех телефонных планов, используйте **get-CsDialPlan.**</span><span class="sxs-lookup"><span data-stu-id="252d4-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="252d4-144">Если регион для абонентских групп не задан, вы можете воспользоваться командлетом **Set-CsDialPlan** и задать такой регион.</span><span class="sxs-lookup"><span data-stu-id="252d4-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="252d4-145">Вы также можете использовать панель управления Skype для бизнеса Server для обновления региона в существующих группах.</span><span class="sxs-lookup"><span data-stu-id="252d4-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="252d4-146">Дополнительные сведения об использовании панели управления Skype для бизнеса Server см. в сведениях о создании или изменении телефонной группы [в Skype для бизнеса Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="252d4-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="252d4-147">Проверка правильности задания регионов для абонентских групп</span><span class="sxs-lookup"><span data-stu-id="252d4-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="252d4-148">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="252d4-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="252d4-149">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="252d4-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="252d4-150">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="252d4-150">Run the following at the command prompt:</span></span>
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="252d4-151">Например:</span><span class="sxs-lookup"><span data-stu-id="252d4-151">For example:</span></span>
    
   ```powershell
   Get-CsDialPlan
   ```

   <span data-ttu-id="252d4-152">В данном примере возвращаются все абонентские группы, настроенные для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="252d4-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="252d4-153">Просмотрите возвращенные абонентские группы, чтобы выявить те из них, для которых не задан регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="252d4-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="252d4-154">Дополнительные сведения см. в [get-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="252d4-154">For more information, see [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="252d4-155">Установка свойства региона для абонентской группы</span><span class="sxs-lookup"><span data-stu-id="252d4-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="252d4-156">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="252d4-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="252d4-157">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="252d4-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="252d4-158">Для всех абонентских групп, у которых не задан регион конференц-связи с телефонным подключением, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="252d4-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="252d4-159">Например:</span><span class="sxs-lookup"><span data-stu-id="252d4-159">For example:</span></span>
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="252d4-160">В данном примере изменяется абонентская группа с идентификатором Redmond — для ее свойства DialinConferencingRegion устанавливается значение «US West Coast».</span><span class="sxs-lookup"><span data-stu-id="252d4-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="252d4-161">Дополнительные сведения [см. в подстройки Set-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="252d4-161">For more information, see [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="252d4-162">Настройка номеров доступа по телефонной линии</span><span class="sxs-lookup"><span data-stu-id="252d4-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="252d4-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="252d4-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span></span>

<span data-ttu-id="252d4-p110">При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции. Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="252d4-p110">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="252d4-166">Прежде чем приступать к созданию номеров доступа, необходимо сначала спланировать регионы конференц-связи с телефонным подключением, а затем настроить абонентские группы в соответствии с регионами.</span><span class="sxs-lookup"><span data-stu-id="252d4-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="252d4-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server.](../../plan-your-deployment/conferencing/dial-in-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="252d4-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="252d4-168">Дополнительные сведения о настройке телефонных планов для телефонных звонков см. в подстройке "Создание или изменение" в [Skype для бизнеса Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="252d4-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="252d4-169">Нельзя использовать новый номер удаленного доступа до завершения репликации номеров доступа доменными службами Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="252d4-169">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete.</span></span> <span data-ttu-id="252d4-170">Репликация может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="252d4-170">Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="252d4-171">Завершив создание номеров доступа, можно изменить отображаемое имя для контактных объектов Active Directory, чтобы пользователи могли легко определить правильный номер доступа.</span><span class="sxs-lookup"><span data-stu-id="252d4-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="252d4-172">Для изменения отображаемого имени используется [cmdlet Set-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="252d4-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="252d4-173">Объекты Active Directory не следует изменять вручную.</span><span class="sxs-lookup"><span data-stu-id="252d4-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="252d4-174">Создание номера для телефонного доступа</span><span class="sxs-lookup"><span data-stu-id="252d4-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="252d4-175">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="252d4-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="252d4-176">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="252d4-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="252d4-177">В левой панели навигации щелкните **Конференция**, а затем выберите **Номер для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="252d4-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="252d4-178">На странице **"Номер доступа** для телефонного доступа" сделайте одно из следующих ок.</span><span class="sxs-lookup"><span data-stu-id="252d4-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="252d4-179">Click **New** to open **New Dial-in Access Number**.</span><span class="sxs-lookup"><span data-stu-id="252d4-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="252d4-180">Щелкните один из номеров доступа к телефонной сети в списке, выберите "Изменить" и **"Показать подробности".**</span><span class="sxs-lookup"><span data-stu-id="252d4-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="252d4-181">Использование поля поиска для поиска содержимого столбца в списке номеров доступа с телефонным номером может не дать результатов, которые вы ожидаете.</span><span class="sxs-lookup"><span data-stu-id="252d4-181">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="252d4-182">Вместо этого отсортировать список по интересуемого столбца, чтобы определить номер доступа к телефонной связи, который необходимо просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="252d4-182">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="252d4-183">Введите **в отображаемом** номере номер телефона, который пользователи телефонной сети общего звонков (PSTN) набирают, чтобы присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="252d4-183">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> <span data-ttu-id="252d4-184">Этот номер отображается в приглашениях на собрания и на веб-странице параметров телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="252d4-184">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="252d4-185">В **отображаемом имени** введите описание номера доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="252d4-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="252d4-186">Это имя, связанное с номером доступа для телефонного номера в результатах поиска Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="252d4-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="252d4-187">Это имя отображается в клиенте, когда пользователь вызывает номер доступа.</span><span class="sxs-lookup"><span data-stu-id="252d4-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="252d4-188">В **строке URI** введите номер E.164 номера для телефонного доступа в формате TEL URI, включая символ +перед номером и исключая пробелы.</span><span class="sxs-lookup"><span data-stu-id="252d4-188">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="252d4-189">Например, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="252d4-189">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="252d4-190">Один и тот же URI линии не может повторно использоваться другим номером доступа к телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="252d4-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="252d4-191">В **SIP URI** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="252d4-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="252d4-192">В текстовом поле введите уникальный SIP URI для этого номера доступа к телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="252d4-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="252d4-193">Этот SIP URI отображается в различных расположениях, включая уведомления о вызовах и предыдущие версии клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="252d4-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="252d4-194">Один и тот же URI SIP не может повторно использоваться другим номером доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="252d4-194">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="252d4-195">URI SIP нельзя изменить после создания номера доступа.</span><span class="sxs-lookup"><span data-stu-id="252d4-195">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="252d4-196">Единственный способ изменить URI SIP — удалить и повторно создать номер доступа.</span><span class="sxs-lookup"><span data-stu-id="252d4-196">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="252d4-197">В поле выпадающего списка щелкните домен приложения помощника по конференцию, которое поддерживает этот номер доступа к телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="252d4-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="252d4-198">В **пуле** выберите пул, в который запущен экземпляр помощника по конференцию, который поддерживает этот номер доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="252d4-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="252d4-199">Если необходимо изменить пул после создания номера доступа, необходимо использовать cmdlet [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) или удалить и повторно создать номер доступа.</span><span class="sxs-lookup"><span data-stu-id="252d4-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="252d4-200">На **основном языке** щелкните язык, на котором будут играть подсказки для этого номера доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="252d4-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="252d4-201">Основной язык — это язык, который помощник по конференцию использует для ответа на вызов.</span><span class="sxs-lookup"><span data-stu-id="252d4-201">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="252d4-202">Поддерживаемые языки отображаются рядом с каждым номером доступа на веб-странице параметров телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="252d4-202">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="252d4-203">(Необязательно) На **дополнительных** языках (не более четырех) нажмите кнопку "Добавить", выберите один или несколько дополнительных языков, которые будут поддерживаться для вызывающих на этот номер доступа по телефонной связи, а затем нажмите кнопку "ОК". </span><span class="sxs-lookup"><span data-stu-id="252d4-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="252d4-204">Для каждого номера доступа к телефонной сети можно выбрать до четырех дополнительных языков.</span><span class="sxs-lookup"><span data-stu-id="252d4-204">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="252d4-205">Пользователи могут выбрать дополнительный язык перед вводом ИД конференции при наборе номера для конференции.</span><span class="sxs-lookup"><span data-stu-id="252d4-205">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="252d4-206">Чтобы добавить регион для номера доступа к телефонной связи, в области "Связанные регионы" нажмите кнопку "Добавить", выберите один или несколько регионов, связанных с телефонными планами для этого номера доступа, а затем нажмите кнопку "ОК".  </span><span class="sxs-lookup"><span data-stu-id="252d4-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="252d4-207">Чтобы удалить регион из номера доступа по телефонной связи, в области "Связанные регионы" щелкните регион, который нужно удалить, а затем нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="252d4-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="252d4-208">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="252d4-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="252d4-209">Настройка политик конфигурации</span><span class="sxs-lookup"><span data-stu-id="252d4-209">Configure conferencing policies</span></span>
<span data-ttu-id="252d4-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="252d4-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span></span>

<span data-ttu-id="252d4-p122">Политика конференц-связи — это настройка учетной записи пользователя, задающая возможности взаимодействия участников в конференц-связи. Политики конференц-связи можно создавать на уровне сайта и на уровне пользователя. Параметры политики конференц-связи охватывают многие аспекты планирования конференций и участия в них. Некоторые параметры политики конференц-связи поддерживают конференц-связь с телефонным подключением участников. При настройке конференц-связи с телефонным подключением необходимо проверить, установлены ли эти поля соответственно вашей организации, и при необходимости изменить их.</span><span class="sxs-lookup"><span data-stu-id="252d4-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="252d4-216">Дополнительные сведения о настройке политикконференций см. в под управлением политик в [Skype для бизнеса Server.](../../manage/conferencing/conferencing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="252d4-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="252d4-217">Назначение строки URI учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="252d4-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="252d4-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="252d4-218"><a name="BKMK_AssignaLineURI"> </a></span></span>

<span data-ttu-id="252d4-219">Для присоединения к конференции в качестве пользователей, прошедших проверку подлинности, пользователи конференц-связи с телефонным подключением вводят номера телефонов или добавочные номера и ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="252d4-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="252d4-220">Для проверки подлинности требуется **URI** телефонной линии, указанный в учетных записях пользователей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="252d4-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="252d4-221">В этом разделе описывается назначение **Line URI** (URI линии) отдельной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="252d4-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="252d4-222">Чтобы назначить **Line URI** (URI линии) нескольким учетным записям пользователей, создайте сценарий, использующий командлет **Set-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="252d4-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="252d4-223">Подробные сведения об использовании примера сценария для назначения строки **URI** нескольким учетным записям пользователей см. в подзагоне "Назначение строки [URI нескольким пользователям".](https://go.microsoft.com/fwlink/p/?linkId=196945)</span><span class="sxs-lookup"><span data-stu-id="252d4-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="252d4-224">Выполните вход на компьютер с учетной записью члена группы RTCUniversalServerAdmins или члена роли **Cs-UserAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="252d4-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="252d4-225">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="252d4-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="252d4-226">В панели навигации слева щелкните **Users** (Пользователи).</span><span class="sxs-lookup"><span data-stu-id="252d4-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="252d4-227">В поле поиска введите имя пользователя, которого нужно настроить для конференц-связи с телефонным подключением, или щелкните **Add filter** (Добавить фильтр), чтобы задать поля поиска, а затем щелкните **Find** (Поиск).</span><span class="sxs-lookup"><span data-stu-id="252d4-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="252d4-228">Дважды щелкните имя пользователя, чтобы открыть диалоговое окно "Изменение пользователя Skype для бизнеса **Server".**</span><span class="sxs-lookup"><span data-stu-id="252d4-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="252d4-229">В разделе **Telephony** (Телефония) введите уникальный нормализованный номер телефона в поле **Line URI** (URI линии) (пример: tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="252d4-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="252d4-230">Вы можете указать **URI строки** только в том случае, если для параметра **Телефония** выбрано значение **Только с одного ПК на другой**, **Корпоративная голосовая связь**, **Удаленное управление звонками** или **Только удаленное управление звонками**.</span><span class="sxs-lookup"><span data-stu-id="252d4-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="252d4-231">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="252d4-231">Click **Commit**.</span></span>
    

