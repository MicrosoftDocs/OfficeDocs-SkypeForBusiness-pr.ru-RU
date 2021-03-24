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
ms.openlocfilehash: 3706e6b4fafe15aa8b799170001af61b837968da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100535"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="756fc-103">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="756fc-103">Set up client policies for your organization</span></span>

<span data-ttu-id="756fc-104">Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="756fc-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="756fc-105">Параметры политики клиента можно настроить во время создания политики или с помощью cmdlet **Set-CsClientPolicy** изменить параметры существующей политики.</span><span class="sxs-lookup"><span data-stu-id="756fc-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="756fc-106">Задание политик клиента</span><span class="sxs-lookup"><span data-stu-id="756fc-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="756fc-107">Для всех настроек политики клиента в Skype для бизнеса Online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="756fc-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="756fc-108">Начать Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="756fc-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="756fc-109">Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="756fc-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="756fc-110">Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="756fc-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="756fc-111">Установите модуль [Teams PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="756fc-111">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="756fc-112">Откройте Windows PowerShell и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="756fc-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="756fc-113">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="756fc-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="756fc-114">Отключение эмотиконов, уведомлений о присутствии и запрет на сохранение мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="756fc-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="756fc-115">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="756fc-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="756fc-116">См. дополнительные [функции для new-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="756fc-116">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="756fc-117">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="756fc-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="756fc-118">Подробнее о [cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="756fc-118">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="756fc-119">Если вы уже создали политику, то можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](/powershell/module/skype/Set-CsClientPolicy) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="756fc-119">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="756fc-120">Разрешение перехода по URL-адресам или гиперссылкам в мгновенных сообщениях</span><span class="sxs-lookup"><span data-stu-id="756fc-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="756fc-121">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="756fc-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="756fc-122">См. дополнительные [функции для new-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="756fc-122">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="756fc-123">Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="756fc-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="756fc-124">Подробнее о [cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="756fc-124">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="756fc-125">Если вы уже создали политику, то можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](/powershell/module/skype/Set-CsClientPolicy) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="756fc-125">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="756fc-126">Запрет отображения последних контактов</span><span class="sxs-lookup"><span data-stu-id="756fc-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="756fc-127">Чтобы создать политику для настроек, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="756fc-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="756fc-128">См. дополнительные [функции для new-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="756fc-128">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="756fc-129">Чтобы предоставить новую политику Amos Marble, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="756fc-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="756fc-130">Подробнее о [cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="756fc-130">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="756fc-131">Если вы уже создали политику, то можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](/powershell/module/skype/Set-CsClientPolicy) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="756fc-131">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="756fc-132">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="756fc-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="756fc-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="756fc-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="756fc-134">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="756fc-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="756fc-135">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="756fc-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="756fc-136">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="756fc-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="756fc-137">Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="756fc-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="756fc-138">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="756fc-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="756fc-139">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="756fc-139">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="756fc-140">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="756fc-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="756fc-141">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="756fc-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="756fc-142">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="756fc-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="756fc-143">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="756fc-143">Related topics</span></span>
[<span data-ttu-id="756fc-144">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="756fc-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="756fc-145">Блокировать передачу файлов по точкам</span><span class="sxs-lookup"><span data-stu-id="756fc-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="756fc-146">Настройка политик для организации</span><span class="sxs-lookup"><span data-stu-id="756fc-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
