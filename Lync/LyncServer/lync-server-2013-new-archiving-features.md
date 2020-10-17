---
title: 'Lync Server 2013: новые функции архивации'
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
ms.openlocfilehash: 3150d56bbd4935d6139c8584fcd69d721056317e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505386"
---
# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="5404a-102">Новые функции архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5404a-102">New Archiving features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5404a-103">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="5404a-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="5404a-104">Архивация в Lync Server 2013 позволяет архивировать следующие типы контента:</span><span class="sxs-lookup"><span data-stu-id="5404a-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="5404a-105">одноранговый обмен мгновенными сообщениями;</span><span class="sxs-lookup"><span data-stu-id="5404a-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="5404a-106">конференции (собрания), которые являются обменом мгновенными сообщениями с несколькими участниками;</span><span class="sxs-lookup"><span data-stu-id="5404a-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="5404a-107">контент конференций, включая отправленный контент (например, раздаточные материалы) и контент, связанный с событиями (например, присоединение, отключение, отправка общедоступных файлов и изменения видимости).</span><span class="sxs-lookup"><span data-stu-id="5404a-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="5404a-108">Кроме того, архивация в Lync Server 2013 предоставляет новые функции, повышающие эффективность развертывания и эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="5404a-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="5404a-109">Сюда входят следующие функции.</span><span class="sxs-lookup"><span data-stu-id="5404a-109">These new features consist of:</span></span>

  - <span data-ttu-id="5404a-110">Совместное размещение **архивации на серверах переднего плана.**     Lync Server 2013 не имеет отдельной роли сервера архивации.</span><span class="sxs-lookup"><span data-stu-id="5404a-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="5404a-111">Архивирование является дополнительной функцией, которая доступна на всех серверах переднего плана в развертывании Enterprise Edition и на серверах Standard Edition, которые можно реализовать в конфигурации для пула или сайта.</span><span class="sxs-lookup"><span data-stu-id="5404a-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="5404a-112">**Интеграция с Microsoft Exchange.**     При развертывании архивации можно интегрировать хранилище данных для архивации с имеющимся хранилищем Exchange 2013 для всех пользователей, размещенных в Exchange 2013 и почтовых ящиков, которые помещаются на In-Place хранения, поэтому нет необходимости развертывать отдельные базы данных SQL Server для архивации данных Lync.</span><span class="sxs-lookup"><span data-stu-id="5404a-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="5404a-113">Если у вас нет развертывания Exchange 2013 или если вы не хотите интегрироваться с ним, или если у вас есть пользователи Lync 2013, не размещенные в Exchange 2013 с их почтовыми ящиками, поIn-Place хранения, можно развернуть отдельные базы данных архивации с помощью SQL Server для хранения архивных данных из коммуникаций Lync.</span><span class="sxs-lookup"><span data-stu-id="5404a-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="5404a-114">Можно использовать как интеграцию Microsoft Exchange, так и базы данных архивации Lync Server 2013, если вы хотите использовать интеграцию Microsoft Exchange для некоторых, но не всех пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="5404a-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="5404a-115">Сведения об удержании In-Place содержатся в разделе "удержание на месте" [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500) .</span><span class="sxs-lookup"><span data-stu-id="5404a-115">For details about In-Place Hold, see “In-Place Hold” at [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="5404a-116">**Зеркальное отображение хранилища SQL.**     При развертывании архивации можно включить зеркальное отображение базы данных SQL Server для базы данных архивации.</span><span class="sxs-lookup"><span data-stu-id="5404a-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="5404a-117">**Архивирование досок и опросов.**     Архивный контент конференции теперь включает в себя доски и опросы, которые совместно используются во время собрания.</span><span class="sxs-lookup"><span data-stu-id="5404a-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="5404a-118">Следующие типы контента не архивируются:</span><span class="sxs-lookup"><span data-stu-id="5404a-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="5404a-119">одноранговые передачи файлов;</span><span class="sxs-lookup"><span data-stu-id="5404a-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="5404a-120">аудио- и видеоданные для однорангового обмена мгновенными сообщениями и конференций;</span><span class="sxs-lookup"><span data-stu-id="5404a-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="5404a-121">общий доступ к приложениям в одноранговом обмене мгновенными сообщениями и конференциях.</span><span class="sxs-lookup"><span data-stu-id="5404a-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5404a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5404a-122">See Also</span></span>


[<span data-ttu-id="5404a-123">Планирование архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5404a-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

