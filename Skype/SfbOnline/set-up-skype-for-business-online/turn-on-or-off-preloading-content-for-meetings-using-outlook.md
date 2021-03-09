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
ms.openlocfilehash: 7a59edb72b72cb42661cdf0e2cb350d7617a47bf
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568905"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="f5cc0-103">Включение и выключение разрешения предварительной загрузки содержимого для собраний с помощью Outlook</span><span class="sxs-lookup"><span data-stu-id="f5cc0-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="f5cc0-104">Пользователи могут заранее перезагружать содержимое, файлы или вложения, вложенные в приглашение на собрание Outlook, на собрание Skype для бизнеса Online, но вы можете включить или отключить эту возможность.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="f5cc0-105">Этот режим по умолчанию включен для всех организаций, использующих Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="f5cc0-106">Узнайте, как [предварительно загрузка вложений для собрания Skype для бизнеса.](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)</span><span class="sxs-lookup"><span data-stu-id="f5cc0-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f5cc0-107">В настоящее время в Skype для бизнеса Online нет cmdlets для настройки и просмотра значений в сети для _MaxContentStorageMB_ и _MaxUploadFileMB._</span><span class="sxs-lookup"><span data-stu-id="f5cc0-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="f5cc0-108">Они доступны только для локальных развертываний.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="f5cc0-109">Важно знать, что содержимое не будет загружено на собрание, если вложенное содержимое превышает максимально допустимый предел _MaxUploadFileSizeMB_ или достигнуто ограничение _MaxContentStorageMB._</span><span class="sxs-lookup"><span data-stu-id="f5cc0-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="f5cc0-110">Чтобы начать работу, можно сделать следующее</span><span class="sxs-lookup"><span data-stu-id="f5cc0-110">To get you started</span></span>

## <a name="start-windows-powershell"></a><span data-ttu-id="f5cc0-111">Начать Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5cc0-111">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="f5cc0-112">Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="f5cc0-113">Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-113">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="f5cc0-114">Установите модуль [Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="f5cc0-114">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="f5cc0-115">Откройте Windows PowerShell и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f5cc0-115">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

<span data-ttu-id="f5cc0-116">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-116">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="f5cc0-117">Включение и выключение функции</span><span class="sxs-lookup"><span data-stu-id="f5cc0-117">Turning it on or off</span></span>

<span data-ttu-id="f5cc0-118">Возможность предварительной загрузки содержимого, вложенного в приглашение на собрание Outlook, в собраниях Skype для бизнеса Online включена по умолчанию, но может потребоваться запретить пользователям в вашей организации предварительной загрузки содержимого во время собраний.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-118">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f5cc0-119">Этот параметр можно отключить только для всей организации; его нельзя включить или отключить для одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-119">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="f5cc0-120">**Чтобы отключить функцию, откройте Windows PowerShell и выполните следующие действия:**</span><span class="sxs-lookup"><span data-stu-id="f5cc0-120">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="f5cc0-121">**Чтобы снова включить функцию, откройте Windows PowerShell и выполните следующие действия:**</span><span class="sxs-lookup"><span data-stu-id="f5cc0-121">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f5cc0-122">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f5cc0-122">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="f5cc0-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f5cc0-124">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-124">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="f5cc0-125">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-125">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f5cc0-126">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f5cc0-126">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f5cc0-127">Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="f5cc0-127">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f5cc0-128">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="f5cc0-128">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f5cc0-129">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="f5cc0-129">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f5cc0-130">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5cc0-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f5cc0-131">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f5cc0-131">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f5cc0-132">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f5cc0-132">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="f5cc0-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f5cc0-133">Related topics</span></span>
[<span data-ttu-id="f5cc0-134">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f5cc0-134">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="f5cc0-135">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f5cc0-135">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
