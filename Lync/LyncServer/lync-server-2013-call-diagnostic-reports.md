---
title: 'Lync Server 2013: диагностические отчеты о вызовах'
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
ms.openlocfilehash: 2cd121aa0f93a6fca92293d926c89bf1527931cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="1826c-102">Диагностические отчеты по вызовам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1826c-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1826c-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="1826c-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="1826c-104">Диагностические отчеты по вызовам предоставляют сводные сведения и диагностические данные для неудачных одноранговых сеансов связи и сеансов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="1826c-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1826c-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="1826c-105">In This Section</span></span>

  - <span data-ttu-id="1826c-106">[Сводный отчет по диагностике звонков в Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   содержит общие сведения о неудачных одноранговых сеансах и сеансах конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="1826c-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="1826c-107">Одноранговые сеансы — это сеансы, в которых только два участника.</span><span class="sxs-lookup"><span data-stu-id="1826c-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="1826c-108">Сеансы конференц-связи включают не менее трех участников.</span><span class="sxs-lookup"><span data-stu-id="1826c-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="1826c-109">[Диагностический отчет по одноранговым действиям в Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   предоставляет общий вид тенденций неудачных одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="1826c-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="1826c-110">В одноранговых сеансах имеется только два участника.</span><span class="sxs-lookup"><span data-stu-id="1826c-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="1826c-111">[Диагностический отчет по конференциям в Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   предоставляет общее представление о неудачных сеансах и представлениях тенденций для каждой модальной Конференции.</span><span class="sxs-lookup"><span data-stu-id="1826c-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="1826c-112">Сеансы конференц-связи включают не менее трех участников.</span><span class="sxs-lookup"><span data-stu-id="1826c-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="1826c-113">[Отчет о самых частых сбоях в Lync Server 2013](lync-server-2013-top-failures-report.md)   предоставляет список наиболее частых сбоев и тенденций их тенденции с течением времени.</span><span class="sxs-lookup"><span data-stu-id="1826c-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="1826c-114">[Отчет о распределении сбоев в Lync Server 2013](lync-server-2013-failure-distribution-report.md)   предоставляет анализ неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="1826c-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="1826c-115">[Отчет по списку отказов в Lync Server 2013](lync-server-2013-failure-list-report.md)   предоставляет подробные сведения об отдельных участниках, участвующих в неудачной конференции.</span><span class="sxs-lookup"><span data-stu-id="1826c-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="1826c-116">[Диагностический отчет в Lync Server 2013](lync-server-2013-diagnostic-report.md)   содержит диагностические сведения и сведения об устранении неполадок (в том числе коды ответа SIP и диагностические заголовки и идентификаторы) для сеансов со сбоями.</span><span class="sxs-lookup"><span data-stu-id="1826c-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

