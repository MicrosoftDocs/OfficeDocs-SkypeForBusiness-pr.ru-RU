---
title: "Управление параметрами звука конференц-связи для организации"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
- Strat_SB_PSTN
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: b890358cebfe6b5d701758c4b6086d6e1f388ca1
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="392c3-103">Управление параметрами звука конференц-связи для организации</span><span class="sxs-lookup"><span data-stu-id="392c3-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="392c3-104">Можно легко видеть все параметры аудиоконференций Скайп для бизнеса и группами Майкрософт в одном месте.</span><span class="sxs-lookup"><span data-stu-id="392c3-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="392c3-105">Назначение лицензии на аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="392c3-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="392c3-106">Невозможно присвоить лицензии с **Скайп по центру администрирования бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="392c3-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="392c3-107">Необходимо использовать Центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="392c3-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="392c3-108">В разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="392c3-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="392c3-109">**Назначение лицензии для пользователя**</span><span class="sxs-lookup"><span data-stu-id="392c3-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="392c3-110">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-111">В левой области переходов **центра администрирования Office 365**, перейдите к **пользователям** > **активных пользователей**и выберите одного или нескольких пользователей из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="392c3-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="392c3-112">Если при назначении лицензии до 20 пользователями в то же время, можно использовать **Выберите представление** раскрывающемся списке а затем выберите один из параметров или создание собственного представления.</span><span class="sxs-lookup"><span data-stu-id="392c3-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="392c3-113">Затем нажмите кнопку **Изменить**, **Далее** два раза а затем выберите лицензии и нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="392c3-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="392c3-114">Также можно назначить лицензий для нескольких пользователей с помощью Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="392c3-114">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="392c3-115">Инструкции и примеры скриптов PowerShell в разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="392c3-115">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="392c3-116">На панели действий в разделе **Лицензии на продукты** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="392c3-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="392c3-117">На странице **Лицензий на продукт** Включение **Звука конференц-связи** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="392c3-117">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="392c3-118">Для получения дополнительных сведений о лицензировании см [Скайп для бизнеса и группами Майкрософт дополнительный компонент лицензирования](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="392c3-118">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="392c3-119">После назначения лицензии Майкрософт могут отсутствовать изначально в списке как поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="392c3-119">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="392c3-120">В таком случае выйдите из центра администрирования Office 365 или нажмите сочетание клавиш CTRL+F5 для обновления окна браузера.</span><span class="sxs-lookup"><span data-stu-id="392c3-120">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="392c3-121">Идентификатор конференции автоматически назначается пользователю, если для него настроена аудиоконференция через Майкрософт как поставщика услуг аудиоконференций. Идентификатор конференции может быть статическим или динамическим. Он отправляется в приглашении на собрание при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="392c3-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="392c3-122">Идентификатор конференции автоматически назначается пользователю, когда они зависят от выбора звукового конференц-связи, используя Microsoft в качестве поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="392c3-122">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="392c3-123">Назначенный идентификатор конференции может быть статических или динамических и отправляется в приглашении на собрание, при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="392c3-123">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> 
  
<span data-ttu-id="392c3-124">Статические идентификаторы используются в том случае, когда пользователи в вашей организации не требуется запомнить случайное число; их можно выбрать нескольких или выберите один из легко запомнить.</span><span class="sxs-lookup"><span data-stu-id="392c3-124">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or choose one that's easy to remember.</span></span> <span data-ttu-id="392c3-125">При использовании идентификаторы динамических конференции каждого собрания, расписания пользователя будет присваивает идентификатор уникальный конференции.</span><span class="sxs-lookup"><span data-stu-id="392c3-125">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="392c3-126">Если вы хотите назначить динамических вместо статических конференции идентификаторы, видеть [звук конференц-связи с помощью динамических идентификаторы в вашей организации](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="392c3-126">If you want to assign dynamic rather than static conference IDs, see [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="392c3-127">Чтобы задать идентификатор конференции для пользователя, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="392c3-127">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="392c3-128">Идентификатор конференции должен содержать 7 цифр, и его нельзя изменить в центре администрирования Skype для бизнеса или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="392c3-128">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="392c3-129">Идентификатор конференции должен содержать 7 символов, и его нельзя изменить в Скайп для бизнеса центра администрирования или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="392c3-129">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="392c3-130">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="392c3-130">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="392c3-131">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="392c3-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="392c3-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="392c3-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="392c3-133">Пользователи могут использовать Скайп средством переноса собрания бизнеса требуется обновить их существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="392c3-133">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="392c3-134">Чтобы узнать, как для загрузки, установки и запуска Скайп для бизнеса средство обновления собрания, обратитесь к разделу: [Средство обновления собрания для Скайп для бизнес-деятельности и Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Скайп для бизнеса в Интернет, средство миграции собрания (64-разрядная версия)](http://go.microsoft.com/fwlink/?LinkID=626047)и [Скайп для бизнеса в Интернет, собрания Средство миграции (32-разрядная версия)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="392c3-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="392c3-135">Изменение поставщика аудиоконференций с Microsoft на стороннего поставщика</span><span class="sxs-lookup"><span data-stu-id="392c3-135">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a><span data-ttu-id="392c3-136">Изменение поставщика аудиоконференций корпорацией Майкрософт стороннего поставщика</span><span class="sxs-lookup"><span data-stu-id="392c3-136">Change the audio conferencing provider from Microsoft to a third-party provider</span></span>

1. <span data-ttu-id="392c3-137">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-137">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-138">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="392c3-138">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="392c3-139">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **пользователей**, а затем выберите изменяемый поставщик услуг аудиоконференций для пользователя.</span><span class="sxs-lookup"><span data-stu-id="392c3-139">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.</span></span>
    
4. <span data-ttu-id="392c3-140">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="392c3-140">In the Action pane, click **Edit**.</span></span> 
    
5. <span data-ttu-id="392c3-141">На странице " **Свойства** " в разделе **имя поставщика**выберите поставщика аудиоконференций для пользователя.</span><span class="sxs-lookup"><span data-stu-id="392c3-141">On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="392c3-142">Microsoft можно выбрать как поставщика услуг аудиоконференций, или значение **None** , только при выборе нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="392c3-142">You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.</span></span>
  
6. <span data-ttu-id="392c3-143">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="392c3-143">Click **Save**.</span></span> 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="392c3-144">Включение или отключение сообщений, отправляемых в пользователей аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="392c3-144">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="392c3-145">Скайп по центру администрирования Business или Windows PowerShell можно использовать для включения или отключения электронной почты для пользователей.</span><span class="sxs-lookup"><span data-stu-id="392c3-145">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="392c3-146">**С помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="392c3-146">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="392c3-147">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-147">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-148">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="392c3-148">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="392c3-149">На странице **параметров Microsoft моста** установите или снимите **автоматически отправлять сообщения электронной почты пользователям при их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="392c3-149">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="392c3-150">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="392c3-150">Click **Save**.</span></span>
    
    <span data-ttu-id="392c3-151">Также можно отправить по электронной почте для пользователя с помощью параметров аудиоконференций, перейдя к свойствам аудиоконференций пользователя и нажав кнопку **Отправить сведения о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="392c3-151">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="392c3-152">Конференции по умолчанию и идентификатор аудиоконференций номер телефона включен в приглашении на собрание, но не ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="392c3-152">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="392c3-153">[Использование Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="392c3-153">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="392c3-154">**С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="392c3-154">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="392c3-155">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="392c3-155">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="392c3-156">[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) можно использовать для управления другими параметрами для вашей организации, включая электронной почты.</span><span class="sxs-lookup"><span data-stu-id="392c3-156">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="392c3-157">Изменить сведения о контакте отправителя в сообщениях электронной почты, отправляемое пользователю</span><span class="sxs-lookup"><span data-stu-id="392c3-157">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="392c3-158">Можно внести изменения в сообщение электронной почты, которое отправляется автоматически для пользователей, включая адрес электронной почты фактические и отображаемое имя отправителя контактные данные.</span><span class="sxs-lookup"><span data-stu-id="392c3-158">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="392c3-159">По умолчанию, отправителя сообщения электронной почты — Office 365, но можно изменить адрес электронной почты и отображаемое имя с помощью командлета [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="392c3-159">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="392c3-160">Чтобы изменить адрес электронной почты, который отправляет сообщение электронной почты для пользователей, необходимо выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="392c3-160">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="392c3-161">Введите адрес электронной почты с помощью параметра _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="392c3-161">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="392c3-162">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="392c3-162">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="392c3-163">Установите для параметра _SendEmailOverride_ значение _True_.</span><span class="sxs-lookup"><span data-stu-id="392c3-163">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="392c3-164">Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="392c3-164">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="392c3-165">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span><span class="sxs-lookup"><span data-stu-id="392c3-165">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="392c3-166">Командлет [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) можно использовать для управления другими параметрами для вашей организации, включая электронной почты.</span><span class="sxs-lookup"><span data-stu-id="392c3-166">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="392c3-167">В разделе [сообщения электронной почты, которые отправляются пользователям при изменении их параметров звука конференц-связи, автоматически](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="392c3-167">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="392c3-168">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="392c3-168">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="392c3-169">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-169">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-170">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="392c3-170">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="392c3-171">В **Скайп по центру администрирования бизнеса**, в левой области переходов перейдите к **аудиоконференции**и в области действий в разделе **Идентификатор конференции**, нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="392c3-171">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="392c3-172">В **Сброс идентификатор конференции?** окно, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="392c3-172">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="392c3-173">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="392c3-173">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="392c3-174">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="392c3-174">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="392c3-175">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="392c3-175">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="392c3-176">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="392c3-176">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="392c3-177">Пользователи могут использовать Скайп средством переноса собрания бизнеса требуется обновить их существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="392c3-177">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="392c3-178">Чтобы узнать, как для загрузки, установки и запуска Скайп для бизнеса средство обновления собрания, обратитесь к разделу: [средство обновления собрания для Скайп для бизнес-деятельности и Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Скайп для бизнеса в Интернет, средство миграции собрания (64-разрядная версия)](http://go.microsoft.com/fwlink/?LinkID=626047)и [Скайп для бизнеса в Интернет, Собрания средства переноса (32-разрядная версия)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="392c3-178">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync]((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="392c3-179">Сброс ПИН-кода организатора конференции</span><span class="sxs-lookup"><span data-stu-id="392c3-179">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="392c3-180">Сброс ПИН-кода организатора конференции</span><span class="sxs-lookup"><span data-stu-id="392c3-180">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="392c3-181">Статические идентификаторы используются в том случае, когда пользователи в вашей организации не требуется запомнить случайное число; их можно выбрать определенное число или использовать один, который легко запомнить.</span><span class="sxs-lookup"><span data-stu-id="392c3-181">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="392c3-182">При использовании идентификаторы динамических конференции каждого собрания, расписания пользователя будет присваивает идентификатор уникальный конференции.</span><span class="sxs-lookup"><span data-stu-id="392c3-182">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="392c3-183">Если вы хотите назначить динамических вместо статических конференции идентификаторы, [звук конференц-связи с помощью динамических идентификаторы в вашей организации](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="392c3-183">If you want to assign dynamic rather than static conference IDs, [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="392c3-184">Идентификатор статического конференции будет автоматически создан и назначенных пользователю, однако иногда может потребоваться при пользователь не нужно использовать этот сертификат и требуется установить на определенное число или пользователи не могут не забудьте или теряют их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="392c3-184">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="392c3-185">Скайп по центру администрирования бизнеса и Windows PowerShell можно использовать для просмотра, изменение и сброс их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="392c3-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
1. <span data-ttu-id="392c3-186">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-186">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-187">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="392c3-187">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="392c3-188">Щелкните элемент **Пользователи**, а затем выберите пользователя, который требуется сбросить ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="392c3-188">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="392c3-189">В области действий в разделе **ПИН-код**, нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="392c3-189">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="392c3-190">Пользователи будут получать сообщения электронной почты с свой ПИН-код, когда они будет включена поддержка аудиоконференций или когда сбросить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="392c3-190">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="392c3-191">Но если вы отключили автоматически отправка по электронной почте, не будут отправляться электронной почты сброс ПИН-кода и необходимо вручную отправлять ПИН-код пользователя.</span><span class="sxs-lookup"><span data-stu-id="392c3-191">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="392c3-192">The PIN will only be shown once after it has been reset.</span><span class="sxs-lookup"><span data-stu-id="392c3-192">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="392c3-193">После отображения сразу после сброса ПИН-код не будет больше отображаться на свойства пользователя; Вместо этого \*\*\* будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="392c3-193">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="392c3-194">Отправка пользователям электронных писем с информацией об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="392c3-194">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="392c3-195">Отправить сообщение электронной почты с информацией аудиоконференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="392c3-195">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="392c3-196">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-196">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-197">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="392c3-197">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="392c3-198">Щелкните элемент **Пользователи**, а затем выберите пользователя, который требуется сбросить ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="392c3-198">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="392c3-199">На панели действий щелкните **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="392c3-199">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="392c3-200">При этом аудиоконференций ПИН-код не отправляется для пользователя.</span><span class="sxs-lookup"><span data-stu-id="392c3-200">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="392c3-201">[Использование Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="392c3-201">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="392c3-202">Установка номера телефона аудиоконференций по умолчанию для Организаторы собраний</span><span class="sxs-lookup"><span data-stu-id="392c3-202">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="392c3-203">**Чтобы задать номер телефона по умолчанию аудиоконференций для Организаторы собраний, когда Включение пользователю аудиоконференций**</span><span class="sxs-lookup"><span data-stu-id="392c3-203">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="392c3-204">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-204">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-205">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="392c3-205">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="392c3-206">В левой области переходов, перейдите к **аудиоконференции** > **пользователей**.</span><span class="sxs-lookup"><span data-stu-id="392c3-206">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="392c3-207">Выберите пользователя, который необходимо включить для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="392c3-207">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="392c3-208">В области действий в окне Свойства пользователя нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="392c3-208">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="392c3-209">На странице " **Свойства** " в разделе **имя поставщика**используйте раскрывающегося списка для выбора поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="392c3-209">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="392c3-210">При выборе Microsoft в качестве поставщика аудиоконференций номер телефона аудиоконференций по умолчанию можно выбрать из списка.</span><span class="sxs-lookup"><span data-stu-id="392c3-210">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="392c3-211">Если выбран ACP стороннего поставщика аудиоконференций, необходимо вручную ввести международную и при необходимости номера бесплатный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="392c3-211">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span> <span data-ttu-id="392c3-212">Эти номера будут номер телефона по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="392c3-212">These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="392c3-213">Номер телефона по умолчанию аудиоконференций пользователя — номер, отображаются в приглашении на собрание, при составлении приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="392c3-213">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="392c3-214">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="392c3-214">Click **Save**.</span></span> 
    
<span data-ttu-id="392c3-215">В разделе [Задайте телефона, номера, находящимся на приглашает](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="392c3-215">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="392c3-216">**Чтобы задать номер телефона по умолчанию аудиоконференций для Организаторы собраний после включения пользователя для аудиоконференций**</span><span class="sxs-lookup"><span data-stu-id="392c3-216">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="392c3-217">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-217">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-218">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="392c3-218">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="392c3-219">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **пользователей**, выберите пользователя и на странице "действия" нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="392c3-219">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="392c3-220">На странице " **Свойства** " в разделе **имя поставщика**используйте раскрывающегося списка для выбора поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="392c3-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="392c3-221">Если пользователь использует Microsoft в качестве поставщика аудиоконференций, номер телефона аудиоконференций по умолчанию можно выбрать из списка.</span><span class="sxs-lookup"><span data-stu-id="392c3-221">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="392c3-222">Если пользователь использует ACP сторонних производителей в качестве поставщика аудиоконференций, необходимо вручную ввести международную и при необходимости номера бесплатный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="392c3-222">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="392c3-223">Номер телефона по умолчанию аудиоконференций пользователя — номер, отображаются в приглашении на собрание, при составлении приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="392c3-223">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="392c3-224">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="392c3-224">Click **Save**.</span></span> 
    
<span data-ttu-id="392c3-225">В разделе [Задайте телефона, номера, находящимся на приглашает](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="392c3-225">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="setting-audio-conferencing-bridge-settings"></a><span data-ttu-id="392c3-226">Настройка параметров моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="392c3-226">Setting audio conferencing bridge settings</span></span>

 <span data-ttu-id="392c3-227">**Установка качества собрания при абонентов присоединиться к собранию**</span><span class="sxs-lookup"><span data-stu-id="392c3-227">**Set the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="392c3-228">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-229">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="392c3-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="392c3-230">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="392c3-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="392c3-231">В разделе **при присоединении к собраниям**выберите следующие действия:</span><span class="sxs-lookup"><span data-stu-id="392c3-231">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="392c3-232">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="392c3-232">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="392c3-233">Если снять этот флажок, пользователей, которые уже присоединились к собранию по умолчанию не будут уведомлены, когда кто-то или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="392c3-233">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="392c3-234">Это можно задать на основе собрания с собрания, если пользователь подключается к сеансу, с помощью Скайп для бизнеса или группами Майкрософт приложения и их изменение **объявлений при людей введите или оставьте** параметр Скайп собрания или группами Майкрософт **Параметры** меню собрания.</span><span class="sxs-lookup"><span data-stu-id="392c3-234">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="392c3-235">**ASK абонентов записать их имя перед присоединением к собранию** Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="392c3-235">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="392c3-236">Если снять этот флажок, вызывающие объекты не будет предложено записать их имя перед их присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="392c3-236">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="392c3-237">См. статью **Изменение параметров моста аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="392c3-237">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="392c3-238">Просмотрите, [Изменить параметры для моста аудиоконференции](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="392c3-238">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="392c3-239">**Задать длину ПИН-кода для собраний**</span><span class="sxs-lookup"><span data-stu-id="392c3-239">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="392c3-240">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-240">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-241">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="392c3-241">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="392c3-242">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="392c3-242">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="392c3-243">В разделе **Безопасность**введите количество цифр, которое необходимо использовать для ПИН-кода в списке **Длина ПИН-код** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="392c3-243">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="392c3-244">ПИН-код должен быть от 4 до 12 цифр.</span><span class="sxs-lookup"><span data-stu-id="392c3-244">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="392c3-245">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="392c3-245">The default is 5.</span></span>
    
<span data-ttu-id="392c3-246">Просмотрите, [Изменить параметры для моста аудиоконференции](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="392c3-246">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="392c3-247">**Включение или отключение электронной почты с передачей звука пользователей**</span><span class="sxs-lookup"><span data-stu-id="392c3-247">**Enable or disable email from being sent to audio users**</span></span>
  
1. <span data-ttu-id="392c3-248">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-248">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-249">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="392c3-249">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="392c3-250">На странице **параметров Microsoft моста** установите или снимите **автоматически отправлять сообщения электронной почты пользователям при их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="392c3-250">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="392c3-251">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="392c3-251">Click **Save**.</span></span>
    
    <span data-ttu-id="392c3-252">Также можно отправить электронной почты для пользователя с параметрами аудиоконференций, перейдя к свойствам аудиоконференций пользователя и нажав кнопку **Отправить сведения о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="392c3-252">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="392c3-253">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="392c3-253">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="392c3-254">Просмотр и установка основного и дополнительных языков для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="392c3-254">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="392c3-255">Просматривать и устанавливать основных и дополнительных языков звукового конференц-канала</span><span class="sxs-lookup"><span data-stu-id="392c3-255">See and set the primary and secondary languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="392c3-256">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-256">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-257">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="392c3-257">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="392c3-258">В **Скайп по центру администрирования бизнеса**, в левой области переходов перейдите к **аудиоконференции**и нажмите кнопку **моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="392c3-258">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="392c3-259">Выберите номер телефона в списке, нажмите кнопку **установить язык** в области действия и на странице **языков** выберите использование списке **основной язык** , чтобы просмотреть полный список поддерживаемых языков.</span><span class="sxs-lookup"><span data-stu-id="392c3-259">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="392c3-260">Также можно настроить основных и дополнительных языков, которые поддерживаются при выборе Microsoft в качестве поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="392c3-260">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="392c3-261">Порядок, в котором можно выбрать в списках является том же порядке, в котором будут представлены языков для вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="392c3-261">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="392c3-262">См. номера для аудиоконференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="392c3-262">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="392c3-263">Просмотра аудиоконференций телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="392c3-263">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="392c3-264">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-264">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-265">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="392c3-265">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="392c3-266">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **мост Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="392c3-266">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="392c3-267">Здесь можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="392c3-267">Here you can:</span></span>
    
  - <span data-ttu-id="392c3-268">Просмотр номера телефонов, установленных с Office 365 для использования для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="392c3-268">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="392c3-269">Просмотр расположения и основных и дополнительных языки, которые будут использоваться автосекретарем конференц-связи звука.</span><span class="sxs-lookup"><span data-stu-id="392c3-269">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="392c3-270">Выберите номер телефона по умолчанию, который будет предоставлен для пользователей, если они включены для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="392c3-270">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="392c3-271">Тем не менее при изменении номера телефона по умолчанию моста аудиоконференций не изменить номер телефона по умолчанию для существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="392c3-271">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="392c3-272">Можно перейти к **аудиоконференции** > **пользователей** и выберите Свойства пользователя, чтобы изменить значение по умолчанию, какой номер для пользователя, выбрав новый номер в списке чисел, которые доступны в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="392c3-272">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="392c3-273">В разделе [список номеров звук конференц-связи](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="392c3-273">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="392c3-274">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="392c3-274">See a list of users that are enabled</span></span>

1. <span data-ttu-id="392c3-275">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="392c3-275">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="392c3-276">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="392c3-276">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="392c3-277">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции**> и затем **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="392c3-277">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="392c3-278">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="392c3-278">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="392c3-279">Можно управлять определенными параметрами на уровне организации с использованием Windows PowerShell. Таким образом, упрощается применение параметров для всех пользователей. Далее представлены параметры на уровне организации:</span><span class="sxs-lookup"><span data-stu-id="392c3-279">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="392c3-280">Существует несколько параметров, которые можно управлять на уровне организации, с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="392c3-280">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="392c3-281">Это упрощает для применения параметров для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="392c3-281">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="392c3-282">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="392c3-282">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="392c3-283">Ниже приведены параметры на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="392c3-283">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="392c3-284">**Настройка уведомлений входа и выхода** Значение по умолчанию — _$true_.</span><span class="sxs-lookup"><span data-stu-id="392c3-284">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="392c3-285">**Параметр имя записи** Значение по умолчанию — _$true_.</span><span class="sxs-lookup"><span data-stu-id="392c3-285">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="392c3-286">**Установка длины ПИН-кода** Значение по умолчанию равно 5.</span><span class="sxs-lookup"><span data-stu-id="392c3-286">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="392c3-287">**Установка только телефонных собраний, с телефона** По умолчанию _$false_.</span><span class="sxs-lookup"><span data-stu-id="392c3-287">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="392c3-288">**Установка необходимость отправки электронной почты для пользователей** Значение по умолчанию — _$true_.</span><span class="sxs-lookup"><span data-stu-id="392c3-288">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="392c3-289">**Установка необходимость отправки электронной почты с другой учетной записи** Значение по умолчанию — _$false_.</span><span class="sxs-lookup"><span data-stu-id="392c3-289">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="392c3-290">**Установка адреса отправителя на электронной почты, которое отправляется пользователям** Значение по умолчанию — _$null_.</span><span class="sxs-lookup"><span data-stu-id="392c3-290">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="392c3-291">**Установка отображаемое имя для электронной почты, отправляемое пользователям** Значение по умолчанию — _$null_.</span><span class="sxs-lookup"><span data-stu-id="392c3-291">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="392c3-292">Чтобы получить дополнительные сведения о Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="392c3-292">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="392c3-p124">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="392c3-p124">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="392c3-296">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="392c3-296">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="392c3-297">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="392c3-297">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="392c3-p125">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="392c3-p125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="392c3-300">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="392c3-300">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="392c3-301">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="392c3-301">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="392c3-302">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="392c3-302">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="392c3-p126">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="392c3-p126">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="392c3-305">See also</span><span class="sxs-lookup"><span data-stu-id="392c3-305">Related topics</span></span>

[<span data-ttu-id="392c3-306">Управление настройками аудиоконференций для пользователя</span><span class="sxs-lookup"><span data-stu-id="392c3-306">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)

[<span data-ttu-id="392c3-307">Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="392c3-307">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
