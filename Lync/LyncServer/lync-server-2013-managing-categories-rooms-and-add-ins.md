---
title: 'Lync Server 2013: управление категориями, чатами и надстройками'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing categories, rooms, and add-ins
ms:assetid: a9807031-7369-4a51-9369-6f09bec24141
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412799(v=OCS.15)
ms:contentKeyID: 48185100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2870d83d463866e07afdffab7c0a840bb2686928
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="d5800-102">Управление категориями, чатами и надстройками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5800-102">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5800-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="d5800-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="d5800-104">В панели управления Lync Server 2013 или с помощью командлетов Windows PowerShell для создания категорий и надстроек можно использовать \*\*\*\* страницу сохраняемого чата. Для управления сохраняемыми комнатами чата администраторы могут использовать командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5800-104">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="d5800-105">Кроме того, если администратор постоянного чата также поддерживает SIP, он может использовать клиент Lync, чтобы открыть веб-страницу для создания комнат чата и управления ими.</span><span class="sxs-lookup"><span data-stu-id="d5800-105">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="d5800-106">В следующих разделах описано, как создавать и работать с категориями и комнатами чата.</span><span class="sxs-lookup"><span data-stu-id="d5800-106">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d5800-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="d5800-107">In This Section</span></span>

  - [<span data-ttu-id="d5800-108">Создание или редактирование новой категории в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5800-108">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="d5800-109">Создание или редактирование нового чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5800-109">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="d5800-110">Создание новых надстроек для чатов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5800-110">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="d5800-111">Установка лиц, которые могут публиковать сообщения в чате аудитории в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5800-111">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="d5800-112">Отключение или включение чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5800-112">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="d5800-113">Перемещение чата из одной категории в другую в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5800-113">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="d5800-114">Удаление чата или категории в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5800-114">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="d5800-115">Удаление сообщения или удаление устаревших сообщений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5800-115">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

