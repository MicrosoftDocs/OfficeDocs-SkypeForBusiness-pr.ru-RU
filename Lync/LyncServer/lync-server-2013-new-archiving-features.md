---
title: 'Lync Server 2013: новые функции архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d736e823892aa6d6edcc5ab90df900a5c6b7ac79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="b3d53-102">Новые функции архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3d53-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3d53-103">_**Тема последнего изменения:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="b3d53-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="b3d53-104">Архивация в Lync Server 2013 может архивировать данные следующих типов:</span><span class="sxs-lookup"><span data-stu-id="b3d53-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="b3d53-105">одноранговые мгновенные сообщения;</span><span class="sxs-lookup"><span data-stu-id="b3d53-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="b3d53-106">Конференции (собрания), которые являются мгновенными сообщениями с несколькими участниками</span><span class="sxs-lookup"><span data-stu-id="b3d53-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="b3d53-107">содержимое конференций, включая загруженное содержимого (например, раздаточные материалы), и связанное с событиями содержание (например, сведения о присоединении, выходе, загрузке, общем доступе и изменениях видимости);</span><span class="sxs-lookup"><span data-stu-id="b3d53-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="b3d53-108">Кроме того, архивация в Lync Server 2013 предоставляет новые функции, повышающие эффективность развертывания и операций.</span><span class="sxs-lookup"><span data-stu-id="b3d53-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="b3d53-109">Эти новые функции состоят из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="b3d53-109">These new features consist of:</span></span>

  - <span data-ttu-id="b3d53-110">**Размещение архивов на серверах переднего плана.**    В Lync Server 2013 отсутствует отдельная роль сервера архивации.</span><span class="sxs-lookup"><span data-stu-id="b3d53-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="b3d53-111">Архивация — это необязательная функция, доступная на всех серверах переднего плана в развертывании Enterprise Edition и на серверах Standard Edition, которые можно реализовать для пула или сайта.</span><span class="sxs-lookup"><span data-stu-id="b3d53-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="b3d53-112">**Интеграция с Microsoft Exchange.**    При развертывании архива вы можете интегрировать хранилище данных для архивации с существующим хранилищем Exchange 2013 для всех пользователей, размещенных на сервере Exchange 2013 и почтовых ящиков, которые помещаются на хранение на месте, поэтому вам не нужно развертывать отдельный сервер SQL Server. базы данных для архивации данных Lync.</span><span class="sxs-lookup"><span data-stu-id="b3d53-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="b3d53-113">Если у вас нет развертывания Exchange 2013 или вы предпочитаете не интегрироваться с ним, а если у вас есть пользователи Lync 2013, не размещенные в Exchange 2013 с почтовыми ящиками на месте, вы можете развернуть отдельные архивные базы данных с помощью SQL Server. стор архивированные данные из Lync Communications.</span><span class="sxs-lookup"><span data-stu-id="b3d53-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="b3d53-114">Базы данных Microsoft Exchange Integration и Lync Server 2013 можно использовать, если вы хотите использовать интеграцию с Microsoft Exchange для некоторых пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="b3d53-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="b3d53-115">Сведения об удержании на месте можно найти в разделе "хранение на месте" [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span><span class="sxs-lookup"><span data-stu-id="b3d53-115">For details about In-Place Hold, see “In-Place Hold” at [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="b3d53-116">**Зеркальное отображение хранилища SQL.**    При развертывании архивации можно включить зеркальное отображение базы данных SQL Server для базы данных архивации.</span><span class="sxs-lookup"><span data-stu-id="b3d53-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="b3d53-117">**Архивирование досок и опросов.**    Архивированное содержимое конференции теперь включает в себя доски и опросы, которые совместно используются во время собрания.</span><span class="sxs-lookup"><span data-stu-id="b3d53-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="b3d53-118">Не архивируются следующие типы контента:</span><span class="sxs-lookup"><span data-stu-id="b3d53-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="b3d53-119">одноранговые передачи файлов;</span><span class="sxs-lookup"><span data-stu-id="b3d53-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="b3d53-120">аудио/видео для одноранговых мгновенных сообщений и конференций;</span><span class="sxs-lookup"><span data-stu-id="b3d53-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="b3d53-121">Общий доступ к приложениям для обмена мгновенными сообщениями и конференц-связи в одноранговой сети</span><span class="sxs-lookup"><span data-stu-id="b3d53-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b3d53-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b3d53-122">See Also</span></span>


[<span data-ttu-id="b3d53-123">Планирование архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3d53-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

