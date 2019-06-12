---
title: 'Lync Server 2013: поддержка больших собраний'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for large meetings
ms:assetid: 8f0446d5-1ed9-4ea0-bb97-6c062a98a1eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205090(v=OCS.15)
ms:contentKeyID: 48184820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c98166b42f48e328809960279b9934b87670101b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="d5bda-102">Поддержка больших собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5bda-102">Support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5bda-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d5bda-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d5bda-104">Lync Server 2013 может поддерживать собрания с участием до 1000 участников, использующих голосовые и видеоконференции (A/V), в том числе предоставлять общий доступ к презентациям PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d5bda-104">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="d5bda-105">Для этого необходимо настроить поддержку больших собраний в выделенном пуле и управлять им таким способом, чтобы одновременно могло проводиться только одно большое собрание.</span><span class="sxs-lookup"><span data-stu-id="d5bda-105">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="d5bda-106">В этом разделе рассказывается о том, как поддерживать большое количество собраний с помощью выделенного пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5bda-106">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="d5bda-107">Она описывает особенности масштабируемости и требования к реализации для выделенного пула, включая топологию, оборудование, программное обеспечение и требования к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d5bda-107">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="d5bda-108">Кроме того, он предоставляет набор рекомендаций для поддержки крупных собраний, краткий обзор методов тестирования и результатов тестирования масштабируемости сервера, проводимого командой разработчиков Lync Server, и ответы на часто задаваемые вопросы о поддержке. для крупных собраний.</span><span class="sxs-lookup"><span data-stu-id="d5bda-108">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d5bda-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="d5bda-109">In This Section</span></span>

  - [<span data-ttu-id="d5bda-110">Общие сведения о масштабируемости конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5bda-110">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="d5bda-111">Поддержка крупных собраний с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5bda-111">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="d5bda-112">Дополнительные вопросы и ответы о поддержке собраний для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5bda-112">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

