---
title: Установка длины ПИН-кода для собраний аудиоконференций в Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Узнайте, параметров длины и требования к ПИН-кода и узнайте, как задать длину для собраний в группах Майкрософт.
ms.openlocfilehash: 94be2277b631df9e8c65c9ce2936faeb961a42d7
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531338"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="6fd8a-103">Установка длины ПИН-кода для собраний аудиоконференций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6fd8a-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="6fd8a-104">При настройке аудиоконференций для Microsoft Teams вы получите мост аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="6fd8a-105">Мост конференц-связи может содержать один или несколько телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="6fd8a-106">Заданный номер телефона будет включен в приглашения на собрание для приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="6fd8a-107">Мост аудиоконференций отвечает на звонок для людей, подключающихся к собранию по телефону.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="6fd8a-108">Он отвечает вызывающему абоненту с помощью голосовых подсказок от автосекретаря, а затем, в зависимости от ваших настроек, может воспроизводить уведомления и просить вызывающего абонента записать свое имя.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="6fd8a-109">**Параметры моста Microsoft** позволяют изменять параметры уведомлений о собрании и присоединения к собранию, а также устанавливать длину ПИН-кодов, которые используются организаторами собраний.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="6fd8a-110">Организаторы собраний используют ПИН-коды для начала собраний, когда им не удается присоединиться с помощью приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="6fd8a-111">Настройка длины ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="6fd8a-111">Setting the PIN length</span></span>

![команды логотип 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="6fd8a-113">Использование групп Майкрософт и Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="6fd8a-113">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="6fd8a-114">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-114">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="6fd8a-115">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-115">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="6fd8a-116">В области **Параметры Bridge** в разделе **Длина ПИН-кода**выберите количество знаков, которое необходимо использовать для ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-116">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="6fd8a-117">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-117">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="6fd8a-118">ПИН-код отличается от идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-118">A PIN is different from a conference ID.</span></span> <span data-ttu-id="6fd8a-119">Идентификаторы конференции используются абонентами для присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-119">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="6fd8a-120">Они используются для идентификации собрания.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-120">They are used to identify the meeting.</span></span> <span data-ttu-id="6fd8a-121">ПИН-код используется для проверки подлинности вызывающего абонента в качестве организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-121">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="6fd8a-122">Хотите узнать больше о параметрах ПИН-кода?</span><span class="sxs-lookup"><span data-stu-id="6fd8a-122">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="6fd8a-123">ПИН-коды может составлять от 4 до 12 цифр; значение по умолчанию равно 5.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-123">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="6fd8a-124">При создании ПИН-кода используются только цифры.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-124">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="6fd8a-125">Буквы и специальные символы не используются.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-125">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="6fd8a-126">ПИН-код только в том случае требуется для организатора собрания при группами Майкрософт пользователей не запущена собрания.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-126">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="6fd8a-127">Если пользователи подключаются к собранию, организатору собрания потребуется ПИН-код для начала собрания.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-127">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="6fd8a-128">Параметры безопасности ПИН-кода применяются ко всем номерам телефона, связанными с мостом Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-128">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="6fd8a-129">Они будут применяться ко всем собраниям, которые используют номера телефонов, связанные с указанным мостом.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-129">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6fd8a-130">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6fd8a-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="6fd8a-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="6fd8a-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6fd8a-134">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="6fd8a-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="6fd8a-135">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fd8a-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="6fd8a-136">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="6fd8a-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="6fd8a-137">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6fd8a-137">Related topics</span></span>

[<span data-ttu-id="6fd8a-138">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="6fd8a-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
