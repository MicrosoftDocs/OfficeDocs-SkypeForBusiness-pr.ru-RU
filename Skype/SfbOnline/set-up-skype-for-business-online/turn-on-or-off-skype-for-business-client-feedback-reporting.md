---
title: Включение и выключение отчетов и отзывов клиентов в Skype для бизнеса
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: Вы можете позволить пользователям Skype для бизнеса пользователям использовать встроенное средство обратной связи Skype для бизнеса приложения, чтобы пользователи могли сообщать о проблемах и напрямую сообщать о своих впечатлениях в Корпорацию Майкрософт.
ms.openlocfilehash: 151ba9ee82c95f088f5c7fc87de3a06ce609ab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239102"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="856b3-103">Включение и выключение отчетов и отзывов клиентов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="856b3-103">Turn on or off Skype for Business client feedback reporting</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="856b3-104">Вы можете позволить пользователям Skype для бизнеса Online использовать встроенное средство обратной связи Skype для бизнеса приложения, чтобы позволить пользователям сообщать о проблемах и напрямую предоставлять корпорации Майкрософт отзывы об их впечатлениях.</span><span class="sxs-lookup"><span data-stu-id="856b3-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Значок "Обратная связь"](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="856b3-106">С помощью этого средства пользователь может скопировать журналы из приложения на своем устройстве, чтобы помочь корпорации Майкрософт лучше исследовать и устранять проблемы, которые могут возникнуть у него.</span><span class="sxs-lookup"><span data-stu-id="856b3-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Сообщение о проблеме с помощью Параметры значка](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="856b3-108">Кроме того, с помощью параметра  _EnableOnlineFeedbackScreenshot_ пользователи могут добавлять в отзывы снимки экранов своих устройств.</span><span class="sxs-lookup"><span data-stu-id="856b3-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="856b3-110">Журналы, собранные средством обратной связи приложения, хранятся в США не более 90 дней, пока ведется изучение проблемы.</span><span class="sxs-lookup"><span data-stu-id="856b3-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="856b3-111">В связи с этим просим не активировать данную функцию, если это условие нарушает действующую в вашей организации политику защиты данных.</span><span class="sxs-lookup"><span data-stu-id="856b3-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="856b3-112">Начните Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="856b3-112">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="856b3-113">Skype для бизнеса Online Connector в настоящее время является частью последней версии Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="856b3-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="856b3-114">Если вы используете последний общедоступный Teams PowerShell, вам не нужно устанавливать Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="856b3-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="856b3-115">Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="856b3-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="856b3-116">Откройте Windows PowerShell командную команду и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="856b3-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   <span data-ttu-id="856b3-117">Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="856b3-117">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="856b3-118">Включение средства обратной связи в клиентском приложении для всех пользователей в организации</span><span class="sxs-lookup"><span data-stu-id="856b3-118">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="856b3-119">Чтобы включить отчеты о отзывах для пользователей в организации и разрешить им отправлять снимки экрана устройства, запустите:</span><span class="sxs-lookup"><span data-stu-id="856b3-119">To enable feedback reporting for users in your organization and allow them to submit device screenshots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="856b3-120">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="856b3-120">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="856b3-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="856b3-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="856b3-122">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="856b3-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="856b3-123">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="856b3-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="856b3-124">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="856b3-124">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="856b3-125">Шесть причин, по которым может потребоваться использовать Windows PowerShell управление Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="856b3-125">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="856b3-126">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="856b3-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="856b3-127">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="856b3-127">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="856b3-128">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="856b3-128">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="856b3-129">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="856b3-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="856b3-130">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="856b3-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="856b3-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="856b3-131">Related topics</span></span>
[<span data-ttu-id="856b3-132">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="856b3-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="856b3-133">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="856b3-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
