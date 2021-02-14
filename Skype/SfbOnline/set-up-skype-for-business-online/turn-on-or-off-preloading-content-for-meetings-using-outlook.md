---
title: Включение и выключение разрешения предварительной загрузки содержимого для собраний с помощью Outlook
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 079d0642158aa6d28b3c92a63e77afa0a0024d94
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814588"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="fc0bf-103">Включение и выключение разрешения предварительной загрузки содержимого для собраний с помощью Outlook</span><span class="sxs-lookup"><span data-stu-id="fc0bf-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="fc0bf-104">Пользователи могут заранее грузить содержимое, файлы или вложения, вложенные в приглашение на собрание Outlook, на собрание Skype для бизнеса Online, но вы можете включить или отключить эту возможность.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="fc0bf-105">Этот режим по умолчанию включен для всех организаций, использующих Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="fc0bf-106">Узнайте, как [предварительно загрузка вложений для собрания Skype для бизнеса.](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)</span><span class="sxs-lookup"><span data-stu-id="fc0bf-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc0bf-107">В настоящее время в Skype для бизнеса Online нет cmdlets для настройки и просмотра значений в сети для _MaxContentStorageMB_ и _MaxUploadFileMB._</span><span class="sxs-lookup"><span data-stu-id="fc0bf-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="fc0bf-108">Они доступны только для локальных развертываний.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="fc0bf-109">Важно знать, что содержимое не будет загружено на собрание, если вложенное содержимое превышает максимально допустимый предел _MaxUploadFileSizeMB_ или достигнуто ограничение _MaxContentStorageMB._</span><span class="sxs-lookup"><span data-stu-id="fc0bf-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="fc0bf-110">Чтобы начать работу, можно сделать следующее</span><span class="sxs-lookup"><span data-stu-id="fc0bf-110">To get you started</span></span>

### 

 <span data-ttu-id="fc0bf-111">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="fc0bf-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="fc0bf-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="fc0bf-113">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="fc0bf-114">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="fc0bf-115">Чтобы [скачать Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) и обновить Windows PowerShell до версии 4.0, см. Windows PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="fc0bf-116">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-116">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="fc0bf-p104">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="fc0bf-120">Если вам нужно узнать больше, см. подключение к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx)в одном окне Windows PowerShell окна.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="fc0bf-121">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fc0bf-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="fc0bf-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="fc0bf-123">В **окне Windows PowerShell** подключения к Microsoft 365 или Office 365, вы работающим с помощью:</span><span class="sxs-lookup"><span data-stu-id="fc0bf-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
> [!NOTE]
> <span data-ttu-id="fc0bf-124">Соединитель Skype для бизнеса Online сейчас является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="fc0bf-125">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
  
```PowerShell
Import-Module -Name MicrosoftTeams
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

<span data-ttu-id="fc0bf-126">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="fc0bf-127">Включение и выключение функции</span><span class="sxs-lookup"><span data-stu-id="fc0bf-127">Turning it on or off</span></span>

<span data-ttu-id="fc0bf-128">Возможность предварительной загрузки содержимого, вложенного в приглашение на собрание Outlook, для собраний Skype для бизнеса Online включена по умолчанию, но может потребоваться запретить пользователям в вашей организации предварительной загрузки содержимого в своих собраниях.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-128">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fc0bf-129">Этот параметр можно отключить только для всей организации. вы не можете включить или отключить ее для одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-129">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="fc0bf-130">**Чтобы отключить функцию, откройте Windows PowerShell и выполните следующие действия:**</span><span class="sxs-lookup"><span data-stu-id="fc0bf-130">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="fc0bf-131">**Чтобы снова включить функцию, откройте Windows PowerShell и выполните следующие действия:**</span><span class="sxs-lookup"><span data-stu-id="fc0bf-131">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="fc0bf-132">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="fc0bf-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="fc0bf-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="fc0bf-134">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="fc0bf-135">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fc0bf-136">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="fc0bf-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="fc0bf-137">Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="fc0bf-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="fc0bf-138">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="fc0bf-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="fc0bf-139">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="fc0bf-139">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="fc0bf-140">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc0bf-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="fc0bf-141">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="fc0bf-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="fc0bf-142">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="fc0bf-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="fc0bf-143">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fc0bf-143">Related topics</span></span>
[<span data-ttu-id="fc0bf-144">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="fc0bf-144">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fc0bf-145">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="fc0bf-145">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
