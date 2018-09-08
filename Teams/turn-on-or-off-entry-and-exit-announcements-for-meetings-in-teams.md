---
title: Включение и отключение запись и выхода из объявления для собраний в группах Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: 'Узнайте, как включить запись и выхода из объявлений включено или отключено на собрании группами Майкрософт. '
ms.openlocfilehash: 94a091590ff00d2c78278e8ad559b61b1e732130
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884631"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="23528-103">Включение и отключение запись и выхода из объявления для собраний в группах Microsoft</span><span class="sxs-lookup"><span data-stu-id="23528-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="23528-104">При установке аудиоконференций в Office 365, вы получите аудио-конференц-канал.</span><span class="sxs-lookup"><span data-stu-id="23528-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="23528-105">Конференц-канал может содержать один или несколько телефонных номеров, которые будут использовать людей, чтобы позвонить собрание группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="23528-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="23528-106">Конференц-канал отвечает на звонок пользователя, подключающегося к собранию с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="23528-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="23528-107">Конференц-канал отвечает вызывающему абоненту голосовым приглашением автосекретаря конференции, а затем, в зависимости от параметров, может воспроизводить уведомления, попросить звонящего записать его имя и настроить ПИН-код безопасности.</span><span class="sxs-lookup"><span data-stu-id="23528-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="23528-108">Организатор собрания групп Майкрософт он получает ПИН-код и позволяет им начало собрания, если они не может начать собрание, с помощью приложения Microsoft группами.</span><span class="sxs-lookup"><span data-stu-id="23528-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="23528-109">Тем не менее, вы можете настроить работу приложения так, чтобы ПИН-код не требовался, чтобы начать собрание.</span><span class="sxs-lookup"><span data-stu-id="23528-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="23528-110">Настройка параметров присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="23528-110">Setting meeting join options</span></span>

1. <span data-ttu-id="23528-111">В левой области переходов, перейдите к **собраниям** > **Мостов конференции**.</span><span class="sxs-lookup"><span data-stu-id="23528-111">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="23528-112">В верхней части страницы **Мостов конференции** нажмите кнопку **Параметры Bridge**.</span><span class="sxs-lookup"><span data-stu-id="23528-112">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="23528-113">В области **Параметры Bridge** Включение или отключение **собрание и выйти из уведомления**.</span><span class="sxs-lookup"><span data-stu-id="23528-113">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="23528-114">Данная опция включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="23528-114">This is selected by default.</span></span> <span data-ttu-id="23528-115">Если снять, пользователей, которые уже присоединились к собранию не уведомления, когда кто-то или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="23528-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="23528-116">В разделе **Тип уведомлений о входе и выходе** выберите **Имена или номера телефонов** или **Гудки**.</span><span class="sxs-lookup"><span data-stu-id="23528-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="23528-117">Если Вы разрешили **имена или номера телефонов**, включения или отключения **абонентов Ask записать их имя перед присоединением к собранию**.</span><span class="sxs-lookup"><span data-stu-id="23528-117">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="23528-118">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="23528-118">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="23528-119">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="23528-119">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="23528-p104">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="23528-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="23528-123">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="23528-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="23528-124">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="23528-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="23528-125">Дополнительные сведения о Windows PowerShell, [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="23528-125">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="23528-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="23528-126">Related topics</span></span>

[<span data-ttu-id="23528-127">Общие вопросы по аудиоконференциям</span><span class="sxs-lookup"><span data-stu-id="23528-127">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
