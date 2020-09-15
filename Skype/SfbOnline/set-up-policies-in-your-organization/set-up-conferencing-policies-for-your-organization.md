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
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814758"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="7495f-103">Настройка политик аудиоконференций в организации</span><span class="sxs-lookup"><span data-stu-id="7495f-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="7495f-104">[] Конференц-связь  это важная часть Skype для бизнеса online: она позволяет группам пользователей объединяться, чтобы просматривать презентации и видео, делиться приложениями, обмениваться файлами, общаться и совместно работать другими способами.</span><span class="sxs-lookup"><span data-stu-id="7495f-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="7495f-p101">Конференциями и их настройками нужно управлять. В некоторых случаях могут возникать проблемы безопасности: по умолчанию в собраниях могут участвовать все (даже не прошедшие проверку подлинности пользователи). Они могут сохранять презентации или раздаточный материал. Кроме того, могут возникать юридические вопросы. Например, по умолчанию участники собрания могут добавлять заметки к общедоступному содержимому. Но эти заметки не сохраняются после архивации собрания. Если вашей организации нужно сохранять переписку, отключите заметки.</span><span class="sxs-lookup"><span data-stu-id="7495f-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="7495f-p102">В Skype для бизнеса online конференции управляются с помощью политик. Политики конференций определяют доступные функции и возможности, в том числе то, разрешена ли передача звука и видео по протоколу IP максимальному числу участников собрания. Политики можно настроить глобально или для каждого пользователя, что дает администраторам большую гибкость.</span><span class="sxs-lookup"><span data-stu-id="7495f-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="7495f-114">Параметры политики можно настроить во время ее создания. Чтобы изменить параметры существующей политики, используйте командлет **Set-CsConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="7495f-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="7495f-115">Задание политик конференц-связи</span><span class="sxs-lookup"><span data-stu-id="7495f-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="7495f-116">Для всех параметров политики конференц-связи в Skype для бизнеса online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="7495f-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="7495f-117">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7495f-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="7495f-118">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="7495f-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="7495f-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7495f-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="7495f-120">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="7495f-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="7495f-p103">Если у вас нет версии 3,0 или более новой, вам нужно скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Перезагрузите компьютер после появления соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="7495f-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="7495f-124">Кроме того, вам потребуется установить модуль Windows PowerShell для Teams, который позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="7495f-124">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="7495f-125">Дополнительные сведения можно найти в разделе [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="7495f-125">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="7495f-126">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7495f-126">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="7495f-127">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7495f-127">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="7495f-128">В окне **Windows PowerShell** подключитесь к службе Microsoft 365 или Office 365, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7495f-128">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
     > [!NOTE]
     > <span data-ttu-id="7495f-129">Skype для бизнеса Online уже входит в состав последнего модуля PowerShell для Teams.</span><span class="sxs-lookup"><span data-stu-id="7495f-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
     >
     > <span data-ttu-id="7495f-130">Если вы используете последнюю версию [общедоступной оболочки для Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="7495f-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="7495f-131">Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или [Настройка компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="7495f-131">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="7495f-132">Блокирование перемещения файлов и демонстрации рабочего стола во время собраний</span><span class="sxs-lookup"><span data-stu-id="7495f-132">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="7495f-133">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7495f-133">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="7495f-134">Дополнительные сведения о командлете [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7495f-134">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7495f-135">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7495f-135">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="7495f-136">Дополнительные сведения о командлете [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7495f-136">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="7495f-137">Если политика уже создана, используйте командлет [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="7495f-137">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="7495f-138">Блокирование записи конференций и запрет анонимных участников собрания</span><span class="sxs-lookup"><span data-stu-id="7495f-138">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="7495f-139">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7495f-139">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="7495f-140">Дополнительные сведения о командлете [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7495f-140">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7495f-141">Чтобы предоставить новую политику Amos Marble, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7495f-141">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="7495f-142">Дополнительные сведения о командлете [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7495f-142">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="7495f-143">Если вы уже создали политику, вы можете использовать командлет [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) , чтобы внести изменения в существующую политику, а затем использовать командлет [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) , чтобы применить параметры к вашим пользователям.</span><span class="sxs-lookup"><span data-stu-id="7495f-143">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="7495f-144">Запрет записи собраний анонимными участниками и сохранения содержимого собрания внешними пользователями</span><span class="sxs-lookup"><span data-stu-id="7495f-144">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="7495f-145">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7495f-145">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="7495f-146">Дополнительные сведения о командлете [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7495f-146">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7495f-147">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7495f-147">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="7495f-148">Дополнительные сведения о командлете [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7495f-148">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="7495f-149">Если политика уже создана, используйте командлет [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="7495f-149">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7495f-150">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7495f-150">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="7495f-151">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="7495f-151">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7495f-152">С помощью Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="7495f-152">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="7495f-153">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="7495f-153">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7495f-154">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7495f-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="7495f-155">Шесть причин, по которым вам может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="7495f-155">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="7495f-156">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="7495f-156">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="7495f-157">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="7495f-157">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="7495f-158">Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7495f-158">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="7495f-159">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7495f-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7495f-160">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7495f-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="7495f-161">См. также</span><span class="sxs-lookup"><span data-stu-id="7495f-161">Related topics</span></span>
[<span data-ttu-id="7495f-162">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="7495f-162">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="7495f-163">Блокировка передачи файлов между точками</span><span class="sxs-lookup"><span data-stu-id="7495f-163">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="7495f-164">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="7495f-164">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
