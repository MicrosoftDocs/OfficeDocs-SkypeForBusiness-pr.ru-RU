---
title: Настройка политик клиента в организации
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям.
ms.openlocfilehash: 791d54dd12e5f222958fd4513abdeca2433cbf16
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23857864"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="36761-103">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="36761-103">Set up client policies for your organization</span></span>

<span data-ttu-id="36761-104">[] Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="36761-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="36761-105">Во время создания политики можно настроить параметры политики клиента или командлет **Set-CsClientPolicy** для изменения параметров существующей политики.</span><span class="sxs-lookup"><span data-stu-id="36761-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="36761-106">Задание политик клиента</span><span class="sxs-lookup"><span data-stu-id="36761-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="36761-107">Для всех настроек политики клиента в Skype для бизнеса Online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="36761-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="36761-108">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36761-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="36761-109">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="36761-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="36761-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="36761-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="36761-111">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="36761-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="36761-p101">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="36761-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="36761-p102">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="36761-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="36761-118">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="36761-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="36761-119">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="36761-119">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="36761-120">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="36761-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="36761-121">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="36761-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="36761-122">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="36761-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="36761-123">Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [подключение к Скайп для бизнеса в Интернет с помощью Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="36761-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="36761-124">Отключение эмотиконов, уведомлений о присутствии и запрет на сохранение мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="36761-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="36761-125">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="36761-125">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  <span data-ttu-id="36761-126">В разделе Дополнительные с параметрами командлета [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="36761-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="36761-127">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="36761-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  <span data-ttu-id="36761-128">Просмотрите Дополнительные сведения о командлета [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="36761-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="36761-129">Если вы уже создали политику, можно использовать командлет [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) для внесения изменений в существующую политику и затем используйте командлет [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) для применения параметров для пользователей.</span><span class="sxs-lookup"><span data-stu-id="36761-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="36761-130">Разрешение перехода по URL-адресам или гиперссылкам в мгновенных сообщениях</span><span class="sxs-lookup"><span data-stu-id="36761-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="36761-131">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="36761-131">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  <span data-ttu-id="36761-132">В разделе Дополнительные с параметрами командлета [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="36761-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="36761-133">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="36761-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  <span data-ttu-id="36761-134">Просмотрите Дополнительные сведения о командлета [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="36761-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="36761-135">Если вы уже создали политику, можно использовать командлет [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) для внесения изменений в существующую политику и затем используйте командлет [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) для применения параметров для пользователей.</span><span class="sxs-lookup"><span data-stu-id="36761-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="36761-136">Запрет отображения последних контактов</span><span class="sxs-lookup"><span data-stu-id="36761-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="36761-137">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="36761-137">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  <span data-ttu-id="36761-138">В разделе Дополнительные с параметрами командлета [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="36761-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="36761-139">Чтобы предоставить новую политику Amos Marble, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="36761-139">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  <span data-ttu-id="36761-140">Просмотрите Дополнительные сведения о командлета [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="36761-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="36761-141">Если вы уже создали политику, можно использовать командлет [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) для внесения изменений в существующую политику и затем используйте командлет [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) для применения параметров для пользователей.</span><span class="sxs-lookup"><span data-stu-id="36761-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="36761-142">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="36761-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="36761-143">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="36761-143">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="36761-144">С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="36761-144">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="36761-145">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="36761-145">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="36761-146">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="36761-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="36761-147">Шесть причин использовать Windows PowerShell для управления Office 365 </span><span class="sxs-lookup"><span data-stu-id="36761-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="36761-p104">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="36761-p104">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="36761-150">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36761-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="36761-151">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="36761-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="36761-152">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="36761-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="36761-153">See also</span><span class="sxs-lookup"><span data-stu-id="36761-153">Related topics</span></span>
[<span data-ttu-id="36761-154">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="36761-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="36761-155">Передача файлов точка-точка блока</span><span class="sxs-lookup"><span data-stu-id="36761-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="36761-156">Настройка политик конференц-связи в вашей организации</span><span class="sxs-lookup"><span data-stu-id="36761-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 