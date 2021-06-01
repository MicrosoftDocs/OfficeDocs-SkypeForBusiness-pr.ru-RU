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
description: 'Узнайте, что следует знать о ПИН-паролях и как сбросить их в Skype для бизнеса Online. '
ms.openlocfilehash: 95c2d19a7d867d97ab977b722648de1373a4739b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237755"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="92a5a-103">Сброс ПИН-кода аудиоконференции в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="92a5a-103">Reset the Audio Conferencing PIN in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="92a5a-104">Информацию о сбросе ПИН-кодов аудиоконференций в Microsoft Teams см. в разделе [Сброс ПИН-кода аудиоконференций в Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="92a5a-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="92a5a-105">ПИН-код представляет собой числовой код, который создается для каждого пользователя Skype для бизнеса, имеющего возможность участия в аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="92a5a-105">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing.</span></span> <span data-ttu-id="92a5a-106">ПИН-коды аудиоконференций используют организаторы собраний для подтверждения статуса организатора собрания и запуска собрания по телефону.</span><span class="sxs-lookup"><span data-stu-id="92a5a-106">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="92a5a-107">При использовании для запуска собрания Skype для бизнеса ПИН-код не требуется.</span><span class="sxs-lookup"><span data-stu-id="92a5a-107">If they use the Skype for Business app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="92a5a-108">Если пользователь забыл свой ПИН-код, и ему не удается найти сообщение электронной почты, отправленное ему при предоставлении возможности участия в аудиоконференциях, администратор может выполнить сброс его ПИН-кода, или же он может изменить свой ПИН-код самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="92a5a-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="92a5a-109">Собрания можно начать, когда пользователь, авторификация, присоединяется с помощью приложения Skype для бизнеса или когда организатор присоединяется с помощью своего ПИН-кода по телефону.</span><span class="sxs-lookup"><span data-stu-id="92a5a-109">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="92a5a-110">Если для участия в телефонном собрании требуется ПИН-код, то все пользователи, подключившиеся к этому собранию по телефону, перенаправляются в зал ожидания и могут прослушивать музыку до начала собрания.</span><span class="sxs-lookup"><span data-stu-id="92a5a-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="92a5a-111">Если организатор собрания не запрашивает ПИН-код при открытии собрания по телефону, то при подключении к собранию участникам не потребуется вводить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="92a5a-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="92a5a-112">Сброс ПИН-кода пользователя</span><span class="sxs-lookup"><span data-stu-id="92a5a-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="92a5a-113">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="92a5a-113">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="92a5a-114">Перейдите в центр администрирования > **Skype для бизнеса** и в области навигации слева выберите аудиоконференцию . </span><span class="sxs-lookup"><span data-stu-id="92a5a-114">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="92a5a-115">Щелкните **Пользователи**, выберите пользователя, для который вы хотите сбросить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="92a5a-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="92a5a-116">В области действий в области **ПИН-код** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="92a5a-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="92a5a-117">Сброс ПИН-кода пользователем</span><span class="sxs-lookup"><span data-stu-id="92a5a-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="92a5a-118">Пользователь может сбросить ПИН-код с помощью параметра **Сброс ПИН-кода** на странице **Конференц-связь с телефонным подключением**.</span><span class="sxs-lookup"><span data-stu-id="92a5a-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="92a5a-119">На эту страницу можно перейти одним из трех способов:</span><span class="sxs-lookup"><span data-stu-id="92a5a-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="92a5a-120">В браузере перейдите на страницу [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span><span class="sxs-lookup"><span data-stu-id="92a5a-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="92a5a-121">В Skype для бизнеса нажмите стрелку **Показать меню** рядом с пунктом **Параметры**, затем нажмите **Средства** > **Параметры конференц-связи с телефонным подключением**.</span><span class="sxs-lookup"><span data-stu-id="92a5a-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="92a5a-122">В Skype для бизнеса выберите **Параметры** и нажмите **Переадресация звонков** в меню слева, а затем в разделе **Дополнительные параметры вызовов** нажмите **Изменить параметры онлайн**.</span><span class="sxs-lookup"><span data-stu-id="92a5a-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="92a5a-123">Что еще необходимо знать о ПИН-кодах?</span><span class="sxs-lookup"><span data-stu-id="92a5a-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="92a5a-124">В целях безопасности ПИН-код отображается однократно и только для администратора, выполняющего сброс.</span><span class="sxs-lookup"><span data-stu-id="92a5a-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="92a5a-125">После сброса ПИН-кода администратор будет указан как \*\*\*\*\*\*\*\*\* в Центре администрирования **Skype для бизнеса** и в результатах при использовании Get-CsCsOnlineDialInConfencingUser в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92a5a-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="92a5a-126">По умолчанию автоматическое отправка сообщений электронной почты пользователям включено, и пользователи получат электронное письмо со своим ПИН-кодом, когда им будет включена аудиоконференция или при сбросе ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="92a5a-126">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="92a5a-127">Но если вы отключили автоматическое отправку сообщений электронной почты, пользователю не будет отправлено сообщение об сбросе ПИН-кода, и вам придется вручную отправлять сведения о ПИН-коде пользователю.</span><span class="sxs-lookup"><span data-stu-id="92a5a-127">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="92a5a-p106">Когда начинается собрание, к нему автоматически присоединяются все пользователи, находящиеся в зале ожидания. Пример: если два участника попытаются присоединиться к собранию, когда оно еще не началось, эти участники будут перенаправлены в зал ожидания. Когда с телефона присоединяется организатор собрания под собственным ПИН-кодом, собрание начинается, и к нему подключаются все участники, находящиеся в зале ожидания.</span><span class="sxs-lookup"><span data-stu-id="92a5a-p106">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="92a5a-130">По умолчанию анонимные звонки не могут начать собрание.</span><span class="sxs-lookup"><span data-stu-id="92a5a-130">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="92a5a-131">Когда пользователь включает аудиоконференцию, по умолчанию ему отправляются сообщения электронной почты, включающие сведения о аудиоконференции и ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="92a5a-131">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="92a5a-132">У пользователя должен быть почтовый ящик Microsoft 365 или Office 365, так как при сбросе ПИН-кода новый ПИН-код отправляется пользователю по электронной почте на его основной SMTP-адрес (псевдоним), установленный для пользователя.</span><span class="sxs-lookup"><span data-stu-id="92a5a-132">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="92a5a-133">При настройке аудиоконференций вы задаете цифры, которые должны быть включены в ПИН-коды в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="92a5a-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="92a5a-134">ПИН-коды могут быть от 4 до 12 цифр ( значение по умолчанию — 5).</span><span class="sxs-lookup"><span data-stu-id="92a5a-134">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="92a5a-135">При изменении длины ПИН-кода новое значение применяется только к новым ПИН-кодам и не применяется к ПИН-кодам для существующих пользователей, которым разрешено участие в аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="92a5a-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="92a5a-136">См. [Настройка длины PIN-кода для собраний с аудиоконференцией](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="92a5a-136">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="92a5a-137">По умолчанию для сообщения электронной почты Microsoft 365 или Office 365 основным SMTP-адресом пользователя.</span><span class="sxs-lookup"><span data-stu-id="92a5a-137">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="92a5a-138">Вы можете отправлять сообщения электронной почты на Microsoft 365 адрес электронной почты, не Office 365, такой как Hotmail или MSN.</span><span class="sxs-lookup"><span data-stu-id="92a5a-138">You can send an email to a non-Microsoft 365 or non-Office 365 address, such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="92a5a-139">Используемый по умолчанию адрес электронной почты можно изменить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92a5a-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="92a5a-140">Это полезно, если у пользователей нет почтового ящика Exchange в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="92a5a-140">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>
    
- <span data-ttu-id="92a5a-141">Чтобы переопредить адрес пользователя по умолчанию, на который отправляется сообщение электронной почты, администратор клиента может использовать следующий cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com".</span><span class="sxs-lookup"><span data-stu-id="92a5a-141">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com".</span></span> <span data-ttu-id="92a5a-142">Параметр SendEmail требуется для переопределения адреса электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="92a5a-142">The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="92a5a-143">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="92a5a-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="92a5a-144">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).</span><span class="sxs-lookup"><span data-stu-id="92a5a-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="92a5a-145">Чтобы задать ПИН-код для Amos Marble, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="92a5a-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="92a5a-146">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="92a5a-146">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="92a5a-147">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="92a5a-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="92a5a-148">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="92a5a-148">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="92a5a-149">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="92a5a-149">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="92a5a-150">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="92a5a-150">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="92a5a-151">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="92a5a-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="92a5a-152">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="92a5a-152">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="92a5a-153">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="92a5a-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="92a5a-154">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="92a5a-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="92a5a-155">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="92a5a-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="92a5a-p113">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="92a5a-p113">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="92a5a-158">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="92a5a-158">Related topics</span></span>

[<span data-ttu-id="92a5a-159">Сброс идентификатора конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="92a5a-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
