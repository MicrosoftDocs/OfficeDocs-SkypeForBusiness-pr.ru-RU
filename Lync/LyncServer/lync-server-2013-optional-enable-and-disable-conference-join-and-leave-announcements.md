---
title: Необязательно Включение и отключение объявлений о присоединении и выходе из конференции
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
ms.openlocfilehash: 67939f67e90e6c0cc044ea871560647cae9e4021
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="f518b-102">Необязательно Включение и отключение объявлений о присоединении и выходе из конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f518b-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f518b-103">_**Последнее изменение темы:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="f518b-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="f518b-104">Когда пользователи присоединяются к Конференции или покидают ее, приложение извещения о конференц-связи может сообщить о своем выходе или выходе, выполнив тон или произнести их имена.</span><span class="sxs-lookup"><span data-stu-id="f518b-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="f518b-105">Вы можете изменить работу объявлений с помощью командлетов.</span><span class="sxs-lookup"><span data-stu-id="f518b-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="f518b-106">Этот шаг является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f518b-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="f518b-107">Изменение объявлений при присоединении к конференции и выходе из нее</span><span class="sxs-lookup"><span data-stu-id="f518b-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="f518b-108">Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="f518b-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="f518b-109">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f518b-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f518b-110">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f518b-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="f518b-111">Этот командлет получает сведения о том, требуются ли участникам для записи их имен при присоединении к Конференции, а также о том, как Lync Server отвечает, когда участники присоединяются к Конференции или покидают ее.</span><span class="sxs-lookup"><span data-stu-id="f518b-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="f518b-112">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f518b-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="f518b-113">**Енабленамерекординг**   определяет, запрашивается ли анонимным участникам запись своего имени перед входом в конференцию.</span><span class="sxs-lookup"><span data-stu-id="f518b-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="f518b-114">По умолчанию используется значение "$true", что означает, что анонимным участникам предлагается указать свое имя при присоединении к конференции.</span><span class="sxs-lookup"><span data-stu-id="f518b-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="f518b-115">(Прошедшие проверку подлинности участники не записывают свое имя, поскольку используется их отображаемое имя.)</span><span class="sxs-lookup"><span data-stu-id="f518b-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="f518b-116">**Ентрекситаннаунцементсенабледбидефаулт**   указывает, включены ли объявления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f518b-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="f518b-117">Значение по умолчанию — "$false", что означает, что по умолчанию при присоединении или выходе участников из Конференции не будет извещений.</span><span class="sxs-lookup"><span data-stu-id="f518b-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="f518b-118">Организатор собрания может переопределить этот параметр при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="f518b-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="f518b-119">**Ентрекситаннаунцементстипе**   указывает действие, выполняемое каждый раз, когда участник присоединяется или покидает Конференцию, для которой включены извещения.</span><span class="sxs-lookup"><span data-stu-id="f518b-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="f518b-120">Значение по умолчанию — "Усенамес", что означает, что существует сообщение, похожее на следующее: "Кен Myer присоединился к Конференции" при включении объявлений.</span><span class="sxs-lookup"><span data-stu-id="f518b-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="f518b-121">Эти параметры можно настроить в глобальной области действия или на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="f518b-121">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="f518b-122">Параметры, настроенные в области сайта, имеют приоритет над параметрами, настроенными в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="f518b-122">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="f518b-123">Например:</span><span class="sxs-lookup"><span data-stu-id="f518b-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="f518b-124">В этом примере параметры настраиваются на уровне сайта для Redmond.</span><span class="sxs-lookup"><span data-stu-id="f518b-124">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="f518b-125">Объявления включены, но при присоединении к Конференции участники не получают запрос на ввод имени.</span><span class="sxs-lookup"><span data-stu-id="f518b-125">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="f518b-126">Звук воспроизводится, когда участники вводят или оставляют конференцию.</span><span class="sxs-lookup"><span data-stu-id="f518b-126">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

