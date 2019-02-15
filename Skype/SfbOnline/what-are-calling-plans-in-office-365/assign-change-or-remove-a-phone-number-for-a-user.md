---
title: Назначение, изменение или удаление номер телефона для пользователя
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
description: Узнайте, как назначить, изменить или удалить рабочий номер телефона ваших пользователей Skype for Business, чтобы другие предприятия и клиенты могли им звонить.
ms.openlocfilehash: 0e354956d1077b2f81de7b889d8085f05db038c4
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2019
ms.locfileid: "30047751"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="38b5a-103">Назначение, изменение или удаление номер телефона для пользователя</span><span class="sxs-lookup"><span data-stu-id="38b5a-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="38b5a-104">При настройке вызов планы в Office 365, нужно назначить номера телефонов пользователей.</span><span class="sxs-lookup"><span data-stu-id="38b5a-104">When you set up Calling Plans in Office 365, you assign phone numbers to your users.</span></span> 

<span data-ttu-id="38b5a-105">В клиенте Microsoft Teams назначаемый вами номер телефона отображается при нажатии на **Вызовы**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![Номер телефона пользователя, отображаемый в Microsoft Teams.](../images/teams-phone-number.png)

<span data-ttu-id="38b5a-107">В клиенте Skype for Business назначаемый вами номер отображается в поле **Рабочий телефон** и не может изменяться пользователем.</span><span class="sxs-lookup"><span data-stu-id="38b5a-107">In the Skype for Business client, the phone number you assign will be listed in the **Work Phone** box and can't be changed by a user.</span></span>
  
