---
title: Проверка совместного использования пилотного пула с устаревшим пулом
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f361882d0994b8e3add5447dbcaaffe2b75127d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="a285f-102">Проверка совместного использования пилотного пула с устаревшим пулом</span><span class="sxs-lookup"><span data-stu-id="a285f-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a285f-103">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="a285f-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="a285f-104">После развертывания пилотного пула вам требуется проверить сосуществование двух пулов, воспользовавшись средствами администрирования для просмотра информации о пуле.</span><span class="sxs-lookup"><span data-stu-id="a285f-104">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="a285f-105">Для пулов Lync Server 2013 и устаревших пулов необходимо использовать инструменты панели управления Lync Server 2013 и построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="a285f-105">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="a285f-106">Проверка того, что службы Lync Server 2013 запущены</span><span class="sxs-lookup"><span data-stu-id="a285f-106">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="a285f-107">На сервере переднего плана Lync Server 2013 перейдите к компоненту "Администрирование\\служб".</span><span class="sxs-lookup"><span data-stu-id="a285f-107">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="a285f-108">Убедитесь, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="a285f-108">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="a285f-109">**Службы Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="a285f-109">**Lync Server 2013 services**</span></span>

<span data-ttu-id="a285f-110">![Список запущенных служб Lync Server](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Список запущенных служб Lync Server")</span><span class="sxs-lookup"><span data-stu-id="a285f-110">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="a285f-111">Открытие панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a285f-111">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="a285f-112">На сервере переднего плана в развертывании Lync Server 2013 откройте панель управления Lync Server 2013 и выберите пул Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a285f-112">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="a285f-113">Повторите процедуру, чтобы открыть пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a285f-113">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="a285f-114">**Открытие панели управления Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="a285f-114">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="a285f-115">![Диалоговое окно "Выбор URL-адреса"](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Диалоговое окно "Выбор URL-адреса"")</span><span class="sxs-lookup"><span data-stu-id="a285f-115">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a285f-116">В Lync Server 2013 необходимо обновить Silverlight до Silverlight версии 5, прежде чем использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a285f-116">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="a285f-117">Эта топология теперь включает роли сервера Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a285f-117">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="a285f-118">**Страница топологии в панели управления Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="a285f-118">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="a285f-119">![Панель управления Lync Server — страница топологии](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Панель управления Lync Server — страница топологии")</span><span class="sxs-lookup"><span data-stu-id="a285f-119">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="a285f-120">Не пытайтесь открыть топологию в построителе топологий Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a285f-120">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="a285f-121">При попытке открыть топологию с помощью построителя топологий Lync Server 2010 вы увидите следующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a285f-121">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="a285f-122">Топологию можно просмотреть только с помощью построителя топологий Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a285f-122">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="a285f-123">Для создания пулов для Lync Server 2013 и Lync Server 2010 необходимо использовать построитель топологий Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a285f-123">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="a285f-124">**Сообщение об ошибке в построителе топологий Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="a285f-124">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="a285f-125">![Ошибка привязки консоли управления "Построитель топологий Lync Server"](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Ошибка привязки консоли управления "Построитель топологий Lync Server"")</span><span class="sxs-lookup"><span data-stu-id="a285f-125">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

