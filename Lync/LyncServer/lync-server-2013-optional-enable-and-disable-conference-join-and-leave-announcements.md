---
title: Необязательно Включение и отключение объявлений о присоединении и выходе из конференции
description: Необязательно Включение и отключение объявлений о присоединении и выходе из конференции.
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
ms.openlocfilehash: 70cd6b452a44d7d40f23d5ca96b6e4b7b063d2ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565785"
---
# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="6d5c0-103">Необязательно Включение и отключение объявлений о присоединении и выходе из конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d5c0-103">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d5c0-104">_**Последнее изменение темы:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6d5c0-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6d5c0-105">Когда пользователи присоединяются к Конференции или покидают ее, приложение извещения о конференц-связи может сообщить о своем выходе или выходе, выполнив тон или произнести их имена.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="6d5c0-106">Вы можете изменить работу объявлений с помощью командлетов.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-106">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="6d5c0-107">Этот шаг является необязательным.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-107">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="6d5c0-108">Изменение объявлений при присоединении к конференции и выходе из нее</span><span class="sxs-lookup"><span data-stu-id="6d5c0-108">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="6d5c0-109">Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="6d5c0-110">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6d5c0-111">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6d5c0-111">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="6d5c0-112">Этот командлет получает сведения о том, требуются ли участникам для записи их имен при присоединении к Конференции, а также о том, как Lync Server отвечает, когда участники присоединяются к Конференции или покидают ее.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-112">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="6d5c0-113">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6d5c0-113">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="6d5c0-114">**Енабленамерекординг**     Определяет, запрашивается ли анонимным участникам запись своего имени перед входом в конференцию.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-114">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="6d5c0-115">По умолчанию используется значение "$true", что означает, что анонимным участникам предлагается указать свое имя при присоединении к конференции.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-115">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="6d5c0-116">(Прошедшие проверку подлинности участники не записывают свое имя, поскольку используется их отображаемое имя.)</span><span class="sxs-lookup"><span data-stu-id="6d5c0-116">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="6d5c0-117">**Ентрекситаннаунцементсенабледбидефаулт**     Указывает, включены ли объявления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-117">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="6d5c0-118">Значение по умолчанию — "$false", что означает, что по умолчанию при присоединении или выходе участников из Конференции не будет извещений.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-118">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="6d5c0-119">Организатор собрания может переопределить этот параметр при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-119">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="6d5c0-120">**Ентрекситаннаунцементстипе**     Указывает действие, выполняемое каждый раз, когда участник присоединяется или покидает Конференцию, для которой включены извещения.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-120">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="6d5c0-121">Значение по умолчанию — "Усенамес", что означает, что существует сообщение, похожее на следующее: "Кен Myer присоединился к Конференции" при включении объявлений.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-121">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="6d5c0-122">Эти параметры можно настроить в глобальной области действия или на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-122">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="6d5c0-123">Параметры, настроенные в области сайта, имеют приоритет над параметрами, настроенными в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-123">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="6d5c0-124">Например:</span><span class="sxs-lookup"><span data-stu-id="6d5c0-124">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="6d5c0-125">В этом примере параметры настраиваются на уровне сайта для Redmond.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-125">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="6d5c0-126">Объявления включены, но при присоединении к Конференции участники не получают запрос на ввод имени.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-126">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="6d5c0-127">Звук воспроизводится, когда участники вводят или оставляют конференцию.</span><span class="sxs-lookup"><span data-stu-id="6d5c0-127">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

