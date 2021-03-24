---
title: Настройка телефонных разговоров в Skype для бизнеса Server
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
description: Сводка. Ознакомьтесь с этой темой, чтобы узнать, как настроить диалоговое общение в Skype для бизнеса Server.
ms.openlocfilehash: 5f618e22cc45585baddf1e8d6090b9e211dc5681
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103855"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="03f92-103">Настройка телефонных разговоров в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="03f92-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="03f92-104">**Сводка:** Ознакомьтесь с этой темой, чтобы узнать, как настроить диалоговое общение в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="03f92-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="03f92-105">После создания топологии, которая включает в себя нагрузку на конференцию и выбор диалоговых телефонных конференций, необходимо выполнить дополнительные действия по настройке телефонных конференций.</span><span class="sxs-lookup"><span data-stu-id="03f92-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="03f92-106">Перед чтением этой темы убедитесь, что вы читали План для телефонных разговоров в Skype для бизнеса [Server,](../../plan-your-deployment/conferencing/dial-in-conferencing.md)требования к оборудованию и программному обеспечению для конференциалов в Skype для бизнеса [Server,](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)а также список и контрольный список развертывания для телефонных [бесед.](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)</span><span class="sxs-lookup"><span data-stu-id="03f92-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="03f92-107">Чтобы настроить диалоговое конференцию, необходимо выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="03f92-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="03f92-108">Настройка абонентских групп</span><span class="sxs-lookup"><span data-stu-id="03f92-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="03f92-109">Настройка регионов телефонных конференций</span><span class="sxs-lookup"><span data-stu-id="03f92-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="03f92-110">Настройка номеров доступа по телефонной линии</span><span class="sxs-lookup"><span data-stu-id="03f92-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="03f92-111">Настройка политик conferencing</span><span class="sxs-lookup"><span data-stu-id="03f92-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="03f92-112">Назначение строки URI учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="03f92-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="03f92-113">Кроме того, вы можете выполнить следующие необязательные задачи.</span><span class="sxs-lookup"><span data-stu-id="03f92-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="03f92-114">Дополнительные сведения об этих необязательных задачах см. в [веб-сведениях Manage dial-in conferencing in Skype for Business Server.](../../manage/conferencing/dial-in-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="03f92-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="03f92-115">Управление политиками ПИН-кода для телефонных контактов</span><span class="sxs-lookup"><span data-stu-id="03f92-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="03f92-116">Управление сопоставлением ключей для команд DTMF</span><span class="sxs-lookup"><span data-stu-id="03f92-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="03f92-117">Создание каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="03f92-117">Create conference directories</span></span>
    
- <span data-ttu-id="03f92-118">Управление регистрациями на конференции и оглашение сообщений об уходе</span><span class="sxs-lookup"><span data-stu-id="03f92-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="03f92-119">Тестовые параметры телефонных телефонных параметров</span><span class="sxs-lookup"><span data-stu-id="03f92-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="03f92-120">Отправка приветствуемой почты пользователям с номером</span><span class="sxs-lookup"><span data-stu-id="03f92-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="03f92-121">Настройка абонентских групп</span><span class="sxs-lookup"><span data-stu-id="03f92-121">Configure dial plans</span></span>
<span data-ttu-id="03f92-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="03f92-122"><a name="BKMK_ConfigureDialPlans"> </a></span></span>

<span data-ttu-id="03f92-123">При развертывании конференц-связи с телефонным подключением требуется создать или изменить одну абонентскую группу или несколько таких групп для маршрутизации номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="03f92-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="03f92-124">Кроме того, необходимо убедиться, что каждый телефонный план содержит по крайней мере одно правило нормализации — правило, которое преобразует телефонные расширения в полные телефонные номера в формате E.164.</span><span class="sxs-lookup"><span data-stu-id="03f92-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="03f92-125">Пользователи конференц-связи с телефонным подключением присоединяются к конференциям в качестве пользователей предприятия, прошедших проверку подлинности, путем ввода ПИН-кода и номера телефона.</span><span class="sxs-lookup"><span data-stu-id="03f92-125">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="03f92-126">Для преобразования добавочных номеров в полные номера телефонов требуется правило нормализации, поэтому пользователи могут проходить проверку подлинности только с помощью добавочного номера.</span><span class="sxs-lookup"><span data-stu-id="03f92-126">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="03f92-127">Настройка телефонных планов для телефонных конференций:</span><span class="sxs-lookup"><span data-stu-id="03f92-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="03f92-128">Развертывание или Корпоративная голосовая связь, измените глобальный телефонный план, чтобы добавить область телефонных телефонов и убедиться, что правило нормализации точно преобразует номера доступа к телефонным номерам.</span><span class="sxs-lookup"><span data-stu-id="03f92-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="03f92-129">Подробные инструкции см. в [описании Create or modify a dial plan in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="03f92-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="03f92-130">Если вы не развернули Корпоративная голосовая связь, создайте телефонные планы для номеров доступа к телефонным телефонам.</span><span class="sxs-lookup"><span data-stu-id="03f92-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="03f92-131">Не забудьте добавить регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="03f92-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="03f92-132">Подробные инструкции см. в [описании Create or modify a dial plan in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="03f92-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="03f92-133">Если вы развернули Корпоративная голосовая связь, измените Корпоративная голосовая связь телефонные планы при необходимости, чтобы включить регионы и использовать соответствующие правила нормализации для номеров доступа к телефонным номерам.</span><span class="sxs-lookup"><span data-stu-id="03f92-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="03f92-134">Кроме того, вы также можете создать выделенные абонентские группы, которые используются только для номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="03f92-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="03f92-135">Подробные инструкции см. в [описании Create or modify a dial plan in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="03f92-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="03f92-136">Дополнительные сведения о создании правил нормализации см. в материале [Create or modify a normalization rule in Skype for Business.](../../deploy/deploy-enterprise-voice/normalization-rules.md)</span><span class="sxs-lookup"><span data-stu-id="03f92-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="03f92-137">Настройка регионов телефонных конференций</span><span class="sxs-lookup"><span data-stu-id="03f92-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="03f92-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="03f92-138"><a name="BKMK_ConfigureDialInRegions"> </a></span></span>

<span data-ttu-id="03f92-139">При настройке абонентской группы вы указываете применяемый к ней регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="03f92-139">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="03f92-140">Регион телефонных телефонов связывает номера доступа к телефонным телефонам с соответствующей телефонной картой.</span><span class="sxs-lookup"><span data-stu-id="03f92-140">The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="03f92-141">При создании номера доступа для телефонного подключения выбираются те области, которые связывают этот номер доступа с соответствующими абонентскими группами.</span><span class="sxs-lookup"><span data-stu-id="03f92-141">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="03f92-142">Так как важно указать регион для всех телефонных планов, рекомендуем проверить, есть ли у всех телефонных планов области телефонных телефонов.</span><span class="sxs-lookup"><span data-stu-id="03f92-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="03f92-143">Чтобы проверить, установлен ли регион для всех телефонных окантовок с диалогом, используйте **cmdlet Get-CsDialPlan.**</span><span class="sxs-lookup"><span data-stu-id="03f92-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="03f92-144">Если регион для абонентских групп не задан, вы можете воспользоваться командлетом **Set-CsDialPlan** и задать такой регион.</span><span class="sxs-lookup"><span data-stu-id="03f92-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="03f92-145">Вы также можете использовать панель управления Skype для бизнес-серверов для обновления региона в существующих наборах.</span><span class="sxs-lookup"><span data-stu-id="03f92-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="03f92-146">Дополнительные сведения об использовании панели управления Skype для бизнес-серверов см. в материале [Create or modify a dial plan in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="03f92-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="03f92-147">Проверка правильности задания регионов для абонентских групп</span><span class="sxs-lookup"><span data-stu-id="03f92-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="03f92-148">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="03f92-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="03f92-149">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="03f92-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="03f92-150">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="03f92-150">Run the following at the command prompt:</span></span>
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="03f92-151">Например:</span><span class="sxs-lookup"><span data-stu-id="03f92-151">For example:</span></span>
    
   ```powershell
   Get-CsDialPlan
   ```

   <span data-ttu-id="03f92-152">В данном примере возвращаются все абонентские группы, настроенные для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="03f92-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="03f92-153">Просмотрите возвращенные абонентские группы, чтобы выявить те из них, для которых не задан регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="03f92-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="03f92-154">Дополнительные сведения см. [в рублях Get-CsDialPlan.](/powershell/module/skype/get-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="03f92-154">For more information, see [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="03f92-155">Установка свойства региона для абонентской группы</span><span class="sxs-lookup"><span data-stu-id="03f92-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="03f92-156">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="03f92-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="03f92-157">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="03f92-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="03f92-158">Для всех абонентских групп, у которых не задан регион конференц-связи с телефонным подключением, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="03f92-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="03f92-159">Например:</span><span class="sxs-lookup"><span data-stu-id="03f92-159">For example:</span></span>
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="03f92-160">В данном примере изменяется абонентская группа с идентификатором Redmond — для ее свойства DialinConferencingRegion устанавливается значение «US West Coast».</span><span class="sxs-lookup"><span data-stu-id="03f92-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="03f92-161">Дополнительные сведения см. [в рублях Set-CsDialPlan.](/powershell/module/skype/set-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="03f92-161">For more information, see [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="03f92-162">Настройка номеров доступа по телефонной линии</span><span class="sxs-lookup"><span data-stu-id="03f92-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="03f92-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="03f92-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span></span>

<span data-ttu-id="03f92-p110">При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции. Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="03f92-p110">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="03f92-166">Прежде чем приступать к созданию номеров доступа, необходимо сначала спланировать регионы конференц-связи с телефонным подключением, а затем настроить абонентские группы в соответствии с регионами.</span><span class="sxs-lookup"><span data-stu-id="03f92-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="03f92-167">Сведения о регионах см. в материале [Plan for dial-in conferencing in Skype for Business Server.](../../plan-your-deployment/conferencing/dial-in-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="03f92-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="03f92-168">Дополнительные сведения о настройке телефонных планов для телефонных разговоров см. в материале [Create or modify a dial plan in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="03f92-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="03f92-169">Нельзя использовать новый номер удаленного доступа до завершения репликации номеров доступа доменными службами Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="03f92-169">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete.</span></span> <span data-ttu-id="03f92-170">Репликация может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="03f92-170">Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="03f92-171">Завершив создание номеров доступа, можно изменить отображаемое имя для контактных объектов Active Directory, чтобы пользователи могли легко определить правильный номер доступа.</span><span class="sxs-lookup"><span data-stu-id="03f92-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="03f92-172">Чтобы изменить имя дисплея, используйте [кодлет Set-CsDialInConferencingAccessNumber.](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="03f92-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="03f92-173">Объекты Active Directory не следует изменять вручную.</span><span class="sxs-lookup"><span data-stu-id="03f92-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="03f92-174">Создание номера доступа к диалоговой сети</span><span class="sxs-lookup"><span data-stu-id="03f92-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="03f92-175">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="03f92-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="03f92-176">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="03f92-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="03f92-177">В левой панели навигации щелкните **Конференция**, а затем выберите **Номер для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="03f92-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="03f92-178">На странице **Номер доступа с номером dial-in** сделайте одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="03f92-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="03f92-179">Нажмите **кнопку New,** чтобы **открыть новый номер доступа с диалогом.**</span><span class="sxs-lookup"><span data-stu-id="03f92-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="03f92-180">Щелкните один из номеров доступа к диалоговому номеру в списке, нажмите **кнопку Изменить** и нажмите кнопку **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="03f92-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="03f92-181">Использование поля поиска для поиска содержимого столбца в списке номеров доступа к диалогу может не дать результатов, которые вы ожидаете.</span><span class="sxs-lookup"><span data-stu-id="03f92-181">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="03f92-182">Вместо этого отсортировать список по интересуемой столбце, чтобы определить номер доступа к диалоговому номеру, который необходимо просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="03f92-182">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="03f92-183">В **отображаемом** номере введите номер телефона, на который звонят пользователи телефонов с общедоступными переключениями телефонных сетей (PSTN), чтобы присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="03f92-183">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> <span data-ttu-id="03f92-184">Этот номер отображается в приглашениях на собрания и на веб-странице "Параметры параметров телефонной связи".</span><span class="sxs-lookup"><span data-stu-id="03f92-184">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="03f92-185">В **имя Display** введите описание номера доступа к диалоговом номеру.</span><span class="sxs-lookup"><span data-stu-id="03f92-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="03f92-186">Это имя, связанное с номером доступа к диалогу в результатах поиска Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="03f92-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="03f92-187">Это имя отображается в клиенте, когда пользователь вызывает номер доступа.</span><span class="sxs-lookup"><span data-stu-id="03f92-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="03f92-188">В **строке URI** введите номер E.164 номера доступа к телефону в формате TEL URI, включая символ + перед номером и за исключением пробелов.</span><span class="sxs-lookup"><span data-stu-id="03f92-188">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="03f92-189">Например, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="03f92-189">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03f92-190">Один и тот же URI линии не может быть повторно использовать другой номер доступа к диалоговой связи.</span><span class="sxs-lookup"><span data-stu-id="03f92-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="03f92-191">В **SIP URI** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="03f92-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="03f92-192">В текстовом окне введите уникальный SIP URI для этого номера доступа к диалоговой связи.</span><span class="sxs-lookup"><span data-stu-id="03f92-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="03f92-193">Этот SIP URI отображается в различных расположениях, включая сообщения уведомлений об вызовах и предыдущие версии клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="03f92-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="03f92-194">Один и тот же SIP URI не может быть повторно использовать другой номер доступа к диалоговой телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="03f92-194">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="03f92-195">URI SIP не может быть изменен после создания номера доступа.</span><span class="sxs-lookup"><span data-stu-id="03f92-195">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="03f92-196">Единственный способ изменить SIP URI — удалить и воссоздать номер доступа.</span><span class="sxs-lookup"><span data-stu-id="03f92-196">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="03f92-197">В окне выпадающего списка щелкните домен приложения Conferencing Attendant, которое поддерживает этот номер доступа к диалоговому номеру.</span><span class="sxs-lookup"><span data-stu-id="03f92-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="03f92-198">В **Пуле** щелкните пул, в который запущен экземпляр помощника по конференциасу, который поддерживает этот номер доступа к диалоговому номеру.</span><span class="sxs-lookup"><span data-stu-id="03f92-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03f92-199">Если после создания номера доступа необходимо изменить пул, необходимо использовать код [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) или удалить и воссоздать номер доступа.</span><span class="sxs-lookup"><span data-stu-id="03f92-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="03f92-200">На **языке Primary** щелкните язык, на котором будут отыграны подсказки для этого номера доступа к диалоговому номеру.</span><span class="sxs-lookup"><span data-stu-id="03f92-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="03f92-201">Основной язык — это язык, который служитель конференциинга использует для ответа на вызов.</span><span class="sxs-lookup"><span data-stu-id="03f92-201">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="03f92-202">Поддерживаемые языки отображаются рядом с каждым номером телефона доступа на веб-странице Параметры телефонных параметров dial-in.</span><span class="sxs-lookup"><span data-stu-id="03f92-202">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="03f92-203">(Необязательный) На дополнительных языках (не более **четырех)** нажмите кнопку **Добавить,** выберите один или несколько дополнительных языков, которые необходимо поддерживать для звонит по этому номеру доступа, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="03f92-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="03f92-204">Вы можете выбрать до четырех дополнительных языков для каждого номера доступа к диалоговом номеру.</span><span class="sxs-lookup"><span data-stu-id="03f92-204">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="03f92-205">Пользователи могут выбрать дополнительный язык перед вводом ID конференции при входе на конференцию.</span><span class="sxs-lookup"><span data-stu-id="03f92-205">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="03f92-206">Чтобы добавить область для номера доступа к диалоговой связи, в связанных регионах щелкните **Добавить,** щелкните один или несколько областей, связанных с планами набора для этого номера доступа, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="03f92-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="03f92-207">Чтобы удалить область из номера доступа к диалогу, в связанных регионах **щелкните** область, которая необходимо удалить, и нажмите **кнопку Удалить**.</span><span class="sxs-lookup"><span data-stu-id="03f92-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="03f92-208">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="03f92-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="03f92-209">Настройка политик conferencing</span><span class="sxs-lookup"><span data-stu-id="03f92-209">Configure conferencing policies</span></span>
<span data-ttu-id="03f92-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="03f92-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span></span>

<span data-ttu-id="03f92-p122">Политика конференц-связи — это настройка учетной записи пользователя, задающая возможности взаимодействия участников в конференц-связи. Политики конференц-связи можно создавать на уровне сайта и на уровне пользователя. Параметры политики конференц-связи охватывают многие аспекты планирования конференций и участия в них. Некоторые параметры политики конференц-связи поддерживают конференц-связь с телефонным подключением участников. При настройке конференц-связи с телефонным подключением необходимо проверить, установлены ли эти поля соответственно вашей организации, и при необходимости изменить их.</span><span class="sxs-lookup"><span data-stu-id="03f92-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="03f92-216">Дополнительные сведения о настройке политик conferencing см. в руб. Управление политиками конференций [в Skype для бизнеса Server.](../../manage/conferencing/conferencing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="03f92-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="03f92-217">Назначение строки URI учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="03f92-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="03f92-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="03f92-218"><a name="BKMK_AssignaLineURI"> </a></span></span>

<span data-ttu-id="03f92-219">Для присоединения к конференции в качестве пользователей, прошедших проверку подлинности, пользователи конференц-связи с телефонным подключением вводят номера телефонов или добавочные номера и ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="03f92-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="03f92-220">Для проверки подлинности требуется **URI** линии телефонии, указанной в учетных записях пользователей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="03f92-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="03f92-221">В этом разделе описывается назначение **Line URI** (URI линии) отдельной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="03f92-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="03f92-222">Чтобы назначить **Line URI** (URI линии) нескольким учетным записям пользователей, создайте сценарий, использующий командлет **Set-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="03f92-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="03f92-223">Сведения об использовании примера скрипта для назначения **line URI** нескольким учетным записям пользователей см. в материале Назначение URL-адресов строк [нескольким пользователям.](https://go.microsoft.com/fwlink/p/?linkId=196945)</span><span class="sxs-lookup"><span data-stu-id="03f92-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="03f92-224">Выполните вход на компьютер с учетной записью члена группы RTCUniversalServerAdmins или члена роли **Cs-UserAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="03f92-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="03f92-225">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="03f92-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="03f92-226">В панели навигации слева щелкните **Users** (Пользователи).</span><span class="sxs-lookup"><span data-stu-id="03f92-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="03f92-227">В поле поиска введите имя пользователя, которого нужно настроить для конференц-связи с телефонным подключением, или щелкните **Add filter** (Добавить фильтр), чтобы задать поля поиска, а затем щелкните **Find** (Поиск).</span><span class="sxs-lookup"><span data-stu-id="03f92-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="03f92-228">Дважды щелкните имя пользователя, чтобы открыть **диалоговое** окно Изменить Skype для пользователей бизнес-сервера.</span><span class="sxs-lookup"><span data-stu-id="03f92-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="03f92-229">В разделе **Telephony** (Телефония) введите уникальный нормализованный номер телефона в поле **Line URI** (URI линии) (пример: tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="03f92-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03f92-230">Вы можете указать **URI строки** только в том случае, если для параметра **Телефония** выбрано значение **Только с одного ПК на другой**, **Корпоративная голосовая связь**, **Удаленное управление звонками** или **Только удаленное управление звонками**.</span><span class="sxs-lookup"><span data-stu-id="03f92-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="03f92-231">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="03f92-231">Click **Commit**.</span></span>
