---
title: 'Lync Server 2013: предотвращение сеансов для служб'
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
ms.openlocfilehash: 6b1737bddb680f597b8009c59dff9e772a7719df
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="66df9-102">Предотвращение сеансов для служб в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66df9-102">Prevent sessions for services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66df9-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="66df9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="66df9-104">Вы можете использовать панель управления Lync Server, чтобы запретить новые сеансы для всех служб Lync Server 2013, работающих на определенном компьютере, или запретить новые сеансы для конкретной службы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66df9-104">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="66df9-105">Запрет новых сеансов для всех служб Lync Server на компьютере</span><span class="sxs-lookup"><span data-stu-id="66df9-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="66df9-106">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66df9-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="66df9-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66df9-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="66df9-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="66df9-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="66df9-109">В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).</span><span class="sxs-lookup"><span data-stu-id="66df9-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="66df9-110">На странице **Состояние** выполните сортировку или поиск по списку, чтобы найти компьютер, на котором выполняются службы, для которых нужно запретить новые сеансы, а затем щелкните ее.</span><span class="sxs-lookup"><span data-stu-id="66df9-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="66df9-111">Щелкните элемент **Action** (Действие).</span><span class="sxs-lookup"><span data-stu-id="66df9-111">Click **Action**.</span></span>

6.  <span data-ttu-id="66df9-112">Щелкните **Запретить новые сеансы для всех служб**.</span><span class="sxs-lookup"><span data-stu-id="66df9-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="66df9-113">Запрет новых сеансов для определенной службы</span><span class="sxs-lookup"><span data-stu-id="66df9-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="66df9-114">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66df9-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="66df9-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66df9-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="66df9-116">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="66df9-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="66df9-117">В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).</span><span class="sxs-lookup"><span data-stu-id="66df9-117">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="66df9-118">На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="66df9-118">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="66df9-119">Нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="66df9-119">Click **Properties**.</span></span>

6.  <span data-ttu-id="66df9-120">Отсортируйте список служб, если это необходимо, и щелкните службу, для которой вы хотите запретить новые сеансы.</span><span class="sxs-lookup"><span data-stu-id="66df9-120">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="66df9-121">Щелкните **Действие**.</span><span class="sxs-lookup"><span data-stu-id="66df9-121">Click **Action**.</span></span>

8.  <span data-ttu-id="66df9-122">Щелкните **Запретить новые сеансы для службы**.</span><span class="sxs-lookup"><span data-stu-id="66df9-122">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="66df9-123">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="66df9-123">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="66df9-124">См. также</span><span class="sxs-lookup"><span data-stu-id="66df9-124">See Also</span></span>


[<span data-ttu-id="66df9-125">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66df9-125">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

