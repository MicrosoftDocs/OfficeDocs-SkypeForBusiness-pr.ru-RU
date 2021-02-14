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
ms.openlocfilehash: 3b91bc88c20450b7c0d9c5705bceec53af5f9edb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814188"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="3fc76-103">Включение и выключение отчетов и отзывов клиентов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3fc76-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="3fc76-104">Вы можете предоставить своим пользователям Skype для бизнеса Online возможность использования встроенного средства обратной связи в приложении Skype для бизнеса, позволяя пользователям сообщать о проблемах и напрямую сообщать майкрософт об их впечатлениях.</span><span class="sxs-lookup"><span data-stu-id="3fc76-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="3fc76-106">С помощью этого средства пользователь может скопировать журналы из приложения на своем устройстве, чтобы помочь корпорации Майкрософт лучше изучить и устранить проблемы, которые могут возникнуть у него.</span><span class="sxs-lookup"><span data-stu-id="3fc76-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="3fc76-108">Кроме того, с помощью параметра  _EnableOnlineFeedbackScreenshot_ пользователи могут добавлять в отзывы снимки экранов своих устройств.</span><span class="sxs-lookup"><span data-stu-id="3fc76-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="3fc76-110">Журналы, собранные средством обратной связи приложения, хранятся в США не более 90 дней, пока ведется работа по ее исследованию.</span><span class="sxs-lookup"><span data-stu-id="3fc76-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="3fc76-111">В связи с этим просим не активировать данную функцию, если это условие нарушает действующую в вашей организации политику защиты данных.</span><span class="sxs-lookup"><span data-stu-id="3fc76-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="3fc76-112">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fc76-112">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="3fc76-113">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="3fc76-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="3fc76-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3fc76-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3fc76-115">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="3fc76-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="3fc76-116">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fc76-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="3fc76-117">Чтобы [скачать Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) и обновить Windows PowerShell до версии 4.0, см. Windows PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="3fc76-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="3fc76-118">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="3fc76-118">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="3fc76-119">Вам также потребуется установить модуль Windows PowerShell для Teams, который позволяет создавать удаленные сеансы Windows PowerShell подключения к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3fc76-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
<span data-ttu-id="3fc76-120">Если вам нужно узнать больше, см. подключение к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx)в одном окне Windows PowerShell окна.</span><span class="sxs-lookup"><span data-stu-id="3fc76-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="3fc76-121">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3fc76-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="3fc76-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3fc76-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3fc76-123">В **окне Windows PowerShell** подключения к Microsoft 365 или Office 365, вы работающим с помощью:</span><span class="sxs-lookup"><span data-stu-id="3fc76-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="3fc76-124">Соединитель Skype для бизнеса Online сейчас является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fc76-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="3fc76-125">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3fc76-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
 
   ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   <span data-ttu-id="3fc76-126">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера[для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fc76-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or[Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="3fc76-127">Включение средства обратной связи в клиентском приложении для всех пользователей в организации</span><span class="sxs-lookup"><span data-stu-id="3fc76-127">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="3fc76-128">Чтобы включить отчеты о отзывах для пользователей в организации и разрешить им отправлять снимки экрана устройств, запустите 2</span><span class="sxs-lookup"><span data-stu-id="3fc76-128">To enable feedback reporting for users in your organization and allow them to submit device screen shots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3fc76-129">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="3fc76-129">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="3fc76-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="3fc76-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3fc76-131">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="3fc76-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="3fc76-132">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="3fc76-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3fc76-133">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3fc76-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3fc76-134">Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="3fc76-134">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="3fc76-135">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="3fc76-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3fc76-136">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3fc76-136">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="3fc76-137">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fc76-137">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="3fc76-138">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3fc76-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3fc76-139">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3fc76-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="3fc76-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3fc76-140">Related topics</span></span>
[<span data-ttu-id="3fc76-141">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3fc76-141">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="3fc76-142">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3fc76-142">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
