---
title: Управление регистрациями на конференции и оглашение сообщений в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: Сводка. Узнайте, как управлять регистрациями на конференции и оставлять объявления в Skype для бизнеса Server.
ms.openlocfilehash: 796266dd3b571e525f657d5dbe712d1577779cae
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119458"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="35267-103">Управление регистрациями на конференции и оглашение сообщений в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="35267-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="35267-104">**Сводка:** Узнайте, как управлять регистрациями на конференции и оставлять объявления в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="35267-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="35267-105">Когда пользователи, вступив в диалог, присоединяются к конференции или покидают конференцию, приложение Conferencing Announcement может объявить о своем входе или выходе, играя в тон или говоря их имена.</span><span class="sxs-lookup"><span data-stu-id="35267-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="35267-106">Вы можете изменить работу объявлений с помощью оболочки управления Skype для бизнес-серверов и команды **Set-CsDialinConferencing** со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="35267-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="35267-107">EnableNameRecording — определяет, просят ли анонимные участники записывать свое имя перед входом на конференцию.</span><span class="sxs-lookup"><span data-stu-id="35267-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="35267-108">По умолчанию используется значение "$true", что означает, что анонимным участникам предлагается указать свое имя при присоединении к конференции.</span><span class="sxs-lookup"><span data-stu-id="35267-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="35267-109">(Прошедшие проверку подлинности участники не записывают свое имя, поскольку используется их отображаемое имя.)</span><span class="sxs-lookup"><span data-stu-id="35267-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="35267-110">EntryExitAnnouncementsEnabledByDefault — указывает, включено или отключено объявление по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="35267-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="35267-111">По умолчанию значение "$false", что означает, что по умолчанию нет объявлений, когда участники присоединяются к конференции или покидают ее.</span><span class="sxs-lookup"><span data-stu-id="35267-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="35267-112">Организатор собрания может переопредить этот параметр при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="35267-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="35267-113">EntryExitAnnouncementsType — указывает действия, которые принимаются, когда участник присоединяется или покидает конференцию, для которой включены объявления.</span><span class="sxs-lookup"><span data-stu-id="35267-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="35267-114">Значение по умолчанию — "UseNames", что означает объявление, аналогичное следующему: "Кен Мойер присоединился к конференции" при включении объявлений.</span><span class="sxs-lookup"><span data-stu-id="35267-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="35267-115">Эти параметры можно настроить в глобальном масштабе или в области сайта.</span><span class="sxs-lookup"><span data-stu-id="35267-115">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="35267-116">Параметры, настроенные в области сайта, имеют приоритет над настройками, настроенными в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="35267-116">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="35267-117">Изменение объявлений при присоединении к конференции и выходе из нее</span><span class="sxs-lookup"><span data-stu-id="35267-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="35267-118">Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="35267-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="35267-119">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="35267-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="35267-120">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="35267-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="35267-121">Этот кодлет извлекает сведения о том, требуется ли участникам записывать свое имя при присоединении к конференции и как Skype для бизнеса Server реагирует, когда участники присоединяются к конференции по вызову или покидают ее.</span><span class="sxs-lookup"><span data-stu-id="35267-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="35267-122">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="35267-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="35267-123">В следующем примере параметры настраиваются в области сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="35267-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="35267-124">Объявления включены, но участникам не предложено назвать свое имя, когда они присоединяются к конференции.</span><span class="sxs-lookup"><span data-stu-id="35267-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="35267-125">Тон играется, когда участники входят или покидают конференцию:</span><span class="sxs-lookup"><span data-stu-id="35267-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="35267-126">Дополнительные сведения, включая синтаксис и полный список параметров, см. в [обзоре Set-CsDialInConferencingConfiguration.](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="35267-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
