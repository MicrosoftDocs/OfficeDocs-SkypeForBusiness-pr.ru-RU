---
title: "Отправить сообщение электронной почты для пользователя с помощью свои данные для подключения"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Отправьте сообщение электронной почты с их аудиоконференций сведения пользователей."
ms.openlocfilehash: cb7aaa956b6a679b918603e2aef2ff15ff04a779
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a><span data-ttu-id="a96b1-103">Отправка пользователям электронных писем с информацией о конференции с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="a96b1-103">Send an email to a user with their Audio Conferencing information</span></span>

<span data-ttu-id="a96b1-104">В некоторых случаях Скайп для бизнеса или группами Майкрософт пользователей может потребоваться отправить их их аудиоконференции сведения.</span><span class="sxs-lookup"><span data-stu-id="a96b1-104">Sometimes Skype for Business or Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="a96b1-105">Это можно сделать с помощью **Скайп по центру администрирования бизнеса** , нажав кнопку **Отправить сведения о конференции по электронной почте** в разделе свойства для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a96b1-105">You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="a96b1-106">При отправке это сообщение, он будет содержать все сведения аудиоконференций, включая:</span><span class="sxs-lookup"><span data-stu-id="a96b1-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="a96b1-107">Телефонный номер конференции или номер телефонного подключения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a96b1-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="a96b1-108">Идентификатор конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="a96b1-108">The user's conference ID.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a96b1-109">Статические идентификаторы используются в том случае, когда пользователи в вашей организации не требуется запомнить случайное число; их можно выбрать определенное число или использовать один, который легко запомнить.</span><span class="sxs-lookup"><span data-stu-id="a96b1-109">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="a96b1-110">При использовании идентификаторы динамических конференции каждого собрания, расписания пользователя будет присваивает идентификатор уникальный конференции.</span><span class="sxs-lookup"><span data-stu-id="a96b1-110">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="a96b1-111">Если вы хотите назначить динамических вместо статических конференции идентификаторы, [Перейдите сюда](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="a96b1-111">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
<span data-ttu-id="a96b1-112">Ниже приведен пример сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="a96b1-112">Here is an example of the email that is sent:</span></span>
  
![Сообщение о конференц-связи с телефонным подключением](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="a96b1-114">Отправить сообщение электронной почты с информацией аудиоконференций для пользователя</span><span class="sxs-lookup"><span data-stu-id="a96b1-114">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="a96b1-115">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="a96b1-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a96b1-116">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса**и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="a96b1-116">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a96b1-117">Щелкните **Пользователи**и затем выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="a96b1-117">Click **Users**, and then select the user.</span></span>
    
4. <span data-ttu-id="a96b1-118">На панели действий щелкните **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a96b1-118">In the Action pane, click **Send conference info via email**.</span></span>
    
> [!TIP]
> <span data-ttu-id="a96b1-119">Можно также отправить электронной почты для пользователя с помощью параметров аудиоконференций путем изменения свойства пользователя **аудиоконференции** > **отправлять сведения о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a96b1-119">You can also send email to the user with the audio conferencing settings by editing the user's properties and then clicking **Audio conferencing** > **Send conference info via email**.</span></span> 
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="a96b1-120">Что еще необходимо знать о таких сообщениях?</span><span class="sxs-lookup"><span data-stu-id="a96b1-120">What else should you know about this email?</span></span>

- <span data-ttu-id="a96b1-121">Существует несколько сообщений электронной почты, отправленных для пользователей в вашей организации после их, необходимо включить для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="a96b1-121">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="a96b1-122">Если для них назначена лицензия на **Аудиоконференции** .</span><span class="sxs-lookup"><span data-stu-id="a96b1-122">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="a96b1-123">При сбросе вручную аудиоконференций ПИН-код пользователя.</span><span class="sxs-lookup"><span data-stu-id="a96b1-123">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="a96b1-124">Выполнение сброса идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="a96b1-124">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="a96b1-125">Если лицензия на **Аудиоконференции** удаляется из их.</span><span class="sxs-lookup"><span data-stu-id="a96b1-125">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="a96b1-126">Поставщик услуг аудиоконференций для пользователя изменении корпорацией Майкрософт на другой поставщик или **Нет**.</span><span class="sxs-lookup"><span data-stu-id="a96b1-126">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="a96b1-127">При изменении поставщика аудиоконференций для пользователя в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a96b1-127">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="a96b1-128">По умолчанию отправителя сообщения электронной почты будут из Office 365, но можно изменить адрес электронной почты и отображаемое имя с помощью командлета [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a96b1-128">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet.</span></span> <span data-ttu-id="a96b1-129">Чтобы изменить адрес электронной почты, который отправляет сообщение электронной почты для пользователей, необходимо выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="a96b1-129">To make changes to the email address that is sending the email to users, you must:</span></span>
    
  - <span data-ttu-id="a96b1-130">Введите адрес электронной почты с помощью параметра SendEmailFromAddress.</span><span class="sxs-lookup"><span data-stu-id="a96b1-130">Enter the email address in the SendEmailFromAddress parameter.</span></span>
    
  - <span data-ttu-id="a96b1-131">Установите для параметра SendEmailOverride значение True.</span><span class="sxs-lookup"><span data-stu-id="a96b1-131">Set the SendEmailOverride parameter to True.</span></span>
    
  - <span data-ttu-id="a96b1-132">Введите отображаемое имя электронной почты с помощью параметра SendEmailFromDisplayName.</span><span class="sxs-lookup"><span data-stu-id="a96b1-132">Enter the email display name in the SendEmailFromDisplayName parameter.</span></span>
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > <span data-ttu-id="a96b1-133">Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a96b1-133">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address that is set.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a96b1-134">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a96b1-134">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a96b1-135">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="a96b1-135">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
    <span data-ttu-id="a96b1-136">Чтобы отправить сообщение электронной почты пользователя с их сведения аудиоконференций, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a96b1-136">To send an email to the user with their audio conferencing information, run the following:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  <span data-ttu-id="a96b1-p104">Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="a96b1-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a96b1-140">Почему необходимо использовать Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a96b1-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a96b1-141">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a96b1-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a96b1-142">Windows PowerShell имеет много преимуществ в скорости, простоты и повышения производительности по сравнению только с помощью центра администрирования Office 365, например, при внесении изменений параметров для нескольких пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="a96b1-142">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="a96b1-143">Сведения об этих преимуществах в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="a96b1-143">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a96b1-144">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a96b1-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="a96b1-145">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a96b1-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a96b1-146">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a96b1-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="a96b1-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="a96b1-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a96b1-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="a96b1-149">Related topics</span></span>

[<span data-ttu-id="a96b1-150">Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a96b1-150">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
