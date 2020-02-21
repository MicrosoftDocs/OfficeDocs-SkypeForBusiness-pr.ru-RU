---
title: 'Lync Server 2013: перемещение комнаты чата из одной категории в другую'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27ca186fa31b1207238c3a7d254bbd6066cc1d89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="8e809-102">Перемещение комнаты чата из одной категории в другую в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e809-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e809-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8e809-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8e809-104">При создании комнаты чата не рекомендуется менять категорию сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="8e809-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="8e809-105">Однако если менеджер комнаты чата имеет привилегии **автора** в другой категории, то технически он или могут переместить комнату из одной категорию в другую.</span><span class="sxs-lookup"><span data-stu-id="8e809-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="8e809-106">Комната не удаляется и воссоздается.</span><span class="sxs-lookup"><span data-stu-id="8e809-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="8e809-107">Это изменение связи с базой данных.</span><span class="sxs-lookup"><span data-stu-id="8e809-107">It is a change of association within the database.</span></span>

<span data-ttu-id="8e809-p102">Изменение категории комнаты должно происходить редко. Категория определяет разрешенное членство в комнате чата, поэтому при перемещении комнаты чата в другую категорию все системные списки управления доступом (SACL), которые более не поддерживаются новой категорией, очищаются. Например, если пользователь был участником комнаты и больше не является **AllowedMember** в новой категории, членство категории будет изменено, а пользователь будет удален из комнаты.</span><span class="sxs-lookup"><span data-stu-id="8e809-p102">Changing a chat room category should be done rarely. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="8e809-111">Дополнительные сведения о перемещении комнаты чата с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой в разделе [Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="8e809-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="8e809-112">Дополнительные сведения о настройке комнат чата приведены в статье [Configure комнаты в Lync Server 2013](lync-server-2013-configure-rooms.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8e809-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

