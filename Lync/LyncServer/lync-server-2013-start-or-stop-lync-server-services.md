---
title: 'Lync Server 2013: запуск или остановка служб Lync Server'
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
ms.openlocfilehash: 0b95e9a49978499d16749f643cdd10d71637daf9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="af5b7-102">Запуск и остановка служб Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af5b7-102">Start or stop Lync Server 2013 services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af5b7-103">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="af5b7-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="af5b7-104">Можно использовать панель управления Lync Server для запуска или остановки всех служб Lync Server 2013, работающих на определенном компьютере или для запуска или остановки определенной службы.</span><span class="sxs-lookup"><span data-stu-id="af5b7-104">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="af5b7-105">Запуск или остановка всех служб Lync Server на компьютере</span><span class="sxs-lookup"><span data-stu-id="af5b7-105">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="af5b7-106">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af5b7-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="af5b7-107">Вы можете определить, назначена ли роль CsServerAdministrator или CsAdministrator RBAC, выполнив команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="af5b7-107">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="af5b7-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af5b7-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="af5b7-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="af5b7-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="af5b7-110">В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).</span><span class="sxs-lookup"><span data-stu-id="af5b7-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="af5b7-111">На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="af5b7-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="af5b7-112">Щелкните элемент **Action** (Действие).</span><span class="sxs-lookup"><span data-stu-id="af5b7-112">Click **Action**.</span></span>

6.  <span data-ttu-id="af5b7-113">Щелкните **Start All services** (Запустить все службы) или **Stop All services** (Остановить все службы).</span><span class="sxs-lookup"><span data-stu-id="af5b7-113">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="af5b7-114">Запуск или остановка конкретной службы</span><span class="sxs-lookup"><span data-stu-id="af5b7-114">To start or stop a specific service</span></span>

1.  <span data-ttu-id="af5b7-115">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="af5b7-115">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="af5b7-116">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af5b7-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="af5b7-117">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="af5b7-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="af5b7-118">В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).</span><span class="sxs-lookup"><span data-stu-id="af5b7-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="af5b7-119">На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="af5b7-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="af5b7-120">Щелкните элемент **Properties** (Свойства).</span><span class="sxs-lookup"><span data-stu-id="af5b7-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="af5b7-121">Отсортируйте список служб, если это необходимо, и щелкните службу, которую хотите запустить или остановить.</span><span class="sxs-lookup"><span data-stu-id="af5b7-121">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="af5b7-122">Щелкните элемент **Action** (Действие).</span><span class="sxs-lookup"><span data-stu-id="af5b7-122">Click **Action**.</span></span>

8.  <span data-ttu-id="af5b7-123">Щелкните **Start service** (Запустить службу) или **Stop service** (Остановить службу).</span><span class="sxs-lookup"><span data-stu-id="af5b7-123">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="af5b7-124">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="af5b7-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af5b7-125">См. также</span><span class="sxs-lookup"><span data-stu-id="af5b7-125">See Also</span></span>


[<span data-ttu-id="af5b7-126">Предотвращение сеансов для служб в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af5b7-126">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="af5b7-127">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af5b7-127">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

