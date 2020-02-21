---
title: Пользовательская модель конференц-связи Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1049ff2d11d76e78661636972c812cc6c9c731f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="e3667-102">Пользовательская модель конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3667-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3667-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e3667-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e3667-104">Важной частью пользовательской модели конференц-связи Lync Server является размер собрания.</span><span class="sxs-lookup"><span data-stu-id="e3667-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="e3667-105">После сбора данных из нескольких точек (как описано в предыдущем разделе) мы определили следующее:</span><span class="sxs-lookup"><span data-stu-id="e3667-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="e3667-106">Большинство собраний являются небольшими собраниями для совместной работы со средним числом участников от четырех до шести.</span><span class="sxs-lookup"><span data-stu-id="e3667-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="e3667-107">Примерно 80 процентов собраний имеет меньше 20 участников.</span><span class="sxs-lookup"><span data-stu-id="e3667-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="e3667-108">99,98 процентов собраний имеет меньше 100 участников.</span><span class="sxs-lookup"><span data-stu-id="e3667-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="e3667-109">Кроме размера собрания, модель пользователя конференц-связи учитывает и другие факторы, например:</span><span class="sxs-lookup"><span data-stu-id="e3667-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="e3667-110">**Количество одновременных собраний**   . сколько пользователей должны одновременно находиться в собраниях?</span><span class="sxs-lookup"><span data-stu-id="e3667-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="e3667-111">**Типы мультимедиа,** которые будут доступны пользователям в собраниях и которые должны использоваться пользователями?   </span><span class="sxs-lookup"><span data-stu-id="e3667-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="e3667-112">**Типы пользователей —**   это внутренние пользователи, удаленные пользователи, Федеративные пользователи и анонимные пользователи?</span><span class="sxs-lookup"><span data-stu-id="e3667-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="e3667-113">**Время, затраченное на собрание**   , сколько времени займет все пользователи собрания для присоединения к собранию?</span><span class="sxs-lookup"><span data-stu-id="e3667-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="e3667-114">Подробные сведения о пользовательской модели можно найти [в статье User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="e3667-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="e3667-115">Для определение числа собраний и пользователей в целях тестирования выполнялись следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e3667-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="e3667-116">Бралось полное число пользователей в организации (например, 80 000 пользователей) и умножалось на долю одновременно работающих пользователей собрания (например, 5% всех пользователей), чтобы определить полное число пользователей, которые, как предполагается, будут участвовать в собраниях одновременно (в данном примере 4 000 пользователей).</span><span class="sxs-lookup"><span data-stu-id="e3667-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="e3667-117">Разделить общее количество пользователей на число серверов Lync Server 2013, серверов переднего плана в развертывании (например, 8 серверов), чтобы определить предполагаемое количество участников собрания на сервере переднего плана (в данном примере — 500 пользователей на сервер переднего плана).</span><span class="sxs-lookup"><span data-stu-id="e3667-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="e3667-118">Разделить количество пользователей на сервер переднего плана по среднему размеру собрания (например, 4 пользователям), чтобы определить предполагаемое среднее количество собраний на сервер переднего плана (в данном примере — 125 собраний на сервер переднего плана).</span><span class="sxs-lookup"><span data-stu-id="e3667-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="e3667-119">Чтобы получить по каждой нагрузке мультимедиа на каждом сервере переднего плана, мы оценили набор носителей.</span><span class="sxs-lookup"><span data-stu-id="e3667-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="e3667-120">Например, при условии, что в 75% для собраний требуется не только поддержка звука, но и 50% этих собраний, требуется общий доступ к приложениям, среднее значение 47 для собраний и 188 пользователей подключаются параллельно к каждому серверу переднего плана для общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="e3667-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="e3667-121">Тестировались различные размеры собраний (на основе нашей модели пользователя, включающей 250 пользователей в общем пуле) для проверки масштабируемости. сервера.</span><span class="sxs-lookup"><span data-stu-id="e3667-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

