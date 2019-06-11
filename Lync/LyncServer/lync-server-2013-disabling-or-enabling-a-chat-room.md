---
title: 'Lync Server 2013: отключение или включение чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f89862b4f7e38a637fa183641f8cdc75e0491379
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="33c4f-102">Отключение или включение чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33c4f-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33c4f-103">_**Тема последнего изменения:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="33c4f-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="33c4f-104">Если тема сохраняемой комнаты чата больше не нужна, вы можете сделать ее недоступной для пользователей, отключив ее.</span><span class="sxs-lookup"><span data-stu-id="33c4f-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="33c4f-105">Если комната чата отключена, все подключенные на данный момент участники отключаются от нее.</span><span class="sxs-lookup"><span data-stu-id="33c4f-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="33c4f-106">Пользователи не могут снова подключиться к комнате чата или найти ее через поиск после ее отключения.</span><span class="sxs-lookup"><span data-stu-id="33c4f-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="33c4f-107">Отключенная комната чата может быть включена позднее администратором постоянного чата.</span><span class="sxs-lookup"><span data-stu-id="33c4f-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="33c4f-108">Если комната чата отключена, список ее членов и другие параметры сохраняются.</span><span class="sxs-lookup"><span data-stu-id="33c4f-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="33c4f-109">Если вы снова включите комнату, вам не нужно будет повторно создавать параметры вручную.</span><span class="sxs-lookup"><span data-stu-id="33c4f-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="33c4f-110">Если история комнаты чата сохраняется (сохраняемый журнал комнаты) — необязательный параметр для категории, которая применяется ко всем помещениям в категории; по умолчанию это значение сохраняется, но может быть отключено с помощью задания для **журнала включения чата** в категорию "включить". false), содержимое сохраняется, когда комната чата отключена.</span><span class="sxs-lookup"><span data-stu-id="33c4f-110">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="33c4f-111">Но содержимое не будет отображаться в поиске, пока комната чата остается в отключенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="33c4f-111">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="33c4f-112">Если включить ее позднее, пользователи смогут находить сообщения, опубликованные до того, как комната чата была отключена.</span><span class="sxs-lookup"><span data-stu-id="33c4f-112">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="33c4f-113">Дополнительные сведения об отключении и включении комнат чата с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой на странице [Настройка сохраняемого сервера чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="33c4f-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="33c4f-114">Чтобы отключить комнату чата, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="33c4f-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="33c4f-115">Чтобы включить комнату чата, установите для свойства Disabled значение false.</span><span class="sxs-lookup"><span data-stu-id="33c4f-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="33c4f-116">Обратите внимание, что комнаты чата нельзя включать или отключать с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33c4f-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="33c4f-117">Дополнительные сведения о настройке комнат чатов можно найти в разделе [Настройка комнат в Lync Server 2013](lync-server-2013-configure-rooms.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="33c4f-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

