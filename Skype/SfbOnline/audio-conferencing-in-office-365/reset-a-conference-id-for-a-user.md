---
title: Сброс идентификатор конференции для пользователя в Скайп для бизнеса в Интернет
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, действия, чтобы сбросить пользователя собрания идентификатор конференции в Скайп для бизнеса в Интернет и получения ссылки на средства обновления и миграции для собраний. '
ms.openlocfilehash: ac37d682d45b22eff61392ee05d7c369d67c3b67
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490538"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="a263a-103">Сброс идентификатор конференции для пользователя в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="a263a-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="a263a-104">Сведения о сбросе идентификатор конференции в группах Microsoft видеть [сбросить идентификатор конференции для пользователя в группах Майкрософт](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="a263a-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="a263a-105">Идентификатор динамических конференции включен в нижней части приглашения, а также телефонные номера телефонов, можно использовать абонентов, чтобы позвонить собрание.</span><span class="sxs-lookup"><span data-stu-id="a263a-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="a263a-106">Когда пользователь набирает номер телефона, автосекретаря собрания запросит вызывающему введите этот идентификатор конференции, поэтому они могут участниками собрания.</span><span class="sxs-lookup"><span data-stu-id="a263a-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a263a-107">Если ваш поставщик конференц-связи Microsoft, идентификаторы пользователей конференции устанавливаются динамических только по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a263a-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="a263a-108">К сожалению, существует возможность изменения в Скайп для бизнеса центра администрирования или с помощью Windows Powershell стать статическими, как это сейчас не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a263a-108">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span> <span data-ttu-id="a263a-109">Идентификаторы конференции автоматически принимает только для Скайп для бизнес-пользователей включена для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="a263a-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="a263a-110">Сброс идентификатор конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="a263a-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="a263a-111">В **Скайп по центру администрирования бизнеса**, щелкните **аудиоконференции** > **пользователей**, выберите пользователя и нажмите кнопку **Сброс**в области действий в разделе **Идентификатор конференции** .</span><span class="sxs-lookup"><span data-stu-id="a263a-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="a263a-112">В **Сброс идентификатор конференции?** окно, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="a263a-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="a263a-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="a263a-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="a263a-114">По умолчанию по электронной почте отправляются пользователям, но это может быть отключена.</span><span class="sxs-lookup"><span data-stu-id="a263a-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a263a-p104">После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции. В большинстве случаев это сообщение электронной почты отправляется на основной адрес электронной почты, которым, как правило, является почтовый ящик Office 365. Сообщение электронной почты содержит новый идентификатор конференции, номера телефонов для телефонного подключения по умолчанию и инструкции по использованию средства обновления для собраний Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a263a-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="a263a-118">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a263a-118">What else should I know?</span></span>

- <span data-ttu-id="a263a-119">Можно отправить все сведения конференц-связи для пользователя в сообщение электронной почты, включая идентификатор конференции и телефонные номера телефонов, нажав кнопку **Отправить сведения о конференции по электронной почте** для пользователя в области действий.</span><span class="sxs-lookup"><span data-stu-id="a263a-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="a263a-120">ПИН-код не отправляется.</span><span class="sxs-lookup"><span data-stu-id="a263a-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="a263a-121">Идентификатор конференции будет содержать 7 символов, и не может изменить его длина Скайп для бизнеса центра администрирования или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a263a-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="a263a-122">После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="a263a-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="a263a-123">Идентификатор конференции для пользователя для аудиоконференций можно просматривать в нижней части области действий в разделе **Audio конференц-связи** , при выборе пользователем на странице " **Пользователи** ".</span><span class="sxs-lookup"><span data-stu-id="a263a-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="a263a-124">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="a263a-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="a263a-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="a263a-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="a263a-126">Пользователи могут использовать Скайп для бизнеса собрания средство для обновления их существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="a263a-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="a263a-127">Чтобы узнать, как для загрузки, установки и запуска Скайп для бизнеса средство обновления собрания, см.</span><span class="sxs-lookup"><span data-stu-id="a263a-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="a263a-128">Средство обновления для собраний Skype для бизнеса и Lync</span><span class="sxs-lookup"><span data-stu-id="a263a-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="a263a-129">Skype для бизнеса Online, инструмент переноса собраний (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="a263a-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="a263a-130">Skype для бизнеса Online, инструмент переноса собраний (32-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="a263a-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a263a-131">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a263a-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a263a-p107">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="a263a-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a263a-135">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a263a-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a263a-136">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="a263a-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="a263a-p108">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="a263a-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="a263a-139">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a263a-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="a263a-140">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a263a-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a263a-141">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a263a-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="a263a-142">See also</span><span class="sxs-lookup"><span data-stu-id="a263a-142">Related topics</span></span>

[<span data-ttu-id="a263a-143">Сброс аудиоконференций ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="a263a-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
