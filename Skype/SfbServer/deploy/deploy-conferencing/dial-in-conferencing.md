---
title: Настройка телефонных конференций в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Сводка: Сведения в этой статье описывается настройка телефонных конференций в Скайп для Business Server.'
ms.openlocfilehash: a0ac408fbdf221d565f17c2d714d7aa1765d5097
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982008"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="052c0-103">Настройка телефонных конференций в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="052c0-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="052c0-104">**Сводка:** Прочтите этот раздел, чтобы узнать, как Настройка телефонных конференций в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="052c0-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="052c0-105">После создания топологии, включающей рабочую нагрузку конференц-связи и выбранных конференц-связи необходимо выполнить дополнительные действия для настройки конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="052c0-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="052c0-106">Прежде чем прочитать этот раздел обязательно ознакомьтесь [Планирование конференций в Скайп для Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [требования к оборудованию и программному обеспечению для конференц-связи в Скайп для Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)и блок-схема [развертывания и контрольный список для конференц связи с телефонным](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span><span class="sxs-lookup"><span data-stu-id="052c0-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="052c0-107">Для настройки конференц-связи с телефонным подключением необходимо выполнить описанные ниже задачи.</span><span class="sxs-lookup"><span data-stu-id="052c0-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="052c0-108">Configure dial plans</span><span class="sxs-lookup"><span data-stu-id="052c0-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="052c0-109">Configure dial-in conferencing regions</span><span class="sxs-lookup"><span data-stu-id="052c0-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="052c0-110">Configure dial-in access numbers</span><span class="sxs-lookup"><span data-stu-id="052c0-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="052c0-111">Configure conferencing policies</span><span class="sxs-lookup"><span data-stu-id="052c0-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="052c0-112">Assign a Line URI to a user account</span><span class="sxs-lookup"><span data-stu-id="052c0-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="052c0-113">Кроме того, можно выполнить дополнительные задачи.</span><span class="sxs-lookup"><span data-stu-id="052c0-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="052c0-114">Дополнительные сведения об этих необязательные задачи, которые содержатся в разделе [Управление телефонных конференций в Скайп для Business Server](../../manage/conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="052c0-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="052c0-115">Управление политиками ПИН-кодов для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="052c0-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="052c0-116">Управление назначенными клавишами для команд DTMF</span><span class="sxs-lookup"><span data-stu-id="052c0-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="052c0-117">Создание каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="052c0-117">Create conference directories</span></span>
    
- <span data-ttu-id="052c0-118">Управление оповещениями о присоединении к конференции и выходе из нее</span><span class="sxs-lookup"><span data-stu-id="052c0-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="052c0-119">Проверка параметров конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="052c0-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="052c0-120">Отправка приветственного почтового сообщения пользователям телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="052c0-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="052c0-121">Настройка абонентских групп</span><span class="sxs-lookup"><span data-stu-id="052c0-121">Configure dial plans</span></span>
<span data-ttu-id="052c0-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="052c0-122"></span></span>

<span data-ttu-id="052c0-123">При развертывании конференц-связи с телефонным подключением необходимо создать или изменить одну или несколько абонентских групп для маршрутизации номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="052c0-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="052c0-124">Кроме того, необходимо убедиться, что каждой абонентской группы содержит по крайней мере один правила нормализации--правило, которое преобразует телефонной расширений в полный телефонных номеров в формат E.164.</span><span class="sxs-lookup"><span data-stu-id="052c0-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="052c0-p104">Пользователи конференц-связи с телефонным подключением присоединяются к конференциям в качестве пользователей предприятия, прошедших проверку подлинности, путем ввода ПИН-кода и номера телефона. Для преобразования добавочных номеров в полные номера телефонов требуется правило нормализации, чтобы пользователи могли для прохождения проверки подлинности вводить только добавочный номер.</span><span class="sxs-lookup"><span data-stu-id="052c0-p104">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="052c0-127">Чтобы настроить абонентские группы для конференц-связи с телефонным подключением, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="052c0-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="052c0-128">Независимо от того, развертываете ли вы корпоративную голосовую связь, добавьте в глобальную абонентскую группу регион конференц-связи с телефонным подключением и убедитесь, что правило нормализации правильно преобразует номера доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="052c0-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="052c0-129">Подробные сведения содержатся в разделе [Создание и изменение абонентской группы в Скайп для Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="052c0-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="052c0-130">Если развертывание корпоративной голосовой связь не планируется, то создайте абонентские группы для номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="052c0-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="052c0-131">Не забудьте добавить регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="052c0-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="052c0-132">Подробные сведения содержатся в разделе [Создание и изменение абонентской группы в Скайп для Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="052c0-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="052c0-133">Если вы развернули корпоративную голосовую связь, добавьте в ее абонентские группы регионы и используйте соответствующие правила нормализации для номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="052c0-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="052c0-134">Кроме того, вы также можете создать выделенные абонентские группы, которые используются только для номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="052c0-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="052c0-135">Подробные сведения содержатся в разделе [Создание и изменение абонентской группы в Скайп для Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="052c0-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="052c0-136">Дополнительные сведения о создании правил нормализации см [Создание или изменение правила нормализации в Скайп для бизнеса](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="052c0-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="052c0-137">Настройка регионов конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="052c0-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="052c0-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="052c0-138"></span></span>

<span data-ttu-id="052c0-p108">При создании абонентской группы следует задать регион конференц-связи с телефонным подключением, применяемый к этой абонентской группе. Регион конференц-связи с телефонным подключением связывает номера доступа к конференц-связи с телефонным подключением с соответствующей абонентской группой. При создании номера доступа по телефонной линии следует выбрать регион, связывающий номер доступа с подходящими абонентскими группами.</span><span class="sxs-lookup"><span data-stu-id="052c0-p108">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="052c0-142">Поскольку важно указать регион для всех абонентских групп, мы рекомендуем проверить наличие регионов конференц-связи у всех абонентских групп.</span><span class="sxs-lookup"><span data-stu-id="052c0-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="052c0-143">Чтобы проверить, задано ли область для всех абонентских групп-связь с телефонным, командлет **Get-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="052c0-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="052c0-144">Если область отсутствует абонентские группы, чтобы задать область можно использовать командлет **Set-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="052c0-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="052c0-145">Можно также использовать Скайп для панели управления Business Server для обновления области в существующих абонентских групп.</span><span class="sxs-lookup"><span data-stu-id="052c0-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="052c0-146">Для получения дополнительных сведений об использовании Скайп для панели управления Business Server см [Создание и изменение абонентской группы в Скайп для Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="052c0-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="052c0-147">Проверка правильности задания регионов для абонентских групп</span><span class="sxs-lookup"><span data-stu-id="052c0-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="052c0-148">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="052c0-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="052c0-149">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="052c0-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="052c0-150">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="052c0-150">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="052c0-151">Например:</span><span class="sxs-lookup"><span data-stu-id="052c0-151">For example:</span></span>
    
   ```
   Get-CsDialPlan
   ```

   <span data-ttu-id="052c0-152">В данном примере возвращаются все абонентские группы, настроенные для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="052c0-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="052c0-153">Просмотрите возвращенные абонентские группы, чтобы выявить те из них, для которых не задан регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="052c0-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="052c0-154">Для получения дополнительных сведений см [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="052c0-154">For more information, see [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="052c0-155">Установка свойства региона для абонентской группы</span><span class="sxs-lookup"><span data-stu-id="052c0-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="052c0-156">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="052c0-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="052c0-157">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="052c0-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="052c0-158">Для всех абонентских групп, у которых не задан регион конференц-связи с телефонным подключением, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="052c0-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="052c0-159">Например:</span><span class="sxs-lookup"><span data-stu-id="052c0-159">For example:</span></span>
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="052c0-160">В данном примере изменяется абонентская группа с идентификатором Redmond –  для ее свойства DialinConferencingRegion устанавливается значение «US West Coast».</span><span class="sxs-lookup"><span data-stu-id="052c0-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="052c0-161">Для получения дополнительных сведений см [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="052c0-161">For more information, see [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="052c0-162">Настройка номеров доступа по телефонной линии</span><span class="sxs-lookup"><span data-stu-id="052c0-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="052c0-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="052c0-163"></span></span>

<span data-ttu-id="052c0-p110">При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции. Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="052c0-p110">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="052c0-166">Прежде чем приступать к созданию номеров доступа, необходимо сначала спланировать регионы конференц-связи с телефонным подключением, а затем настроить абонентские группы в соответствии с регионами.</span><span class="sxs-lookup"><span data-stu-id="052c0-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="052c0-167">Для получения дополнительных сведений об областях видеть [Планирование конференций в Скайп для Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="052c0-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="052c0-168">Подробные сведения о настройке абонентские группы для конференц-связи, см [Создание и изменение абонентской группы в Скайп для Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="052c0-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="052c0-p112">Нельзя использовать новый номер удаленного доступа до завершения репликации номеров доступа доменными службами Active Directory (AD DS). Репликация может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="052c0-p112">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete. Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="052c0-171">Завершив создание номеров доступа, можно изменить отображаемое имя для контактных объектов Active Directory, чтобы пользователи могли легко определить правильный номер доступа.</span><span class="sxs-lookup"><span data-stu-id="052c0-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="052c0-172">Чтобы изменить отображаемое имя, используйте командлет [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="052c0-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="052c0-173">Не следует изменять объекты Active Directory вручную.</span><span class="sxs-lookup"><span data-stu-id="052c0-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="052c0-174">Создание номера для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="052c0-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="052c0-175">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="052c0-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="052c0-176">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="052c0-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="052c0-177">На левой панели навигации щелкните **Конференция**, а затем выберите **Номер для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="052c0-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="052c0-178">На странице **Номер для телефонного подключения** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="052c0-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="052c0-179">Нажмите **Создать**, чтобы открыть диалоговое окно **Создание номера для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="052c0-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="052c0-180">Выберите один из номеров для телефонного подключения, щелкните элемент **Правка**, а затем выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="052c0-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="052c0-p114">Использование поля поиска для поиска содержимого столбца в списке номеров доступа по телефонной линии может не дать желаемый результат. Вместо этого рекомендуется упорядочить список по интересующему столбцу, чтобы найти номер доступа по телефонной линии, который требуется просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="052c0-p114">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="052c0-p115">В поле **Отображаемый номер** введите телефонный номер, который набирают пользователи телефонной сети общего пользования (ТСОП), чтобы присоединиться к конференции. Этот номер отображается в приглашениях на собрание и на веб-странице параметров конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="052c0-p115">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference. This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="052c0-185">В поле **Отображаемое имя** введите описание для этого номера для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="052c0-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="052c0-186">Это имя, связанное с номером доступа в Скайп для результатов поиска бизнес-деятельности.</span><span class="sxs-lookup"><span data-stu-id="052c0-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="052c0-187">Это имя отображается в клиенте, когда пользователь набирает этот номер доступа.</span><span class="sxs-lookup"><span data-stu-id="052c0-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="052c0-p117">В поле **URI линии** введите номер E.164 для номера для телефонного подключения в формате TEL URI, включая символ + (плюс) перед номером и исключая пробелы. Например, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="052c0-p117">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="052c0-190">Этот же самый URI линии не может использоваться другим номером доступа к конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="052c0-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="052c0-191">В разделе **SIP URI** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="052c0-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="052c0-192">В текстовом поле введите уникальный SIP URI для этого номера доступа к конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="052c0-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="052c0-193">Этот URI SIP отображается в различных местах, в том числе, но не ограничиваясь вызова сообщений уведомлений и предыдущих версий клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="052c0-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="052c0-p119">Этот же самый SIP URI не может использоваться другим номером доступа к конференции с телефонным подключением. Этот SIP URI нельзя изменить после создания номера доступа. Единственный способ изменить SIP URI для номера доступа заключается в в удалении и повторном создании этого номера доступа.</span><span class="sxs-lookup"><span data-stu-id="052c0-p119">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="052c0-197">В раскрывающемся списке выберите домен приложения помощник по конференц-связи, поддерживающий этот номер доступа.</span><span class="sxs-lookup"><span data-stu-id="052c0-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="052c0-198">В области **Пул** выберите пул, в котором работает экземпляр помощника по конференц-связи, поддерживающий этот номер для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="052c0-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="052c0-199">Если требуется изменить пул после создания номера доступа, необходимо с помощью командлета [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) или удалить и воссоздайте номер доступа.</span><span class="sxs-lookup"><span data-stu-id="052c0-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="052c0-200">В области **Основной язык** выберите язык, на котором будут воспроизводиться приглашения для этого номера для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="052c0-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="052c0-p120">Основной язык – это язык, который помощник по конференц-связи использует для ответа на вызов. Поддерживаемые языки отображаются на веб-странице параметров конференц-связи с телефонным подключением рядом с каждым номером доступа.</span><span class="sxs-lookup"><span data-stu-id="052c0-p120">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="052c0-203">В области **Дополнительные языки (не более четырех)** нажмите **Добавить**, выберите дополнительные языки, которые требуется поддерживать для абонентов, набирающих этот номер для телефонного подключения, и нажмите кнопку **ОК** (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="052c0-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="052c0-p121">Для каждого номера доступа по телефонной линии можно выбрать вплоть до четырех дополнительных языков. Пользователи могут выбирать дополнительный язык до ввода идентификатора конференции, когда они набирают номер доступа к конференции.</span><span class="sxs-lookup"><span data-stu-id="052c0-p121">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="052c0-206">Добавление области в качестве номера для телефонного номера, в разделе **связанные регионы**, нажмите кнопку **Добавить**, выберите одну или несколько областей, которые связаны с абонентские группы для этого номера доступа и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="052c0-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="052c0-207">Чтобы удалить регион из номера для телефонного подключения, в разделе **Связанные регионы** выберите регион, который требуется удалить, и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="052c0-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="052c0-208">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="052c0-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="052c0-209">Настройка политик конференц-связи</span><span class="sxs-lookup"><span data-stu-id="052c0-209">Configure conferencing policies</span></span>
<span data-ttu-id="052c0-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="052c0-210"></span></span>

<span data-ttu-id="052c0-p122">Политика конференц-связи – это настройка учетной записи пользователя, задающая возможности взаимодействия участников в конференц-связи. Политики конференц-связи можно создавать на уровне сайта и на уровне пользователя. Параметры политики конференц-связи охватывают многие аспекты планирования конференций и участия в них. Некоторые параметры политики конференц-связи поддерживают конференц-связь с телефонным подключением участников. При настройке конференц-связи с телефонным подключением необходимо проверить, установлены ли эти поля соответственно вашей организации, и при необходимости изменить их.</span><span class="sxs-lookup"><span data-stu-id="052c0-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="052c0-216">Дополнительные сведения о настройке политик конференц-связи содержатся в разделе [Управление политики конференц-связи в Скайп для Business Server](../../manage/conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="052c0-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="052c0-217">Assign a Line URI to a user account</span><span class="sxs-lookup"><span data-stu-id="052c0-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="052c0-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="052c0-218"></span></span>

<span data-ttu-id="052c0-219">Для присоединения к конференции в качестве пользователей, прошедших проверку подлинности, пользователи конференц-связи с телефонным подключением вводят номера телефонов или добавочные номера и ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="052c0-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="052c0-220">Указан на Скайп для учетных записей пользователей Business Server **URI линии** телефонии является обязательным для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="052c0-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="052c0-221">В этом разделе описывается назначение **URI линии** отдельной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="052c0-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="052c0-222">Чтобы назначить **URI линии** нескольким учетным записям пользователей, можно создать сценарий, использующий командлет **Set-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="052c0-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="052c0-223">Для получения дополнительных сведений об использовании пример сценария для назначения **URI линии** для нескольких учетных записей пользователей видеть [Назначить коды URI строки к нескольким пользователям](https://go.microsoft.com/fwlink/p/?linkId=196945).</span><span class="sxs-lookup"><span data-stu-id="052c0-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="052c0-224">Выполните вход на компьютер с учетной записью члена группы RTCUniversalServerAdmins или члена роли **Cs-UserAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="052c0-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="052c0-225">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="052c0-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="052c0-226">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="052c0-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="052c0-227">В поле поиска введите имя пользователя, которого нужно настроить для конференц-связи с телефонным подключением, или щелкните **Добавить фильтр**, чтобы задать поля поиска, а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="052c0-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="052c0-228">Дважды нажмите имя пользователя, чтобы открыть диалоговое окно **Изменение пользователя Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="052c0-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="052c0-229">В разделе **Телефония** введите уникальный нормализованный номер телефона в поле **URI линии** (пример: tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="052c0-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="052c0-230">Вы можете указать **URI линии**, только если для параметра **Телефония** выбрано значение **Только с одного ПК на другой**, **Корпоративная голосовая связь**, **Удаленное управление звонками** или **Только удаленное управление звонками**.</span><span class="sxs-lookup"><span data-stu-id="052c0-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="052c0-231">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="052c0-231">Click **Commit**.</span></span>
    

