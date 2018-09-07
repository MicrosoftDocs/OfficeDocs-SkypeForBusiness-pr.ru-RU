---
title: Сброс ПИН-кода аудиоконференций в Skype для бизнеса Online
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: 'Узнайте все, что нужно знать о ПИН-кодах и о том, как их сбросить в Skype для бизнеса Online. '
ms.openlocfilehash: 57431b51607f963f6dbd6da688e9bf7bd2758b53
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854298"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="e5e09-103">Сброс ПИН-кода аудиоконференций в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e5e09-103">Manage the Audio Conferencing settings for a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="e5e09-104">Информацию о сбросе ПИН-кодов аудиоконференций в Microsoft Teams см. в разделе [Сброс ПИН-кода аудиоконференций в Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="e5e09-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="e5e09-105">ПИН-код представляет собой числовой код, который создается для каждого пользователя Skype для бизнеса, имеющего возможность участия в аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="e5e09-105">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing.</span></span> <span data-ttu-id="e5e09-106">ПИН-коды аудиоконференций используют организаторы собраний для подтверждения статуса организатора собрания и запуска собрания по телефону.</span><span class="sxs-lookup"><span data-stu-id="e5e09-106">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="e5e09-107">При использовании для запуска собрания Skype для бизнеса ПИН-код не требуется.</span><span class="sxs-lookup"><span data-stu-id="e5e09-107">If they use the Skype for Business app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="e5e09-108">Если пользователь забыл свой ПИН-код, и ему не удается найти сообщение электронной почты, отправленное ему при предоставлении возможности участия в аудиоконференциях, администратор может выполнить сброс его ПИН-кода, или же он может изменить свой ПИН-код самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="e5e09-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="e5e09-109">Собрание начинается, когда аутентифицированный пользователь подключается с помощью приложения Skype для бизнеса или когда организатор подключается с использованием собственного ПИН-кода по телефону.</span><span class="sxs-lookup"><span data-stu-id="e5e09-109">Meetings can be started when an authenticated user joins using a Skype for Business client or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="e5e09-110">Если для участия в телефонном собрании требуется ПИН-код, то все пользователи, подключившиеся к этому собранию по телефону, перенаправляются в зал ожидания и могут прослушивать музыку до начала собрания.</span><span class="sxs-lookup"><span data-stu-id="e5e09-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="e5e09-111">Если организатор собрания не запрашивает ПИН-код при открытии собрания по телефону, то при подключении к собранию участникам не потребуется вводить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="e5e09-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="e5e09-112">Сброс ПИН-кода пользователя</span><span class="sxs-lookup"><span data-stu-id="e5e09-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="e5e09-113">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="e5e09-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e5e09-114">Выберите **центр администрирования Office 365** > **Skype для бизнеса** и в левой панели навигации щелкните **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="e5e09-114">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**.</span></span>
    
3. <span data-ttu-id="e5e09-115">На панели действий нажмите **Пользователи** и выберите пользователя, для которого требуется сбросить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="e5e09-115">Click on **Dial-in users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="e5e09-116">На панели действий в разделе **ПИН-код** нажмите **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="e5e09-116">In the Action pane, click **Reset PIN**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="e5e09-117">Сброс ПИН-кода пользователем</span><span class="sxs-lookup"><span data-stu-id="e5e09-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="e5e09-118">Пользователь может сбросить ПИН-код с помощью параметра **Сброс ПИН-кода** на странице **Конференц-связь с телефонным подключением**.</span><span class="sxs-lookup"><span data-stu-id="e5e09-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="e5e09-119">На эту страницу можно перейти одним из трех способов:</span><span class="sxs-lookup"><span data-stu-id="e5e09-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="e5e09-120">В браузере перейдите на страницу [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span><span class="sxs-lookup"><span data-stu-id="e5e09-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="e5e09-121">В Skype для бизнеса нажмите стрелку **Показать меню** рядом с пунктом **Параметры**, затем нажмите **Средства** > **Параметры конференц-связи с телефонным подключением**.</span><span class="sxs-lookup"><span data-stu-id="e5e09-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="e5e09-122">В Skype для бизнеса выберите **Параметры** и нажмите **Переадресация звонков** в меню слева, а затем в разделе **Дополнительные параметры вызовов** нажмите **Изменить параметры онлайн**.</span><span class="sxs-lookup"><span data-stu-id="e5e09-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="e5e09-123">Что еще необходимо знать о ПИН-кодах?</span><span class="sxs-lookup"><span data-stu-id="e5e09-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="e5e09-124">В целях безопасности ПИН-код отображается однократно и только для администратора, выполняющего сброс.</span><span class="sxs-lookup"><span data-stu-id="e5e09-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="e5e09-125">После сброса ПИН-кода он отображается в виде символов \*\*\*\*\*\*\*\*\*\*\* в Центре администрирования Skype для бизнеса и в области результатов при использовании **Get-CsCsOnlineDialInConfencingUser** в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5e09-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the Skype for Business admin center and in the results when they use **Get-CsCsOnlineDialInConfencingUser** in the Windows PowerShell.</span></span>
    
- <span data-ttu-id="e5e09-126">По умолчанию включена автоматическая отправка сообщений электронной почты пользователям; пользователи получают сообщение с ПИН-кодом при подключении к аудиоконференции или при сбросе ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="e5e09-126">Automatically sending emails to users is enabled by default and users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset. But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span> <span data-ttu-id="e5e09-127">Однако если автоматическая отправка писем отключена, сообщение о сбросе ПИН-кода не отправляется пользователю, и нужно отправить информацию о ПИН-коде пользователю вручную.</span><span class="sxs-lookup"><span data-stu-id="e5e09-127">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN to the user.</span></span>
    
- <span data-ttu-id="e5e09-p106">Когда начинается собрание, к нему автоматически присоединяются все пользователи, находящиеся в зале ожидания. Пример: если два участника попытаются присоединиться к собранию, когда оно еще не началось, эти участники будут перенаправлены в зал ожидания. Когда с телефона присоединяется организатор собрания под собственным ПИН-кодом, собрание начинается, и к нему подключаются все участники, находящиеся в зале ожидания.</span><span class="sxs-lookup"><span data-stu-id="e5e09-p106">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="e5e09-130">По умолчанию анонимные абоненты не могут начинать собрание.</span><span class="sxs-lookup"><span data-stu-id="e5e09-130">The default setting isn't to allow a meeting to be started by an anonymous callers.</span></span>
    
- <span data-ttu-id="e5e09-131">Когда пользователя приглашают на аудиоконференцию, он по умолчанию получает сообщение электронной почты с информацией о конференции и ПИН-кодом.</span><span class="sxs-lookup"><span data-stu-id="e5e09-131">When you enable a user for dial-in conferencing, by default they are sent emails that includes conferencing information and their PIN.</span></span> <span data-ttu-id="e5e09-132">Пользователю требуется почтовый ящик Office 365, так как при сбросе ПИН-кода новый ПИН-код отправляется на основной электронный адрес SMTP (псевдоним), назначенный этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="e5e09-132">The user must have an Office 365 mailbox because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="e5e09-133">При настройке аудиоконференций вы задаете цифры, которые должны быть включены в ПИН-коды в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e5e09-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="e5e09-134">ПИН-код может включать от 4 до 12 цифр; по умолчанию он составляет 5 цифр.</span><span class="sxs-lookup"><span data-stu-id="e5e09-134">The PIN can only be from 4 to 12 digits. The default is 5.</span></span> <span data-ttu-id="e5e09-135">При изменении длины ПИН-кода новое значение применяется только к новым ПИН-кодам и не применяется к ПИН-кодам для существующих пользователей, которым разрешено участие в аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="e5e09-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="e5e09-136">См. [Настройка длины PIN-кода для собраний с аудиоконференцией](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="e5e09-136">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="e5e09-137">Сообщение электронной почты по умолчанию будет отправлено на основной SMTP-адрес пользователя в Office 365.</span><span class="sxs-lookup"><span data-stu-id="e5e09-137">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="e5e09-138">Вы можете отправить сообщение электронной почты на адрес электронной почты, который не относится к Office 365, например, на портале Hotmail или MSN.</span><span class="sxs-lookup"><span data-stu-id="e5e09-138">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="e5e09-139">Используемый по умолчанию адрес электронной почты можно изменить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5e09-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="e5e09-140">Это полезно, если у пользователя нет почтового ящика Exchange в Office 365.</span><span class="sxs-lookup"><span data-stu-id="e5e09-140">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>
    
- <span data-ttu-id="e5e09-141">Чтобы переопределить используемый по умолчанию адрес электронной почты пользователя, администратор клиента может использовать следующий командлет: Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - sendemail действие - SendEmailToAddress «u@hotmail.com».</span><span class="sxs-lookup"><span data-stu-id="e5e09-141">To override the default user address where the email is sent to, the tenant admin can use the following cmdlet:  .</span></span> <span data-ttu-id="e5e09-142">Для переопределения адреса электронной почты пользователя требуется параметр SendEmail.</span><span class="sxs-lookup"><span data-stu-id="e5e09-142">The  SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e5e09-143">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5e09-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e5e09-144">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="e5e09-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="e5e09-145">Чтобы задать ПИН-код для Amos Marble, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e5e09-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="e5e09-p111">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="e5e09-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e5e09-149">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="e5e09-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e5e09-150">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5e09-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="e5e09-p112">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="e5e09-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="e5e09-153">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e5e09-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="e5e09-154">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e5e09-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e5e09-155">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e5e09-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="e5e09-p113">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="e5e09-p113">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e5e09-158">See also</span><span class="sxs-lookup"><span data-stu-id="e5e09-158">Related topics</span></span>

[<span data-ttu-id="e5e09-159">Сброс идентификатора конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="e5e09-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
