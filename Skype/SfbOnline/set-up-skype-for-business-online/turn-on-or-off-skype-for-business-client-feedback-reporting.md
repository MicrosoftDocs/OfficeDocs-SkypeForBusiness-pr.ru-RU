---
title: Включение и выключение отчетов и отзывов клиентов в Skype для бизнеса
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: Можно включить вашей Скайп для бизнес-пользователям использовать встроенные Скайп для средство отправки отзывов приложения Business чтобы дать возможность пользователям отчитываться о проблемах и отзывы и напрямую в корпорацию Майкрософт о своих качества.
ms.openlocfilehash: f681a3745f44745083abc4b1750870aa7d3c4efe
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370795"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="cb534-103">Включение и выключение отчетов и отзывов клиентов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cb534-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="cb534-104">Можно включить вашей Скайп для бизнеса в Интернет пользователей для использования встроенной Скайп для средство отправки отзывов приложения Business чтобы дать возможность пользователям отчитываться о проблемах и отзывы и напрямую в корпорацию Майкрософт о своих качества.</span><span class="sxs-lookup"><span data-stu-id="cb534-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="cb534-106">С помощью этой программы, пользователь может копировать журналы из приложения на мобильном устройстве, помогая корпорации Майкрософт лучше исследовать и устранения проблем, которые они могут оказать.</span><span class="sxs-lookup"><span data-stu-id="cb534-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="cb534-108">Кроме того, с помощью параметра  _EnableOnlineFeedbackScreenshot_ пользователи могут добавлять в отзывы снимки экранов своих устройств.</span><span class="sxs-lookup"><span data-stu-id="cb534-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="cb534-110">Будут храниться журналы, собранные средство отправки отзывов приложения для более чем на 90 дней в Соединенных Штатах Америки при проблемы изучается.</span><span class="sxs-lookup"><span data-stu-id="cb534-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="cb534-111">В связи с этим просим не активировать данную функцию, если это условие нарушает действующую в вашей организации политику защиты данных.</span><span class="sxs-lookup"><span data-stu-id="cb534-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="cb534-112">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb534-112">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="cb534-113">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="cb534-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="cb534-114">Чтобы убедиться, что выполняется версия 3.0 или более поздняя версия, зайдите в **Меню "Пуск"** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="cb534-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="cb534-115">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="cb534-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="cb534-p102">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="cb534-p102">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="cb534-p103">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="cb534-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="cb534-122">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="cb534-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="cb534-123">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cb534-123">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="cb534-124">Из **меню "Пуск"** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="cb534-124">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="cb534-125">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cb534-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cb534-126">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="cb534-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
 
   ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   <span data-ttu-id="cb534-127">Дополнительные сведения о запуске Windows PowerShell см. в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или[Подключение к Skype для бизнеса с использованием Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="cb534-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="cb534-128">Включение средства обратной связи в клиентском приложении для всех пользователей в организации</span><span class="sxs-lookup"><span data-stu-id="cb534-128">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="cb534-129">Чтобы включить свои отзывы и предложения отчетов для пользователей в вашей организации и их отправка снимки экрана устройства, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cb534-129">To enable feedback reporting for users in your organization and allow them to submit device screen shots, run:</span></span>
 
  ```
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="cb534-130">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="cb534-130">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="cb534-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="cb534-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="cb534-132">С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="cb534-132">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="cb534-133">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="cb534-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cb534-134">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cb534-134">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="cb534-135">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="cb534-135">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="cb534-p105">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="cb534-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="cb534-138">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb534-138">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="cb534-139">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cb534-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="cb534-140">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cb534-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="cb534-141">See also</span><span class="sxs-lookup"><span data-stu-id="cb534-141">Related topics</span></span>
[<span data-ttu-id="cb534-142">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cb534-142">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="cb534-143">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cb534-143">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
