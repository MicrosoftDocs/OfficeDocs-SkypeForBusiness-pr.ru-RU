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
ms.openlocfilehash: 36162c64490edf58bbfac5c7022bebf6f39595ca
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569201"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="bb9eb-104">Настройка политик мобильных устройств в организации</span><span class="sxs-lookup"><span data-stu-id="bb9eb-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="bb9eb-p102">[] Можно настроить способ подключения к Skype для бизнеса Online с помощью приложения Skype для бизнеса на мобильных устройствах, например с помощью функции, которая позволяет пользователям совершать и принимать звонки по рабочим, а не личным номерам мобильных телефонов. Можно также использовать политики мобильных устройств, чтобы запросить подключение Wi-Fi при звонках.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="bb9eb-107">Параметры политики мобильных устройств можно настроить во время создания политики. Чтобы изменить настройки существующей политики, используйте командлет **Set-CsMobilityPolicy**.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="bb9eb-108">Задание политик мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="bb9eb-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="bb9eb-109">Для всех параметров политики мобильных устройств в Skype для бизнеса online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="bb9eb-110">Начать Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb9eb-110">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="bb9eb-111">Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-111">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="bb9eb-112">Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-112">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="bb9eb-113">Установите модуль [Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="bb9eb-113">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="bb9eb-114">Откройте Windows PowerShell и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="bb9eb-114">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="bb9eb-115">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-115">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="bb9eb-116">Требование подключения Wi-Fi для видеосвязи с пользователем</span><span class="sxs-lookup"><span data-stu-id="bb9eb-116">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="bb9eb-117">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb9eb-117">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="bb9eb-118">См. дополнительные [функции для new-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb9eb-118">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="bb9eb-119">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb9eb-119">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="bb9eb-120">Подробнее о [cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb9eb-120">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="bb9eb-121">Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-121">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="bb9eb-122">Запрет на использование приложения Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bb9eb-122">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="bb9eb-123">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb9eb-123">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="bb9eb-124">См. дополнительные [функции для new-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb9eb-124">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="bb9eb-125">Чтобы предоставить новую политику Amos Marble, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb9eb-125">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="bb9eb-126">Подробнее о [cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb9eb-126">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="bb9eb-127">Если вы уже создали политику, вы можете изменить существующую политику с помощью cmdlet [Set-CsMobilityPolicy,](https://technet.microsoft.com/library/mt779147.aspx) а затем с помощью cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) применить параметр к пользователям.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-127">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="bb9eb-128">Запрет звонков по VoIP на мобильных устройствах</span><span class="sxs-lookup"><span data-stu-id="bb9eb-128">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="bb9eb-129">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb9eb-129">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="bb9eb-130">См. дополнительные [функции для new-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb9eb-130">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="bb9eb-131">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb9eb-131">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="bb9eb-132">Подробнее о [cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb9eb-132">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="bb9eb-133">Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-133">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bb9eb-134">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bb9eb-134">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="bb9eb-135">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-135">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bb9eb-136">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-136">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="bb9eb-137">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-137">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bb9eb-138">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="bb9eb-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bb9eb-139">Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="bb9eb-139">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="bb9eb-140">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="bb9eb-140">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="bb9eb-141">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="bb9eb-141">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bb9eb-142">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb9eb-142">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="bb9eb-143">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="bb9eb-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bb9eb-144">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="bb9eb-144">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="bb9eb-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bb9eb-145">Related topics</span></span>
[<span data-ttu-id="bb9eb-146">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="bb9eb-146">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="bb9eb-147">Блокировать передачу файлов по точкам</span><span class="sxs-lookup"><span data-stu-id="bb9eb-147">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="bb9eb-148">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="bb9eb-148">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="bb9eb-149">Настройка политик для организации</span><span class="sxs-lookup"><span data-stu-id="bb9eb-149">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
