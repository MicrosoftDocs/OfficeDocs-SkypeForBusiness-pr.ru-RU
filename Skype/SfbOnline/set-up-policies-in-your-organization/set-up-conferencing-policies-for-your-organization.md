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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Конференц-связь \x97 это важная часть Skype для бизнеса online: она позволяет группам пользователей объединяться, чтобы просматривать презентации и видео, делиться приложениями, обмениваться файлами, общаться и совместно работать другими способами."
ms.openlocfilehash: 46e22191875709f13936db395563eb9f7326300f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884537"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="0bff1-103">Настройка политик аудиоконференций в организации</span><span class="sxs-lookup"><span data-stu-id="0bff1-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="0bff1-104">[] Конференц-связь  это важная часть Skype для бизнеса online: она позволяет группам пользователей объединяться, чтобы просматривать презентации и видео, делиться приложениями, обмениваться файлами, общаться и совместно работать другими способами.</span><span class="sxs-lookup"><span data-stu-id="0bff1-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="0bff1-p101">Конференциями и их настройками нужно управлять. В некоторых случаях могут возникать проблемы безопасности: по умолчанию в собраниях могут участвовать все (даже не прошедшие проверку подлинности пользователи). Они могут сохранять презентации или раздаточный материал. Кроме того, могут возникать юридические вопросы. Например, по умолчанию участники собрания могут добавлять заметки к общедоступному содержимому. Но эти заметки не сохраняются после архивации собрания. Если вашей организации нужно сохранять переписку, отключите заметки.</span><span class="sxs-lookup"><span data-stu-id="0bff1-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="0bff1-p102">В Skype для бизнеса online конференции управляются с помощью политик. Политики конференций определяют доступные функции и возможности, в том числе то, разрешена ли передача звука и видео по протоколу IP максимальному числу участников собрания. Политики можно настроить глобально или для каждого пользователя, что дает администраторам большую гибкость.</span><span class="sxs-lookup"><span data-stu-id="0bff1-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="0bff1-114">Параметры политики можно настроить во время ее создания. Чтобы изменить параметры существующей политики, используйте командлет **Set-CsConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="0bff1-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="0bff1-115">Задание политик конференц-связи</span><span class="sxs-lookup"><span data-stu-id="0bff1-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="0bff1-116">Для всех параметров политики конференц-связи в Skype для бизнеса online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="0bff1-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="0bff1-117">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bff1-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="0bff1-118">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="0bff1-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="0bff1-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0bff1-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0bff1-120">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="0bff1-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="0bff1-p103">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="0bff1-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="0bff1-p104">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="0bff1-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="0bff1-127">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="0bff1-127">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="0bff1-128">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0bff1-128">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="0bff1-129">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0bff1-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0bff1-130">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0bff1-130">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0bff1-131">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="0bff1-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="0bff1-132">Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [настроить компьютер для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0bff1-132">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="0bff1-133">Блокирование перемещения файлов и демонстрации рабочего стола во время собраний</span><span class="sxs-lookup"><span data-stu-id="0bff1-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="0bff1-134">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0bff1-134">To create a new policy for these settings, run:</span></span>
  > 
  > ```
  > New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  > ```
  > <span data-ttu-id="0bff1-135">В разделе Дополнительные с параметрами командлета [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0bff1-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0bff1-136">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0bff1-136">To grant the new policy you created to all users in your organization, run:</span></span>
  > 
  > ```
  > Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  > ```
  > <span data-ttu-id="0bff1-137">Просмотрите Дополнительные сведения о командлета [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0bff1-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="0bff1-138">Если политика уже создана, используйте командлет [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="0bff1-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="0bff1-139">Блокирование записи конференций и запрет анонимных участников собрания</span><span class="sxs-lookup"><span data-stu-id="0bff1-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="0bff1-140">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0bff1-140">To create a new policy for these settings, run:</span></span> 
  > 
  > ```
  > New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  > ```
  > <span data-ttu-id="0bff1-141">В разделе Дополнительные с параметрами командлета [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0bff1-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0bff1-142">Чтобы предоставить новую политику Amos Marble, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0bff1-142">To grant the new policy you created to Amos Marble, run:</span></span>
  > 
  > ```
  >  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  > ```
  > <span data-ttu-id="0bff1-143">Просмотрите Дополнительные сведения о командлета [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0bff1-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="0bff1-144">Если вы уже создали политику, можно использовать командлет [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) внесение изменений в существующую политику и затем командлет [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) используется для применения параметров для пользователей.</span><span class="sxs-lookup"><span data-stu-id="0bff1-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="0bff1-145">Запрет записи собраний анонимными участниками и сохранения содержимого собрания внешними пользователями</span><span class="sxs-lookup"><span data-stu-id="0bff1-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="0bff1-146">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0bff1-146">To create a new policy for these settings, run:</span></span>  
  > 
  > ```
  > New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  > ```
  > <span data-ttu-id="0bff1-147">В разделе Дополнительные с параметрами командлета [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0bff1-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0bff1-148">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0bff1-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```
>   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
>   ```

<span data-ttu-id="0bff1-149">Просмотрите Дополнительные сведения о командлета [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0bff1-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="0bff1-150">Если политика уже создана, используйте командлет [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="0bff1-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0bff1-151">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0bff1-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="0bff1-152">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="0bff1-152">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0bff1-153">С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="0bff1-153">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="0bff1-154">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="0bff1-154">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0bff1-155">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0bff1-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0bff1-156">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="0bff1-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="0bff1-p106">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="0bff1-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="0bff1-159">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bff1-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="0bff1-160">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0bff1-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0bff1-161">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0bff1-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="0bff1-162">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0bff1-162">Related topics</span></span>
[<span data-ttu-id="0bff1-163">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="0bff1-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="0bff1-164">Передача файлов точка-точка блока</span><span class="sxs-lookup"><span data-stu-id="0bff1-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="0bff1-165">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="0bff1-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
