---
title: 'Lync Server 2013: соглашения об уровне обслуживания'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445b7189d7f13f1b854bfb4bd921251c319f87ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="e162d-102">Соглашения об уровне обслуживания в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e162d-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e162d-103">_**Тема последнего изменения:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="e162d-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="e162d-104">Соглашение об уровне обслуживания — это документ, который определяет услуги, которые ваш клиент ожидает от вас.</span><span class="sxs-lookup"><span data-stu-id="e162d-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="e162d-105">Сложность и содержание этого документа зависят от того, являются ли клиенты внутренними (внутри вашей среды) или внешними.</span><span class="sxs-lookup"><span data-stu-id="e162d-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="e162d-106">Внешние клиенты</span><span class="sxs-lookup"><span data-stu-id="e162d-106">External Customers</span></span>

<span data-ttu-id="e162d-107">Если ваш клиент является внешним, соглашение об уровне обслуживания может быть частью юридического контракта с учетом финансовых стимулов и санкций для повышения производительности, которые выпадают на внутренние или внешние уровни обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e162d-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="e162d-108">Определение уровней обслуживания должно быть частью всего согласования контракта.</span><span class="sxs-lookup"><span data-stu-id="e162d-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="e162d-109">Как и в случае со всеми контрактами, важно, чтобы обе стороны понимали ожидания.</span><span class="sxs-lookup"><span data-stu-id="e162d-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="e162d-110">Эти ожидания определяются соглашением об уровне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e162d-110">The SLA defines these expectations.</span></span> <span data-ttu-id="e162d-111">Содержимое документа должно изменяться редко и только из-за переговоров с клиентом.</span><span class="sxs-lookup"><span data-stu-id="e162d-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="e162d-112">Внутренние пользователи</span><span class="sxs-lookup"><span data-stu-id="e162d-112">Internal Customers</span></span>

<span data-ttu-id="e162d-113">Если клиент является внутренним, вы по-прежнему можете определять службы, которые должны быть в Teams и в информационных системах.</span><span class="sxs-lookup"><span data-stu-id="e162d-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="e162d-114">Соглашение об уровне обслуживания может быть создано сотрудниками операций и служить набором целей для обеспечения доступности ИТ-услуг в Организации.</span><span class="sxs-lookup"><span data-stu-id="e162d-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="e162d-115">Кроме того, уровни производительности можно настроить с помощью управления и использования в качестве тестовых показателей при оценке производительности сотрудников.</span><span class="sxs-lookup"><span data-stu-id="e162d-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="e162d-116">Типичные условия</span><span class="sxs-lookup"><span data-stu-id="e162d-116">Typical Criteria</span></span>

<span data-ttu-id="e162d-117">Соглашения об уровне обслуживания включают разделы, которые определяют условия минимального уровня доступности, поддержки и емкости.</span><span class="sxs-lookup"><span data-stu-id="e162d-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="e162d-118">**Доступность**   . Определите часы и операционные системы, в которых будут доступны сайты и другие службы Lync.</span><span class="sxs-lookup"><span data-stu-id="e162d-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="e162d-119">Должно быть определено любое плановое обслуживание, которое влияет на доступность служб.</span><span class="sxs-lookup"><span data-stu-id="e162d-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="e162d-120">Определите внешние факторы, влияющие на обслуживание, например потерю подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="e162d-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="e162d-121">**Поддержка**   . определяет часы, в которых будет доступна поддержка системы.</span><span class="sxs-lookup"><span data-stu-id="e162d-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="e162d-122">Укажите методы для пользователей, которые должны обратиться в службу поддержки, как они группируются, а также указывают время, в течение которого нужно ответить, и устранить инцидент.</span><span class="sxs-lookup"><span data-stu-id="e162d-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="e162d-123">Определение частоты и контента отзыва для клиента.</span><span class="sxs-lookup"><span data-stu-id="e162d-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="e162d-124">**Емкость**   определяет максимально допустимый размер сайтов Lync и шаги, которые необходимо выполнить при превышении ограничения.</span><span class="sxs-lookup"><span data-stu-id="e162d-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="e162d-125">Определение максимального разрешенного времени для выполнения стандартных задач, таких как время получения документа из библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="e162d-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="e162d-126">Определите максимальное количество пользователей на пул Lync и пригласите его к процессу, чтобы увеличить его емкость, если их добавить больше пользователей.</span><span class="sxs-lookup"><span data-stu-id="e162d-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

