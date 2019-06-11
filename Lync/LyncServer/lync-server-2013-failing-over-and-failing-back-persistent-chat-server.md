---
title: 'Lync Server 2013: отработка отказа и восстановление после сбоя сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over and failing back Persistent Chat Server
ms:assetid: bc9a791f-d15c-48c8-8682-1a8ad19d8c75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205214(v=OCS.15)
ms:contentKeyID: 48185259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9871c5cfe4d92bacadd6ec8c2c92dea0d3b25a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-and-failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="61cd9-102">Отработка отказа и восстановление после сбоя сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61cd9-102">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61cd9-103">_**Тема последнего изменения:** 2012-08-03_</span><span class="sxs-lookup"><span data-stu-id="61cd9-103">_**Topic Last Modified:** 2012-08-03_</span></span>

<span data-ttu-id="61cd9-104">Чтобы отдать отказ и отдать отказ на переход на сервер Lync Server 2013, постоянный чат, вам необходимо ознакомиться с процессами репликации и перемещения при сбое для Microsoft SQL Server 2008 R2 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="61cd9-104">To fail over and fail back Lync Server 2013, Persistent Chat Server, you should be familiar with replication and failover processes for Microsoft SQL Server 2008 R2 and later.</span></span> <span data-ttu-id="61cd9-105">Кроме того, необходимо ознакомиться со службами сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="61cd9-105">You should also be familiar with the Persistent Chat Server services.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="61cd9-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="61cd9-106">In This Section</span></span>

  - [<span data-ttu-id="61cd9-107">Отработка отказа сервером сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61cd9-107">Failing over Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-persistent-chat-server.md)

  - [<span data-ttu-id="61cd9-108">Восстановление сервера сохраняемого чата после сбоя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61cd9-108">Failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

