---
title: Сброс ПИН-кода голосовой конференции в Skype для бизнеса Online
ms.author: tonysmit
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте о том, что нужно знать о контактах и о том, как сбросить их в Skype для бизнеса Online. '
ms.openlocfilehash: ca2bbef02b0c6ecdefef700ca316188f5c544070
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792281"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="2d2af-103">Сброс ПИН-кода голосовой конференции в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2d2af-103">Reset the Audio Conferencing PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="2d2af-104">Информацию о сбросе ПИН-кодов аудиоконференций в Microsoft Teams см. в разделе [Сброс ПИН-кода аудиоконференций в Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="2d2af-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="2d2af-p101">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing. Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone. If they use the Skype for Business app to start the meeting, a PIN isn't required. If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span><span class="sxs-lookup"><span data-stu-id="2d2af-p101">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing. Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone. If they use the Skype for Business app to start the meeting, a PIN isn't required. If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="2d2af-p102">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone. When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts. If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span><span class="sxs-lookup"><span data-stu-id="2d2af-p102">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone. When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts. If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="2d2af-112">Сброс ПИН-кода пользователя</span><span class="sxs-lookup"><span data-stu-id="2d2af-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="2d2af-113">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="2d2af-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2d2af-114">Перейдите в центр администрирования > **Skype для бизнеса**, а затем на панели навигации слева выберите пункт **звуковые конференции**.</span><span class="sxs-lookup"><span data-stu-id="2d2af-114">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="2d2af-115">Щелкните **Пользователи**, выберите пользователя, для которого вы хотите сбросить PIN-код.</span><span class="sxs-lookup"><span data-stu-id="2d2af-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="2d2af-116">На панели действий в разделе **ПИН-код**нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="2d2af-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="2d2af-117">Сброс ПИН-кода пользователем</span><span class="sxs-lookup"><span data-stu-id="2d2af-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="2d2af-p103">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page. This page can be accessed in one of three ways:</span><span class="sxs-lookup"><span data-stu-id="2d2af-p103">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page. This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="2d2af-120">В браузере перейдите на страницу [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span><span class="sxs-lookup"><span data-stu-id="2d2af-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="2d2af-121">В Skype для бизнеса нажмите стрелку **Показать меню** рядом с пунктом **Параметры**, затем нажмите **Средства** > **Параметры конференц-связи с телефонным подключением**.</span><span class="sxs-lookup"><span data-stu-id="2d2af-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="2d2af-122">В Skype для бизнеса выберите **Параметры** и нажмите **Переадресация звонков** в меню слева, а затем в разделе **Дополнительные параметры вызовов** нажмите **Изменить параметры онлайн**.</span><span class="sxs-lookup"><span data-stu-id="2d2af-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="2d2af-123">Что еще необходимо знать о ПИН-кодах?</span><span class="sxs-lookup"><span data-stu-id="2d2af-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="2d2af-p104">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset. After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d2af-p104">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset. After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="2d2af-p105">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span><span class="sxs-lookup"><span data-stu-id="2d2af-p105">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="2d2af-p106">Когда начинается собрание, к нему автоматически присоединяются все пользователи, находящиеся в зале ожидания. Пример: если два участника попытаются присоединиться к собранию, когда оно еще не началось, эти участники будут перенаправлены в зал ожидания. Когда с телефона присоединяется организатор собрания под собственным ПИН-кодом, собрание начинается, и к нему подключаются все участники, находящиеся в зале ожидания.</span><span class="sxs-lookup"><span data-stu-id="2d2af-p106">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="2d2af-130">По умолчанию собрание не разрешается запускать с помощью анонимных абонентов.</span><span class="sxs-lookup"><span data-stu-id="2d2af-130">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="2d2af-p107">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN. The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span><span class="sxs-lookup"><span data-stu-id="2d2af-p107">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN. The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="2d2af-p108">When you set up audio conferencing, you set the digits that are required for the PINs in your organization. PINs can be from 4 to 12 digits - the default is 5. If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing. See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="2d2af-p108">When you set up audio conferencing, you set the digits that are required for the PINs in your organization. PINs can be from 4 to 12 digits - the default is 5. If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing. See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="2d2af-p109">The email by default will be set to the Office 365 primary SMTP address of the user. You can send an email to a non-Office 365 address such as a Hotmail or MSN email address. You can override the default email address by using Windows PowerShell. This is useful if the users don't have an Exchange mailbox in Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d2af-p109">The email by default will be set to the Office 365 primary SMTP address of the user. You can send an email to a non-Office 365 address such as a Hotmail or MSN email address. You can override the default email address by using Windows PowerShell. This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>
    
- <span data-ttu-id="2d2af-p110">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". The SendEmail parameter is required to override the email address of the user.</span><span class="sxs-lookup"><span data-stu-id="2d2af-p110">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="2d2af-143">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d2af-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="2d2af-144">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="2d2af-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="2d2af-145">Чтобы задать ПИН-код для Amos Marble, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2d2af-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="2d2af-p111">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="2d2af-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2d2af-149">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="2d2af-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="2d2af-150">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d2af-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="2d2af-151">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности при использовании только в центре администрирования Microsoft 365, например при изменении параметров для нескольких пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="2d2af-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="2d2af-152">Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="2d2af-152">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="2d2af-153">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2d2af-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="2d2af-154">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2d2af-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="2d2af-155">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2d2af-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="2d2af-p113">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="2d2af-p113">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2d2af-158">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2d2af-158">Related topics</span></span>

[<span data-ttu-id="2d2af-159">Сброс идентификатора конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="2d2af-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
