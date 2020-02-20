---
title: Lync Server 2013 поддерживаемые варианты связывания пула и рекомендации
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c73108f832aaa10b0539aa6fd56b4f4a7bb0cbb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="4b9bf-102">Поддерживаемые варианты связывания пулов и рекомендации для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b9bf-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b9bf-103">_**Последнее изменение темы:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="4b9bf-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="4b9bf-104">Не существует ограничений на расстояние между двумя центрами обработки данных, которые включают в себя межсерверные пулы, связанные друг с другом.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-104">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other.</span></span> <span data-ttu-id="4b9bf-105">Мы рекомендуем использовать два центра обработки данных в одном регионе мира с высокоскоростными связями между ними.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-105">We recommend that you use two data centers in the same world region, with high-speed links between them.</span></span> <span data-ttu-id="4b9bf-106">Лучше всего, если два центра обработки данных достаточно отделены друг от друга, чтобы избежать одиночной аварии одновременно.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-106">It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="4b9bf-107">Наличие двух центров обработки данных в регионах мира возможно, но это может привести к более высокому снижению потери данных из-за задержки в репликации данных.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="4b9bf-108">При планировании того, какие пулы необходимо связать, необходимо учитывать, что поддерживаются только следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4b9bf-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="4b9bf-109">Пулы корпоративных выпусков можно связать только с другими пулами Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-109">Enterprise Edition pools can be paired only with other Enterprise Edition pools.</span></span> <span data-ttu-id="4b9bf-110">Аналогично, пулы Standard Edition можно связать только с другими пулами Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-110">Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="4b9bf-111">Физические пулы можно связать только с другими физическими пулами.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-111">Physical pools can be paired only with other physical pools.</span></span> <span data-ttu-id="4b9bf-112">Аналогично виртуальные пулы можно связать только с другими виртуальными пулами.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-112">Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="4b9bf-113">Пулы, Объединенные вместе, должны работать под управлением одной и той же операционной системы.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="4b9bf-114">Ни построитель топологий, ни проверка топологии не будут иметь возможность связывания двух пулов без соблюдения этих рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="4b9bf-115">Например, построитель топологий позволяет связать пул Enterprise Edition с пулом Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="4b9bf-116">Однако эти типы связей не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="4b9bf-117">Каждый пул в каждой из них должен иметь емкость для обслуживания всех пользователей из обоих пулов в случае аварии.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="4b9bf-118">Если вы объединяете пулы Enterprise Edition, вы также можете реализовать высокую доступность на внутренних серверах, но для пар пулов Standard Edition доступны только меры аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

