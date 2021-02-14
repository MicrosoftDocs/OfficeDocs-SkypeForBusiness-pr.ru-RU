---
title: Настройка политик клиента в организации
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям.
ms.openlocfilehash: 3a7dd7a2840a4e94abe88c472e6dc5b0e1720704
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814358"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="46280-103">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="46280-103">Set up client policies for your organization</span></span>

<span data-ttu-id="46280-104">[] Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="46280-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="46280-105">Параметры политики клиента можно настроить во время ее создания или с помощью cmdlet **Set-CsClientPolicy** изменить параметры существующей политики.</span><span class="sxs-lookup"><span data-stu-id="46280-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="46280-106">Задание политик клиента</span><span class="sxs-lookup"><span data-stu-id="46280-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="46280-107">Для всех настроек политики клиента в Skype для бизнеса Online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="46280-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="46280-108">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46280-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="46280-109">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="46280-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="46280-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="46280-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="46280-111">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="46280-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="46280-p101">Если у вас нет версии 3.0 или более высокой, необходимо скачать и установить обновления для Windows PowerShell. Чтобы [скачать Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) и обновить Windows PowerShell до версии 4.0, см. Windows PowerShell 4.0. Перезагрузите компьютер, когда вам будет предложено.</span><span class="sxs-lookup"><span data-stu-id="46280-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="46280-115">Вам также потребуется установить модуль Windows PowerShell для Teams, который позволяет создавать удаленные сеансы Windows PowerShell подключения к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="46280-115">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="46280-116">Если вам нужно узнать больше, см. подключение к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx)в одном окне Windows PowerShell окна.</span><span class="sxs-lookup"><span data-stu-id="46280-116">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="46280-117">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="46280-117">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="46280-118">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="46280-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="46280-119">В **окне Windows PowerShell** подключения к Microsoft 365 или Office 365, вы работающим с помощью:</span><span class="sxs-lookup"><span data-stu-id="46280-119">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="46280-120">Соединитель Skype для бизнеса Online сейчас является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46280-120">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
    >
    > <span data-ttu-id="46280-121">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="46280-121">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
<span data-ttu-id="46280-122">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46280-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="46280-123">Отключение эмотиконов, уведомлений о присутствии и запрет на сохранение мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="46280-123">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="46280-124">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46280-124">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="46280-125">См. дополнительные [функции для new-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="46280-125">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="46280-126">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46280-126">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="46280-127">Дополнительные узнать о [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="46280-127">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="46280-128">Если вы уже создали политику, то можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](https://technet.microsoft.com/library/mt779153.aspx) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="46280-128">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="46280-129">Разрешение перехода по URL-адресам или гиперссылкам в мгновенных сообщениях</span><span class="sxs-lookup"><span data-stu-id="46280-129">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="46280-130">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46280-130">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="46280-131">См. дополнительные [функции для new-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="46280-131">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="46280-132">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46280-132">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="46280-133">Дополнительные узнать о [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="46280-133">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="46280-134">Если вы уже создали политику, то можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](https://technet.microsoft.com/library/mt779153.aspx) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="46280-134">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="46280-135">Запрет отображения последних контактов</span><span class="sxs-lookup"><span data-stu-id="46280-135">Prevent showing recent contacts</span></span>

- <span data-ttu-id="46280-136">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46280-136">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="46280-137">См. дополнительные [функции для new-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="46280-137">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="46280-138">Чтобы предоставить новую политику Amos Marble, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46280-138">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="46280-139">Дополнительные узнать о [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="46280-139">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="46280-140">Если вы уже создали политику, то можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](https://technet.microsoft.com/library/mt779153.aspx) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="46280-140">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="46280-141">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="46280-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="46280-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="46280-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="46280-143">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="46280-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="46280-144">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="46280-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="46280-145">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="46280-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="46280-146">Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="46280-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="46280-147">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="46280-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="46280-148">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="46280-148">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="46280-149">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46280-149">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="46280-150">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="46280-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="46280-151">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="46280-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="46280-152">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="46280-152">Related topics</span></span>
[<span data-ttu-id="46280-153">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="46280-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="46280-154">Блокировать передачу файлов по точкам</span><span class="sxs-lookup"><span data-stu-id="46280-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="46280-155">Настройка политик для организации</span><span class="sxs-lookup"><span data-stu-id="46280-155">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
