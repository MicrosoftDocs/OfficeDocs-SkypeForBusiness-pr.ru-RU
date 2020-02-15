---
title: 'Lync Server 2013: Управление категориями, комнатами и надстройками'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing categories, rooms, and add-ins
ms:assetid: a9807031-7369-4a51-9369-6f09bec24141
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412799(v=OCS.15)
ms:contentKeyID: 48185100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1fcd4422ca855e7247c57d07887b9df20ea695
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="4f07e-102">Управление категориями, комнатами и надстройками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f07e-102">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f07e-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="4f07e-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="4f07e-104">В панели управления Lync Server 2013 или с помощью командлетов Windows PowerShell администраторы сохраняемого чата могут создавать категории и надстройки с помощью страницы **сохраняемого чата** . Для управления комнатами сохраняемого чата администраторы могут использовать командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f07e-104">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4f07e-105">Кроме того, если администратор сохраняемого чата также поддерживает поддержку SIP, он может использовать клиент Lync для запуска веб-страницы для создания комнат чата и управления ими.</span><span class="sxs-lookup"><span data-stu-id="4f07e-105">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="4f07e-106">В следующих разделах описывается создание категорий и чатов и работа с ними.</span><span class="sxs-lookup"><span data-stu-id="4f07e-106">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4f07e-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="4f07e-107">In This Section</span></span>

  - [<span data-ttu-id="4f07e-108">Создание или изменение новой категории в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f07e-108">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="4f07e-109">Создание или редактирование нового помещения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f07e-109">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="4f07e-110">Создание новых надстроек для комнат в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f07e-110">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="4f07e-111">Настройка пользователей, которые могут отправлять сообщения в комнату чата аудитория в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f07e-111">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="4f07e-112">Отключение или включение комнаты чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f07e-112">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="4f07e-113">Перемещение комнаты чата из одной категории в другую в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f07e-113">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="4f07e-114">Удаление комнаты или категории чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f07e-114">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="4f07e-115">Удаление сообщения или удаление устаревших сообщений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f07e-115">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

