---
title: Включение и отключение входа и выхода из объявлений для собрания в Скайп для бизнеса в Интернет
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: 'Узнайте, как включить запись и выхода из Включение и отключение оповещений в Скайп для бизнеса собрания с помощью Скайп по центру администрирования бизнес. '
ms.openlocfilehash: d6d1b70713ac0cd7a38f7de9cb84f0acb54cbe30
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490488"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="c47e5-103">Включение и отключение входа и выхода из объявлений для собрания в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="c47e5-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="c47e5-104">Сведения о входе и выходе участников в группами Майкрософт содержатся в разделе [Включение или отключение входе и выходе участников собраний в группах Microsoft](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="c47e5-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="c47e5-105">При установке аудиоконференций в Office 365, вы получите звукового конференц-канала.</span><span class="sxs-lookup"><span data-stu-id="c47e5-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="c47e5-106">Конференц-канал может содержать один или несколько телефонных номеров, которые пользователи будут использовать вызывает Скайп для собраний.</span><span class="sxs-lookup"><span data-stu-id="c47e5-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="c47e5-107">Мост конференц-связи ответы звонка для пользователя, который, к собрания с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="c47e5-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="c47e5-108">Мост конференц-связи ответы вызывающего абонента с голосовые приглашения участников автосекретарь конференц-связи и затем, в зависимости от параметров, можно воспроизводить уведомления, попросите звонящих записать их имя и настройка безопасности ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="c47e5-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="c47e5-109">ПИН-код предоставляется Скайп для бизнеса Организатор собрания и позволяет им начало собрания, если они не может начать собрание, с помощью Скайп для бизнес-приложения.</span><span class="sxs-lookup"><span data-stu-id="c47e5-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="c47e5-110">Тем не менее, устанавливать, чтобы ПИН-код не требуется для запуска собрания.</span><span class="sxs-lookup"><span data-stu-id="c47e5-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="c47e5-111">Настройка параметров присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="c47e5-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="c47e5-112">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c47e5-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="c47e5-113">В разделе **при присоединении к собраниям**установите или снимите флажок **Включить запись собрание и выйти из уведомления, чтобы быть включенным**.</span><span class="sxs-lookup"><span data-stu-id="c47e5-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="c47e5-114">Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c47e5-114">This is selected by default.</span></span> <span data-ttu-id="c47e5-115">Если снять, пользователей, которые уже присоединились к собранию не уведомления, когда кто-то или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="c47e5-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="c47e5-116">В разделе **объявлений типа входа и выхода**выберите **имена или номера телефонов** или **тона**.</span><span class="sxs-lookup"><span data-stu-id="c47e5-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="c47e5-117">Установите или снимите флажок **задать абонентов записать их имя перед присоединением к собранию**.</span><span class="sxs-lookup"><span data-stu-id="c47e5-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="c47e5-118">После внесения изменений нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c47e5-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c47e5-119">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c47e5-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c47e5-120">Для экономии времени или автоматизировать этот процесс, можно использовать командлет [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c47e5-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="c47e5-p104">Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="c47e5-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c47e5-124">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="c47e5-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c47e5-125">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c47e5-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c47e5-126">Windows PowerShell имеет много преимуществ в скорости, простоты и повышения производительности по сравнению только с помощью центра администрирования Office 365, например, когда выполняются изменения параметров для нескольких пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="c47e5-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="c47e5-127">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c47e5-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="c47e5-128">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c47e5-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c47e5-129">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c47e5-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c47e5-130">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c47e5-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="c47e5-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="c47e5-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c47e5-133">See also</span><span class="sxs-lookup"><span data-stu-id="c47e5-133">Related topics</span></span>

[<span data-ttu-id="c47e5-134">Общие вопросы по аудиоконференциям</span><span class="sxs-lookup"><span data-stu-id="c47e5-134">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
