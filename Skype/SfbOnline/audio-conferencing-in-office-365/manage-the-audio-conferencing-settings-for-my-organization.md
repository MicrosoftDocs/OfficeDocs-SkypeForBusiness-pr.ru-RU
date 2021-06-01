---
title: Управление параметрами аудиоконференций организации в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'См. Skype для бизнеса действий в Интернете, чтобы назначить пользователю лицензию на конференц-конференцию с телефонным доступом и ИД конференции, а также многие другие параметры конференц-конференции с телефонным доступом. '
ms.openlocfilehash: 3a0f6d37612c345c8561fbd2a64b4c90fdb27957
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237251"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="b1290-103">Управление параметрами аудиоконференций организации в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b1290-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="b1290-104">Для получения информации о том, как управлять этими параметрами с помощью Microsoft Teams, см. [Управление параметрами аудиоконференций для организаций в Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="b1290-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="b1290-105">Возможно, вам будет проще увидеть все параметры аудиоконференции для Skype для бизнеса в одном месте.</span><span class="sxs-lookup"><span data-stu-id="b1290-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="b1290-106">Назначение лицензии на аудиоконференцию</span><span class="sxs-lookup"><span data-stu-id="b1290-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="b1290-107">В Центре администрирования Skype для бизнеса **назначить лицензии нельзя.**</span><span class="sxs-lookup"><span data-stu-id="b1290-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="b1290-108">Для этого необходимо использовать Microsoft 365 администрирования.</span><span class="sxs-lookup"><span data-stu-id="b1290-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="b1290-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="b1290-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="b1290-110">**Назначение лицензии пользователю**</span><span class="sxs-lookup"><span data-stu-id="b1290-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="b1290-111">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-111">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-112">В левой области навигации Центра администрирования выберите Пользователи Активные пользователи , а затем выберите пользователя или пользователей из списка  >  доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b1290-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b1290-113">Если вы одновременно назначаете лицензии 20 пользователям, то можете  использовать в меню Выберите представление один из вариантов или создать собственное представление.</span><span class="sxs-lookup"><span data-stu-id="b1290-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="b1290-114">Нажмите на кнопку **Редактировать**, после чего, дважды нажмите на кнопку **Далее**, выделите лицензию и нажмите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="b1290-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="b1290-115">Для назначения лицензии нескольким пользователям можно также воспользоваться Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="b1290-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="b1290-116">Для ознакомления с инструкцией и примерами скриптов PowerShell см. [Назначение лицензий в Skype для бизнеса](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="b1290-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="b1290-117">На панели действий в разделе **Лицензии на продукты** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b1290-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="b1290-118">На странице **Лицензии на продукты** включите функцию **Аудиконференции**, а затем нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b1290-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="b1290-119">Дополнительные о лицензировании см. в Skype для бизнеса [лицензировании надстройки.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="b1290-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b1290-120">После назначения лицензии корпорация Майкрософт может не отображаться в списке в качестве поставщика услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="b1290-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="b1290-121">В этом случае выйдите из Центра администрирования или нажмите CTRL+F5, чтобы обновить окно браузера.</span><span class="sxs-lookup"><span data-stu-id="b1290-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="b1290-122">Включить или отключить сообщения электронной почты, отправленные пользователям аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="b1290-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="b1290-123">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="b1290-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="b1290-124">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-124">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-125">Перейдите в центр администрирования > **Skype для бизнеса** навигации слева щелкните Аудиоконференция. </span><span class="sxs-lookup"><span data-stu-id="b1290-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="b1290-126">На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="b1290-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="b1290-127">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b1290-127">Click **Save**.</span></span>

    <span data-ttu-id="b1290-128">Вы также можете отправлять электронные письма пользователю с помощью параметров аудиоконференции, перейдите к его свойствам аудиоконференции и выберите Отправить сведения о конференции по электронной **почте**.</span><span class="sxs-lookup"><span data-stu-id="b1290-128">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="b1290-129">В приглашение на собрание включаются код конференции и номер телефона для аудиоконференции по умолчанию, но не ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="b1290-129">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="b1290-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="b1290-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="b1290-131">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b1290-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="b1290-132">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="b1290-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="b1290-133">С помощью [set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) можно управлять другими настройками для организации, включая электронную почту.</span><span class="sxs-lookup"><span data-stu-id="b1290-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="b1290-134">Изменение контактных данных отправитель в сообщениях электронной почты, отправленных пользователям</span><span class="sxs-lookup"><span data-stu-id="b1290-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="b1290-135">В сообщение, которое отправляется пользователям автоматически, можно внести изменения, включив в него фактический адрес электронной почты и отобразив имя отправителя в составе контактной информации.</span><span class="sxs-lookup"><span data-stu-id="b1290-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="b1290-136">По умолчанию отправитель сообщений — Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемого имени с помощью Windows PowerShell [и cmdlet Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="b1290-136">By default, the sender of the emails is Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="b1290-137">Чтобы изменить адрес электронной почты, отправляемый пользователям, необходимо:</span><span class="sxs-lookup"><span data-stu-id="b1290-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="b1290-138">Введите адрес электронной почты в параметр _SendEmailFromAddress._</span><span class="sxs-lookup"><span data-stu-id="b1290-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="b1290-139">Введите отображаемое имя в параметр  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="b1290-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="b1290-140">Присвойте параметру _SendEmailOverride_ значение _True_.</span><span class="sxs-lookup"><span data-stu-id="b1290-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="b1290-141">Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b1290-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="b1290-142">Чтобы изменить адрес электронной почты, нужно убедиться в том, что применяемая организацией политика входящих сообщений позволяет принимать сообщения, отправленные с настраиваемого адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b1290-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="b1290-143">Для управления другими настройками организации, включая электронную почту, можно использовать [set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="b1290-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="b1290-144">См. [сообщения электронной почты, которые](emails-sent-to-users-when-their-settings-change.md)автоматически отправляются пользователям при изменении их параметров аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="b1290-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="b1290-145">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="b1290-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="b1290-146">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-146">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-147">Перейдите в центр администрирования > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b1290-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="b1290-148">На панели навигации слева в **центре администрирования Skype для бизнеса** перейдите к секции **Аудиоконференции** и на панели действий в области **Идентификатор конференции** нажмите на кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="b1290-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="b1290-149">В **окне Сбросить ИД конференции?** нажмите кнопку **Да.**</span><span class="sxs-lookup"><span data-stu-id="b1290-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="b1290-150">При этом будет автоматически создан идентификатор конференции и, если функция отправки сообщений включена, пользователям будут отправлены сообщения с новым идентификатором конференции.</span><span class="sxs-lookup"><span data-stu-id="b1290-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="b1290-151">По умолчанию эта настройка остается включенной.</span><span class="sxs-lookup"><span data-stu-id="b1290-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="b1290-152">После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов.</span><span class="sxs-lookup"><span data-stu-id="b1290-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="b1290-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="b1290-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="b1290-154">Пользователи могут использовать средство переноса Skype для бизнеса собраний для обновления существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="b1290-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="b1290-155">Чтобы узнать, как скачать, установить и запустить средство обновления собраний Skype для бизнеса, см. средства обновления собраний для Skype для бизнеса и [Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), Skype для бизнеса Online, Средство переноса собраний [(64-битная версия)](https://go.microsoft.com/fwlink/?LinkID=626047)и Skype для бизнеса Online, Средство переноса собраний [(32-битная версия).](https://www.microsoft.com/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="b1290-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="b1290-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="b1290-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="b1290-157">Reset a conference organizer's PIN</span><span class="sxs-lookup"><span data-stu-id="b1290-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="b1290-158">Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="b1290-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="b1290-159">Хотя ИД конференции будет автоматически создан и назначен пользователю, иногда пользователь не хочет использовать этот номер и хочет установить определенное число, или пользователи не могут вспомнить или потеряли свой ИД конференции.</span><span class="sxs-lookup"><span data-stu-id="b1290-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="b1290-160">Войдите в административную панель Skype для бизнеса и Windows PowerShell для просмотра, изменения и сброса идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="b1290-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="b1290-161">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-161">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-162">Перейдите в центр администрирования > **Skype для бизнеса** навигации слева щелкните Аудиоконференция. </span><span class="sxs-lookup"><span data-stu-id="b1290-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="b1290-163">**Щелкните** Пользователи и выберите пользователя, для который вы хотите сбросить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="b1290-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="b1290-164">В области действий в области **ПИН-код** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="b1290-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="b1290-165">Пользователи получат сообщение электронной почты со своим ПИН-кодом, если у них включена аудиоконференция или при сбросе ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="b1290-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="b1290-166">Но если вы отключили автоматическое отправку сообщений электронной почты, сообщение об сбросе ПИН-кода отправляться не будет и вам придется вручную отправлять ПИН-код пользователю.</span><span class="sxs-lookup"><span data-stu-id="b1290-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="b1290-167">The PIN will only be shown once after it has been reset.</span><span class="sxs-lookup"><span data-stu-id="b1290-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="b1290-168">После сброса ПИН-код больше не будет отображаться в свойствах пользователя. вместо этого будут показаны \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="b1290-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="b1290-169">См. [сброс ПИН-кода аудиоконференции.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="b1290-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="b1290-170">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="b1290-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="b1290-171">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-171">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-172">Перейдите в центр администрирования > **Skype для бизнеса** навигации слева щелкните Аудиоконференция. </span><span class="sxs-lookup"><span data-stu-id="b1290-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="b1290-173">**Щелкните** Пользователи и выберите пользователя, для который вы хотите сбросить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="b1290-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="b1290-174">На панели действий щелкните **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="b1290-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b1290-175">При этом ПИН-код аудиоконференции не отправляется пользователю.</span><span class="sxs-lookup"><span data-stu-id="b1290-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="b1290-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="b1290-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="b1290-177">Настройка номеров телефонов, включенных в приглашения</span><span class="sxs-lookup"><span data-stu-id="b1290-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="b1290-178">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-178">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-179">Перейдите в центр администрирования > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b1290-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="b1290-180">В панели навигации слева перейдите к секции **Аудиоконференции** > **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="b1290-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="b1290-181">Выберите пользователя, для который вы хотите включить аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="b1290-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="b1290-182">На панели «Действия» можно указать **Платный номер** и, если разрешено, **Бесплатный номер**.</span><span class="sxs-lookup"><span data-stu-id="b1290-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="b1290-183">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b1290-183">Click **Save**.</span></span>

<span data-ttu-id="b1290-184">См. [настройка номеров телефонов, включенных в приглашения.](set-the-phone-numbers-included-on-invites.md)</span><span class="sxs-lookup"><span data-stu-id="b1290-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="b1290-185">Выбор параметров моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="b1290-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="b1290-186">**Настройка окна собраний, когда звонит на собрание**</span><span class="sxs-lookup"><span data-stu-id="b1290-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="b1290-187">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-187">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-188">Перейдите в центр администрирования > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b1290-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="b1290-189">В центре **администрирования** Skype для бизнеса навигации слева перейдите в параметры моста Аудиоконференция   >  **Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="b1290-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="b1290-190">В **области Присоединиться к собранию** выберите следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b1290-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="b1290-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="b1290-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="b1290-192">Если этот режим не засвещен, пользователи, которые уже присоединились к собранию по умолчанию, не будут уведомлены о том, что кто-то вошел в собрание или покинул его.</span><span class="sxs-lookup"><span data-stu-id="b1290-192">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="b1290-193">Этот параметр можно настроить на основе собрания по собранию, если пользователь присоединяется к собранию с помощью приложения Skype для бизнеса и может  изменить параметр Объявлять при входе или выходе пользователей в меню Параметры Skype собрания собрания. </span><span class="sxs-lookup"><span data-stu-id="b1290-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="b1290-194">**Попросите звоняющих записать свое имя перед присоединением к собранию** Этот выбор выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1290-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="b1290-195">Если снять этот флажок, то предложение записать свое имя перед присоединением к собранию пользователям, совершающим вызов, не поступает.</span><span class="sxs-lookup"><span data-stu-id="b1290-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="b1290-196">См. статью **Изменение параметров моста аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="b1290-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="b1290-197">См. [статью Изменение](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)параметров моста аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="b1290-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="b1290-198">**Настройка длины ПИН-кода для собраний**</span><span class="sxs-lookup"><span data-stu-id="b1290-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="b1290-199">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-199">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-200">Перейдите в центр администрирования > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b1290-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="b1290-201">В центре **администрирования** Skype для бизнеса навигации слева перейдите в параметры моста Аудиоконференция   >  **Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="b1290-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="b1290-202">В **списке** Безопасность введите в списке длина  ПИН-кода нужное число цифр и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b1290-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="b1290-203">ПИН-код должен включать в себя от 4 до 12 цифр.</span><span class="sxs-lookup"><span data-stu-id="b1290-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="b1290-204">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="b1290-204">The default is 5.</span></span>
    
<span data-ttu-id="b1290-205">См. [статью Изменение](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)параметров моста аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="b1290-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="b1290-206">**Включить или отключить отправку электронной почты пользователям со звуком**</span><span class="sxs-lookup"><span data-stu-id="b1290-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="b1290-207">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-207">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-208">Перейдите в центр администрирования > **Skype для бизнеса** навигации слева щелкните Аудиоконференция. </span><span class="sxs-lookup"><span data-stu-id="b1290-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="b1290-209">На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="b1290-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="b1290-210">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b1290-210">Click **Save**.</span></span>

    <span data-ttu-id="b1290-211">Вы также можете отправить сообщение электронной почты пользователю с помощью параметров аудиоконференции. Для этого перейдите к его свойствам аудиоконференции и выберите отправить сведения о конференции по электронной **почте.**</span><span class="sxs-lookup"><span data-stu-id="b1290-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="b1290-212">В этом случае, пользователям отправляются сообщения, содержащие идентификатор конференции и номер телефона, но не включающие в себя ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="b1290-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="b1290-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="b1290-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="b1290-214">См. и установите основной (по умолчанию) и дополнительный (альтернативный) языки на мосте аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="b1290-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="b1290-215">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-215">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-216">Перейдите в центр администрирования > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b1290-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="b1290-217">В центре **Skype для бизнеса** администрирования на левой навигации перейдите в аудиоконференцию **,** а затем щелкните Мост **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b1290-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="b1290-218">Выберите номер телефона в списке, нажмите кнопку Выбрать языки  в области действий,  а затем на странице Выбор языков щелкните список Использовать основной язык, чтобы просмотреть полный список поддерживаемых языков. </span><span class="sxs-lookup"><span data-stu-id="b1290-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="b1290-219">Вы также можете выбрать основной и дополнительный языки, которые поддерживаются при выборе Майкрософт в качестве поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="b1290-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="b1290-220">Языки отображаются для участников конференции в том порядке, в котором они выбираются из списков.</span><span class="sxs-lookup"><span data-stu-id="b1290-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="b1290-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="b1290-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="b1290-222">См. номера для аудиоконференции с телефонным номером</span><span class="sxs-lookup"><span data-stu-id="b1290-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="b1290-223">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-223">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-224">Перейдите в центр администрирования > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b1290-224">Go to the admin center > **Skype for Business**.</span></span>
 
3. <span data-ttu-id="b1290-225">В центре **Skype для бизнеса** на левой навигации перейдите к мосту Microsoft **Audio Conferencing**  >  .</span><span class="sxs-lookup"><span data-stu-id="b1290-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="b1290-226">Здесь вы можете:</span><span class="sxs-lookup"><span data-stu-id="b1290-226">Here you can:</span></span>

   - <span data-ttu-id="b1290-227">Просмотр телефонных номеров, которые Microsoft 365 или Office 365 для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="b1290-227">View the phone numbers that are set by Microsoft 365 or Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="b1290-228">Просмотреть расположение, основной и дополнительный языки, которые будут использоваться автоконферентором аудиоконференации.</span><span class="sxs-lookup"><span data-stu-id="b1290-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="b1290-229">Выберите номер телефона по умолчанию, который будет предоставлен пользователям, если для них включена аудиоконференция.</span><span class="sxs-lookup"><span data-stu-id="b1290-229">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="b1290-230">Однако если номер телефона по умолчанию для моста аудиоконференций изменится, номер телефона по умолчанию для существующих пользователей не изменится.</span><span class="sxs-lookup"><span data-stu-id="b1290-230">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="b1290-231">Вы можете перейти в статью Пользователи аудиоконференции и выбрать свойства пользователя, чтобы изменить номер по умолчанию для пользователя, выбрав новый номер из списка доступных в организации  >   номеров.</span><span class="sxs-lookup"><span data-stu-id="b1290-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="b1290-232">См. [список номеров аудиоконференций.](see-a-list-of-audio-conferencing-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="b1290-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="b1290-233">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="b1290-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="b1290-234">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b1290-234">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="b1290-235">Перейдите в центр администрирования > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b1290-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="b1290-236">В центре **Skype для бизнеса** на левой навигации перейдите  в меню Аудиоконференция> **пользователи**.</span><span class="sxs-lookup"><span data-stu-id="b1290-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="b1290-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="b1290-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b1290-238">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1290-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="b1290-239">На уровне организации можно управлять несколькими настройками с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1290-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="b1290-240">Это упрощает применение параметров для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="b1290-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="b1290-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="b1290-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span></span>

<span data-ttu-id="b1290-242">Ниже параметров на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="b1290-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="b1290-243">**Настройка уведомлений о входе и выходе** Значением по умолчанию является _$true_.</span><span class="sxs-lookup"><span data-stu-id="b1290-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="b1290-244">**Настройка записи имени** Значением по умолчанию является _$true_.</span><span class="sxs-lookup"><span data-stu-id="b1290-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="b1290-245">**Настройка длины ПИН-кода** Значение по умолчанию равно 5.</span><span class="sxs-lookup"><span data-stu-id="b1290-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="b1290-246">**Настройка с телефона только для собраний с телефонным подключением** Значением по умолчанию является _$false_.</span><span class="sxs-lookup"><span data-stu-id="b1290-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="b1290-247">**Настройки отправки сообщений пользователям** Значением по умолчанию является _$true_.</span><span class="sxs-lookup"><span data-stu-id="b1290-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="b1290-248">**Настройка отправки сообщений с другой учетной записи** Значением по умолчанию является _$false_.</span><span class="sxs-lookup"><span data-stu-id="b1290-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="b1290-249">**Настройка адреса отправителя в сообщениях, отправляемых пользователям** Значением по умолчанию является _$null_.</span><span class="sxs-lookup"><span data-stu-id="b1290-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="b1290-250">**Настройка имени, отображаемого в сообщениях, отправляемых пользователям** Значением по умолчанию является _$null_.</span><span class="sxs-lookup"><span data-stu-id="b1290-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b1290-251">Хотите узнать больше о Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1290-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="b1290-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="b1290-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b1290-253">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="b1290-253">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="b1290-254">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="b1290-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="b1290-255">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1290-255">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="b1290-256">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="b1290-256">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

- <span data-ttu-id="b1290-257">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="b1290-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="b1290-258">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="b1290-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="b1290-259">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b1290-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="b1290-260">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b1290-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="b1290-261">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b1290-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    <span data-ttu-id="b1290-p121">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="b1290-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1290-264">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b1290-264">Related topics</span></span>

[<span data-ttu-id="b1290-265">Управление настройками аудиоконференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="b1290-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)
