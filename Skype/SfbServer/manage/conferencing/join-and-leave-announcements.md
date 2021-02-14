---
title: Управление объявлениями о подступах к конференции и отправляемой из нее в Skype для бизнеса Server
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
description: Сводка. Узнайте, как управлять объявлениями о под подступах к конференции и оставьте их в Skype для бизнеса Server.
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828109"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="1cba1-103">Управление объявлениями о подступах к конференции и отправляемой из нее в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1cba1-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="1cba1-104">**Сводка:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1cba1-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="1cba1-105">Когда пользователи с телефонным входом присоединяются к конференции или покидают ее, приложение "Извещание о конференции" может объявлять о входе или выходе из нее, выступая в звуковом сигнале или сообщая свои имена.</span><span class="sxs-lookup"><span data-stu-id="1cba1-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="1cba1-106">Вы можете изменить работу объявлений с помощью skype для бизнеса Server Management Shell и с помощью команды **Set-CsDialinConferencing** со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="1cba1-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="1cba1-107">EnableNameRecording — определяет, требуется ли анонимным участникам записать свое имя перед входом в конференцию.</span><span class="sxs-lookup"><span data-stu-id="1cba1-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="1cba1-108">По умолчанию используется значение "$true", что означает, что анонимным участникам предлагается указать свое имя при присоединении к конференции.</span><span class="sxs-lookup"><span data-stu-id="1cba1-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="1cba1-109">(Прошедшие проверку подлинности участники не записывают свое имя, поскольку используется их отображаемое имя.)</span><span class="sxs-lookup"><span data-stu-id="1cba1-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="1cba1-110">EntryExitAnnouncementsEnabledByDefault — указывает, включено ли по умолчанию объявление.</span><span class="sxs-lookup"><span data-stu-id="1cba1-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="1cba1-111">Значение по умолчанию — "$false". Это означает, что по умолчанию, когда участники присоединяются к конференции или покидают ее, нет объявлений.</span><span class="sxs-lookup"><span data-stu-id="1cba1-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="1cba1-112">Организатор собрания может переопредить этот параметр при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="1cba1-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="1cba1-113">EntryExitAnnouncementsType — указывает действие, которое происходит, когда участник присоединяется к конференции или покидает ее, для которой включены объявления.</span><span class="sxs-lookup"><span data-stu-id="1cba1-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="1cba1-114">Значение по умолчанию — "UseNames", которое означает, что при включании объявлений имеется следующее сообщение: "Ken Myer has joined the conference".</span><span class="sxs-lookup"><span data-stu-id="1cba1-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="1cba1-115">Эти параметры можно настроить на глобальном уровне или на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="1cba1-115">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="1cba1-116">Параметры, настроенные на уровне сайта, имеют приоритет над настройками, настроенными на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="1cba1-116">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="1cba1-117">Изменение объявлений при присоединении к конференции и выходе из нее</span><span class="sxs-lookup"><span data-stu-id="1cba1-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="1cba1-118">Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1cba1-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="1cba1-119">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="1cba1-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1cba1-120">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1cba1-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="1cba1-121">Этот cmdlet извлекает сведения о том, должны ли участники записывать свое имя при присоединении к конференции и как Skype для бизнеса Server реагирует, когда участники присоединяются к конференции или покидают ее.</span><span class="sxs-lookup"><span data-stu-id="1cba1-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="1cba1-122">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1cba1-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="1cba1-123">В следующем примере параметры настраиваются на уровне сайта для Redmond.</span><span class="sxs-lookup"><span data-stu-id="1cba1-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="1cba1-124">Объявления будут включены, но участникам не будет предложено ввести свое имя при подмыве конференции.</span><span class="sxs-lookup"><span data-stu-id="1cba1-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="1cba1-125">Когда участники входят в конференцию или покидают ее, будет заиметь тон:</span><span class="sxs-lookup"><span data-stu-id="1cba1-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="1cba1-126">Дополнительные сведения, включая синтаксис и полный список параметров, см. в подстроке [Set-CsDialInConferencingConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1cba1-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

