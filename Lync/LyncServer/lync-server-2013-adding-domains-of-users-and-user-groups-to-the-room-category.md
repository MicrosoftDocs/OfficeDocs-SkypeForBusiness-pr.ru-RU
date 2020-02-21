---
title: 'Lync Server 2013: Добавление доменов пользователей и групп пользователей в категорию комнаты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding domains of users and user groups to the room category
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48706013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44138fba7524f74f660073f31a6af075d889ea64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-domains-of-users-and-user-groups-to-the-room-category-in-lync-server-2013"></a><span data-ttu-id="eb725-102">Добавление доменов пользователей и групп пользователей в категорию комнаты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb725-102">Adding domains of users and user groups to the room category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb725-103">_**Последнее изменение темы:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="eb725-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="eb725-104">Чтобы добавить крупные группы пользователей в комнату чата, ознакомьтесь со статьей [Настройка категорий в Lync Server 2013](lync-server-2013-configure-categories.md) и [Управление категориями](manage-categories.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="eb725-104">To add larger groups of users to a chat room, see [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) and [Manage categories](manage-categories.md) in the Deployment documentation.</span></span> <span data-ttu-id="eb725-105">Например, эта команда добавляет всех пользователей из подразделения Норсамерикаусерс в Active Directory в комнату чата NorthAmerica:</span><span class="sxs-lookup"><span data-stu-id="eb725-105">For example, this command adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

<span data-ttu-id="eb725-106">Эта команда добавляет всех участников из группы рассылки Finance в ту же комнату чата:</span><span class="sxs-lookup"><span data-stu-id="eb725-106">His command adds all the members from the Finance distribution group to the same chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

</div>

<span> </span>

</div>

</div>

</div>

