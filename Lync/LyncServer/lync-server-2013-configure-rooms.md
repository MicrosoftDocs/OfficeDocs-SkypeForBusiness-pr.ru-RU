---
title: 'Lync Server 2013: настройка чатов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08b7cb0146f96b151af021a63ef97a485a0a9dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="bafe7-102">Настройка чатов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bafe7-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bafe7-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="bafe7-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="bafe7-104">Настройка постоянных комнат чатов обычно обрабатывают пользователи или другие центральные группы с помощью интерфейса командной строки Windows PowerShell; Администратор, как правило, не управляет помещениями чата.</span><span class="sxs-lookup"><span data-stu-id="bafe7-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="bafe7-105">Тем не менее, если вам нужно создать комнаты чата и управлять ими, вы можете воспользоваться интерфейсом командной строки Windows PowerShell или добавить себя как участника в комнату чата и использовать клиент Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="bafe7-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="bafe7-106">Дополнительные сведения о настройке комнат чата с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой на странице [Настройка сохраняемого сервера чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="bafe7-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="bafe7-107">Управление данными в комнатах чата</span><span class="sxs-lookup"><span data-stu-id="bafe7-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="bafe7-108">Сервер сохраняемого чата позволяет пользователям работать совместно, подмещая сообщения в сохраняемые комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="bafe7-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="bafe7-109">Данные сохраняются на сервере, а участники комнаты могут иметь доступ к данным, в том числе к данным с предысторией.</span><span class="sxs-lookup"><span data-stu-id="bafe7-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="bafe7-110">Тем не менее, пользователи с разными ролями имеют разный доступ к сохраненным данным, как описано в приведенном ниже списке.</span><span class="sxs-lookup"><span data-stu-id="bafe7-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="bafe7-111">Администраторы могут удалять старое содержимое (например, содержимое, размещенное до определенной даты) из любой комнаты чата, чтобы база данных сильно не увеличивалась в размерах.</span><span class="sxs-lookup"><span data-stu-id="bafe7-111">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="bafe7-112">Кроме того, они могут удалять или заменять сообщения, которые считаются неприемлемыми для определенной комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="bafe7-112">Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="bafe7-113">Сами пользователи, включая авторов сообщений, не могут удалять содержимое комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="bafe7-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="bafe7-114">Руководители комнаты чата могут отключить помещения, но не могут удалять помещения.</span><span class="sxs-lookup"><span data-stu-id="bafe7-114">Chat room managers can disable rooms, but cannot delete rooms.</span></span> <span data-ttu-id="bafe7-115">Только администраторы могут удалить комнату чата после того, как она будет создана.</span><span class="sxs-lookup"><span data-stu-id="bafe7-115">Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="bafe7-116">После удаления сообщения отменить это действие невозможно.</span><span class="sxs-lookup"><span data-stu-id="bafe7-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="bafe7-117">Однако удаленные сообщения могут быть восстановлены при наличии резервной копии.</span><span class="sxs-lookup"><span data-stu-id="bafe7-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="bafe7-118">Если включен постоянный сервер соответствия чатов, старые сообщения сохраняются в базе данных соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="bafe7-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bafe7-119">Это использование данных в комнате чата распространяется на приложение Lync Server 2013, сохраняемый серверный чат, за исключением случаев, когда вовлечена роль администратора.</span><span class="sxs-lookup"><span data-stu-id="bafe7-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="bafe7-120">Серверный API постоянного чата не может использоваться для выполнения каких-либо действий администратора.</span><span class="sxs-lookup"><span data-stu-id="bafe7-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="bafe7-121">Эти операции необходимо выполнять в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="bafe7-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

