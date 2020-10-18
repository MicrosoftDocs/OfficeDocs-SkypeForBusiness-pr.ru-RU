---
title: 'Lync Server 2013: соглашения об уровне обслуживания'
description: 'Lync Server 2013: соглашения об уровне обслуживания.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 817aa8e092d9d368dfd8cb920958553ee32e8600
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576475"
---
# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="9dd55-103">Соглашения об уровне обслуживания в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dd55-103">Service level agreements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dd55-104">_**Последнее изменение темы:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="9dd55-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="9dd55-105">Соглашение об уровне обслуживания — это документ, в котором определяются службы, которые клиент ожидает от вас.</span><span class="sxs-lookup"><span data-stu-id="9dd55-105">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="9dd55-106">Сложность и содержание этого документа зависят от того, являются ли клиенты внутренними (внутри вашей среды) или внешними.</span><span class="sxs-lookup"><span data-stu-id="9dd55-106">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="9dd55-107">Внешние клиенты</span><span class="sxs-lookup"><span data-stu-id="9dd55-107">External Customers</span></span>

<span data-ttu-id="9dd55-108">Если ваш клиент является внешним, соглашение об уровне обслуживания может быть составным юридическим соглашением с финансовыми поощрениями и штрафами за производительность, которая должна быть внутри или снаружи определенных уровней обслуживания.</span><span class="sxs-lookup"><span data-stu-id="9dd55-108">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="9dd55-109">Определение этих уровней службы должно быть частью общего согласования контрактов.</span><span class="sxs-lookup"><span data-stu-id="9dd55-109">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="9dd55-110">Как и во всех контрактах, важно, чтобы обе стороны понимали ожидания.</span><span class="sxs-lookup"><span data-stu-id="9dd55-110">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="9dd55-111">Соглашение об уровне обслуживания определяет эти ожидания.</span><span class="sxs-lookup"><span data-stu-id="9dd55-111">The SLA defines these expectations.</span></span> <span data-ttu-id="9dd55-112">Содержимое документа должно изменяться нечасто и только из-за согласования с клиентом.</span><span class="sxs-lookup"><span data-stu-id="9dd55-112">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="9dd55-113">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="9dd55-113">Internal Customers</span></span>

<span data-ttu-id="9dd55-114">Если ваш клиент является внутренним, вы по-прежнему можете определить службы, которые должны использоваться в Teams и ИТ-системах.</span><span class="sxs-lookup"><span data-stu-id="9dd55-114">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="9dd55-115">Соглашение об уровне обслуживания может быть создано сотрудником Operations и служить набором целей для доступности ИТ служб в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9dd55-115">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="9dd55-116">Или уровни производительности могут задаваться по управлению и использоваться в качестве тестовых показателей при оценке производительности сотрудников.</span><span class="sxs-lookup"><span data-stu-id="9dd55-116">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="9dd55-117">Типичные критерии</span><span class="sxs-lookup"><span data-stu-id="9dd55-117">Typical Criteria</span></span>

<span data-ttu-id="9dd55-118">SLA включает разделы, определяющие условия минимального уровня доступности, поддержки и емкости.</span><span class="sxs-lookup"><span data-stu-id="9dd55-118">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="9dd55-119">**Доступность**     Определите часы и операционные системы, на которых будут доступны сайты и другие службы Lync.</span><span class="sxs-lookup"><span data-stu-id="9dd55-119">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="9dd55-120">Должно быть определено любое плановое обслуживание, которое влияет на доступность служб.</span><span class="sxs-lookup"><span data-stu-id="9dd55-120">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="9dd55-121">Определите внешние факторы, влияющие на работу службы, например потерю подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="9dd55-121">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="9dd55-122">**Поддержка**     Определите часы, когда будет доступна поддержка системы.</span><span class="sxs-lookup"><span data-stu-id="9dd55-122">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="9dd55-123">Укажите методы для клиентов, которые будут обращаться к сотрудникам службы поддержки, как инциденты группируются, а целевое время — для устранения инцидента.</span><span class="sxs-lookup"><span data-stu-id="9dd55-123">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="9dd55-124">Определите частоту и контент обратной связи с клиентом.</span><span class="sxs-lookup"><span data-stu-id="9dd55-124">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="9dd55-125">**Емкость**     Определите максимальный включенный размер сайтов Lync и действия, которые необходимо выполнить при превышении ограничения.</span><span class="sxs-lookup"><span data-stu-id="9dd55-125">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="9dd55-126">Определите максимальное разрешенное время для выполнения стандартных задач, например время извлечения документа из библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="9dd55-126">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="9dd55-127">Определите максимальное число пользователей на пул Lync и пригласитесь на процесс увеличения емкости при добавлении новых пользователей.</span><span class="sxs-lookup"><span data-stu-id="9dd55-127">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

