---
title: Назначение, изменение и удаление номера телефона пользователя
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Узнайте, как назначить, изменить или удалить рабочий номер телефона для пользователей Teams, чтобы внешние организации и клиенты могли звонить.
ms.openlocfilehash: e606885aee1e87dfdfc9b36a5247eedba225a185
ms.sourcegitcommit: 91fbc7c9cd43c2a5b7e6dfedf2388939f2f77d57
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50589623"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a><span data-ttu-id="8a866-103">Назначение, изменение или удаление номера телефона пользователя (планы звонков)</span><span class="sxs-lookup"><span data-stu-id="8a866-103">Assign, change, or remove a phone number for a user (Calling Plans)</span></span>

<span data-ttu-id="8a866-104">При назначении планов звонков пользователям назначаются телефонные номера.</span><span class="sxs-lookup"><span data-stu-id="8a866-104">When you set up Calling Plans, you assign phone numbers to your users.</span></span> <span data-ttu-id="8a866-105">В Microsoft Teams номер телефона, который вы назначаете, указан при нажатии кнопки **"Звонки".**</span><span class="sxs-lookup"><span data-stu-id="8a866-105">In Microsoft Teams, the phone number that you assign is listed when a user clicks **Calls**.</span></span> <span data-ttu-id="8a866-106">Инструкции по назначению, изменению и удалению номера телефона пользователя в сценарии [](https://docs.microsoft.com/microsoftteams/direct-routing-enable-users)прямой маршрутки см. в инструкциях по прямой маршрутике, голосовой и голосовой почте.</span><span class="sxs-lookup"><span data-stu-id="8a866-106">For instructions about assigning, changing, or removing a phone number from a user in a Direct Routing scenario, see [Enable users for Direct Routing, voice, and voicemail](https://docs.microsoft.com/microsoftteams/direct-routing-enable-users).</span></span>

![Номер телефона пользователя, отображаемого в Teams.](media/teams-phone-number.png)

<span data-ttu-id="8a866-108">При настройке пользователей для того, чтобы они могли звонить и принимать телефонные звонки, необходимо сначала использовать Центр администрирования Microsoft Teams и назначить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="8a866-108">When you're setting up users so they can make and receive phone calls, you must first use the Microsoft Teams admin center and assign a phone number.</span></span> <span data-ttu-id="8a866-109">При необходимости вы можете изменить или удалить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="8a866-109">You can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="8a866-110">Чтобы узнать, как получить планы звонков в Teams и сколько они стоят, см. лицензирование [надстройки Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="8a866-110">To learn how to get Calling Plans in Teams and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a866-111">Чтобы узнать, назначена ли пользователю лицензия, переходить в Центр администрирования Microsoft Teams > **Users.**</span><span class="sxs-lookup"><span data-stu-id="8a866-111">One way to see whether a user has a license assigned is by going to the Microsoft Teams admin center > **Users**.</span></span> <span data-ttu-id="8a866-112">Если лицензия назначена, она будет указана на странице.</span><span class="sxs-lookup"><span data-stu-id="8a866-112">If a license is assigned, it will be indicated on the page.</span></span>  <span data-ttu-id="8a866-113">Вы также можете использовать Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a866-113">You can also use the Microsoft 365 admin center.</span></span>
  
## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="8a866-114">Назначение номера телефона пользователю</span><span class="sxs-lookup"><span data-stu-id="8a866-114">Assign a phone number to a user</span></span>
 
<span data-ttu-id="8a866-115">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="8a866-115">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
    
1. <span data-ttu-id="8a866-116">В области навигации слева щелкните **"Номера**  >  **голосовых телефонов".**</span><span class="sxs-lookup"><span data-stu-id="8a866-116">In the left navigation, click **Voice** > **Phone numbers**.</span></span>
2. <span data-ttu-id="8a866-117">На странице **"Номера телефонов"** выберите в списке ненаписаный номер и нажмите кнопку "Изменить". </span><span class="sxs-lookup"><span data-stu-id="8a866-117">On the **Phone numbers** page, select an unassigned number in the list, and then click **Edit**.</span></span>  
3. <span data-ttu-id="8a866-118">В области **редактирования** в области "Назначено" найдите пользователя по отображаемом имени или имени пользователя, а затем нажмите кнопку "Назначить". </span><span class="sxs-lookup"><span data-stu-id="8a866-118">In the **Edit** pane, under **Assigned to**, search for the user by display name or user name, and then click **Assign**.</span></span>
4. <span data-ttu-id="8a866-119">Чтобы назначить или изменить связанное местоположение для экстренного помощи, в области **"Местоположение для** экстренного помощи" наберите и выберите нужное расположение.</span><span class="sxs-lookup"><span data-stu-id="8a866-119">To assign or change the associated emergency location, under **Emergency location**, search for and then select the location.</span></span>
5. <span data-ttu-id="8a866-120">В зависимости от того, хотите ли вы отправить пользователю сообщение электронной почты со сведениями о номере телефона, отключите или включите для пользователя электронной почты сведения о **телефонном номере.**</span><span class="sxs-lookup"><span data-stu-id="8a866-120">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="8a866-121">По умолчанию этот режим имеет значение "В этом режиме".</span><span class="sxs-lookup"><span data-stu-id="8a866-121">By default, this is on.</span></span> 
6. <span data-ttu-id="8a866-122">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8a866-122">Click **Save**.</span></span>

<span data-ttu-id="8a866-123">Пример PowerShell см. в [примере Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8a866-123">For a PowerShell example, see [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).</span></span>

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="8a866-124">Изменение номера телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="8a866-124">Change a phone number for a user</span></span>
 
<span data-ttu-id="8a866-125">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="8a866-125">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
    
1. <span data-ttu-id="8a866-126">В области навигации слева выберите "Пользователи", найдите и дважды щелкните нужного пользователя, щелкните "Учетная запись", а затем в области "Общие сведения" обратите внимание на номер телефона, который назначен пользователю. </span><span class="sxs-lookup"><span data-stu-id="8a866-126">In the left navigation, click **Users**, locate and double-click the user you want, click **Account**, and then under **General information**, make a note of the phone number that's assigned to the user.</span></span>
2. <span data-ttu-id="8a866-127">В области навигации слева щелкните **"Номера**  >  **голосовых телефонов".**</span><span class="sxs-lookup"><span data-stu-id="8a866-127">In the left navigation, click **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="8a866-128">На странице **"Номера телефонов"** выберите номер, который вы определили в шаге 1, и нажмите кнопку "Изменить". </span><span class="sxs-lookup"><span data-stu-id="8a866-128">On the **Phone numbers** page, select the number that you identified in step 1, and then click **Edit**.</span></span>  
4. <span data-ttu-id="8a866-129">В области **редактирования** в **области**"Назначено" щелкните **X,** чтобы удалить пользователя.</span><span class="sxs-lookup"><span data-stu-id="8a866-129">In the **Edit** pane, under **Assigned to**, click the **X** to remove the user.</span></span>
5. <span data-ttu-id="8a866-130">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8a866-130">Click **Save**.</span></span>
6. <span data-ttu-id="8a866-131">На странице **"Номера телефонов"** выберите в списке ненаписаный номер и нажмите кнопку "Изменить". </span><span class="sxs-lookup"><span data-stu-id="8a866-131">On the **Phone numbers** page, select an unassigned number in the list, and then click **Edit**.</span></span>  
7. <span data-ttu-id="8a866-132">В области **редактирования** в области "Назначено" найдите пользователя по отображаемом имени или имени пользователя, а затем нажмите кнопку "Назначить". </span><span class="sxs-lookup"><span data-stu-id="8a866-132">In the **Edit** pane, under **Assigned to**, search for the user by display name or user name, and then click **Assign**.</span></span>
8. <span data-ttu-id="8a866-133">Чтобы назначить или изменить связанное местоположение для экстренного помощи, в области **"Местоположение для** экстренного помощи" наберите и выберите нужное расположение.</span><span class="sxs-lookup"><span data-stu-id="8a866-133">To assign or change the associated emergency location, under **Emergency location**, search for and then select the location.</span></span>
9. <span data-ttu-id="8a866-134">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8a866-134">Click **Save**.</span></span>

<span data-ttu-id="8a866-135">Пример PowerShell см. в [примере Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8a866-135">For a PowerShell example, please see [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).</span></span>

## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="8a866-136">Удаление номера телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="8a866-136">Remove a phone number from a user</span></span>
 
<span data-ttu-id="8a866-137">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="8a866-137">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8a866-138">В области навигации слева выберите "Пользователи", найдите и дважды щелкните нужного пользователя, щелкните "Учетная запись", а затем в области "Общие сведения" обратите внимание на номер телефона, который назначен пользователю. </span><span class="sxs-lookup"><span data-stu-id="8a866-138">In the left navigation, click **Users**, locate and double-click the user you want, click **Account**, and then under **General information**, make a note of the phone number that's assigned to the user.</span></span>
2. <span data-ttu-id="8a866-139">В области навигации слева щелкните **"Номера**  >  **голосовых телефонов".**</span><span class="sxs-lookup"><span data-stu-id="8a866-139">In the left navigation, click **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="8a866-140">На странице **"Номера телефонов"** выберите номер, который вы определили в шаге 2, и нажмите кнопку "Изменить". </span><span class="sxs-lookup"><span data-stu-id="8a866-140">On the **Phone numbers** page, select the number that you identified in step 2, and then click **Edit**.</span></span>  
4. <span data-ttu-id="8a866-141">В области **редактирования** в **области**"Назначено" щелкните **X,** чтобы удалить пользователя.</span><span class="sxs-lookup"><span data-stu-id="8a866-141">In the **Edit** pane, under **Assigned to**, click the **X** to remove the user.</span></span>
5. <span data-ttu-id="8a866-142">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8a866-142">Click **Save**.</span></span>

<span data-ttu-id="8a866-143">Пример PowerShell см. в [примере Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8a866-143">For a PowerShell example, please see [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8a866-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8a866-144">Related topics</span></span>

[<span data-ttu-id="8a866-145">Что такое проверка адреса?</span><span class="sxs-lookup"><span data-stu-id="8a866-145">What is address validation?</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[<span data-ttu-id="8a866-146">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="8a866-146">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="8a866-147">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="8a866-147">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="8a866-148">[Метка заявление об отказе для экстренных вызовов](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8a866-148">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

[<span data-ttu-id="8a866-149">Set-CsOnlineVoiceUser</span><span class="sxs-lookup"><span data-stu-id="8a866-149">Set-CsOnlineVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[<span data-ttu-id="8a866-150">Планы звонков для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a866-150">Calling Plans for Microsoft 365</span></span>](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)
