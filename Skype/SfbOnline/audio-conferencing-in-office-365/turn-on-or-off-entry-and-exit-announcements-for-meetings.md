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
description: 'Узнайте, как включать и выключать уведомления о входе и выходе из собраний Skype для бизнеса Online с помощью центра администрирования Skype для бизнеса. '
ms.openlocfilehash: f097563ca8dce47277a44573f2af66ed7f1539dd
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237575"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="78d48-103">Включение и отключение уведомлений о входе и выходе из собраний в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="78d48-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="78d48-104">Информацию об уведомлениях о входе и выходе в Microsoft Teams см. в статье [Включение или отключение уведомлений о входе и выходе из собраний в Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="78d48-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="78d48-105">При настройке аудиоконференций в Microsoft 365 или Office 365 вы получите мост аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="78d48-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="78d48-106">Конференц-канал может содержать один или несколько телефонных номеров, которые пользователи будут использовать для звонков на собрание Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="78d48-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="78d48-107">Конференц-канал отвечает на звонок пользователя, подключающегося к собранию с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="78d48-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="78d48-108">Конференц-канал отвечает вызывающему абоненту голосовым приглашением автосекретаря конференции, а затем, в зависимости от параметров, может воспроизводить уведомления, попросить звонящего записать его имя и настроить ПИН-код безопасности.</span><span class="sxs-lookup"><span data-stu-id="78d48-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="78d48-109">ПИН-код предоставляется организатору собрания Skype для бизнеса и позволяет ему начать собрание, если он не может начать собрание с помощью приложения Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="78d48-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="78d48-110">Тем не менее, вы можете настроить работу приложения так, чтобы ПИН-код не требовался, чтобы начать собрание.</span><span class="sxs-lookup"><span data-stu-id="78d48-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="78d48-111">Настройка параметров присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="78d48-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="78d48-112">В центре **Skype для бизнеса** администрирования на левой навигации перейдите в параметры моста  >  **Аудиоконференция Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="78d48-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="78d48-113">В **области Присоединиться к собранию** выберите или отключим включить уведомления о входе и выходе из **собрания.**</span><span class="sxs-lookup"><span data-stu-id="78d48-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="78d48-114">Данная опция включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="78d48-114">This is selected by default.</span></span> <span data-ttu-id="78d48-115">Если его снять, пользователи, уже присоединившиеся к собранию, не будут получать уведомления, когда кто-либо подключается к собранию или покидает его.</span><span class="sxs-lookup"><span data-stu-id="78d48-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="78d48-116">В разделе **Тип уведомлений о входе и выходе** выберите **Имена или номера телефонов** или **Гудки**.</span><span class="sxs-lookup"><span data-stu-id="78d48-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="78d48-117">Перед присоединением к собранию убедитесь в том, что перед присоединением к собранию нужно проверить или отозвать запрос на запись **имени.**</span><span class="sxs-lookup"><span data-stu-id="78d48-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="78d48-118">После внесения изменений нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="78d48-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="78d48-119">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78d48-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="78d48-120">Чтобы сэкономить время или автоматизировать эту функцию, можно использовать для этого [cmdlet Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="78d48-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
- <span data-ttu-id="78d48-121">Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия.</span><span class="sxs-lookup"><span data-stu-id="78d48-121">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="78d48-122">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="78d48-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="78d48-123">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="78d48-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="78d48-124">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="78d48-124">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="78d48-125">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="78d48-125">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="78d48-126">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="78d48-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="78d48-127">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="78d48-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="78d48-128">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="78d48-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="78d48-129">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="78d48-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="78d48-130">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="78d48-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="78d48-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="78d48-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="78d48-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="78d48-133">Related topics</span></span>

[<span data-ttu-id="78d48-134">Общие вопросы об аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="78d48-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
