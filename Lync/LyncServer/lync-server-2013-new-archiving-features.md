---
title: 'Lync Server 2013: новые функции архивации'
description: 'Lync Server 2013: новые функции архивации.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b69c90e62914284f178ae328375c6e350f5b3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561355"
---
# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="85725-103">Новые функции архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85725-103">New Archiving features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85725-104">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="85725-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="85725-105">Архивация в Lync Server 2013 позволяет архивировать следующие типы контента:</span><span class="sxs-lookup"><span data-stu-id="85725-105">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="85725-106">одноранговый обмен мгновенными сообщениями;</span><span class="sxs-lookup"><span data-stu-id="85725-106">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="85725-107">конференции (собрания), которые являются обменом мгновенными сообщениями с несколькими участниками;</span><span class="sxs-lookup"><span data-stu-id="85725-107">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="85725-108">контент конференций, включая отправленный контент (например, раздаточные материалы) и контент, связанный с событиями (например, присоединение, отключение, отправка общедоступных файлов и изменения видимости).</span><span class="sxs-lookup"><span data-stu-id="85725-108">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="85725-109">Кроме того, архивация в Lync Server 2013 предоставляет новые функции, повышающие эффективность развертывания и эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="85725-109">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="85725-110">Сюда входят следующие функции.</span><span class="sxs-lookup"><span data-stu-id="85725-110">These new features consist of:</span></span>

  - <span data-ttu-id="85725-111">Совместное размещение **архивации на серверах переднего плана.**     Lync Server 2013 не имеет отдельной роли сервера архивации.</span><span class="sxs-lookup"><span data-stu-id="85725-111">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="85725-112">Архивирование является дополнительной функцией, которая доступна на всех серверах переднего плана в развертывании Enterprise Edition и на серверах Standard Edition, которые можно реализовать в конфигурации для пула или сайта.</span><span class="sxs-lookup"><span data-stu-id="85725-112">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="85725-113">**Интеграция с Microsoft Exchange.**     При развертывании архивации можно интегрировать хранилище данных для архивации с имеющимся хранилищем Exchange 2013 для всех пользователей, размещенных в Exchange 2013 и почтовых ящиков, которые помещаются на In-Place хранения, поэтому нет необходимости развертывать отдельные базы данных SQL Server для архивации данных Lync.</span><span class="sxs-lookup"><span data-stu-id="85725-113">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="85725-114">Если у вас нет развертывания Exchange 2013 или если вы не хотите интегрироваться с ним, или если у вас есть пользователи Lync 2013, не размещенные в Exchange 2013 с их почтовыми ящиками, поIn-Place хранения, можно развернуть отдельные базы данных архивации с помощью SQL Server для хранения архивных данных из коммуникаций Lync.</span><span class="sxs-lookup"><span data-stu-id="85725-114">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="85725-115">Можно использовать как интеграцию Microsoft Exchange, так и базы данных архивации Lync Server 2013, если вы хотите использовать интеграцию Microsoft Exchange для некоторых, но не всех пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="85725-115">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="85725-116">Сведения об удержании In-Place содержатся в разделе "удержание на месте" [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500) .</span><span class="sxs-lookup"><span data-stu-id="85725-116">For details about In-Place Hold, see “In-Place Hold” at [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="85725-117">**Зеркальное отображение хранилища SQL.**     При развертывании архивации можно включить зеркальное отображение базы данных SQL Server для базы данных архивации.</span><span class="sxs-lookup"><span data-stu-id="85725-117">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="85725-118">**Архивирование досок и опросов.**     Архивный контент конференции теперь включает в себя доски и опросы, которые совместно используются во время собрания.</span><span class="sxs-lookup"><span data-stu-id="85725-118">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="85725-119">Следующие типы контента не архивируются:</span><span class="sxs-lookup"><span data-stu-id="85725-119">The following types of content are not archived:</span></span>

  - <span data-ttu-id="85725-120">одноранговые передачи файлов;</span><span class="sxs-lookup"><span data-stu-id="85725-120">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="85725-121">аудио- и видеоданные для однорангового обмена мгновенными сообщениями и конференций;</span><span class="sxs-lookup"><span data-stu-id="85725-121">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="85725-122">общий доступ к приложениям в одноранговом обмене мгновенными сообщениями и конференциях.</span><span class="sxs-lookup"><span data-stu-id="85725-122">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="85725-123">См. также</span><span class="sxs-lookup"><span data-stu-id="85725-123">See Also</span></span>


[<span data-ttu-id="85725-124">Планирование архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85725-124">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