![Номер рабочего телефона выделяется серым цветом.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="38b5a-109">Если пользователь хочет [изменить свой номер телефона для Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) и номер телефона в приложении Skype for Business не может быть изменен или выделен серым цветом, это означает, что администратор установил для пользователя номер телефона и пользователь его не может изменить.</span><span class="sxs-lookup"><span data-stu-id="38b5a-109">If a user wants to [change his or her phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) and the phone number in the Skype for Business app can't be changed or is grayed out, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="38b5a-110">Когда вы настраиваете пользователей, чтобы они могли совершать и принимать телефонные звонки, вам необходимо сначала использовать центр администрирования Skype for Business и назначить номер телефона, но если вам нужно, вы можете изменить или удалить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="38b5a-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number, but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="38b5a-111">Чтобы узнать, как получить тарифные планы в Office 365, а также их стоимость, см. [Лицензирование дополнительных компонентов Skype for Business и Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="38b5a-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="38b5a-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="38b5a-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="38b5a-115">Назначение номер телефона для пользователя</span><span class="sxs-lookup"><span data-stu-id="38b5a-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="38b5a-116">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="38b5a-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="38b5a-117">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="38b5a-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="38b5a-118">Перейдите в **Центр администрирования группами Майкрософт** > **портала прежних версий**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-118">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="38b5a-119">На левой панели навигации нажмите **Голосовая связь** > **Пользователи голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-119">In the left navigation, click **Voice** > **Voice users**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="38b5a-120">Позволяет параметр **голосовой связи** в левой области навигации в Скайп по центру администрирования бизнеса необходимо купить по крайней мере один **E5 корпоративной лицензии**, дополнительная лицензия на одной **Телефонной системой** или дополнительная лицензия на один **Аудио конференц-связи** .</span><span class="sxs-lookup"><span data-stu-id="38b5a-120">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="38b5a-121">На странице **Пользователи голосовой связи** найдите и выберите пользователя или пользователей для назначения номера телефона.</span><span class="sxs-lookup"><span data-stu-id="38b5a-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="38b5a-122">На Панели операций нажмите **Назначить номер**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="38b5a-123">На странице **нумерации** в списке **выберите номер, чтобы назначить** выберите номер телефона для пользователя.</span><span class="sxs-lookup"><span data-stu-id="38b5a-123">On the **Assign number** page in the **Select number to assign** list, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="38b5a-124">Если не отображается перечисленных телефонных номеров, необходимо [получить номера телефонов для пользователей](getting-phone-numbers-for-your-users.md) сначала.</span><span class="sxs-lookup"><span data-stu-id="38b5a-124">If you don't see any phone numbers listed, you need to [get phone numbers for your users](getting-phone-numbers-for-your-users.md) first.</span></span> <span data-ttu-id="38b5a-125">Или, если вы используете страницу **Центр администрирования Skype for Business** > **Голосовая связь** > **Телефонные номера** , нажмите **Добавить**, а затем нажмите **Номера новых пользователей**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="38b5a-126">Для назначения или изменения связанного экстренного адреса в разделе **Выбор подтвержденного местоположения экстренного реагирования**, либо выберите местоположение из списка, либо, если имеется много местоположений, введите название города в поле поиска и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-126">To assign or change the associated emergency address, under **Select validated emergency location**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
8. <span data-ttu-id="38b5a-127">После того, как вы выбрали номер телефона и местоположение экстренного реагирования, нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38b5a-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span><span class="sxs-lookup"><span data-stu-id="38b5a-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="38b5a-131">Изменение номера телефона для пользователя</span><span class="sxs-lookup"><span data-stu-id="38b5a-131">Change a phone number for a user</span></span>
 
<span data-ttu-id="38b5a-132">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="38b5a-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="38b5a-133">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="38b5a-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="38b5a-134">Перейдите в **Центр администрирования группами Майкрософт** > **портала прежних версий**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-134">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="38b5a-135">На левой панели навигации нажмите **Голосовая связь** > **Пользователи голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-135">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="38b5a-136">На странице " **Пользователи голосовой связи** " найдите и выберите одного или нескольких пользователей, которые нужно изменить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="38b5a-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="38b5a-137">В области действий в поле **назначен номер**, нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-137">In the Action pane, under **Assigned number**, click **Change**.</span></span> 
    
6. <span data-ttu-id="38b5a-138">На странице **Назначение номера** нажмите **Изменить номер**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="38b5a-139">На странице **Назначение номера** , под строкой **Выбрать номер для назначения**, воспользуйтесь списком для выбора нового номера телефона.</span><span class="sxs-lookup"><span data-stu-id="38b5a-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="38b5a-140">Для изменения связанного адреса экстренного реагирования, нажмите кнопку **Изменить местоположение**, а затем в разделе **Изменить адрес экстренного реагирования на**, либо выберите местоположение в списке, либо, если вы имеете много определенных местоположений, введите в поле поиска название города и нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-140">To change the associated emergency address, click **Change location**, and then under **Change emergency address to**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
9. <span data-ttu-id="38b5a-141">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="38b5a-142">Удаление номера телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="38b5a-142">Remove a phone number from a user</span></span>
 
<span data-ttu-id="38b5a-143">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="38b5a-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="38b5a-144">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="38b5a-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="38b5a-145">Перейдите в **Центр администрирования группами Майкрософт** > **портала прежних версий**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-145">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="38b5a-146">На левой панели навигации нажмите **Голосовая связь** > **Пользователи голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-146">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="38b5a-147">На странице " **Пользователи голосовой связи** " найдите и выберите одного или нескольких пользователей, которые вы хотите удалить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="38b5a-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="38b5a-148">В области действий в поле **назначен номер**, нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-148">In the Action pane, under **Assigned number**, click **Remove**.</span></span> 
    
6. <span data-ttu-id="38b5a-149">На панели действий, под строкой ontenteditable="false" class="locked monad startTag">**Назначить номер**, нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="38b5a-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="38b5a-150">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="38b5a-150">Related topics</span></span>
[<span data-ttu-id="38b5a-151">Что такое проверка адреса?</span><span class="sxs-lookup"><span data-stu-id="38b5a-151">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="38b5a-152">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="38b5a-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="38b5a-153">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="38b5a-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="38b5a-154">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="38b5a-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 