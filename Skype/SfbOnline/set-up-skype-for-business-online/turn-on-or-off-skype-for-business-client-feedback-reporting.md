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
description: Вы можете предоставить пользователям Skype для бизнеса возможность использования встроенного средства обратной связи в приложении Skype для бизнеса, позволяя пользователям сообщать о проблемах и напрямую сообщать майкрософт об их впечатлениях.
ms.openlocfilehash: 9b9134f857be540a528ca12b51a4793c01f70fa4
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569005"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="c0816-103">Включение и выключение отчетов и отзывов клиентов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c0816-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="c0816-104">Вы можете предоставить пользователям Skype для бизнеса Online возможность использования встроенного средства обратной связи в приложении Skype для бизнеса, позволяя пользователям сообщать о проблемах и напрямую сообщать майкрософт об их впечатлениях.</span><span class="sxs-lookup"><span data-stu-id="c0816-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Значок "Предоставить отзыв"](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="c0816-106">С помощью этого средства пользователь может скопировать журналы из приложения на своем устройстве, чтобы помочь корпорации Майкрософт лучше изучить и устранить проблемы, которые могут возникнуть у него.</span><span class="sxs-lookup"><span data-stu-id="c0816-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Сообщение о проблеме с помощью значка "Параметры"](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="c0816-108">Кроме того, с помощью параметра  _EnableOnlineFeedbackScreenshot_ пользователи могут добавлять в отзывы снимки экранов своих устройств.</span><span class="sxs-lookup"><span data-stu-id="c0816-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="c0816-110">Журналы, собранные средством обратной связи приложения, хранятся в США не более 90 дней, пока ведется работа по ее исследованию.</span><span class="sxs-lookup"><span data-stu-id="c0816-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="c0816-111">В связи с этим просим не активировать данную функцию, если это условие нарушает действующую в вашей организации политику защиты данных.</span><span class="sxs-lookup"><span data-stu-id="c0816-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="c0816-112">Начать Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0816-112">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="c0816-113">Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0816-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="c0816-114">Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="c0816-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="c0816-115">Установите модуль [Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="c0816-115">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="c0816-116">Откройте Windows PowerShell и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="c0816-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   <span data-ttu-id="c0816-117">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0816-117">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="c0816-118">Включение средства обратной связи в клиентском приложении для всех пользователей в организации</span><span class="sxs-lookup"><span data-stu-id="c0816-118">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="c0816-119">Чтобы включить отчеты о отзывах для пользователей в организации и разрешить им отправлять снимки экрана устройств, запустите 3</span><span class="sxs-lookup"><span data-stu-id="c0816-119">To enable feedback reporting for users in your organization and allow them to submit device screenshots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c0816-120">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c0816-120">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="c0816-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="c0816-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c0816-122">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="c0816-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c0816-123">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="c0816-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c0816-124">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c0816-124">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c0816-125">Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="c0816-125">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c0816-126">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="c0816-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c0816-127">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c0816-127">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c0816-128">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0816-128">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c0816-129">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c0816-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c0816-130">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c0816-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="c0816-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c0816-131">Related topics</span></span>
[<span data-ttu-id="c0816-132">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c0816-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="c0816-133">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c0816-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
