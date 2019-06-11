---
title: 'Lync Server 2013: предотвращение сеансов для служб'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8d22b74168c784d6a5e19c3ffc32b9e275040b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="660e6-102">Предотвращение сеансов для служб в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="660e6-102">Prevent sessions for services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="660e6-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="660e6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="660e6-104">Панель управления Lync Server можно использовать для предотвращения новых сеансов для всех служб Lync Server 2013, запущенных на определенном компьютере, или для предотвращения новых сеансов для конкретной службы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="660e6-104">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="660e6-105">Запрещение новых сеансов для всех служб Lync Server на компьютере</span><span class="sxs-lookup"><span data-stu-id="660e6-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="660e6-106">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="660e6-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="660e6-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="660e6-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="660e6-108">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="660e6-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="660e6-109">На панели навигации слева щелкните топология \*\*\*\* и выберите **состояние**.</span><span class="sxs-lookup"><span data-stu-id="660e6-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="660e6-110">На странице " **состояние** " выполните сортировку или поиск по списку, если это необходимо, чтобы найти компьютер, на котором запущены службы, для которых вы хотите запретить новые сеансы, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="660e6-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="660e6-111">Нажмите кнопку **действие**.</span><span class="sxs-lookup"><span data-stu-id="660e6-111">Click **Action**.</span></span>

6.  <span data-ttu-id="660e6-112">Нажмите кнопку **запретить новые сеансы для всех служб**.</span><span class="sxs-lookup"><span data-stu-id="660e6-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="660e6-113">Запрещение новых сеансов для конкретной службы</span><span class="sxs-lookup"><span data-stu-id="660e6-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="660e6-114">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="660e6-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="660e6-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="660e6-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="660e6-116">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="660e6-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="660e6-117">На панели навигации слева щелкните топология \*\*\*\* и выберите **состояние**.</span><span class="sxs-lookup"><span data-stu-id="660e6-117">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="660e6-118">На странице " **состояние** " выполните сортировку и поиск по списку, если это необходимо, чтобы найти компьютер, на котором запущена служба, которую вы хотите запустить или остановить, а затем щелкните ее.</span><span class="sxs-lookup"><span data-stu-id="660e6-118">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="660e6-119">Нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="660e6-119">Click **Properties**.</span></span>

6.  <span data-ttu-id="660e6-120">При необходимости отсортируйте список служб и выберите службу, для которой вы хотите запретить новые сеансы.</span><span class="sxs-lookup"><span data-stu-id="660e6-120">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="660e6-121">Нажмите кнопку **действие**.</span><span class="sxs-lookup"><span data-stu-id="660e6-121">Click **Action**.</span></span>

8.  <span data-ttu-id="660e6-122">Выберите команду **запретить новые сеансы для службы**.</span><span class="sxs-lookup"><span data-stu-id="660e6-122">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="660e6-123">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="660e6-123">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="660e6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="660e6-124">See Also</span></span>


[<span data-ttu-id="660e6-125">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="660e6-125">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

