---
title: Установка длины ПИН-кода для аудиоконференций в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Получите информацию относительно длины и требований к ПИН-коду, а также узнайте, как устанавливать необходимую длину кода для совещаний в Skype для бизнеса.
ms.openlocfilehash: 4e4308eab334b37d32cbd53d047ba5fd077a1cad
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792740"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="dc8da-103">Установка длины ПИН-кода для аудиоконференций в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="dc8da-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="dc8da-104">Для получения информации об установке длины ПИН-кода в Microsoft Teams см. статью [Установка длины ПИН-кода для аудиоконференций в Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="dc8da-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="dc8da-p101">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. The phone number you set will be included on the meeting invites for the Skype for Business app.</span><span class="sxs-lookup"><span data-stu-id="dc8da-p101">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="dc8da-p102">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone. It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name. **Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers. Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span><span class="sxs-lookup"><span data-stu-id="dc8da-p102">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone. It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name. **Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers. Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="dc8da-112">Установка длины ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="dc8da-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="dc8da-113">В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите к разделу**Настройка моста**видеоконференций \*\*\*\* > Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dc8da-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="dc8da-114">В разделе**длина ПИН-кода** **безопасности** > выберите нужное количество цифр, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dc8da-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dc8da-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span><span class="sxs-lookup"><span data-stu-id="dc8da-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="dc8da-119">Хотите узнать больше о параметрах ПИН-кода?</span><span class="sxs-lookup"><span data-stu-id="dc8da-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="dc8da-p104">PINs can be from 4 to 12 digits; the default is 5. Numbers are only used when creating PINs. Letters and special characters aren't used.</span><span class="sxs-lookup"><span data-stu-id="dc8da-p104">PINs can be from 4 to 12 digits; the default is 5. Numbers are only used when creating PINs. Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="dc8da-p105">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting. If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span><span class="sxs-lookup"><span data-stu-id="dc8da-p105">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting. If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="dc8da-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span><span class="sxs-lookup"><span data-stu-id="dc8da-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="dc8da-127">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc8da-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="dc8da-128">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=715757) .</span><span class="sxs-lookup"><span data-stu-id="dc8da-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="dc8da-129">Для установки в качестве ПИН-кода 8 цифр выполните следующие действия.  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="dc8da-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="dc8da-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="dc8da-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="dc8da-133">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="dc8da-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="dc8da-134">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc8da-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="dc8da-135">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности при использовании только в центре администрирования Microsoft 365, например при изменении параметров для нескольких пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="dc8da-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="dc8da-136">Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="dc8da-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="dc8da-137">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="dc8da-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="dc8da-138">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="dc8da-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="dc8da-139">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="dc8da-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="dc8da-140">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="dc8da-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="dc8da-p109">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="dc8da-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc8da-143">См. также</span><span class="sxs-lookup"><span data-stu-id="dc8da-143">See also</span></span>

[<span data-ttu-id="dc8da-144">Платная или пробная версия аудиоконференций в Office 365</span><span class="sxs-lookup"><span data-stu-id="dc8da-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
