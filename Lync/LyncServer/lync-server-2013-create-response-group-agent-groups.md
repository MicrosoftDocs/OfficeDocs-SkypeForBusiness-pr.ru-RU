---
title: 'Lync Server 2013: создание групп агентов группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48b4f97ad93ecdbfef9e8e170c999f8c9860f830
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="60b27-102">Создание групп агентов группы ответа Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60b27-102">Create Response Group agent groups Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60b27-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="60b27-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="60b27-104">Когда вы создаете группу агентов, вы выбираете агентов, назначаемых группе, и указываете дополнительные параметры группы, такие как метод маршрутизации и возможность агента выполнять вход в группу и выход из нее.</span><span class="sxs-lookup"><span data-stu-id="60b27-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="60b27-105">Агент, который должен входить в группу и выходить из нее, отличается от входа или выхода из Lync Server, называется *формальным агентом*.</span><span class="sxs-lookup"><span data-stu-id="60b27-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="60b27-106">Официальные агенты должны войти в группу, прежде чем они смогут получать направленные в нее звонки.</span><span class="sxs-lookup"><span data-stu-id="60b27-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="60b27-107">Это может быть удобно для агентов, которые отвечают на звонки из группы неполный рабочий день.</span><span class="sxs-lookup"><span data-stu-id="60b27-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="60b27-108">Формальные агенты входят в группы и выходят из них, щелкая элемент меню в Lync 2013, чтобы открыть браузер Windows Internet Explorer и отобразить консоль веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="60b27-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="60b27-109">Агент, который не входит в группу и не выходит из нее, называется *неофициальным агентом*.</span><span class="sxs-lookup"><span data-stu-id="60b27-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="60b27-110">Неформальные агенты автоматически подписываются в группу при входе в Lync Server и не могут выходить из группы.</span><span class="sxs-lookup"><span data-stu-id="60b27-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60b27-p103">Агентами могут быть только локальные пользователи. Если агент переходит из локального режима в интерактивный, ему не будут направляться звонки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="60b27-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="60b27-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="60b27-113">In This Section</span></span>

[<span data-ttu-id="60b27-114">Создание или изменение группы агентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60b27-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

