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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Получите информацию относительно длины и требований к ПИН-коду, а также узнайте, как устанавливать необходимую длину кода для совещаний в Skype для бизнеса.
ms.openlocfilehash: 0714a55add1d3a4840d5868d0e09f0a3dc4b8561
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861726"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="1136d-103">Установка длины ПИН-кода для аудиоконференций в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1136d-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="1136d-104">Для получения информации об установке длины ПИН-кода в Microsoft Teams см. статью [Установка длины ПИН-кода для аудиоконференций в Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="1136d-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="1136d-105">При установке аудиоконференций в Skype для бизнеса вы получите мост аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="1136d-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="1136d-106">Мост конференц-связи может содержать один или несколько телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="1136d-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> <span data-ttu-id="1136d-107">Установленный номер телефона будет указан в приглашениях на собрания в приложении Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1136d-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="1136d-108">Мост аудиоконференций отвечает на звонок пользователей, подключающихся к собранию с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="1136d-108">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="1136d-109">Он отвечает вызывающему абоненту голосовым приглашением автосекретаря, а затем, в зависимости от параметров, может воспроизводить уведомления и попросить вызывающего абонента записать его имя.</span><span class="sxs-lookup"><span data-stu-id="1136d-109">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="1136d-110">**Параметры моста Microsoft** позволяют изменять параметры уведомлений о собрании и присоединения к собранию, а также устанавливать длину ПИН-кодов, которые используются организаторами собраний.</span><span class="sxs-lookup"><span data-stu-id="1136d-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="1136d-111">Организаторы собраний используют ПИН-коды для начала собраний, если они не могут присоединиться к собранию с помощью приложения Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1136d-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="1136d-112">Установка длины ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="1136d-112">Setting the PIN length The default is 5.</span></span>
 
1. <span data-ttu-id="1136d-113">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Аудиоконференции** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1136d-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="1136d-114">В разделе **Безопасность** > **Длина ПИН-кода** выберите количество цифр, которое необходимо использовать для ПИН-кода, затем нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1136d-114">Under **Security** > **PIN length** > enter the number of digits you want for the PIN and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1136d-115">ПИН-код отличается от идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="1136d-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="1136d-116">Идентификаторы конференции используются абонентами для присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="1136d-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="1136d-117">Они используются для идентификации собрания.</span><span class="sxs-lookup"><span data-stu-id="1136d-117">They are used to identify the meeting.</span></span> <span data-ttu-id="1136d-118">ПИН-код используется для проверки подлинности вызывающего абонента в качестве организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="1136d-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="1136d-119">Хотите узнать больше о параметрах ПИН-кода?</span><span class="sxs-lookup"><span data-stu-id="1136d-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="1136d-120">ПИН-код может включать от 4 до 12 цифр; по умолчанию он составляет 5 цифр.</span><span class="sxs-lookup"><span data-stu-id="1136d-120">The PIN can only be from 4 to 12 digits. The default is 5.</span></span> <span data-ttu-id="1136d-121">При создании ПИН-кода используются только цифры.</span><span class="sxs-lookup"><span data-stu-id="1136d-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="1136d-122">Буквы и специальные символы не используются.</span><span class="sxs-lookup"><span data-stu-id="1136d-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="1136d-123">ПИН-код требуется только для организатора собрания, если пользователь Skype для бизнеса еще не начал собрание.</span><span class="sxs-lookup"><span data-stu-id="1136d-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="1136d-124">Если пользователи подключаются к собранию, организатору собрания потребуется ПИН-код для начала собрания.</span><span class="sxs-lookup"><span data-stu-id="1136d-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="1136d-125">Параметры безопасности ПИН-кода применяются ко всем номерам телефона, связанными с мостом Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1136d-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="1136d-126">Они будут применяться ко всем собраниям, которые используют номера телефонов, связанные с указанным мостом.</span><span class="sxs-lookup"><span data-stu-id="1136d-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1136d-127">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1136d-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1136d-128">Можно сэкономить время и автоматизировать процесс, используя командлет [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="1136d-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="1136d-129">Для установки в качестве ПИН-кода 8 цифр выполните следующие действия.  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="1136d-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="1136d-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="1136d-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1136d-133">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="1136d-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1136d-134">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1136d-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="1136d-p108">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="1136d-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="1136d-137">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1136d-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1136d-138">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1136d-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="1136d-139">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1136d-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1136d-140">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1136d-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="1136d-p109">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="1136d-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1136d-143">См. также</span><span class="sxs-lookup"><span data-stu-id="1136d-143">See also</span></span>

[<span data-ttu-id="1136d-144">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="1136d-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
