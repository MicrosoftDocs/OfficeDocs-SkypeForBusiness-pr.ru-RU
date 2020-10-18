---
title: 'Lync Server 2013: предотвращение сеансов для служб'
description: 'Lync Server 2013: предотвращение сеансов для служб.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 846a9da5330c3e64f61c27dfadd883f0c43a0ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579815"
---
# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="03c3d-103">Предотвращение сеансов для служб в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03c3d-103">Prevent sessions for services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03c3d-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="03c3d-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="03c3d-105">Вы можете использовать панель управления Lync Server, чтобы запретить новые сеансы для всех служб Lync Server 2013, работающих на определенном компьютере, или запретить новые сеансы для конкретной службы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03c3d-105">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="03c3d-106">Запрет новых сеансов для всех служб Lync Server на компьютере</span><span class="sxs-lookup"><span data-stu-id="03c3d-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="03c3d-107">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03c3d-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="03c3d-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="03c3d-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="03c3d-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="03c3d-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="03c3d-110">В левой панели навигации щелкните **Топология**, а затем щелкните **Состояние**.</span><span class="sxs-lookup"><span data-stu-id="03c3d-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="03c3d-111">На странице **Состояние** выполните сортировку или поиск по списку, чтобы найти компьютер, на котором выполняются службы, для которых нужно запретить новые сеансы, а затем щелкните ее.</span><span class="sxs-lookup"><span data-stu-id="03c3d-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="03c3d-112">Щелкните **Действие**.</span><span class="sxs-lookup"><span data-stu-id="03c3d-112">Click **Action**.</span></span>

6.  <span data-ttu-id="03c3d-113">Щелкните **Запретить новые сеансы для всех служб**.</span><span class="sxs-lookup"><span data-stu-id="03c3d-113">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="03c3d-114">Запрет новых сеансов для определенной службы</span><span class="sxs-lookup"><span data-stu-id="03c3d-114">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="03c3d-115">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03c3d-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="03c3d-116">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="03c3d-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="03c3d-117">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="03c3d-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="03c3d-118">В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).</span><span class="sxs-lookup"><span data-stu-id="03c3d-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="03c3d-119">На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="03c3d-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="03c3d-120">Нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="03c3d-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="03c3d-121">Отсортируйте список служб, если это необходимо, и щелкните службу, для которой вы хотите запретить новые сеансы.</span><span class="sxs-lookup"><span data-stu-id="03c3d-121">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="03c3d-122">Щелкните **Действие**.</span><span class="sxs-lookup"><span data-stu-id="03c3d-122">Click **Action**.</span></span>

8.  <span data-ttu-id="03c3d-123">Щелкните **Запретить новые сеансы для службы**.</span><span class="sxs-lookup"><span data-stu-id="03c3d-123">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="03c3d-124">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="03c3d-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03c3d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="03c3d-125">See Also</span></span>


[<span data-ttu-id="03c3d-126">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03c3d-126">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

