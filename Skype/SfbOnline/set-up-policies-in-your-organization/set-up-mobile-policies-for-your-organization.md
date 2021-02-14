---
title: Настройка политик мобильных устройств в организации
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Можно настроить способ подключения к Skype для бизнеса Online с помощью приложения Skype для бизнеса на мобильных устройствах, например с помощью функции, которая позволяет пользователям совершать и принимать звонки по рабочим, а не личным номерам мобильных телефонов. Можно также использовать политики мобильных устройств, чтобы запросить подключение Wi-Fi при звонках.
ms.openlocfilehash: 5094a536a636300ea70a7d358e24ee5c0f511379
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814748"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="c52b8-104">Настройка политик мобильных устройств в организации</span><span class="sxs-lookup"><span data-stu-id="c52b8-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="c52b8-p102">[] Можно настроить способ подключения к Skype для бизнеса Online с помощью приложения Skype для бизнеса на мобильных устройствах, например с помощью функции, которая позволяет пользователям совершать и принимать звонки по рабочим, а не личным номерам мобильных телефонов. Можно также использовать политики мобильных устройств, чтобы запросить подключение Wi-Fi при звонках.</span><span class="sxs-lookup"><span data-stu-id="c52b8-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="c52b8-107">Параметры политики мобильных устройств можно настроить во время создания политики. Чтобы изменить настройки существующей политики, используйте командлет **Set-CsMobilityPolicy**.</span><span class="sxs-lookup"><span data-stu-id="c52b8-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="c52b8-108">Задание политик мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="c52b8-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="c52b8-109">Для всех параметров политики мобильных устройств в Skype для бизнеса online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="c52b8-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="c52b8-110">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c52b8-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="c52b8-111">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="c52b8-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="c52b8-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c52b8-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="c52b8-113">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="c52b8-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="c52b8-p103">Если у вас нет версии 3.0 или более высокой, необходимо скачать и установить обновления для Windows PowerShell. Чтобы [скачать Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) и обновить Windows PowerShell до версии 4.0, см. Windows PowerShell 4.0. Перезагрузите компьютер, когда вам будет предложено.</span><span class="sxs-lookup"><span data-stu-id="c52b8-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="c52b8-117">Вам также потребуется установить модуль Windows PowerShell для Teams, который позволяет создавать удаленные сеансы Windows PowerShell подключения к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="c52b8-117">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="c52b8-118">Если вам нужно узнать больше, см. подключение к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx)в одном окне Windows PowerShell окна.</span><span class="sxs-lookup"><span data-stu-id="c52b8-118">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="c52b8-119">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c52b8-119">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="c52b8-120">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c52b8-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="c52b8-121">В **окне Windows PowerShell** подключения к Microsoft 365 или Office 365, вы работающим с помощью:</span><span class="sxs-lookup"><span data-stu-id="c52b8-121">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
       > [!NOTE]
       > <span data-ttu-id="c52b8-122">Соединитель Skype для бизнеса Online сейчас является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c52b8-122">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
       >
       > <span data-ttu-id="c52b8-123">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="c52b8-123">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="c52b8-124">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c52b8-124">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="c52b8-125">Требование подключения Wi-Fi для видеосвязи с пользователем</span><span class="sxs-lookup"><span data-stu-id="c52b8-125">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="c52b8-126">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c52b8-126">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="c52b8-127">См. дополнительные [функции для new-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="c52b8-127">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="c52b8-128">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c52b8-128">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="c52b8-129">Подробнее о [cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="c52b8-129">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="c52b8-130">Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="c52b8-130">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="c52b8-131">Запрет на использование приложения Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c52b8-131">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="c52b8-132">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c52b8-132">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="c52b8-133">См. дополнительные [функции для new-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="c52b8-133">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="c52b8-134">Чтобы предоставить новую политику Amos Marble, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c52b8-134">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="c52b8-135">Подробнее о [cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="c52b8-135">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="c52b8-136">Если вы уже создали политику, то можете изменить ее с помощью cmdlet [Set-CsMobilityPolicy,](https://technet.microsoft.com/library/mt779147.aspx) а затем с помощью cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) применить параметр к пользователям.</span><span class="sxs-lookup"><span data-stu-id="c52b8-136">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="c52b8-137">Запрет звонков по VoIP на мобильных устройствах</span><span class="sxs-lookup"><span data-stu-id="c52b8-137">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="c52b8-138">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c52b8-138">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="c52b8-139">См. дополнительные [функции для new-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="c52b8-139">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="c52b8-140">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c52b8-140">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="c52b8-141">Подробнее о [cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="c52b8-141">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="c52b8-142">Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="c52b8-142">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c52b8-143">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c52b8-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="c52b8-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="c52b8-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c52b8-145">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="c52b8-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c52b8-146">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="c52b8-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c52b8-147">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c52b8-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c52b8-148">Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="c52b8-148">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c52b8-149">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="c52b8-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c52b8-150">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c52b8-150">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c52b8-151">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c52b8-151">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c52b8-152">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c52b8-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c52b8-153">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c52b8-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="c52b8-154">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c52b8-154">Related topics</span></span>
[<span data-ttu-id="c52b8-155">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="c52b8-155">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="c52b8-156">Блокировать передачу файлов по точкам</span><span class="sxs-lookup"><span data-stu-id="c52b8-156">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="c52b8-157">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="c52b8-157">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="c52b8-158">Настройка политик для организации</span><span class="sxs-lookup"><span data-stu-id="c52b8-158">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
