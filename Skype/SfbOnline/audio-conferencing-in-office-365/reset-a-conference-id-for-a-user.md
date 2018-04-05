---
title: Сброс идентификатора конференции для пользователя
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: 6cc73876d188f1ae00ec267e14af4771ded7b957
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="39711-103">Сброс идентификатора конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="39711-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="39711-104">При вашей организации не включен для идентификаторы динамических конференции, идентификатор статического конференции автоматически создается при включении Скайп для бизнеса или группами Майкрософт пользователя для конференц-связи звука, используя Microsoft в качестве поставщика.</span><span class="sxs-lookup"><span data-stu-id="39711-104">When your organizations hasn't been enabled for dynamic conference IDs, a static conference ID is automatically created when a Skype for Business or Microsoft Teams user is enabled for Audio Conferencing using Microsoft as the provider.</span></span> <span data-ttu-id="39711-105">Этот идентификатор конференции включен в нижней части приглашения, а также телефонные номера телефонов, можно использовать абонентов, чтобы позвонить собрание.</span><span class="sxs-lookup"><span data-stu-id="39711-105">This conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="39711-106">Когда пользователь набирает номер телефона, автосекретаря собрания запросит вызывающему введите этот идентификатор конференции, поэтому они могут участниками собрания.</span><span class="sxs-lookup"><span data-stu-id="39711-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39711-107">Если ваш поставщик конференц-связи Microsoft, идентификаторы пользователей конференции устанавливаются динамических только по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="39711-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="39711-108">К сожалению нельзя будет изменить его в Скайп для бизнеса центра администрирования или с помощью Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="39711-108">Unfortunately, you won't be able to change it in the Skype for Business Admin Center or using Windows Powershell.</span></span> <span data-ttu-id="39711-109">Необходимо обратиться в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="39711-109">You will have to contact Microsoft support.</span></span> 
  
<span data-ttu-id="39711-110">Статические идентификаторы используются в том случае, когда пользователи в вашей организации не требуется запомнить случайное число; их можно выбрать определенное число или использовать один, который легко запомнить.</span><span class="sxs-lookup"><span data-stu-id="39711-110">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="39711-111">При использовании идентификаторы динамических конференции каждого собрания, расписания пользователя будет присваивает идентификатор уникальный конференции.</span><span class="sxs-lookup"><span data-stu-id="39711-111">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="39711-112">Если вы хотите назначить динамических вместо статических конференции идентификаторы, [Перейдите сюда](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="39711-112">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="39711-113">Идентификаторы конференции только автоматически принимает только для Скайп для бизнеса и группами Майкрософт пользователям с поддержкой аудиоконференций с помощью Microsoft как их поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="39711-113">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing using Microsoft as their audio conferencing provider.</span></span> <span data-ttu-id="39711-114">Если необходимо выполнить сброс идентификатор конференции для пользователя, с использованием поставщика сторонних производителей аудиоконференций (ACP), необходимо вручную ввести идентификатор конференции на странице "Свойства" для пользователя.</span><span class="sxs-lookup"><span data-stu-id="39711-114">If you need to reset a conference ID for a user who is using a third-party audio conferencing provider (ACP), you will need to manually enter a conference ID on the properties page for the user.</span></span>
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="39711-115">Сброс идентификатор конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="39711-115">Resetting the conference ID for a user</span></span>

<span data-ttu-id="39711-116">**Использование групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="39711-116">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="39711-117">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="39711-117">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="39711-118">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="39711-118">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="39711-119">Щелкните меню рядом с пунктом **Мостов конференции**и нажмите кнопку **сбросить идентификатор конференции** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="39711-119">Click the menu next to **Conference Bridges**, and then click **Reset conference id** in the drop-down list.</span></span>

2. <span data-ttu-id="39711-120">В окне **сбросить идентификатор конференции** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="39711-120">In the **Reset conference id** window, click **Ok**.</span></span> <span data-ttu-id="39711-121">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="39711-121">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="39711-122">По умолчанию по электронной почте отправляются пользователям, но это может быть отключена.</span><span class="sxs-lookup"><span data-stu-id="39711-122">By default, emails are sent to users, but this can be turned off.</span></span>   

<span data-ttu-id="39711-123">**С помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="39711-123">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="39711-124">В **Скайп по центру администрирования бизнеса**, щелкните **аудиоконференции** > **пользователей**, выберите пользователя и нажмите кнопку **Сброс**в области действий в разделе **Идентификатор конференции** .</span><span class="sxs-lookup"><span data-stu-id="39711-124">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="39711-125">В **Сброс идентификатор конференции?** окно, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="39711-125">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="39711-126">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="39711-126">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="39711-127">По умолчанию по электронной почте отправляются пользователям, но это может быть отключена.</span><span class="sxs-lookup"><span data-stu-id="39711-127">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="39711-p107">После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции. В большинстве случаев это сообщение электронной почты отправляется на основной адрес электронной почты, которым, как правило, является почтовый ящик Office 365. Сообщение электронной почты содержит новый идентификатор конференции, номера телефонов для телефонного подключения по умолчанию и инструкции по использованию средства обновления для собраний Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="39711-p107">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="39711-131">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="39711-131">What else should I know?</span></span>

- <span data-ttu-id="39711-132">Можно отправить все сведения конференц-связи для пользователя в сообщение электронной почты, включая идентификатор конференции и телефонные номера телефонов, нажав кнопку **Отправить сведения о конференции по электронной почте** для пользователя в области действий.</span><span class="sxs-lookup"><span data-stu-id="39711-132">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="39711-133">ПИН-код не отправляется.</span><span class="sxs-lookup"><span data-stu-id="39711-133">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="39711-134">Идентификатор конференции будет содержать 7 символов, и не может изменить его длина Скайп для бизнеса центра администрирования или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39711-134">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="39711-135">После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="39711-135">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="39711-136">Идентификатор конференции для пользователя для аудиоконференций можно просматривать в нижней части области действий в разделе **Audio конференц-связи** , при выборе пользователем на странице " **Пользователи** ".</span><span class="sxs-lookup"><span data-stu-id="39711-136">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="39711-137">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="39711-137">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="39711-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="39711-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="39711-139">Пользователи могут использовать Скайп для бизнеса собрания средство для обновления их существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="39711-139">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="39711-140">Чтобы узнать, как для загрузки, установки и запуска Скайп для бизнеса средство обновления собрания, см.</span><span class="sxs-lookup"><span data-stu-id="39711-140">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="39711-141">Средство обновления для собраний Skype для бизнеса и Lync</span><span class="sxs-lookup"><span data-stu-id="39711-141">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="39711-142">Skype для бизнеса Online, инструмент переноса собраний (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="39711-142">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="39711-143">Skype для бизнеса Online, инструмент переноса собраний (32-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="39711-143">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="39711-144">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39711-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="39711-p110">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="39711-p110">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="39711-148">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="39711-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="39711-149">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="39711-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="39711-p111">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="39711-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="39711-152">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39711-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="39711-153">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="39711-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="39711-154">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="39711-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="39711-155">See also</span><span class="sxs-lookup"><span data-stu-id="39711-155">Related topics</span></span>

[<span data-ttu-id="39711-156">Сброс ПИН-кода аудиоконференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="39711-156">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
