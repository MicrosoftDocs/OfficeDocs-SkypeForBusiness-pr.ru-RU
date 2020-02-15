---
title: 'Lync Server 2013: отключение или включение комнаты чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55d9c706c0ea5afcff4f249a9c00a2355667f221
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="f723c-102">Отключение или включение комнаты чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f723c-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f723c-103">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="f723c-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="f723c-104">Если тема сохраняемого чата больше не важна, вы можете сделать комнату чата недоступной для пользователей, отключив ее.</span><span class="sxs-lookup"><span data-stu-id="f723c-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="f723c-105">Когда чат отключен, все подключенные на данный момент участники отключаются от него.</span><span class="sxs-lookup"><span data-stu-id="f723c-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="f723c-106">Пользователи не могут снова подключиться к чату или найти его через поиск после его отключения.</span><span class="sxs-lookup"><span data-stu-id="f723c-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="f723c-107">Отключенная комната чата может быть включена позже администратором сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f723c-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="f723c-108">Если чат отключен, список его участников и другие параметры сохраняются.</span><span class="sxs-lookup"><span data-stu-id="f723c-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="f723c-109">При повторном включении их не потребуется создавать вручную повторно.</span><span class="sxs-lookup"><span data-stu-id="f723c-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="f723c-p103">Если журнал чата сохраняется (сохранение журнала чата — это дополнительный параметр категории, который применяется ко всем чатам категории; по умолчанию он сохраняется, но эту функцию можно отключить путем установки для параметра **Enable Chat History** (Включить журнал чата) категории значения «false»), содержимое сохраняется, даже если чат отключен. Тем не менее, содержимое не будет отображаться в поиске, пока чат остается в отключенном состоянии. Если включить чат позднее, пользователи смогут находить сообщения, опубликованные до того, как чат был отключен.</span><span class="sxs-lookup"><span data-stu-id="f723c-p103">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled. However, that content will not appear in searches during the time that the chat room remains in a disabled state. If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="f723c-113">Дополнительные сведения об отключении и активации комнат чата с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой в разделе [Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="f723c-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="f723c-114">Чтобы отключить комнату чата, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="f723c-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="f723c-115">Чтобы включить комнату чата, установите для свойства Disabled значение false:</span><span class="sxs-lookup"><span data-stu-id="f723c-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="f723c-116">Обратите внимание, что комнаты чата невозможно включать и отключать с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f723c-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="f723c-117">Дополнительные сведения о настройке комнат чата приведены в статье [Configure комнаты в Lync Server 2013](lync-server-2013-configure-rooms.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f723c-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

