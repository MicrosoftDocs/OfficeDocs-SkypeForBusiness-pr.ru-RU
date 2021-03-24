---
title: Позволить пользователям записывать свое имя для собрания
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Узнайте, как включить или отключить возможность записи имен пользователями при подступе к собранию в Microsoft Teams.
ms.openlocfilehash: 8b92e0d4a73cc18ceaf374f1a05102e51752c083
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092697"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="7e52b-103">Предоставление пользователям возможности записи собственного имени при присоединении к собранию в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e52b-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="7e52b-104">При настройке аудиоконференции в Microsoft 365 или Office 365 вы получите телефонные номера и мост аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="7e52b-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="7e52b-105">Мост для conferencing может содержать один или несколько телефонных номеров, которые могут быть выделенным или общим номером телефона.</span><span class="sxs-lookup"><span data-stu-id="7e52b-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="7e52b-p102">Мост конференц-связи обеспечивает ответ на вызов пользователя, который присоединяется к собранию с телефона. Мост конференц-связи отвечает вызывающей стороне голосовыми подсказками с помощью автосекретаря, а затем, в зависимости от настроек, может воспроизвести уведомления, попросить вызывающую сторону записать свое имя и настроить ПИН-код безопасности для организаторов собрания. ПИН-коды предоставляются организаторам собраний. Организаторы могут начать собрание, введя ПИН-код. Однако собрание можно настроить таким образом, чтобы ПИН-код не требовался.</span><span class="sxs-lookup"><span data-stu-id="7e52b-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="7e52b-110">Настройка записи имени вызывателям</span><span class="sxs-lookup"><span data-stu-id="7e52b-110">Set whether callers should record their name</span></span>

<span data-ttu-id="7e52b-111">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="7e52b-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7e52b-112">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="7e52b-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7e52b-113">В верхней части страницы **"Мосты** конференций" щелкните **"Параметры моста".**</span><span class="sxs-lookup"><span data-stu-id="7e52b-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="7e52b-114">Включить или отключить уведомления **о входе и выходе из собрания.**</span><span class="sxs-lookup"><span data-stu-id="7e52b-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="7e52b-115">Если включить уведомления,  выберите имена или номера телефонов в списке "Тип объявления о входе/выходе", а затем включите "Попросить вызывающих вас записать свое имя перед присоединением к **собранию".**</span><span class="sxs-lookup"><span data-stu-id="7e52b-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="7e52b-116">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7e52b-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7e52b-117">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7e52b-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7e52b-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="7e52b-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7e52b-119">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="7e52b-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="7e52b-120">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="7e52b-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7e52b-121">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="7e52b-121">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="7e52b-122">[Лучшие способы управления Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="7e52b-122">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="7e52b-123">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="7e52b-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7e52b-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7e52b-124">Related topics</span></span>

[<span data-ttu-id="7e52b-125">Попробуйте или приобретйте аудиоконференцию</span><span class="sxs-lookup"><span data-stu-id="7e52b-125">Try or purchase Audio Conferencing</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)