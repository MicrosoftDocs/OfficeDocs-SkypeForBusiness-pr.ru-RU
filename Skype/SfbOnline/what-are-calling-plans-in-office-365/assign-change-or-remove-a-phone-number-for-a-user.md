---
title: Назначение, изменение или удаление телефонного номера пользователя
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Узнайте, как назначить, изменить или удалить рабочий номер телефона ваших пользователей Skype for Business, чтобы другие предприятия и клиенты могли им звонить.
ms.openlocfilehash: 8c80bf9da5471f1a7293a01ed9e2d56f6e1aa15b
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780942"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="93e34-103">Назначение, изменение или удаление телефонного номера пользователя</span><span class="sxs-lookup"><span data-stu-id="93e34-103">Assign, change or remove a phone number for a user</span></span>

<span data-ttu-id="93e34-104">Когда вы настраиваете тарифные планы в Office 365, вы назначаете вашим пользователям номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="93e34-104">When you set up Calling Plans in Office 365, you will need to assign a phone number and emergency address to each of your users.</span></span> 

<span data-ttu-id="93e34-105">В клиенте Microsoft Teams назначаемый вами номер телефона отображается при нажатии на **Вызовы**.</span><span class="sxs-lookup"><span data-stu-id="93e34-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![Номер телефона пользователя, отображаемый в Microsoft Teams.](../images/teams-phone-number.png)

<span data-ttu-id="93e34-107">В клиенте Skype for Business назначаемый вами номер отображается в поле **Рабочий телефон** и не может изменяться пользователем.</span><span class="sxs-lookup"><span data-stu-id="93e34-107">In the Skype for Business client, the phone number you assign will be listed in the **Work Phone** box and can't be changed by a user.</span></span>
  
