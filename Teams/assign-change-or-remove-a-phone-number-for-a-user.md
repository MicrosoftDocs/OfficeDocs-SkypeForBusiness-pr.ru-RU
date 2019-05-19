---
title: Назначение, изменение и удаление номера телефона пользователя
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Сведения о назначении, изменении и удалении номера рабочего телефона для пользователей Teams и Skype для бизнеса, чтобы внешние компании и клиенты могли звонить через Skype.
ms.openlocfilehash: 547d9d4a4af68ef3cdd19a6f11c2854a4c2ba4ec
ms.sourcegitcommit: a6d34297fd4e91e873372513b270f34e15cb8003
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "34164578"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="c1053-103">Назначение, изменение и удаление номера телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="c1053-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="c1053-104">При настройке планов звонков в Office 365 назначаются номера телефонов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="c1053-104">When you set up Calling Plans in Office 365, you assign phone numbers to your users.</span></span> 

<span data-ttu-id="c1053-105">В клиенте Microsoft Teams назначаемый вами номер телефона отображается при нажатии на **Вызовы**.</span><span class="sxs-lookup"><span data-stu-id="c1053-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![Номер телефона пользователя, отображаемый в Microsoft Teams.](media/teams-phone-number.png)

<span data-ttu-id="c1053-107">В клиенте Skype for Business назначаемый вами номер отображается в поле **Рабочий телефон** и не может изменяться пользователем.</span><span class="sxs-lookup"><span data-stu-id="c1053-107">In the Skype for Business client, the phone number you assign will be listed in the **Work Phone** box and can't be changed by a user.</span></span>
  
