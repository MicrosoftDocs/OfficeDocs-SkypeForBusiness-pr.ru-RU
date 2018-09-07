---
title: Настройка политик мобильных устройств в организации
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Можно настроить способ подключения к Skype для бизнеса Online с помощью приложения Skype для бизнеса на мобильных устройствах, например с помощью функции, которая позволяет пользователям совершать и принимать звонки по рабочим, а не личным номерам мобильных телефонов. Можно также использовать политики мобильных устройств, чтобы запросить подключение Wi-Fi при звонках.
ms.openlocfilehash: 21d1b19a72686d618bf8fca484bf828e62ee3a37
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861530"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="d42bf-104">Настройка политик мобильных устройств в организации</span><span class="sxs-lookup"><span data-stu-id="d42bf-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="d42bf-p102">[] Можно настроить способ подключения к Skype для бизнеса Online с помощью приложения Skype для бизнеса на мобильных устройствах, например с помощью функции, которая позволяет пользователям совершать и принимать звонки по рабочим, а не личным номерам мобильных телефонов. Можно также использовать политики мобильных устройств, чтобы запросить подключение Wi-Fi при звонках.</span><span class="sxs-lookup"><span data-stu-id="d42bf-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="d42bf-107">Параметры политики мобильных устройств можно настроить во время создания политики. Чтобы изменить настройки существующей политики, используйте командлет **Set-CsMobilityPolicy**.</span><span class="sxs-lookup"><span data-stu-id="d42bf-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="d42bf-108">Задание политик мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="d42bf-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="d42bf-109">Для всех параметров политики мобильных устройств в Skype для бизнеса online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="d42bf-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="d42bf-110">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d42bf-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="d42bf-111">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="d42bf-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="d42bf-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d42bf-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d42bf-113">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="d42bf-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="d42bf-p103">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="d42bf-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="d42bf-p104">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="d42bf-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="d42bf-120">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="d42bf-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="d42bf-121">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d42bf-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="d42bf-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d42bf-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d42bf-123">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d42bf-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d42bf-124">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d42bf-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="d42bf-125">Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [подключение к Скайп для бизнеса в Интернет с помощью Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d42bf-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="d42bf-126">Требование подключения Wi-Fi для видеосвязи с пользователем</span><span class="sxs-lookup"><span data-stu-id="d42bf-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="d42bf-127">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d42bf-127">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  <span data-ttu-id="d42bf-128">Просмотрите Дополнительные сведения о командлет [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d42bf-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d42bf-129">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d42bf-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  <span data-ttu-id="d42bf-130">Просмотрите Дополнительные сведения о командлета [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d42bf-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="d42bf-131">Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="d42bf-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="d42bf-132">Запрет на использование приложения Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d42bf-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="d42bf-133">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d42bf-133">To create a new policy for these settings, run:</span></span>
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  <span data-ttu-id="d42bf-134">Просмотрите Дополнительные сведения о командлет [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d42bf-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d42bf-135">Чтобы предоставить новую политику Amos Marble, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d42bf-135">To grant the new policy you created to Amos Marble, run:</span></span>  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  <span data-ttu-id="d42bf-136">Просмотрите Дополнительные сведения о командлета [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d42bf-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="d42bf-137">Если вы уже создали политику, можно использовать командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) внесение изменений в существующую политику и затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) о настройке параметров для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d42bf-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="d42bf-138">Запрет звонков по VoIP на мобильных устройствах</span><span class="sxs-lookup"><span data-stu-id="d42bf-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="d42bf-139">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d42bf-139">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  <span data-ttu-id="d42bf-140">Просмотрите Дополнительные сведения о командлет [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d42bf-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d42bf-141">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d42bf-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  <span data-ttu-id="d42bf-142">Просмотрите Дополнительные сведения о командлета [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d42bf-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="d42bf-143">Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx), чтобы применить настройки к пользователям.</span><span class="sxs-lookup"><span data-stu-id="d42bf-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d42bf-144">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d42bf-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="d42bf-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="d42bf-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d42bf-146">С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="d42bf-146">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d42bf-147">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="d42bf-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d42bf-148">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d42bf-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d42bf-149">Шесть причин использовать Windows PowerShell для управления Office 365 </span><span class="sxs-lookup"><span data-stu-id="d42bf-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="d42bf-p106">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d42bf-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d42bf-152">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d42bf-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d42bf-153">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d42bf-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d42bf-154">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d42bf-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="d42bf-155">See also</span><span class="sxs-lookup"><span data-stu-id="d42bf-155">Related topics</span></span>
[<span data-ttu-id="d42bf-156">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="d42bf-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="d42bf-157">Передача файлов точка-точка блока</span><span class="sxs-lookup"><span data-stu-id="d42bf-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="d42bf-158">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="d42bf-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="d42bf-159">Настройка политик конференц-связи в вашей организации</span><span class="sxs-lookup"><span data-stu-id="d42bf-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 