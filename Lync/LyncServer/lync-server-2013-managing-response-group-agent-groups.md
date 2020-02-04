---
title: 'Lync Server 2013: Управление группами агента группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6001e8b6301df1863de21e0d88369116cef03ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="01a97-102">Управление группами агентов группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01a97-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01a97-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="01a97-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="01a97-104">Группа агента состоит из группы пользователей, которые предназначены для ответа на звонки в группу ответа.</span><span class="sxs-lookup"><span data-stu-id="01a97-104">An agent group consists of a group of people who are designated to answer calls to a response group.</span></span> <span data-ttu-id="01a97-105">При создании группы агента вы выбираете агенты, назначенные группе, и задаете дополнительные параметры групп, такие как метод маршрутизации, и может ли агент входить в группу и выходить из нее.</span><span class="sxs-lookup"><span data-stu-id="01a97-105">When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01a97-106">Пользователи должны быть включены для корпоративного голосовой связи, прежде чем вы сможете добавить их в группы агента.</span><span class="sxs-lookup"><span data-stu-id="01a97-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="01a97-107">Дополнительные сведения о том, как включить пользователя для голосовой связи, можно найти <A href="lync-server-2013-enable-users-for-enterprise-voice.md">в разделе Включение поддержки пользователей для корпоративной голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="01a97-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="01a97-108">Агентами могут быть только локальные пользователи.</span><span class="sxs-lookup"><span data-stu-id="01a97-108">Only on-premises users can be agents.</span></span> <span data-ttu-id="01a97-109">Если агент перемещается из локальной сети в Online, звонки групп ответов не будут маршрутизироваться этому агенту.</span><span class="sxs-lookup"><span data-stu-id="01a97-109">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="01a97-110">Агент, который должен входить в группу и выйти из нее, отличается от входного и выходного в Lync Server, называется *формальным агентом*.</span><span class="sxs-lookup"><span data-stu-id="01a97-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="01a97-111">Формальные агенты должны входить в группу, прежде чем они смогут принимать звонки, перенаправляемые группе.</span><span class="sxs-lookup"><span data-stu-id="01a97-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="01a97-112">Это может быть удобно для агентов, которые отвечают на вызовы из группы неполный рабочий день.</span><span class="sxs-lookup"><span data-stu-id="01a97-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="01a97-113">Формальные агенты для входа и выхода из их групп щелкают элемент меню в Lync 2013, чтобы открыть веб-браузер Windows Internet Explorer и отобразить ее консоль.</span><span class="sxs-lookup"><span data-stu-id="01a97-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="01a97-114">Агент, который не входит в группу и не выходит из нее, называется *неофициальным агентом*.</span><span class="sxs-lookup"><span data-stu-id="01a97-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="01a97-115">Неформальные агенты автоматически подписываются в группу при входе в Lync Server и не могут выйти из группы.</span><span class="sxs-lookup"><span data-stu-id="01a97-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="01a97-p106">При назначении пользователей в качестве агентов группы ответа оповестите их о том, что при включенном режиме конфиденциальности им потребуется выполнить поиск контактов "RGS Presence Watcher" и добавить их в список контактов. Агенты с включенным режимом конфиденциальности и без "RGS Presence Watcher" в списке контактов не могут принимать звонки, направленные в группу ответа. На агентов, у которых режим конфиденциальности отключен, данная особенность не распространяется.</span><span class="sxs-lookup"><span data-stu-id="01a97-p106">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="01a97-119">Содержание</span><span class="sxs-lookup"><span data-stu-id="01a97-119">In This Section</span></span>

  - [<span data-ttu-id="01a97-120">Создание или изменение группы агента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01a97-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="01a97-121">Удаление группы агента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01a97-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

