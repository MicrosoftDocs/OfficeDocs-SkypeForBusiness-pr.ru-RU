---
title: Включение и отключение отправки по электронной почте при изменении параметров звука конференц-связи в группах Майкрософт
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как включить или отключить Скайп может отправлять сообщения электронной почты для пользователей при изменении параметров, таких как ПИН-код или изменения номера конференц-связи по умолчанию в группах Microsoft. '
ms.openlocfilehash: a59553f26ee39e042fa28d9e58e7f5ae2aae21be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892504"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="9bc35-103">Включение и отключение отправки по электронной почте при изменении параметров звука конференц-связи в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9bc35-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="9bc35-104">Пользователи автоматически получают уведомления по электронной почте, если они активированы для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="9bc35-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="9bc35-105">Возможны ситуации, тем не менее, чтобы сократить число сообщений электронной почты, отправленных в Microsoft группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="9bc35-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="9bc35-106">В этом случае можно отключить функцию отправки сообщений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="9bc35-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="9bc35-107">Если отключить отправку сообщения электронной почты, аудиоконференций по электронной почте не будут отправлены для пользователей, в том числе по электронной почте для пользователей включены или отключены для аудиоконференций, когда сбросить свой ПИН-код, а идентификатор конференции и конференц-связи по умолчанию телефонный номер изменения .</span><span class="sxs-lookup"><span data-stu-id="9bc35-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="9bc35-108">Ниже приведен пример сообщений электронной почты, которое отправляется пользователям, когда они были включены для аудиоконференции:</span><span class="sxs-lookup"><span data-stu-id="9bc35-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Сообщение электронной почты относительно аудиоконференции](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="9bc35-110">Когда пользователи получают уведомления по электронной почте?</span><span class="sxs-lookup"><span data-stu-id="9bc35-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="9bc35-111">Существует несколько сообщений электронной почты, отправленных для пользователей в вашей организации после их, необходимо включить для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="9bc35-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="9bc35-112">При назначении пользователям лицензии **аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="9bc35-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="9bc35-113">При сбросе вручную аудиоконференций ПИН-код пользователя.</span><span class="sxs-lookup"><span data-stu-id="9bc35-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="9bc35-114">Выполнение сброса идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="9bc35-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="9bc35-115">Если удаляется лицензия  **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="9bc35-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="9bc35-116">Поставщик услуг аудиоконференций пользователя изменении корпорацией Майкрософт на другой поставщик или **Нет**.</span><span class="sxs-lookup"><span data-stu-id="9bc35-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="9bc35-117">При изменении поставщика аудиоконференций пользователя в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9bc35-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="9bc35-118">Включение или отключение сообщением электронной почты, отправляемые пользователями</span><span class="sxs-lookup"><span data-stu-id="9bc35-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="9bc35-119">Группами Майкрософт или Windows PowerShell можно использовать для включения или отключения электронной почты для пользователей.</span><span class="sxs-lookup"><span data-stu-id="9bc35-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="9bc35-120">![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="9bc35-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="9bc35-121">В левой области переходов, перейдите к **собраниям** > **Мостов конференции**.</span><span class="sxs-lookup"><span data-stu-id="9bc35-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9bc35-122">В верхней части страницы **Мостов конференции** нажмите кнопку **Параметры Bridge**.</span><span class="sxs-lookup"><span data-stu-id="9bc35-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9bc35-123">В области **Параметры Bridge** Включение или отключение **автоматически отправлять сообщения электронной почты пользователям при их параметров - связи**.</span><span class="sxs-lookup"><span data-stu-id="9bc35-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="9bc35-124">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="9bc35-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="9bc35-125">**С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9bc35-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="9bc35-126">В разделе [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="9bc35-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9bc35-127">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9bc35-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9bc35-p102">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="9bc35-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9bc35-131">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="9bc35-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9bc35-132">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bc35-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="9bc35-133">Дополнительные сведения о Windows PowerShell, [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="9bc35-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="9bc35-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="9bc35-134">Related topics</span></span>

[<span data-ttu-id="9bc35-135">Отправить пользователям при изменении их параметров звука конференц-связи по электронной почте</span><span class="sxs-lookup"><span data-stu-id="9bc35-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="9bc35-136">Отправка пользователям электронных писем с информацией о конференции с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="9bc35-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


