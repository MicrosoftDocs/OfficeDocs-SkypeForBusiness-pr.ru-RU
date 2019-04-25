---
title: Предоставление пользователям возможности записи собственного имени при присоединении к собранию в Microsoft Teams
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
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Сведения о том, как разрешить или запретить пользователям записывать свои имена при присоединении к собранию в Microsoft Teams.
ms.openlocfilehash: ce2e2c019018ac3e2585928567632ea4a74b70fa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32246031"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="bd39b-103">Предоставление пользователям возможности записи собственного имени при присоединении к собранию в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd39b-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="bd39b-p101">[] При настройке конференц-связи с телефонным подключением в Skype для бизнеса online вы получите телефонные номера и ресурс, который называется мостом для конференц-связи с телефонным подключением или для аудиоконференций. Мост для конференц-связи может содержать один или несколько телефонных номеров, которые могут быть как выделенными, так и общими.</span><span class="sxs-lookup"><span data-stu-id="bd39b-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="bd39b-p102">Мост конференц-связи обеспечивает ответ на вызов пользователя, который присоединяется к собранию с телефона. Мост конференц-связи отвечает вызывающей стороне голосовыми подсказками с помощью автосекретаря, а затем, в зависимости от настроек, может воспроизвести уведомления, попросить вызывающую сторону записать свое имя и настроить ПИН-код безопасности для организаторов собрания. ПИН-коды предоставляются организаторам собраний. Организаторы могут начать собрание, введя ПИН-код. Однако собрание можно настроить таким образом, чтобы ПИН-код не требовался.</span><span class="sxs-lookup"><span data-stu-id="bd39b-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="bd39b-110">Выбор необходимости записи имени вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="bd39b-110">Set whether callers should record their name</span></span>

<span data-ttu-id="bd39b-111">![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью центра администрирования группами Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="bd39b-111">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="bd39b-112">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="bd39b-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bd39b-113">В верхней части страницы **Мостов конференции** нажмите кнопку **Параметры Bridge**.</span><span class="sxs-lookup"><span data-stu-id="bd39b-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="bd39b-114">Включение или отключение **собрание и выйти из уведомления**.</span><span class="sxs-lookup"><span data-stu-id="bd39b-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="bd39b-115">Если Включение уведомлений, выберите **имена или телефонных номеров** в списке **Тип входа и выхода объявлений**и включите **попросите звонящих записать их имя перед присоединением к собранию.**</span><span class="sxs-lookup"><span data-stu-id="bd39b-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="bd39b-116">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bd39b-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bd39b-117">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bd39b-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="bd39b-p103">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="bd39b-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bd39b-121">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="bd39b-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bd39b-122">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd39b-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="bd39b-123">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="bd39b-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bd39b-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="bd39b-124">Related topics</span></span>

[<span data-ttu-id="bd39b-125">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="bd39b-125">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
