---
title: Установка длины ПИН-кода для аудиоконференции
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Узнайте параметры длины и требований ПИН-кода и узнайте, как установить продолжительность собраний в Microsoft Teams.
ms.openlocfilehash: 68dc1f3ea5508dc88bc168a5f3fbed837bbee04f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117167"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="e73b3-103">Установка длины ПИН-кода для собраний аудиоконференций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e73b3-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="e73b3-104">При настройке аудиоконференции для Microsoft Teams вы получите мост аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="e73b3-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="e73b3-105">Мост конференц-связи может содержать один или несколько телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="e73b3-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="e73b3-106">Номер телефона, который вы настроили, будет включен в приглашения на собрание для приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e73b3-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="e73b3-107">Мост аудиоконференцсвязи отвечает на вызов людей, которые звонят на собрание с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="e73b3-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="e73b3-108">Она отвечает вызываемой звоняке с помощью голосовых подсказок автозаверха, а затем (в зависимости от параметров) может играть в уведомления и просить вызывающего человека записать свое имя.</span><span class="sxs-lookup"><span data-stu-id="e73b3-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="e73b3-109">**Параметры моста Microsoft** позволяют изменять параметры уведомлений о собрании и присоединения к собранию, а также устанавливать длину ПИН-кодов, которые используются организаторами собраний.</span><span class="sxs-lookup"><span data-stu-id="e73b3-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="e73b3-110">Организаторы собраний используют ПИН-записи для начала собраний, если не могут присоединиться к собранию с помощью приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e73b3-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="e73b3-111">Настройка длины ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="e73b3-111">Setting the PIN length</span></span>

<span data-ttu-id="e73b3-112">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="e73b3-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e73b3-113">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="e73b3-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="e73b3-114">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="e73b3-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="e73b3-115">В области **параметров моста** в области длины **ПИН-кода** выберите нужное количество цифр.</span><span class="sxs-lookup"><span data-stu-id="e73b3-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="e73b3-116">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e73b3-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="e73b3-117">ПИН-код отличается от идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="e73b3-117">A PIN is different from a conference ID.</span></span> <span data-ttu-id="e73b3-118">Идентификаторы конференции используются абонентами для присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="e73b3-118">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="e73b3-119">Они используются для идентификации собрания.</span><span class="sxs-lookup"><span data-stu-id="e73b3-119">They are used to identify the meeting.</span></span> <span data-ttu-id="e73b3-120">ПИН-код используется для проверки подлинности вызывающего абонента в качестве организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="e73b3-120">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="e73b3-121">Хотите узнать больше о параметрах ПИН-кода?</span><span class="sxs-lookup"><span data-stu-id="e73b3-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="e73b3-122">ПИН-коды могут иметь от 4 до 12 цифр. значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="e73b3-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="e73b3-123">При создании ПИН-кода используются только цифры.</span><span class="sxs-lookup"><span data-stu-id="e73b3-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="e73b3-124">Буквы и специальные символы не используются.</span><span class="sxs-lookup"><span data-stu-id="e73b3-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="e73b3-125">ПИН-код требуется только организатору собрания, если пользователь Microsoft Teams еще не начал собрание.</span><span class="sxs-lookup"><span data-stu-id="e73b3-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="e73b3-126">Если пользователи подключаются к собранию, организатору собрания потребуется ПИН-код для начала собрания.</span><span class="sxs-lookup"><span data-stu-id="e73b3-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="e73b3-127">Параметры безопасности ПИН-кода применяются ко всем номерам телефона, связанными с мостом Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e73b3-127">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="e73b3-128">Они будут применяться ко всем собраниям, которые используют номера телефонов, связанные с указанным мостом.</span><span class="sxs-lookup"><span data-stu-id="e73b3-128">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e73b3-129">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e73b3-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="e73b3-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="e73b3-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e73b3-131">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="e73b3-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e73b3-132">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="e73b3-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e73b3-133">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="e73b3-133">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="e73b3-134">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e73b3-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="e73b3-135">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="e73b3-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="e73b3-136">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e73b3-136">Related topics</span></span>

[<span data-ttu-id="e73b3-137">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="e73b3-137">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)