![Номер рабочего телефона выделяется серым цветом.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="93e34-109">Если пользователь хочет [изменить свой номер телефона для Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) и номер телефона в приложении Skype for Business не может быть изменен или выделен серым цветом, это означает, что администратор установил для пользователя номер телефона и пользователь его не может изменить.</span><span class="sxs-lookup"><span data-stu-id="93e34-109">If a user wants to [change his or her phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) and the phone number in the Skype for Business app can't be changed or is grayed out, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="93e34-110">Когда вы настраиваете пользователей, чтобы они могли совершать и принимать телефонные звонки, вам необходимо сначала использовать центр администрирования Skype for Business и назначить номер телефона, но если вам нужно, вы можете изменить или удалить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="93e34-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number, but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="93e34-111">Чтобы узнать, как получить тарифные планы в Office 365, а также их стоимость, см. [Лицензирование дополнительных компонентов Skype for Business и Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="93e34-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="93e34-112">Чтобы увидеть, имеет ли пользователь лицензию, вы можете перейти в **Центр администрирования Skype for Business** > **Голосовая связь** > **Пользователи голосовой связи** и выбрать пользователя.</span><span class="sxs-lookup"><span data-stu-id="93e34-112">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user.</span></span> <span data-ttu-id="93e34-113">Если лицензия назначена, она будет записана в разделе **Назначенная лицензия**.</span><span class="sxs-lookup"><span data-stu-id="93e34-113">If a license is assigned, it will be noted under **Assigned license**.</span></span> <span data-ttu-id="93e34-114">Также вы можете использовать центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="93e34-114">You also can use the Office 365 admin center.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="93e34-115">Назначение номера телефона пользователю</span><span class="sxs-lookup"><span data-stu-id="93e34-115">Assign a phone number to a user.</span></span>
 
<span data-ttu-id="93e34-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="93e34-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="93e34-117">Войдите в Office 365 под своей рабочей или учебной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="93e34-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="93e34-118">Перейдите в **Центр администрирования Office 365** > **Центры администрирования** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="93e34-118">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="93e34-119">На левой панели навигации нажмите **Голосовая связь** > **Пользователи голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="93e34-119">In the left navigation, click **Voice** > **Voice users**.</span></span>
   > [!NOTE]
 <span data-ttu-id="93e34-120">Чтобы на левой панели навигации центра администрирования Skype for Business появилась опция **Голосовая связь** ,вам необходимо сначала приобрести хотя бы одну лицензию **Enterprise E5**, одну лицензию на дополнение **Phone System** , или одну лицензию на дополнение **Audio Conferencing**.</span><span class="sxs-lookup"><span data-stu-id="93e34-120">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="93e34-121">На странице **Пользователи голосовой связи** найдите и выберите пользователя или пользователей, которым вы хотите назначить номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="93e34-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="93e34-122">На Панели операций нажмите **Назначить номер**.</span><span class="sxs-lookup"><span data-stu-id="93e34-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="93e34-123">На странице **Назначение номера** в списке **Выбрать номер для назначения** выберите номер телефона для пользователя.</span><span class="sxs-lookup"><span data-stu-id="93e34-123">On the **Assign number** page, in the **Select number to assign** drop down, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="93e34-124">Если вы не видите в списке никаких телефонных номеров, вам нужно сначала в раздел [Получение номеров телефонов для ваших пользователей](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="93e34-124">If you don't see any phone numbers listed, you need to [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md) first.</span></span> <span data-ttu-id="93e34-125">Или, если вы используете страницу **Центр администрирования Skype for Business** > **Голосовая связь** > **Телефонные номера** , нажмите **Добавить**, а затем нажмите **Номера новых пользователей**.</span><span class="sxs-lookup"><span data-stu-id="93e34-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="93e34-126">Для назначения или изменения связанного экстренного адреса в разделе **Выбор подтвержденного местоположения экстренного реагирования**, либо выберите местоположение из списка, либо, если имеется много местоположений, введите название города в поле поиска и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="93e34-126">To assign or change the associated emergency address, under **Select validated emergency location**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
8. <span data-ttu-id="93e34-127">После того, как вы выбрали номер телефона и местоположение экстренного реагирования, нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="93e34-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="93e34-128">Из-за задержки между Office 365 и Skype for Business Online, может потребоваться до 24 часов для включения пользователей.</span><span class="sxs-lookup"><span data-stu-id="93e34-128">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled.</span></span> <span data-ttu-id="93e34-129">Если по истечении 24 часов номер телефона не назначен правильно, [обратитесь в службу поддержки продуктов для бизнеса - Помощь администратора](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="93e34-129">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="93e34-130">Мы готовы помочь!</span><span class="sxs-lookup"><span data-stu-id="93e34-130">We're here to help</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="93e34-131">Изменение номера телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="93e34-131">Assign, change or remove a phone number for a user</span></span>
 
<span data-ttu-id="93e34-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="93e34-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="93e34-133">Войдите в Office 365 под своей рабочей или учебной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="93e34-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="93e34-134">Перейдите в **Центр администрирования Office 365** > **Центры администрирования** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="93e34-134">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="93e34-135">На левой панели навигации нажмите **Голосовая связь** > **Пользователи голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="93e34-135">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="93e34-136">На странице **Пользователи голосовой связи** найдите и выберите пользователя или пользователей, которым вы хотите изменить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="93e34-136">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="93e34-137">На Панели операций, под строкой **Назначенный номер**, нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="93e34-137">In the Action pane under **Assigned license**, click **Edit**.</span></span> 
    
6. <span data-ttu-id="93e34-138">На странице **Назначение номера** нажмите **Изменить номер**.</span><span class="sxs-lookup"><span data-stu-id="93e34-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="93e34-139">На странице **Назначение номера** , под строкой **Выбрать номер для назначения**, воспользуйтесь списком для выбора нового номера телефона.</span><span class="sxs-lookup"><span data-stu-id="93e34-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="93e34-140">Для изменения связанного адреса экстренного реагирования, нажмите кнопку **Изменить местоположение**, а затем в разделе **Изменить адрес экстренного реагирования на**, либо выберите местоположение в списке, либо, если вы имеете много определенных местоположений, введите в поле поиска название города и нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="93e34-140">To change the associated emergency address, click **Change location**, and then under **Change emergency address to**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
9. <span data-ttu-id="93e34-141">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="93e34-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="93e34-142">Удаление номера телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="93e34-142">Remove a phone number from a user</span></span>
 
<span data-ttu-id="93e34-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="93e34-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="93e34-144">Войдите в Office 365 под своей рабочей или учебной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="93e34-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="93e34-145">Перейдите в **Центр администрирования Office 365** > **Центры администрирования** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="93e34-145">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="93e34-146">На левой панели навигации нажмите **Голосовая связь** > **Пользователи голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="93e34-146">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="93e34-147">На странице **Пользователи голосовой связи** найдите и выберите пользователя или пользователей, номера телефонов которых вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="93e34-147">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="93e34-148">На панели операций под строкой **Назначенный номер**, нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="93e34-148">In the Action pane under **Assigned license**, click **Edit**.</span></span> 
    
6. <span data-ttu-id="93e34-149">На панели действий, под строкой ontenteditable="false" class="locked monad startTag">**Назначить номер**, нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="93e34-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="93e34-150">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="93e34-150">Related topics</span></span>
[<span data-ttu-id="93e34-151">Что такое проверка адреса?</span><span class="sxs-lookup"><span data-stu-id="93e34-151">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="93e34-152">Управление номерами телефонов вашей организации</span><span class="sxs-lookup"><span data-stu-id="93e34-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="93e34-153">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="93e34-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="93e34-154">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="93e34-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 