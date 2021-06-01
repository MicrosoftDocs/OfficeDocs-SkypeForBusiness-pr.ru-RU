---
title: Настройка политик аудиоконференций в организации
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: "Конференц-связь \x97 это важная часть Skype для бизнеса online: она позволяет группам пользователей объединяться, чтобы просматривать презентации и видео, делиться приложениями, обмениваться файлами, общаться и совместно работать другими способами."
ms.openlocfilehash: 84037d571bf6f9dc3451793678a6d1b650492bd9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240081"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="4dea8-103">Настройка политик аудиоконференций в организации</span><span class="sxs-lookup"><span data-stu-id="4dea8-103">Set up conferencing policies for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="4dea8-104">[] Конференц-связь  это важная часть Skype для бизнеса online: она позволяет группам пользователей объединяться, чтобы просматривать презентации и видео, делиться приложениями, обмениваться файлами, общаться и совместно работать другими способами.</span><span class="sxs-lookup"><span data-stu-id="4dea8-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="4dea8-p101">Конференциями и их настройками нужно управлять. В некоторых случаях могут возникать проблемы безопасности: по умолчанию в собраниях могут участвовать все (даже не прошедшие проверку подлинности пользователи). Они могут сохранять презентации или раздаточный материал. Кроме того, могут возникать юридические вопросы. Например, по умолчанию участники собрания могут добавлять заметки к общедоступному содержимому. Но эти заметки не сохраняются после архивации собрания. Если вашей организации нужно сохранять переписку, отключите заметки.</span><span class="sxs-lookup"><span data-stu-id="4dea8-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="4dea8-p102">В Skype для бизнеса online конференции управляются с помощью политик. Политики конференций определяют доступные функции и возможности, в том числе то, разрешена ли передача звука и видео по протоколу IP максимальному числу участников собрания. Политики можно настроить глобально или для каждого пользователя, что дает администраторам большую гибкость.</span><span class="sxs-lookup"><span data-stu-id="4dea8-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="4dea8-114">Параметры политики можно настроить во время ее создания. Чтобы изменить параметры существующей политики, используйте командлет **Set-CsConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="4dea8-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="4dea8-115">Задание политик конференц-связи</span><span class="sxs-lookup"><span data-stu-id="4dea8-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="4dea8-116">Для всех параметров политики конференц-связи в Skype для бизнеса online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="4dea8-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 

### <a name="start-windows-powershell"></a><span data-ttu-id="4dea8-117">Начните Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dea8-117">Start Windows PowerShell</span></span>

 > [!Note]
> <span data-ttu-id="4dea8-118">Skype для бизнеса Online Connector в настоящее время является частью последней версии Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dea8-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="4dea8-119">Если вы используете последний общедоступный Teams PowerShell, вам не нужно устанавливать Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="4dea8-119">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="4dea8-120">Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="4dea8-120">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="4dea8-121">Откройте Windows PowerShell командную команду и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="4dea8-121">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="4dea8-122">Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dea8-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="4dea8-123">Блокирование перемещения файлов и демонстрации рабочего стола во время собраний</span><span class="sxs-lookup"><span data-stu-id="4dea8-123">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="4dea8-124">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4dea8-124">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="4dea8-125">См. дополнительные новости о [новом csConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="4dea8-125">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="4dea8-126">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4dea8-126">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="4dea8-127">См. дополнительные новости [о cmdlet Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="4dea8-127">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="4dea8-128">Если политика уже создана, используйте командлет [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="4dea8-128">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="4dea8-129">Блокирование записи конференций и запрет анонимных участников собрания</span><span class="sxs-lookup"><span data-stu-id="4dea8-129">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="4dea8-130">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4dea8-130">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="4dea8-131">См. дополнительные новости о [новом csConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="4dea8-131">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="4dea8-132">Чтобы предоставить новую политику Amos Marble, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4dea8-132">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="4dea8-133">См. дополнительные новости [о cmdlet Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="4dea8-133">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="4dea8-134">Если вы уже создали политику, можно использовать для изменения существующей политики cmdlet [Set-CsConferencingPolicy,](/powershell/module/skype/Set-CsConferencingPolicy) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="4dea8-134">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="4dea8-135">Запрет записи собраний анонимными участниками и сохранения содержимого собрания внешними пользователями</span><span class="sxs-lookup"><span data-stu-id="4dea8-135">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="4dea8-136">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4dea8-136">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="4dea8-137">См. дополнительные новости о [новом csConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="4dea8-137">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="4dea8-138">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4dea8-138">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="4dea8-139">См. дополнительные новости [о cmdlet Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="4dea8-139">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="4dea8-140">Если политика уже создана, используйте командлет [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="4dea8-140">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4dea8-141">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4dea8-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="4dea8-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="4dea8-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4dea8-143">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="4dea8-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4dea8-144">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="4dea8-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4dea8-145">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4dea8-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="4dea8-146">Шесть причин, по которым может потребоваться использовать Windows PowerShell управление Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="4dea8-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="4dea8-147">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="4dea8-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4dea8-148">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4dea8-148">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="4dea8-149">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="4dea8-149">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="4dea8-150">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4dea8-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="4dea8-151">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4dea8-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="4dea8-152">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4dea8-152">Related topics</span></span>
[<span data-ttu-id="4dea8-153">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="4dea8-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="4dea8-154">Блокировка передачи файлов по точкам</span><span class="sxs-lookup"><span data-stu-id="4dea8-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="4dea8-155">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="4dea8-155">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
