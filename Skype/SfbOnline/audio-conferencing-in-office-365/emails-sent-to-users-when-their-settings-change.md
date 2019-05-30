---
title: Сообщения электронной почты, отправляемые пользователям при изменении их параметров в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Сведения о том, какие данные автоматически отправляются пользователям по электронной почте при изменении настроек конференц-связи с телефонным подключением в Skype для бизнеса Online. '
ms.openlocfilehash: acdc16a1af2666dcb84599fae31a910be83ac08f
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494289"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="c1f72-103">Сообщения электронной почты, отправляемые пользователям при изменении их параметров в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c1f72-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="c1f72-104">Если вы ищете автоматические данные электронной почты в Microsoft Teams, просмотрите [сообщения, отправляемые пользователям при изменении их параметров в Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="c1f72-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="c1f72-105">Пользователи, которым разрешено использовать [голосовую конференцию](set-up-audio-conferencing.md) с помощью Microsoft в качестве поставщика видеоконференций, смогут автоматически отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="c1f72-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="c1f72-106">По умолчанию существует четыре типа сообщений электронной почты, которые будут отправляться пользователям, которым разрешено использовать голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="c1f72-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="c1f72-107">Однако если вы хотите ограничить количество сообщений электронной почты, отправляемых пользователям, вы можете отключить его.</span><span class="sxs-lookup"><span data-stu-id="c1f72-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="c1f72-108">Голосовая связь в Office 365 отправляет сообщение электронной почты пользователям, когда:</span><span class="sxs-lookup"><span data-stu-id="c1f72-108">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="c1f72-109">**Им назначена лицензия на голосовую конференцию или при смене поставщика видеоконференций на Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="c1f72-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="c1f72-110">Это сообщение содержит идентификатор конференции, номер телефона конференции по умолчанию для собраний, ПИН-код для голосовой конференции для пользователя, а также инструкции и ссылка на средство обновления собрания Skype для бизнеса Online, которое используется для обновления существующих собраний для пользователям.</span><span class="sxs-lookup"><span data-stu-id="c1f72-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="c1f72-111">В разделе [Назначение лицензий Skype для бизнеса](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) или [назначение Microsoft в качестве поставщика](assign-microsoft-as-the-audio-conferencing-provider.md)видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="c1f72-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c1f72-112">Если в вашей организации разрешены динамические идентификаторы конференций, все собранные собрания пользователя будут иметь уникальные идентификаторы конференций.</span><span class="sxs-lookup"><span data-stu-id="c1f72-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="c1f72-113">Вы можете настроить [динамические идентификаторы голосовой конференции в Организации](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c1f72-113">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="c1f72-114">Вот пример этого сообщения:</span><span class="sxs-lookup"><span data-stu-id="c1f72-114">Here is an example of this email:</span></span>
    
     ![Проверка лицензий в Skype для бизнеса](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="c1f72-116">Дополнительные сведения о лицензировании Skype для бизнеса можно найти в подлицензировании [надстроек Skype для бизнеса](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c1f72-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="c1f72-117">**Идентификатор конференции или телефонный номер конференции по умолчанию для пользователя меняется.**</span><span class="sxs-lookup"><span data-stu-id="c1f72-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="c1f72-118">Это сообщение содержит идентификатор конференции, номер телефона конференции по умолчанию, а также инструкции и ссылка для использования средства обновления собрания Skype для бизнеса Online, которое используется для обновления существующих собраний для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1f72-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="c1f72-119">Но этот адрес электронной почты не включает ПИН-код для голосовой конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1f72-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="c1f72-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c1f72-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c1f72-121">Если в вашей организации разрешены динамические идентификаторы конференций, все собранные собрания пользователя будут иметь уникальные идентификаторы конференций.</span><span class="sxs-lookup"><span data-stu-id="c1f72-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="c1f72-122">Вы можете настроить [динамические идентификаторы голосовой конференции в Организации](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c1f72-122">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="c1f72-123">Вот пример этого сообщения:</span><span class="sxs-lookup"><span data-stu-id="c1f72-123">Here is an example of this email:</span></span>
    
     ![Изменились сведения о конференц-связи с телефонным подключением.](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="c1f72-125">**ПИН-код голосовой конференции пользователя сброшен.**</span><span class="sxs-lookup"><span data-stu-id="c1f72-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="c1f72-126">Это сообщение включает ПИН-код голосовой конференции организатора, существующий идентификатор конференции и телефонный номер конференции по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1f72-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="c1f72-127">Посмотрите [, как сбросить ПИН-код голосовых конференций](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="c1f72-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c1f72-128">Если в вашей организации разрешены динамические идентификаторы конференций, все собранные собрания пользователя будут иметь уникальные идентификаторы конференций.</span><span class="sxs-lookup"><span data-stu-id="c1f72-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="c1f72-129">Вы можете настроить [динамические идентификаторы голосовой конференции в Организации](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c1f72-129">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="c1f72-130">Вот пример этого сообщения:</span><span class="sxs-lookup"><span data-stu-id="c1f72-130">Here is an example of this email:</span></span>
    
     ![КОНТАКТ для конференц-связи с телефонным подключением изменен.](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="c1f72-132">**Лицензия пользователя удалена или в случае изменения поставщика услуг голосовой связи от корпорации Майкрософт на другого поставщика или нет.**</span><span class="sxs-lookup"><span data-stu-id="c1f72-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="c1f72-133">Это происходит, когда \*\*\*\* лицензия на голосовую конференцию удаляется от пользователя или при смене поставщика видеоконференций от корпорации Майкрософт на стороннего поставщика голосовой конференц-связи или при установке провайдера на **None (нет**).</span><span class="sxs-lookup"><span data-stu-id="c1f72-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="c1f72-134">В этом сообщении содержатся инструкции и сведения о том, как использовать средство обновления собрания Skype для бизнеса Online для удаления данных, связанных с голосовой связью, например номера телефона конференции по умолчанию или идентификатора Конференции.</span><span class="sxs-lookup"><span data-stu-id="c1f72-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="c1f72-135">Ознакомьтесь с разназначением [и удалением лицензий для Office 365 для бизнеса](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c1f72-135">See [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="c1f72-136">Вот пример этого сообщения:</span><span class="sxs-lookup"><span data-stu-id="c1f72-136">Here is an example of this email:</span></span>
    
     ![Конференц-связь с телефонным подключением отключена.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="c1f72-138">Внесение изменений в сообщения электронной почты, отправленные им</span><span class="sxs-lookup"><span data-stu-id="c1f72-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="c1f72-139">Вы можете вносить изменения в сообщение электронной почты, которое автоматически отправляется пользователям, включая адрес электронной почты и отображаемое имя, которое входит \*\* в состав контактной информации.</span><span class="sxs-lookup"><span data-stu-id="c1f72-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="c1f72-140">По умолчанию отправитель сообщений электронной почты отправляется из Office 365, но вы можете изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell и командлета [Set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="c1f72-140">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="c1f72-141">Чтобы внести изменения в адрес электронной почты, который отправляет пользователям сообщение электронной почты, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="c1f72-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="c1f72-142">Введите адрес электронной почты в параметр  _SendEmailFromAddress_.</span><span class="sxs-lookup"><span data-stu-id="c1f72-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="c1f72-143">Введите отображаемое имя в параметр  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="c1f72-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="c1f72-144">Установите для параметра _сендемаиловерриде_ значение _true_.</span><span class="sxs-lookup"><span data-stu-id="c1f72-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="c1f72-145">Вы можете внести изменения в сообщения, отправляемые пользователям, например адрес электронной почты, с которого отправляется сообщение электронной почты, и отображаемое имя для сообщения, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c1f72-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="c1f72-146">Если вы хотите изменить адрес электронной почты, необходимо убедиться в том, что политики входящей электронной почты для вашей среды допускают письма, полученные из специального адреса.</span><span class="sxs-lookup"><span data-stu-id="c1f72-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="c1f72-147">Если вы решите переопределить данные *из* контактных данных, убедитесь, что они правильно отправлены пользователям.</span><span class="sxs-lookup"><span data-stu-id="c1f72-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="c1f72-148">Это можно сделать, проверив это с одним пользователем в Организации.</span><span class="sxs-lookup"><span data-stu-id="c1f72-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="c1f72-149">Вы можете использовать командлет [Set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) для управления другими настройками организации, включая электронную почту.</span><span class="sxs-lookup"><span data-stu-id="c1f72-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="c1f72-150">Что делать, если вы не хотите отправлять электронную почту?</span><span class="sxs-lookup"><span data-stu-id="c1f72-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="c1f72-151">Когда вы отключаете отправку сообщений электронной почты пользователям, электронная почта не отправляется, даже если пользователю назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="c1f72-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="c1f72-152">В этом случае идентификатор конференции, номер телефона конференц-связи по умолчанию и, что важнее, ПИН-код для Конференции с голосовой связью не будет отправлен пользователю.</span><span class="sxs-lookup"><span data-stu-id="c1f72-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="c1f72-153">В этом случае необходимо сообщить пользователю, отправив ему отдельное сообщение электронной почты или позвонив по нему.</span><span class="sxs-lookup"><span data-stu-id="c1f72-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="c1f72-154">По умолчанию сообщения будут отправляться пользователям, но если вы не хотите, чтобы они могли получать электронную почту для голосовой конференции, вы можете использовать центр администрирования Skype для бизнеса или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1f72-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="c1f72-155">![Значок, показывающий логотип](../images/sfb-logo-30x30.png)Skype для бизнеса **, с помощью центра администрирования Skype для бизнеса**  </span><span class="sxs-lookup"><span data-stu-id="c1f72-155">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="c1f72-156">В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите к разделу**Настройка моста**видеоконференций \*\*\*\* > Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c1f72-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="c1f72-157">На странице **Параметры моста Microsoft** установите или снимите флажок **автоматически отправлять электронные письма пользователям при изменении параметров голосовой конференции**.</span><span class="sxs-lookup"><span data-stu-id="c1f72-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="c1f72-158">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c1f72-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="c1f72-159">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c1f72-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="c1f72-160">Чтобы отключить отправку сообщений электронной почты для всех пользователей, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c1f72-160">Run the following to disable sending all of your users email:</span></span>
    
   ```
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

<span data-ttu-id="c1f72-161">Вы можете использовать командлет [Set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) для управления другими настройками организации, включая электронную почту.</span><span class="sxs-lookup"><span data-stu-id="c1f72-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="c1f72-162">Что еще необходимо знать о таких сообщениях?</span><span class="sxs-lookup"><span data-stu-id="c1f72-162">What else should you know about this email?</span></span>

- <span data-ttu-id="c1f72-163">Дополнительные сведения о включении и отключении автоматической отправки электронной почты пользователям можно найти в разделе [Включение и отключение отправки сообщений при изменении параметров голосовой конференции](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="c1f72-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="c1f72-164">Иногда пользователи теряют свои аудиофайлы и вам нужно отправить им все свои звуковые данные.</span><span class="sxs-lookup"><span data-stu-id="c1f72-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="c1f72-165">Это можно сделать с помощью центра администрирования Skype для бизнеса и выбрав команду **отправить сведения о конференции по электронной почте** в свойствах голосовой конференции для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1f72-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="c1f72-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="c1f72-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="c1f72-167">Однако эти данные не включают ПИН-код голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c1f72-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="c1f72-168">Вот пример сообщения электронной почты, которое будет отправлено таким образом:</span><span class="sxs-lookup"><span data-stu-id="c1f72-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![Сообщение о конференц-связи с телефонным подключением](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c1f72-170">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1f72-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c1f72-171">По умолчанию отправитель сообщений электронной почты отправляется из Office 365, но вы можете изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell и командлета [Set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="c1f72-171">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span>
    
- <span data-ttu-id="c1f72-p113">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="c1f72-p113">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c1f72-175">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="c1f72-175">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c1f72-176">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1f72-176">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c1f72-p114">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c1f72-p114">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="c1f72-179">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c1f72-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c1f72-180">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c1f72-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c1f72-181">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c1f72-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="c1f72-p115">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="c1f72-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c1f72-184">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c1f72-184">Related topics</span></span>

[<span data-ttu-id="c1f72-185">Включение и отключение отправки писем при смене настроек аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="c1f72-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="c1f72-186">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="c1f72-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
