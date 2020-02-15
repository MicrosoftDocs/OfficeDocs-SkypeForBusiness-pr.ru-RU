---
title: 'Lync Server 2013: соглашения об уровне обслуживания'
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
ms.openlocfilehash: e96edf9fe2fefb54e608ee6840cfb2717c92d136
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="25593-102">Соглашения об уровне обслуживания в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25593-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25593-103">_**Последнее изменение темы:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="25593-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="25593-104">Соглашение об уровне обслуживания — это документ, в котором определяются службы, которые клиент ожидает от вас.</span><span class="sxs-lookup"><span data-stu-id="25593-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="25593-105">Сложность и содержание этого документа зависят от того, являются ли клиенты внутренними (внутри вашей среды) или внешними.</span><span class="sxs-lookup"><span data-stu-id="25593-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="25593-106">Внешние клиенты</span><span class="sxs-lookup"><span data-stu-id="25593-106">External Customers</span></span>

<span data-ttu-id="25593-107">Если ваш клиент является внешним, соглашение об уровне обслуживания может быть составным юридическим соглашением с финансовыми поощрениями и штрафами за производительность, которая должна быть внутри или снаружи определенных уровней обслуживания.</span><span class="sxs-lookup"><span data-stu-id="25593-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="25593-108">Определение этих уровней службы должно быть частью общего согласования контрактов.</span><span class="sxs-lookup"><span data-stu-id="25593-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="25593-109">Как и во всех контрактах, важно, чтобы обе стороны понимали ожидания.</span><span class="sxs-lookup"><span data-stu-id="25593-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="25593-110">Соглашение об уровне обслуживания определяет эти ожидания.</span><span class="sxs-lookup"><span data-stu-id="25593-110">The SLA defines these expectations.</span></span> <span data-ttu-id="25593-111">Содержимое документа должно изменяться нечасто и только из-за согласования с клиентом.</span><span class="sxs-lookup"><span data-stu-id="25593-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="25593-112">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="25593-112">Internal Customers</span></span>

<span data-ttu-id="25593-113">Если ваш клиент является внутренним, вы по-прежнему можете определить службы, которые должны использоваться в Teams и ИТ-системах.</span><span class="sxs-lookup"><span data-stu-id="25593-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="25593-114">Соглашение об уровне обслуживания может быть создано сотрудником Operations и служить набором целей для доступности ИТ служб в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="25593-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="25593-115">Или уровни производительности могут задаваться по управлению и использоваться в качестве тестовых показателей при оценке производительности сотрудников.</span><span class="sxs-lookup"><span data-stu-id="25593-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="25593-116">Типичные критерии</span><span class="sxs-lookup"><span data-stu-id="25593-116">Typical Criteria</span></span>

<span data-ttu-id="25593-117">SLA включает разделы, определяющие условия минимального уровня доступности, поддержки и емкости.</span><span class="sxs-lookup"><span data-stu-id="25593-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="25593-118">**Доступность**   определите часы и операционные системы, на которых будут доступны сайты и другие службы Lync.</span><span class="sxs-lookup"><span data-stu-id="25593-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="25593-119">Должно быть определено любое плановое обслуживание, которое влияет на доступность служб.</span><span class="sxs-lookup"><span data-stu-id="25593-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="25593-120">Определите внешние факторы, влияющие на работу службы, например потерю подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="25593-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="25593-121">**Поддерживает**   определение часов, когда будет доступна поддержка системы.</span><span class="sxs-lookup"><span data-stu-id="25593-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="25593-122">Укажите методы для клиентов, которые будут обращаться к сотрудникам службы поддержки, как инциденты группируются, а целевое время — для устранения инцидента.</span><span class="sxs-lookup"><span data-stu-id="25593-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="25593-123">Определите частоту и контент обратной связи с клиентом.</span><span class="sxs-lookup"><span data-stu-id="25593-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="25593-124">**Capacity**   определяет максимальный допустимый размер сайтов Lync и действия, которые необходимо выполнить при превышении ограничения.</span><span class="sxs-lookup"><span data-stu-id="25593-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="25593-125">Определите максимальное разрешенное время для выполнения стандартных задач, например время извлечения документа из библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="25593-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="25593-126">Определите максимальное число пользователей на пул Lync и пригласитесь на процесс увеличения емкости при добавлении новых пользователей.</span><span class="sxs-lookup"><span data-stu-id="25593-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

