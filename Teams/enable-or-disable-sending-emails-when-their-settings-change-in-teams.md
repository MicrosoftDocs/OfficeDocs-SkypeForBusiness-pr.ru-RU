---
title: Включение и отключение отправки сообщений электронной почты при изменении настроек аудиоконференций в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Сведения о том, как включить или отключить в Skype отправку сообщений пользователям при изменении таких настроек, как ПИН-код или номер по умолчанию для конференц-связи в Microsoft Teams. '
ms.openlocfilehash: 0a86316fcc331e258eb13df73693f32b7ef21814
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494644"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="0dc82-103">Включение и отключение отправки сообщений электронной почты при изменении настроек аудиоконференций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0dc82-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="0dc82-104">Если пользователи активированы для участия в аудиоконференциях, они автоматически получают уведомление по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="0dc82-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="0dc82-105">В некоторых случаях потребуется сократить количество уведомлений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="0dc82-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="0dc82-106">Для этого можно отключить отправку сообщений.</span><span class="sxs-lookup"><span data-stu-id="0dc82-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="0dc82-107">Если отправка уведомлений по электронной почте отключена, пользователи не будут получать сообщения аудиоконференций, включая сообщения о разрешении/запрете на использование аудиоконференций, а также о сбросе ПИН-кода и изменении идентификатора конференции или телефонного номера для конференц-связи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0dc82-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="0dc82-108">Ниже приведен пример сообщения, отправляемого пользователям, для которых разрешены аудиоконференции:</span><span class="sxs-lookup"><span data-stu-id="0dc82-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Пример сообщения электронной почты о голосовой конференции](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="0dc82-110">Когда сообщения отправляются пользователям по электронной почте?</span><span class="sxs-lookup"><span data-stu-id="0dc82-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="0dc82-111">Когда пользователям в вашей организации разрешены аудиоконференции, им направляется несколько сообщений электронной почты в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="0dc82-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="0dc82-112">При назначении пользователям лицензии **аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="0dc82-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="0dc82-113">Сброс ПИН-кода аудиоконференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="0dc82-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="0dc82-114">Сброс идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="0dc82-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="0dc82-115">Если удаляется лицензия  **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="0dc82-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="0dc82-116">Изменение поставщика услуг аудиоконференций с Майкрософт на другого поставщика или на значение **Нет**.</span><span class="sxs-lookup"><span data-stu-id="0dc82-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="0dc82-117">Изменение поставщика услуг аудиоконференций на Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0dc82-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="0dc82-118">Включение или отключение отправки сообщения пользователям</span><span class="sxs-lookup"><span data-stu-id="0dc82-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="0dc82-119">Вы можете использовать Microsoft Teams или Windows PowerShell, чтобы включить или отключить отправку сообщения пользователям.</span><span class="sxs-lookup"><span data-stu-id="0dc82-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="0dc82-120">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0dc82-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0dc82-121">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="0dc82-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0dc82-122">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="0dc82-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="0dc82-123">В области **Настройки моста** включите или отключите настройку **Автоматически отправлять пользователям электронные письма при изменении их настроек телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="0dc82-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="0dc82-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0dc82-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="0dc82-125">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0dc82-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="0dc82-126">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="0dc82-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0dc82-127">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0dc82-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0dc82-p102">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="0dc82-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0dc82-131">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="0dc82-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0dc82-132">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dc82-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0dc82-133">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="0dc82-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="0dc82-134">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0dc82-134">Related topics</span></span>

[<span data-ttu-id="0dc82-135">Сообщения электронной почты, отправляемые пользователям при изменении их настроек аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="0dc82-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="0dc82-136">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="0dc82-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


