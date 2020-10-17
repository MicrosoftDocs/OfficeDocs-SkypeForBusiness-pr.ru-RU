---
title: 'Lync Server 2013: запуск или остановка служб Lync Server'
description: 'Lync Server 2013: запуск или остановка служб Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d6e6520cbf6fda38676beab984c2d006061b019
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541865"
---
# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="20547-103">Запуск и остановка служб Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20547-103">Start or stop Lync Server 2013 services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20547-104">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="20547-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="20547-105">Можно использовать панель управления Lync Server для запуска или остановки всех служб Lync Server 2013, работающих на определенном компьютере или для запуска или остановки определенной службы.</span><span class="sxs-lookup"><span data-stu-id="20547-105">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="20547-106">Запуск или остановка всех служб Lync Server на компьютере</span><span class="sxs-lookup"><span data-stu-id="20547-106">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="20547-107">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20547-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="20547-108">Вы можете определить, назначена ли роль CsServerAdministrator или CsAdministrator RBAC, выполнив команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="20547-108">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="20547-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20547-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="20547-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="20547-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="20547-111">В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).</span><span class="sxs-lookup"><span data-stu-id="20547-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="20547-112">На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="20547-112">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="20547-113">Щелкните элемент **Action** (Действие).</span><span class="sxs-lookup"><span data-stu-id="20547-113">Click **Action**.</span></span>

6.  <span data-ttu-id="20547-114">Щелкните **Start All services** (Запустить все службы) или **Stop All services** (Остановить все службы).</span><span class="sxs-lookup"><span data-stu-id="20547-114">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="20547-115">Запуск или остановка конкретной службы</span><span class="sxs-lookup"><span data-stu-id="20547-115">To start or stop a specific service</span></span>

1.  <span data-ttu-id="20547-116">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="20547-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="20547-117">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20547-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="20547-118">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="20547-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="20547-119">В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).</span><span class="sxs-lookup"><span data-stu-id="20547-119">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="20547-120">На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="20547-120">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="20547-121">Щелкните элемент **Properties** (Свойства).</span><span class="sxs-lookup"><span data-stu-id="20547-121">Click **Properties**.</span></span>

6.  <span data-ttu-id="20547-122">Отсортируйте список служб, если это необходимо, и щелкните службу, которую хотите запустить или остановить.</span><span class="sxs-lookup"><span data-stu-id="20547-122">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="20547-123">Щелкните элемент **Action** (Действие).</span><span class="sxs-lookup"><span data-stu-id="20547-123">Click **Action**.</span></span>

8.  <span data-ttu-id="20547-124">Щелкните **Start service** (Запустить службу) или **Stop service** (Остановить службу).</span><span class="sxs-lookup"><span data-stu-id="20547-124">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="20547-125">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="20547-125">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="20547-126">См. также</span><span class="sxs-lookup"><span data-stu-id="20547-126">See Also</span></span>


[<span data-ttu-id="20547-127">Предотвращение сеансов для служб в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20547-127">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="20547-128">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20547-128">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

