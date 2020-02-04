---
title: 'Lync Server 2013: запуск и остановка служб Lync Server'
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
ms.openlocfilehash: a986f0bef8c41cf5113e99504369974562e294a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="2f4f1-102">Запуск и остановка служб Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f4f1-102">Start or stop Lync Server 2013 services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f4f1-103">_**Тема последнего изменения:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="2f4f1-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="2f4f1-104">С помощью панели управления Lync Server можно запускать и останавливать все службы Lync Server 2013, запущенные на конкретном компьютере, а также запускать и останавливать определенную службу.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-104">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="2f4f1-105">Запуск и остановка всех служб Lync Server на компьютере</span><span class="sxs-lookup"><span data-stu-id="2f4f1-105">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="2f4f1-106">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="2f4f1-107">Вы можете определить, назначена ли вам роль Кссерверадминистратор или Ксадминистратор RBAC, выполнив команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="2f4f1-107">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="2f4f1-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2f4f1-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2f4f1-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2f4f1-110">На панели навигации слева щелкните **топология** и выберите **состояние**.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="2f4f1-111">На странице " **состояние** " выполните сортировку и поиск по списку, если это необходимо, чтобы найти компьютер, на котором запущены службы, которые вы хотите запустить или остановить, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="2f4f1-112">Нажмите кнопку **действие**.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-112">Click **Action**.</span></span>

6.  <span data-ttu-id="2f4f1-113">Нажмите кнопку **начать все службы** или **остановить все службы**.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-113">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="2f4f1-114">Запуск и остановка определенной службы</span><span class="sxs-lookup"><span data-stu-id="2f4f1-114">To start or stop a specific service</span></span>

1.  <span data-ttu-id="2f4f1-115">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-115">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2f4f1-116">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2f4f1-117">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2f4f1-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2f4f1-118">На панели навигации слева щелкните **топология** и выберите **состояние**.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="2f4f1-119">На странице " **состояние** " выполните сортировку и поиск по списку, если это необходимо, чтобы найти компьютер, на котором запущена служба, которую вы хотите запустить или остановить, а затем щелкните ее.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="2f4f1-120">Нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="2f4f1-121">При необходимости отсортируйте список служб и выберите службу, которую вы хотите запустить или остановить.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-121">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="2f4f1-122">Нажмите кнопку **действие**.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-122">Click **Action**.</span></span>

8.  <span data-ttu-id="2f4f1-123">Нажмите кнопку **запустить службу** или **остановить службу**.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-123">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="2f4f1-124">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2f4f1-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f4f1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2f4f1-125">See Also</span></span>


[<span data-ttu-id="2f4f1-126">Предотвращение сеансов для служб в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f4f1-126">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="2f4f1-127">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f4f1-127">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

