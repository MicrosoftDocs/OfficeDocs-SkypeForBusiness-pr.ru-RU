---
title: Проверка возможности совместного использования пилотного и старого пула
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
ms.openlocfilehash: 7585970a53ffd94959653555dad8a02724ba2f03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="3a860-102">Проверка возможности совместного использования пилотного и старого пула</span><span class="sxs-lookup"><span data-stu-id="3a860-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a860-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3a860-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="3a860-104">Проверка пула в средстве администрирования Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3a860-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="3a860-105">Откройте средство администрирования Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3a860-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="3a860-106">Разверните узел **леса** , разверните узел **Стандартные серверы выпуска** или **Пулы предприятий** , а затем разверните имя пула или сервера.</span><span class="sxs-lookup"><span data-stu-id="3a860-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="3a860-107">Убедитесь в том, что службы Office Communications Server 2007 R2 запущены в пуле.</span><span class="sxs-lookup"><span data-stu-id="3a860-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="3a860-108">![Консоль администрирования Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Консоль администрирования Office Communications Server 2007 R2")</span><span class="sxs-lookup"><span data-stu-id="3a860-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="3a860-109">Проверка пула пилотных проектов в Lync Server 2013 панели управления</span><span class="sxs-lookup"><span data-stu-id="3a860-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="3a860-110">Войдите в учетную запись пользователя, которая является членом роли Ксадминистратор, выполните вход на сервер переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a860-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="3a860-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a860-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3a860-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3a860-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3a860-113">Нажмите **топология**.</span><span class="sxs-lookup"><span data-stu-id="3a860-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="3a860-114">Убедитесь, что развернутые серверы находятся в вашем пилотном пуле.</span><span class="sxs-lookup"><span data-stu-id="3a860-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="3a860-115">![Страница топологии панели управления сервера Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Страница топологии панели управления сервера Lync Server")</span><span class="sxs-lookup"><span data-stu-id="3a860-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="3a860-116">Проверка того, что службы Lync Server 2013 запущены</span><span class="sxs-lookup"><span data-stu-id="3a860-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="3a860-117">На сервере переднего плана Lync Server 2013 откройте приложение " **службы** " из группы " **Администрирование** ".</span><span class="sxs-lookup"><span data-stu-id="3a860-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="3a860-118">Убедитесь, что список служб соответствует списку, показанному на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="3a860-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="3a860-119">![Страница служб, на которой запущены службы Lync](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Страница служб, на которой запущены службы Lync")</span><span class="sxs-lookup"><span data-stu-id="3a860-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

