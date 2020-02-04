---
title: 'Lync Server 2013: отчеты о диагностике звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Reports
ms:assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615013(v=OCS.15)
ms:contentKeyID: 48184794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41100a6cc41c38b3d32870d530f99d8c919a2e83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="1289d-102">Диагностические отчеты о звонках в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1289d-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1289d-103">_**Тема последнего изменения:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="1289d-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="1289d-104">Диагностические отчеты по вызовам предоставляют сводные сведения и диагностические данные для неудачных одноранговых сеансов связи и сеансов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="1289d-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1289d-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="1289d-105">In This Section</span></span>

  - <span data-ttu-id="1289d-106">[Сводный отчет о вызовах в Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   — Общая сводка сбоев одноранговых сеансов и сеансов конференций.</span><span class="sxs-lookup"><span data-stu-id="1289d-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="1289d-107">Одноранговые сеансы – это сеансы, в которых только два участника.</span><span class="sxs-lookup"><span data-stu-id="1289d-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="1289d-108">Сеансы конференц-связи включают не менее трех участников.</span><span class="sxs-lookup"><span data-stu-id="1289d-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="1289d-109">[Диагностический отчет о действиях одноранговой сети в Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   обеспечивает общее представление сбоев одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="1289d-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="1289d-110">В одноранговых сеансах имеется только два участника.</span><span class="sxs-lookup"><span data-stu-id="1289d-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="1289d-111">[Отчет о диагностике конференций в Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   предоставляет общее представление о неудачных сеансах и представлениях тенденций для всех модальных конференций.</span><span class="sxs-lookup"><span data-stu-id="1289d-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="1289d-112">Сеансы конференц-связи включают не менее трех участников.</span><span class="sxs-lookup"><span data-stu-id="1289d-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="1289d-113">[Отчет об ошибках Top в Lync Server 2013](lync-server-2013-top-failures-report.md)   предоставляет список наиболее часто используемых сбоев и тенденций их тенденции с течением времени.</span><span class="sxs-lookup"><span data-stu-id="1289d-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="1289d-114">[Отчет о распределении отказов в Lync Server 2013](lync-server-2013-failure-distribution-report.md)   обеспечивает анализ неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="1289d-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="1289d-115">[Отчет о списке отказов в Lync Server 2013](lync-server-2013-failure-list-report.md)   предоставляет подробные сведения об отдельных участниках, вовлеченных в неудачную конференцию.</span><span class="sxs-lookup"><span data-stu-id="1289d-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="1289d-116">[Диагностический отчет в Lync Server 2013](lync-server-2013-diagnostic-report.md)   содержит сведения о диагностике и устранении неполадок (в том числе коды ответов SIP и диагностические заголовки и идентификаторы) для сеансов с ошибками.</span><span class="sxs-lookup"><span data-stu-id="1289d-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

