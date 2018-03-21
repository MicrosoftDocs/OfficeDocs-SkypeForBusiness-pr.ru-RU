---
title: "Включение и выключение разрешения предварительной загрузки содержимого для собраний с помощью Outlook"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 459be3e5ca1c9c2e2ba008ed169942435910b4f4
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2018
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="9cf0a-103">Включение и выключение разрешения предварительной загрузки содержимого для собраний с помощью Outlook</span><span class="sxs-lookup"><span data-stu-id="9cf0a-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="9cf0a-104">Пользователи может предварительно контент, файлы или вложения, подключенные к приглашения собрание Outlook Скайп для собраний по сети предприятия, но его можно включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="9cf0a-105">Он включен по умолчанию для всех организаций, использующих Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="9cf0a-106">Просмотреть как [предварительной загрузки вложений для Скайп для собраний](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span><span class="sxs-lookup"><span data-stu-id="9cf0a-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9cf0a-107">На данный момент недоступны не командлеты в Скайп для бизнеса в Интернет для просмотра online значения для _MaxContentStorageMB_ и _MaxUploadFileMB_или параметр.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="9cf0a-108">Они доступны только для локальных развертываний.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="9cf0a-109">Важно знать, что содержимое не будет загружена в собрание Если вложенные превышает _MaxUploadFileSizeMB_ или _MaxContentStorageMB_ максимального числа.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="9cf0a-110">Чтобы начать работу, можно сделать следующее</span><span class="sxs-lookup"><span data-stu-id="9cf0a-110">To get you started</span></span>

### 

 <span data-ttu-id="9cf0a-111">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="9cf0a-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="9cf0a-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9cf0a-113">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="9cf0a-p103">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="9cf0a-p104">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="9cf0a-120">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="9cf0a-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="9cf0a-121">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9cf0a-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="9cf0a-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9cf0a-123">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9cf0a-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9cf0a-124">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

<span data-ttu-id="9cf0a-125">Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [подключение к Скайп для бизнеса в Интернет с помощью Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="9cf0a-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="9cf0a-126">Включение и выключение функции</span><span class="sxs-lookup"><span data-stu-id="9cf0a-126">Turning it on or off</span></span>

<span data-ttu-id="9cf0a-127">Возможность загрузки содержимого, подключенного к приглашения собрание Outlook Скайп для собраний по сети Business включен по умолчанию, но может потребоваться запретить пользователям в вашей организации из предварительной загрузки содержимого в свои собрания.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-127">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9cf0a-128">Этот параметр можно только включить или выключить для всей организации; не может быть включено или отключено для одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-128">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="9cf0a-129">**Чтобы отключить функцию, откройте Windows PowerShell и выполните следующие действия:**</span><span class="sxs-lookup"><span data-stu-id="9cf0a-129">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="9cf0a-130">**Чтобы снова включить функцию, откройте Windows PowerShell и выполните следующие действия:**</span><span class="sxs-lookup"><span data-stu-id="9cf0a-130">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9cf0a-131">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9cf0a-131">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="9cf0a-p105">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9cf0a-135">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9cf0a-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9cf0a-136">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="9cf0a-136">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="9cf0a-p106">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9cf0a-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="9cf0a-139">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cf0a-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="9cf0a-140">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9cf0a-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9cf0a-141">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9cf0a-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="9cf0a-142">See also</span><span class="sxs-lookup"><span data-stu-id="9cf0a-142">Related topics</span></span>
[<span data-ttu-id="9cf0a-143">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9cf0a-143">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="9cf0a-144">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9cf0a-144">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

## <a name="feedback"></a><span data-ttu-id="9cf0a-145">Отзыв?</span><span class="sxs-lookup"><span data-stu-id="9cf0a-145">Feedback?</span></span>
<span data-ttu-id="9cf0a-146">Для предоставления продукта свои отзывы и предложения или сообщите нам знать, как в нашем [Скайп для бизнеса свои отзывы и предложения](https://www.skypefeedback.com)см.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-146">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>