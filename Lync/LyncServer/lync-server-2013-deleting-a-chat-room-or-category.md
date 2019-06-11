---
title: 'Lync Server 2013: удаление чата или категории'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f64b89abd0b3266d2be52e300458ceabf3f9b915
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="af2bb-102">Удаление чата или категории в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af2bb-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af2bb-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="af2bb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="af2bb-104">Сохраняемые комнаты чата могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="af2bb-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="af2bb-105">Если у вас есть комната чата, которая больше не используется, ее можно отключить.</span><span class="sxs-lookup"><span data-stu-id="af2bb-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="af2bb-106">Подробности можно найти [в разделе Отключение и включение комнаты чата в Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span><span class="sxs-lookup"><span data-stu-id="af2bb-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="af2bb-107">Администратор сохраняемого чата может запрашивать отключенные комнаты чата, а также периодически очищать и удалять комнаты чата с помощью командлета Windows PowerShell **Remove-ксперсистентчатрум**.</span><span class="sxs-lookup"><span data-stu-id="af2bb-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="af2bb-108">Категории можно удалить.</span><span class="sxs-lookup"><span data-stu-id="af2bb-108">Categories can be deleted.</span></span> <span data-ttu-id="af2bb-109">Тем не менее, чтобы удалить категорию, необходимо сначала удалить из нее все комнаты чата или переместить комнаты чата в новую категорию, оставив пустую категорию для удаления.</span><span class="sxs-lookup"><span data-stu-id="af2bb-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="af2bb-110">На сервере сохраняемого чата не разрешается удалять категории, содержащие комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="af2bb-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="af2bb-111">Подробности можно найти [в разделе Перемещение комнаты чата из одной категории в другую в Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span><span class="sxs-lookup"><span data-stu-id="af2bb-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="af2bb-112">Подробнее об удалении пустых категорий с помощью интерфейса командной строки Windows PowerShell можно узнать в разделе Управление комнатой на странице [Настройка сохраняемого сервера чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="af2bb-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="af2bb-113">Дополнительные сведения о комнатах и категориях чата в разделе [Настройка комнат в Lync server 2013](lync-server-2013-configure-rooms.md) и [Настройка категорий в Lync Server 2013](lync-server-2013-configure-categories.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="af2bb-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

