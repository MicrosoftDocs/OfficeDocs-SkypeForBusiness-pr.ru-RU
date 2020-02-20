---
title: 'Lync Server 2013: Настройка комнат'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3521e533dee1ff995fae417b8a7f29a75a77ac63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="7c491-102">Настройка комнат в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c491-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c491-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="7c491-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="7c491-104">Настройка комнат сохраняемого чата обычно обрабатываются пользователями или другими центральными группами с помощью интерфейса командной строки Windows PowerShell; как правило, администратор не управляет комнатами чата.</span><span class="sxs-lookup"><span data-stu-id="7c491-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="7c491-105">Тем не менее, если вы хотите создавать комнаты чата и управлять ими, вы можете использовать интерфейс командной строки Windows PowerShell или добавить себя в качестве участника в комнату чата и использовать клиент Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7c491-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="7c491-106">Дополнительные сведения о настройке комнат чата с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой в разделе [Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="7c491-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="7c491-107">Управление данными в комнатах чата</span><span class="sxs-lookup"><span data-stu-id="7c491-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="7c491-108">Сервер сохраняемого чата позволяет пользователям сотрудничать, отправив сообщения в сохраняемые комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="7c491-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="7c491-109">Данные сохраняются на сервере, а участники чата могут получать доступ к данным, включая данные журналов.</span><span class="sxs-lookup"><span data-stu-id="7c491-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="7c491-110">Однако пользователи с разными ролями будут иметь разный доступ к сохраненным данным, как описано в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="7c491-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="7c491-p103">Администраторы могут удалить старое содержимое (например, содержимое, размещенное до определенной даты) из любой комнаты чата, чтобы не дать базе данных сильно увеличиться в размерах. Кроме того, они могут заменить удалить или заменить сообщения, которые кажутся несоответствующими данной комнате чата.</span><span class="sxs-lookup"><span data-stu-id="7c491-p103">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large. Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="7c491-113">Сами пользователи, включая авторов сообщений, не могут удалять содержимое комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="7c491-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="7c491-p104">Руководители комнат чата могут отключать комнаты, но не удалять их. Только администраторы могут удалить комнату чата после ее создания.</span><span class="sxs-lookup"><span data-stu-id="7c491-p104">Chat room managers can disable rooms, but cannot delete rooms. Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="7c491-116">Удаление сообщения невозможно отменить.</span><span class="sxs-lookup"><span data-stu-id="7c491-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="7c491-117">Однако удаленные сообщения могут быть восстановлены из резервной копии (если таковая существует).</span><span class="sxs-lookup"><span data-stu-id="7c491-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="7c491-118">Если включен сервер соответствия сохраняемого чата, старые сообщения сохраняются в базе данных соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7c491-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c491-119">Это использование данных для комнаты чата применяется к приложению серверного API сервера сохраняемого чата для Lync Server 2013, кроме случая, когда задействована роль администратора.</span><span class="sxs-lookup"><span data-stu-id="7c491-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="7c491-120">Невозможно использовать API сервера сохраняемого чата для выполнения каких-либо действий администратора.</span><span class="sxs-lookup"><span data-stu-id="7c491-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="7c491-121">Эти операции необходимо выполнить в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7c491-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

