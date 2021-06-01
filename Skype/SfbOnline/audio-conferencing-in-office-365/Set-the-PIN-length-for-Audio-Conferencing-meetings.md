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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Получите информацию относительно длины и требований к ПИН-коду, а также узнайте, как устанавливать необходимую длину кода для совещаний в Skype для бизнеса.
ms.openlocfilehash: 2e4e1d087ad6e0f91d034c6a5abe513e8b3aab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238604"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="ef490-103">Установка длины ПИН-кода для аудиоконференций в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ef490-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


> [!NOTE]
> <span data-ttu-id="ef490-104">Для получения информации об установке длины ПИН-кода в Microsoft Teams см. статью [Установка длины ПИН-кода для аудиоконференций в Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="ef490-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="ef490-105">При установке аудиоконференций в Skype для бизнеса вы получите мост аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="ef490-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="ef490-106">Мост конференц-связи может содержать один или несколько телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="ef490-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="ef490-107">Установленный номер телефона будет указан в приглашениях на собрания в приложении Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ef490-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="ef490-108">Мост аудиоконференцсвязи отвечает на вызов людей, которые звонят на собрание с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="ef490-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="ef490-109">Она отвечает вызывающего звоняку с помощью голосовых подсказок автозаверха, а затем (в зависимости от параметров) может воспроизведения уведомлений и попросить вызывающего человека записать свое имя.</span><span class="sxs-lookup"><span data-stu-id="ef490-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="ef490-110">**Параметры моста Microsoft** позволяют изменять параметры уведомлений о собрании и присоединения к собранию, а также устанавливать длину ПИН-кодов, которые используются организаторами собраний.</span><span class="sxs-lookup"><span data-stu-id="ef490-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="ef490-111">Организаторы собраний используют ПИН-коды для начала собраний, если они не могут присоединиться к собранию с помощью приложения Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ef490-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="ef490-112">Установка длины ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="ef490-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="ef490-113">В центре **администрирования** Skype для бизнеса навигации слева перейдите в параметры моста Аудиоконференция   >  **Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="ef490-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="ef490-114">В **области Длина**  >  **ПИН-кода** безопасности выберите нужное число цифр и нажмите кнопку **Сохранить.**</span><span class="sxs-lookup"><span data-stu-id="ef490-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ef490-115">ПИН-код отличается от идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="ef490-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="ef490-116">Идентификаторы конференции используются абонентами для присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="ef490-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="ef490-117">Они используются для идентификации собрания.</span><span class="sxs-lookup"><span data-stu-id="ef490-117">They are used to identify the meeting.</span></span> <span data-ttu-id="ef490-118">ПИН-код используется для проверки подлинности вызывающего абонента в качестве организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="ef490-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="ef490-119">Хотите узнать больше о параметрах ПИН-кода?</span><span class="sxs-lookup"><span data-stu-id="ef490-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="ef490-120">ПИН-коды могут иметь от 4 до 12 цифр. по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="ef490-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="ef490-121">При создании ПИН-кода используются только цифры.</span><span class="sxs-lookup"><span data-stu-id="ef490-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="ef490-122">Буквы и специальные символы не используются.</span><span class="sxs-lookup"><span data-stu-id="ef490-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="ef490-123">ПИН-код требуется только для организатора собрания, если пользователь Skype для бизнеса еще не начал собрание.</span><span class="sxs-lookup"><span data-stu-id="ef490-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="ef490-124">Если пользователи подключаются к собранию, организатору собрания потребуется ПИН-код для начала собрания.</span><span class="sxs-lookup"><span data-stu-id="ef490-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="ef490-125">Параметры безопасности ПИН-кода применяются ко всем номерам телефона, связанными с мостом Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef490-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="ef490-126">Они будут применяться ко всем собраниям, которые используют номера телефонов, связанные с указанным мостом.</span><span class="sxs-lookup"><span data-stu-id="ef490-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ef490-127">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef490-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ef490-128">Чтобы сэкономить время или автоматизировать эту функцию, можно использовать для этого [cmdlet Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)</span><span class="sxs-lookup"><span data-stu-id="ef490-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet.</span></span>
    
- <span data-ttu-id="ef490-129">Для установки в качестве ПИН-кода 8 цифр выполните следующие действия.  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="ef490-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="ef490-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="ef490-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ef490-131">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="ef490-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="ef490-132">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="ef490-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ef490-133">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef490-133">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="ef490-134">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="ef490-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="ef490-135">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="ef490-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="ef490-136">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="ef490-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="ef490-137">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ef490-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="ef490-138">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ef490-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="ef490-139">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ef490-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="ef490-140">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ef490-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="ef490-p109">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="ef490-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ef490-143">См. также</span><span class="sxs-lookup"><span data-stu-id="ef490-143">See also</span></span>

[<span data-ttu-id="ef490-144">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="ef490-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
