---
title: 'Lync Server 2013: удаление комнаты или категории чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e94068337747feee592ec25669e9d7b5fc10bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="6b59d-102">Удаление комнаты или категории чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b59d-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b59d-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6b59d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6b59d-104">Можно удалить комнаты сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="6b59d-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="6b59d-105">Если комната чата больше не используется, вы можете отключить ее.</span><span class="sxs-lookup"><span data-stu-id="6b59d-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="6b59d-106">Дополнительные сведения см. [в разделе Отключение или включение комнаты чата в Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span><span class="sxs-lookup"><span data-stu-id="6b59d-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="6b59d-107">Администратор сохраняемого чата может запрашивать отключенные комнаты чата, а также периодически очищать и удалять комнаты чата с помощью командлета Windows PowerShell **Remove – CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="6b59d-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="6b59d-108">Можно удалять категории.</span><span class="sxs-lookup"><span data-stu-id="6b59d-108">Categories can be deleted.</span></span> <span data-ttu-id="6b59d-109">Однако чтобы удалить категорию, нужно сначала удалить в ней все комнаты чата или перенести их в другую категорию, оставив удаляемую категорию пустой.</span><span class="sxs-lookup"><span data-stu-id="6b59d-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="6b59d-110">Сервер сохраняемого чата не позволяет удалять категорию, которая содержит комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="6b59d-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="6b59d-111">Дополнительную информацию можно узнать [в статье Перемещение комнаты чата из одной категории в другую в Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span><span class="sxs-lookup"><span data-stu-id="6b59d-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="6b59d-112">Дополнительные сведения об удалении пустых категорий с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой в разделе [Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="6b59d-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="6b59d-113">Дополнительные сведения о комнатах и категориях чата приведены в статье [Настройка комнат в Lync server 2013](lync-server-2013-configure-rooms.md) и [Настройка категорий в Lync Server 2013](lync-server-2013-configure-categories.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6b59d-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

