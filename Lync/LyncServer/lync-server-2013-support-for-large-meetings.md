---
title: Lync Server 2013 — поддержка больших собраний
description: 'Lync Server 2013: поддержка больших собраний.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for large meetings
ms:assetid: 8f0446d5-1ed9-4ea0-bb97-6c062a98a1eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205090(v=OCS.15)
ms:contentKeyID: 48184820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb37cbfb95e36b9a07604eb4fbbc548e4d7ce9a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546265"
---
# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="c8a3c-103">Поддержка больших собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8a3c-103">Support for large meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8a3c-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c8a3c-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c8a3c-105">Lync Server 2013 может поддерживать собрания с участием до 1000 участников, использующих аудио-и видеоконференции (A/V), включая совместное использование презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c8a3c-105">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="c8a3c-106">Такая поддержка требует выделенный пул, настроенный для поддержки больших собраний и управляемый таким способом, чтобы гарантировать размещение только одного большого собрания в каждый момент времени.</span><span class="sxs-lookup"><span data-stu-id="c8a3c-106">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="c8a3c-107">В этом разделе описывается, как поддерживать большое количество собраний с помощью выделенного пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8a3c-107">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="c8a3c-108">Рассматриваются рекомендации по масштабированию и требования к реализации для выделенного пула, включая требования к топологии, оборудованию, программному обеспечению и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c8a3c-108">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="c8a3c-109">Кроме того, он предоставляет набор рекомендаций для поддержки больших собраний, краткий обзор методов тестирования и результатов тестирования масштабируемости серверов, проводимых группой разработчиков Lync Server, а также ответы на часто задаваемые вопросы о поддержке больших собраний.</span><span class="sxs-lookup"><span data-stu-id="c8a3c-109">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c8a3c-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="c8a3c-110">In This Section</span></span>

  - [<span data-ttu-id="c8a3c-111">Обзор масштабируемости конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8a3c-111">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="c8a3c-112">Поддержка больших собраний с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8a3c-112">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="c8a3c-113">Вопросы и ответы по поддержке больших собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8a3c-113">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

