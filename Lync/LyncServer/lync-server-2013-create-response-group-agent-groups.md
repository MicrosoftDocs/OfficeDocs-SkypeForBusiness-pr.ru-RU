---
title: 'Lync Server 2013: создание групп агента группы ответа'
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
ms.openlocfilehash: 8e2a8a41b67818cf1f2aec9ec8daaa46eeff783a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="8ac2d-102">Создание групп агента группы ответа Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ac2d-102">Create Response Group agent groups Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ac2d-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8ac2d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8ac2d-104">Когда вы создаете группу агентов, вы выбираете агентов, назначаемых группе, и указываете дополнительные параметры группы, такие как метод маршрутизации и возможность агента выполнять вход в группу и выход из нее.</span><span class="sxs-lookup"><span data-stu-id="8ac2d-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="8ac2d-105">Агент, который должен входить в группу и выйти из нее, отличается от входного и выходного в Lync Server, называется *формальным агентом*.</span><span class="sxs-lookup"><span data-stu-id="8ac2d-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="8ac2d-106">Для приема вызовов, направленных в группу, официальные агенты должны сначала войти в группу.</span><span class="sxs-lookup"><span data-stu-id="8ac2d-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="8ac2d-107">Это может быть удобно для агентов, которые отвечают на вызовы из группы неполный рабочий день.</span><span class="sxs-lookup"><span data-stu-id="8ac2d-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="8ac2d-108">Формальные агенты для входа и выхода из их групп щелкают элемент меню в Lync 2013, чтобы открыть веб-браузер Windows Internet Explorer и отобразить ее консоль.</span><span class="sxs-lookup"><span data-stu-id="8ac2d-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="8ac2d-109">Агент, который не входит в группу и не выходит из нее, называется *неофициальным агентом*.</span><span class="sxs-lookup"><span data-stu-id="8ac2d-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="8ac2d-110">Неформальные агенты автоматически подписываются в группу при входе в Lync Server и не могут выйти из группы.</span><span class="sxs-lookup"><span data-stu-id="8ac2d-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ac2d-111">Агентами могут быть только локальные пользователи.</span><span class="sxs-lookup"><span data-stu-id="8ac2d-111">Only on-premises users can be agents.</span></span> <span data-ttu-id="8ac2d-112">Если агент перемещается из локальной сети в Online, звонки групп ответов не будут маршрутизироваться этому агенту.</span><span class="sxs-lookup"><span data-stu-id="8ac2d-112">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8ac2d-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="8ac2d-113">In This Section</span></span>

[<span data-ttu-id="8ac2d-114">Создание или изменение группы агента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ac2d-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

