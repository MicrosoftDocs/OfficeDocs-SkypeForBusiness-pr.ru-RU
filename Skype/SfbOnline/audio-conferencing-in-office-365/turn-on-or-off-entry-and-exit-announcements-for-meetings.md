---
title: Включение и отключение уведомлений о входе и выходе из собраний в Skype для бизнеса Online
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
description: 'Узнайте, как включать и выключать уведомления о входе и выходе из собраний Skype для бизнеса Online с помощью центра администрирования Skype для бизнеса. '
ms.openlocfilehash: 874624c3d7cfb184f4206f61cf2a91a67eb2e2cd
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779038"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="226af-103">Включение и отключение уведомлений о входе и выходе из собраний в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="226af-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="226af-104">Информацию об уведомлениях о входе и выходе в Microsoft Teams см. в статье [Включение или отключение уведомлений о входе и выходе из собраний в Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="226af-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="226af-105">При установке аудиоконференций в Office 365, вы получите аудио-конференц-канал.</span><span class="sxs-lookup"><span data-stu-id="226af-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="226af-106">Конференц-канал может содержать один или несколько телефонных номеров, которые пользователи будут использовать для звонков на собрание Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="226af-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="226af-107">Конференц-канал отвечает на звонок пользователя, подключающегося к собранию с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="226af-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="226af-108">Конференц-канал отвечает вызывающему абоненту голосовым приглашением автосекретаря конференции, а затем, в зависимости от параметров, может воспроизводить уведомления, попросить звонящего записать его имя и настроить ПИН-код безопасности.</span><span class="sxs-lookup"><span data-stu-id="226af-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="226af-109">ПИН-код предоставляется организатору собрания Skype для бизнеса и позволяет ему начать собрание, если он не может начать собрание с помощью приложения Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="226af-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="226af-110">Тем не менее, вы можете настроить работу приложения так, чтобы ПИН-код не требовался, чтобы начать собрание.</span><span class="sxs-lookup"><span data-stu-id="226af-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="226af-111">Настройка параметров присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="226af-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="226af-112">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Аудиоконференция с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="226af-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="226af-113">В разделе **При присоединении к собраниям**установите или снимите флажок **Разрешить включение уведомлений о входе и выходе из собрания**.</span><span class="sxs-lookup"><span data-stu-id="226af-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="226af-114">Данная опция включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="226af-114">This is selected by default.</span></span> <span data-ttu-id="226af-115">Если снять этот флажок, то пользователи, которые уже присоединились к собранию, не получат уведомления о присоединении или выходе из него других участников.</span><span class="sxs-lookup"><span data-stu-id="226af-115">However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="226af-116">В разделе **Тип уведомлений о входе и выходе** выберите **Имена или номера телефонов** или **Гудки**.</span><span class="sxs-lookup"><span data-stu-id="226af-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="226af-117">Установите или снимите флажок **Просить абонентов записывать свое имя перед присоединением к собранию**.</span><span class="sxs-lookup"><span data-stu-id="226af-117">Ask callers to record their name before joining the meeting</span></span>
    
5. <span data-ttu-id="226af-118">После внесения изменений нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="226af-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="226af-119">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="226af-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="226af-120">Можно сэкономить время и автоматизировать процесс, используя командлет [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="226af-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="226af-p104">Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="226af-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="226af-124">Почему следует использовать Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="226af-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="226af-125">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="226af-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="226af-126">Windows PowerShell имеет множество преимуществ по скорости, простоте и производительности по сравнению с использованием только центра администрирования Office 365, например, когда выполняются изменения параметров для нескольких пользователей сразу.</span><span class="sxs-lookup"><span data-stu-id="226af-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> <span data-ttu-id="226af-127">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="226af-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="226af-128">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="226af-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="226af-129">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="226af-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="226af-130">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="226af-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="226af-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="226af-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="226af-133">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="226af-133">Related topics</span></span>

[<span data-ttu-id="226af-134">Общие вопросы по аудиоконференциям</span><span class="sxs-lookup"><span data-stu-id="226af-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
