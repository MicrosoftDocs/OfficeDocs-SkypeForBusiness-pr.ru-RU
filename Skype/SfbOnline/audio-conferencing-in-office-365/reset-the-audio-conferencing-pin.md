---
title: Сброс ПИН-кода аудиоконференции в Skype для бизнеса Online
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, что вам следует знать о ПИН-сах и как сбросить их в Skype для бизнеса Online. '
ms.openlocfilehash: 21e2742653e72919df0647c0539fdb335585cc84
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164698"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="c82a9-103">Сброс ПИН-кода аудиоконференции в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c82a9-103">Reset the Audio Conferencing PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="c82a9-104">Информацию о сбросе ПИН-кодов аудиоконференций в Microsoft Teams см. в разделе [Сброс ПИН-кода аудиоконференций в Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="c82a9-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="c82a9-p101">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing. Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone. If they use the Skype for Business app to start the meeting, a PIN isn't required. If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span><span class="sxs-lookup"><span data-stu-id="c82a9-p101">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing. Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone. If they use the Skype for Business app to start the meeting, a PIN isn't required. If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="c82a9-p102">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone. When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts. If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span><span class="sxs-lookup"><span data-stu-id="c82a9-p102">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone. When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts. If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="c82a9-112">Сброс ПИН-кода пользователя</span><span class="sxs-lookup"><span data-stu-id="c82a9-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="c82a9-113">Войте свою учетную запись с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c82a9-113">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="c82a9-114">Перейдите в Центр администрирования > **Skype** для бизнеса и на левой навигации щелкните "Аудиоконференция". </span><span class="sxs-lookup"><span data-stu-id="c82a9-114">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c82a9-115">Щелкните **"Пользователи"** и выберите пользователя, для который вы хотите сбросить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="c82a9-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="c82a9-116">На области действий в области **"ПИН-код"** нажмите кнопку **"Сброс".**</span><span class="sxs-lookup"><span data-stu-id="c82a9-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="c82a9-117">Сброс ПИН-кода пользователем</span><span class="sxs-lookup"><span data-stu-id="c82a9-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="c82a9-p103">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page. This page can be accessed in one of three ways:</span><span class="sxs-lookup"><span data-stu-id="c82a9-p103">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page. This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="c82a9-120">В браузере перейдите на страницу [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span><span class="sxs-lookup"><span data-stu-id="c82a9-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="c82a9-121">В Skype для бизнеса нажмите стрелку **Показать меню** рядом с пунктом **Параметры**, затем нажмите **Средства** > **Параметры конференц-связи с телефонным подключением**.</span><span class="sxs-lookup"><span data-stu-id="c82a9-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="c82a9-122">В Skype для бизнеса выберите **Параметры** и нажмите **Переадресация звонков** в меню слева, а затем в разделе **Дополнительные параметры вызовов** нажмите **Изменить параметры онлайн**.</span><span class="sxs-lookup"><span data-stu-id="c82a9-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="c82a9-123">Что еще необходимо знать о ПИН-кодах?</span><span class="sxs-lookup"><span data-stu-id="c82a9-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="c82a9-p104">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset. After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c82a9-p104">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset. After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="c82a9-p105">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span><span class="sxs-lookup"><span data-stu-id="c82a9-p105">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="c82a9-p106">Когда начинается собрание, к нему автоматически присоединяются все пользователи, находящиеся в зале ожидания. Пример: если два участника попытаются присоединиться к собранию, когда оно еще не началось, эти участники будут перенаправлены в зал ожидания. Когда с телефона присоединяется организатор собрания под собственным ПИН-кодом, собрание начинается, и к нему подключаются все участники, находящиеся в зале ожидания.</span><span class="sxs-lookup"><span data-stu-id="c82a9-p106">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="c82a9-130">По умолчанию анонимные звонки не могут начать собрание.</span><span class="sxs-lookup"><span data-stu-id="c82a9-130">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="c82a9-p107">Если пользователю включена аудиоконференция, по умолчанию ему отправляются сообщения электронной почты, включающие данные для аудиоконференции и ПИН-код. У пользователя должен быть почтовый ящик Microsoft 365 или Office 365, так как при сбросе ПИН-кода новый ПИН-код отправляется пользователю по электронной почте на его основной SMTP-адрес (псевдоним), установленный для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c82a9-p107">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN. The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="c82a9-p108">When you set up audio conferencing, you set the digits that are required for the PINs in your organization. PINs can be from 4 to 12 digits - the default is 5. If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing. See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="c82a9-p108">When you set up audio conferencing, you set the digits that are required for the PINs in your organization. PINs can be from 4 to 12 digits - the default is 5. If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing. See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="c82a9-p109">По умолчанию для электронной почты устанавливается основной SMTP-адрес Microsoft 365 или Office 365 пользователя. Вы можете отправить сообщение электронной почты на адрес, не отправляемый на Microsoft 365 или не на office 365, например на Hotmail или MSN. Адрес электронной почты, заданный по умолчанию, можно Windows PowerShell. Это полезно, если у пользователей нет почтового ящика Exchange в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="c82a9-p109">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user. You can send an email to a non-Microsoft 365 or non-Office 365 address, such as a Hotmail or MSN email address. You can override the default email address by using Windows PowerShell. This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>
    
- <span data-ttu-id="c82a9-p110">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". The SendEmail parameter is required to override the email address of the user.</span><span class="sxs-lookup"><span data-stu-id="c82a9-p110">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c82a9-143">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c82a9-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c82a9-144">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="c82a9-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="c82a9-145">Чтобы задать ПИН-код для Amos Marble, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c82a9-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="c82a9-p111">Windows PowerShell все о том, как управлять пользователями, а также о том, какие пользователи разрешены или не разрешены. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, см. указанные здесь разделы.</span><span class="sxs-lookup"><span data-stu-id="c82a9-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c82a9-149">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c82a9-149">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c82a9-150">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c82a9-150">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c82a9-p112">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих темах:</span><span class="sxs-lookup"><span data-stu-id="c82a9-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c82a9-153">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c82a9-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="c82a9-154">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c82a9-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c82a9-155">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c82a9-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="c82a9-p113">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="c82a9-p113">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c82a9-158">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c82a9-158">Related topics</span></span>

[<span data-ttu-id="c82a9-159">Сброс идентификатора конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="c82a9-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
