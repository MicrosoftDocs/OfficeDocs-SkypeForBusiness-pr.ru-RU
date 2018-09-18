---
title: Установка длины ПИН-кода для собраний аудиоконференций в Microsoft Teams
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Сведения о параметрах длины и требованиях для ПИН-кода, а также о настройке этой длины для собраний в Microsoft Teams.
ms.openlocfilehash: 0300bba9139bdf98315b8af4200dd729ff6e70a1
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882993"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="0b27c-103">Установка длины ПИН-кода для собраний аудиоконференций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0b27c-103">For information about setting the PIN length in Microsoft Teams, see Set the PIN length for Audio Conferencing meetings in Microsoft Teams.</span></span>

<span data-ttu-id="0b27c-104">При настройке аудиоконференций для Microsoft Teams вы получите мост аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="0b27c-104">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="0b27c-105">Мост конференц-связи может содержать один или несколько телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="0b27c-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> <span data-ttu-id="0b27c-106">Заданный номер телефона будет включен в приглашения на собрание для приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0b27c-106">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="0b27c-107">Мост аудиоконференций отвечает на звонок для людей, подключающихся к собранию по телефону.</span><span class="sxs-lookup"><span data-stu-id="0b27c-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="0b27c-108">Он отвечает вызывающему абоненту с помощью голосовых подсказок от автосекретаря, а затем, в зависимости от ваших настроек, может воспроизводить уведомления и просить вызывающего абонента записать свое имя.</span><span class="sxs-lookup"><span data-stu-id="0b27c-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="0b27c-109">**Параметры моста Microsoft** позволяют изменять параметры уведомлений о собрании и присоединения к собранию, а также устанавливать длину ПИН-кодов, которые используются организаторами собраний.</span><span class="sxs-lookup"><span data-stu-id="0b27c-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="0b27c-110">Организаторы собраний используют ПИН-коды для начала собраний, когда им не удается присоединиться с помощью приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0b27c-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="0b27c-111">Настройка длины ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="0b27c-111">Setting the PIN length The default is 5.</span></span>

1. <span data-ttu-id="0b27c-112">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="0b27c-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0b27c-113">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="0b27c-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="0b27c-114">В области **Длина ПИН-кода** раздела **Настройки моста** выберите требуемое число цифр для ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="0b27c-114">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="0b27c-115">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0b27c-115">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="0b27c-116">ПИН-код отличается от идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="0b27c-116">A PIN is different from a conference ID.</span></span> <span data-ttu-id="0b27c-117">Идентификаторы конференции используются абонентами для присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="0b27c-117">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="0b27c-118">Они используются для идентификации собрания.</span><span class="sxs-lookup"><span data-stu-id="0b27c-118">They are used to identify the meeting.</span></span> <span data-ttu-id="0b27c-119">ПИН-код используется для проверки подлинности вызывающего абонента в качестве организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="0b27c-119">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="0b27c-120">Хотите узнать больше о параметрах ПИН-кода?</span><span class="sxs-lookup"><span data-stu-id="0b27c-120">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="0b27c-121">ПИН-коды могут содержать от 4 до 12 цифр, по умолчанию их число равно 5.</span><span class="sxs-lookup"><span data-stu-id="0b27c-121">The PIN can only be from 4 to 12 digits. The default is 5.</span></span> <span data-ttu-id="0b27c-122">При создании ПИН-кода используются только цифры.</span><span class="sxs-lookup"><span data-stu-id="0b27c-122">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="0b27c-123">Буквы и специальные знаки не применяются.</span><span class="sxs-lookup"><span data-stu-id="0b27c-123">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="0b27c-124">ПИН-код требуется организатору собрания только в том случае, если пользователь Microsoft Teams еще не начал собрание.</span><span class="sxs-lookup"><span data-stu-id="0b27c-124">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="0b27c-125">Если все подключаются к собранию по телефону, то ПИН-код необходим организатору для начала собрания.</span><span class="sxs-lookup"><span data-stu-id="0b27c-125">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="0b27c-126">Параметры безопасности ПИН-кода применяются ко всем номерам телефона, связанными с мостом Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0b27c-126">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="0b27c-127">Они применяются ко всем собраниям, использующим телефонные номера, которые сопоставлены с данным мостом.</span><span class="sxs-lookup"><span data-stu-id="0b27c-127">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0b27c-128">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0b27c-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0b27c-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="0b27c-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0b27c-132">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="0b27c-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0b27c-133">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b27c-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0b27c-134">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="0b27c-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="0b27c-135">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0b27c-135">Related topics</span></span>

[<span data-ttu-id="0b27c-136">Оцените или приобретите аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="0b27c-136">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
