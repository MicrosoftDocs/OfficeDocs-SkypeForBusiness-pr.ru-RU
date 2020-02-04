---
title: Включение и отключение объявлений о присоединении и выходе из конференции (необязательно)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b8e75a0d2ed81a515540f2a8a1811998a85d44c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="534b0-102">Включение и отключение объявлений о присоединении и выходе из конференции в Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="534b0-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="534b0-103">_**Тема последнего изменения:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="534b0-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="534b0-104">При присоединении к Конференции или выходе из нее пользователи могут сообщать о своем входе в приложение и выходить из него с помощью звукового сопровождения или произнесения их имен.</span><span class="sxs-lookup"><span data-stu-id="534b0-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="534b0-105">Вы можете изменить способ работы объявлений, выполнив командлеты.</span><span class="sxs-lookup"><span data-stu-id="534b0-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="534b0-106">Этот шаг является необязательным.</span><span class="sxs-lookup"><span data-stu-id="534b0-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="534b0-107">Изменение объявлений при присоединении к конференции и выходе из нее</span><span class="sxs-lookup"><span data-stu-id="534b0-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="534b0-108">Войдите в систему под учетной записью члена группы Рткуниверсалсерверадминс или члена роли **CS-серверадминистратор** или **ксадминистратор** .</span><span class="sxs-lookup"><span data-stu-id="534b0-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="534b0-109">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="534b0-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="534b0-110">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="534b0-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="534b0-111">Этот командлет извлекает сведения о том, требуется ли участникам записывать свое имя при присоединении к Конференции, а также о том, как Lync Server отвечает за присоединение или выход из конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="534b0-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="534b0-112">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="534b0-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="534b0-113">**Енабленамерекординг**   определяет, должны ли анонимные участники запрашивать запись имени перед входом в конференцию.</span><span class="sxs-lookup"><span data-stu-id="534b0-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="534b0-114">По умолчанию используется значение "$true", что означает, что анонимным участникам будет предложено указать свое имя при присоединении к Конференции.</span><span class="sxs-lookup"><span data-stu-id="534b0-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="534b0-115">(Участники, прошедшие проверку подлинности, не записывают свое имя, так как вместо этого используется отображаемое имя.)</span><span class="sxs-lookup"><span data-stu-id="534b0-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="534b0-116">**Ентрекситаннаунцементсенабледбидефаулт**   указывает, включены ли извещения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="534b0-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="534b0-117">Значением по умолчанию является "$false, что означает, что по умолчанию при присоединении к Конференции или выходе участников из нее не будет извещений.</span><span class="sxs-lookup"><span data-stu-id="534b0-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="534b0-118">Организатор собрания может переопределить этот параметр при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="534b0-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="534b0-119">**Ентрекситаннаунцементстипе**   указывает действие, предпринимаемое каждый раз, когда участник присоединяется к Конференции, для которой включены извещения, или выходит из нее.</span><span class="sxs-lookup"><span data-stu-id="534b0-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="534b0-120">По умолчанию используется значение "Усенамес", которое означает, что на Конференции было объявлено извещение о том, что "Кен мер входит в конференцию", когда извещения включены.</span><span class="sxs-lookup"><span data-stu-id="534b0-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="534b0-p105">Эти параметры можно настроить в глобальной области или в области узла. Параметры, настроенные в области узла, имеют более высокий приоритет, чем параметры, настроенные в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="534b0-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="534b0-123">Например:</span><span class="sxs-lookup"><span data-stu-id="534b0-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="534b0-124">В этом примере параметры задаются в области сайта для Redmond.</span><span class="sxs-lookup"><span data-stu-id="534b0-124">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="534b0-125">Объявления включены, но у участников не запрашивается имя при подключении к конференции.</span><span class="sxs-lookup"><span data-stu-id="534b0-125">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="534b0-126">Звуковой сигнал воспроизводится, когда участники вводят или покидают Конференцию.</span><span class="sxs-lookup"><span data-stu-id="534b0-126">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

