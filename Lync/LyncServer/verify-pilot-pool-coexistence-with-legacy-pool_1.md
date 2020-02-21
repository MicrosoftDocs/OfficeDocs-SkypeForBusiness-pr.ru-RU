---
title: Проверка совместного использования пилотного пула с устаревшим пулом
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4952640d6f6e938b460855118163d98e001f6a77
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="52c86-102">Проверка совместного использования пилотного пула с устаревшим пулом</span><span class="sxs-lookup"><span data-stu-id="52c86-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52c86-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="52c86-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="52c86-104">Проверка пула в средстве администрирования Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="52c86-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="52c86-105">Откройте средство администрирования Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="52c86-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="52c86-106">Разверните узел **Лес**, разверните узел **Серверы Standard Edition** или **Корпоративные пулы**, а затем разверните пул или сервер.</span><span class="sxs-lookup"><span data-stu-id="52c86-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="52c86-107">Убедитесь, что службы Office Communications Server 2007 R2 запущены в пуле.</span><span class="sxs-lookup"><span data-stu-id="52c86-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="52c86-108">![Консоль администрирования Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Консоль администрирования Office Communications Server 2007 R2")</span><span class="sxs-lookup"><span data-stu-id="52c86-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="52c86-109">Проверка пилотного пула в панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52c86-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="52c86-110">Войдите на сервер переднего плана Lync Server 2013 с учетной записью пользователя, которая является участником роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="52c86-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="52c86-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52c86-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="52c86-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="52c86-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="52c86-113">Щелкните пункт **Топология**.</span><span class="sxs-lookup"><span data-stu-id="52c86-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="52c86-114">Убедитесь, что все развернутые серверы присутствуют в пилотном пуле.</span><span class="sxs-lookup"><span data-stu-id="52c86-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="52c86-115">![Страница топологии панели управления Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Страница топологии панели управления Lync Server")</span><span class="sxs-lookup"><span data-stu-id="52c86-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="52c86-116">Проверка того, что службы Lync Server 2013 запущены</span><span class="sxs-lookup"><span data-stu-id="52c86-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="52c86-117">На сервере переднего плана Lync Server 2013 откройте приложение **службы** из группы " **Администрирование** ".</span><span class="sxs-lookup"><span data-stu-id="52c86-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="52c86-118">Убедитесь, что отображенные службы соответствуют службам в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="52c86-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="52c86-119">![Страница служб, на которой запущены службы Lync](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Страница служб, на которой запущены службы Lync")</span><span class="sxs-lookup"><span data-stu-id="52c86-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

