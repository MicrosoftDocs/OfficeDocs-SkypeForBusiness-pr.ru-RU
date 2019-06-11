---
title: 'Lync Server 2013: перемещение чата из одной категории в другую'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61d20ff1de7437054df36af224293dcdcb61d54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="19a08-102">Перемещение чата из одной категории в другую в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19a08-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19a08-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="19a08-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="19a08-104">Мы не рекомендуем менять категорию сохраняемой комнаты чата после создания комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="19a08-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="19a08-105">Тем не менее, если у руководителя комнаты чата есть полномочия **создателя** в другой категории, он может переместить комнату из одной категории в другую.</span><span class="sxs-lookup"><span data-stu-id="19a08-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="19a08-106">Комната не удаляется и воссоздается.</span><span class="sxs-lookup"><span data-stu-id="19a08-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="19a08-107">Это изменение связи с базой данных.</span><span class="sxs-lookup"><span data-stu-id="19a08-107">It is a change of association within the database.</span></span>

<span data-ttu-id="19a08-108">Изменение категории комнаты чата может выполняться редко.</span><span class="sxs-lookup"><span data-stu-id="19a08-108">Changing a chat room category should be done rarely.</span></span> <span data-ttu-id="19a08-109">Категория определяет разрешенное членство в комнате чата, поэтому при перемещении комнаты чата в другую категорию все системные списки управления доступом (SACL), которые более не поддерживаются новой категорией, очищаются.</span><span class="sxs-lookup"><span data-stu-id="19a08-109">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="19a08-110">Например, если пользователь был участником комнаты и больше не является **алловедмембер** в новой категории, принадлежность к комнате будет изменена, и пользователь будет удален из комнаты.</span><span class="sxs-lookup"><span data-stu-id="19a08-110">For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="19a08-111">Подробнее о перемещении комнаты чата с помощью интерфейса командной строки Windows PowerShell можно узнать в разделе Управление комнатой на странице [Настройка сохраняемого сервера чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="19a08-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="19a08-112">Дополнительные сведения о настройке комнат чатов можно найти в разделе [Настройка комнат в Lync Server 2013](lync-server-2013-configure-rooms.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="19a08-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