![Номер рабочего телефона выделяется серым цветом.](media/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="c1053-109">Если пользователь хочет [изменить свой номер телефона для Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) и номер телефона в приложении Skype for Business не может быть изменен или выделен серым цветом, это означает, что администратор установил для пользователя номер телефона и пользователь его не может изменить.</span><span class="sxs-lookup"><span data-stu-id="c1053-109">If a user wants to [change his or her phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) and the phone number in the Skype for Business app can't be changed or is grayed out, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="c1053-110">Когда вы настраиваете пользователей, чтобы они могли совершать и принимать телефонные звонки, вам необходимо сначала использовать центр администрирования Skype for Business и назначить номер телефона, но если вам нужно, вы можете изменить или удалить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="c1053-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number, but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="c1053-111">Чтобы узнать, как получить тарифные планы в Office 365, а также их стоимость, см. [Лицензирование дополнительных компонентов Skype for Business и Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="c1053-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1053-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="c1053-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="c1053-115">Назначение пользователю номера телефона</span><span class="sxs-lookup"><span data-stu-id="c1053-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="c1053-116">![SFB-Logo-30x30. png](media/sfb-logo-30x30.png) **с помощью центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="c1053-116">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="c1053-117">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="c1053-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c1053-118">Перейдите к устаревшему порталу **Microsoft Teams центра** > \*\*\*\* администрирования.</span><span class="sxs-lookup"><span data-stu-id="c1053-118">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="c1053-119">На левой панели навигации нажмите **Голосовая связь** > **Пользователи голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="c1053-119">In the left navigation, click **Voice** > **Voice users**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="c1053-120">Для просмотра параметров **голоса** на левой панели навигации в центре администрирования Skype для бизнеса вы должны сначала приобрести хотя бы одну **лицензию**на корпоративную, одну лицензию на надстройку \*\*\*\* или лицензию для **голосовой конференции** .</span><span class="sxs-lookup"><span data-stu-id="c1053-120">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="c1053-121">На странице **Пользователи голосовой связи** найдите и выберите пользователя или пользователей для назначения номера телефона.</span><span class="sxs-lookup"><span data-stu-id="c1053-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="c1053-122">На Панели операций нажмите **Назначить номер**.</span><span class="sxs-lookup"><span data-stu-id="c1053-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="c1053-123">На странице **Назначение номера** в списке **выбрать номер для назначения** выберите номер телефона для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1053-123">On the **Assign number** page in the **Select number to assign** list, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c1053-124">Если вы не видите ни одного номера телефона, вы должны сначала [получить номера телефонов для пользователей](/microsoftteams/getting-phone-numbers-for-your-users) .</span><span class="sxs-lookup"><span data-stu-id="c1053-124">If you don't see any phone numbers listed, you need to [get phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users) first.</span></span> <span data-ttu-id="c1053-125">Или, если вы используете страницу **Центр администрирования Skype for Business** > **Голосовая связь** > **Телефонные номера** , нажмите **Добавить**, а затем нажмите **Номера новых пользователей**.</span><span class="sxs-lookup"><span data-stu-id="c1053-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="c1053-126">Для назначения или изменения связанного экстренного адреса в разделе **Выбор подтвержденного местоположения экстренного реагирования**, либо выберите местоположение из списка, либо, если имеется много местоположений, введите название города в поле поиска и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="c1053-126">To assign or change the associated emergency address, under **Select validated emergency location**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
8. <span data-ttu-id="c1053-127">После того, как вы выбрали номер телефона и местоположение экстренного реагирования, нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c1053-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c1053-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span><span class="sxs-lookup"><span data-stu-id="c1053-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="c1053-131">Изменение номера телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="c1053-131">Change a phone number for a user</span></span>
 
<span data-ttu-id="c1053-132">![SFB-Logo-30x30. png](media/sfb-logo-30x30.png) **с помощью центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="c1053-132">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="c1053-133">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="c1053-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c1053-134">Перейдите к устаревшему порталу **Microsoft Teams центра** > \*\*\*\* администрирования.</span><span class="sxs-lookup"><span data-stu-id="c1053-134">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="c1053-135">На левой панели навигации нажмите **Голосовая связь** > **Пользователи голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="c1053-135">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="c1053-136">На странице **Пользователи голосовой связи** найдите и выберите пользователя или пользователей, для которых вы хотите изменить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="c1053-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="c1053-137">На панели действий в разделе **назначенный номер**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c1053-137">In the Action pane, under **Assigned number**, click **Change**.</span></span> 
    
6. <span data-ttu-id="c1053-138">На странице **Назначение номера** нажмите **Изменить номер**.</span><span class="sxs-lookup"><span data-stu-id="c1053-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="c1053-139">На странице **Назначение номера** , под строкой **Выбрать номер для назначения**, воспользуйтесь списком для выбора нового номера телефона.</span><span class="sxs-lookup"><span data-stu-id="c1053-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="c1053-140">Для изменения связанного адреса экстренного реагирования, нажмите кнопку **Изменить местоположение**, а затем в разделе **Изменить адрес экстренного реагирования на**, либо выберите местоположение в списке, либо, если вы имеете много определенных местоположений, введите в поле поиска название города и нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="c1053-140">To change the associated emergency address, click **Change location**, and then under **Change emergency address to**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
9. <span data-ttu-id="c1053-141">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c1053-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="c1053-142">Удаление номера телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="c1053-142">Remove a phone number from a user</span></span>
 
<span data-ttu-id="c1053-143">![SFB-Logo-30x30. png](media/sfb-logo-30x30.png) **с помощью центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="c1053-143">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="c1053-144">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="c1053-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c1053-145">Перейдите к устаревшему порталу **Microsoft Teams центра** > \*\*\*\* администрирования.</span><span class="sxs-lookup"><span data-stu-id="c1053-145">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="c1053-146">На левой панели навигации нажмите **Голосовая связь** > **Пользователи голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="c1053-146">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="c1053-147">На странице **Пользователи голосовой связи** найдите и выберите пользователя или пользователей, для которых вы хотите удалить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="c1053-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="c1053-148">На панели действий в разделе **назначенный номер**нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c1053-148">In the Action pane, under **Assigned number**, click **Remove**.</span></span> 
    
6. <span data-ttu-id="c1053-149">На панели действий, под строкой ontenteditable="false" class="locked monad startTag">**Назначить номер**, нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c1053-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="c1053-150">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c1053-150">Related topics</span></span>
[<span data-ttu-id="c1053-151">Что такое проверка адреса?</span><span class="sxs-lookup"><span data-stu-id="c1053-151">What is address validation?</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[<span data-ttu-id="c1053-152">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="c1053-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="c1053-153">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="c1053-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="c1053-154">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c1053-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 