---
title: Проверка возможности совместного использования пилотного и старого пула
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b76c1296f69421bfbfe83e61055249f2642420ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="eb181-102">Проверка возможности совместного использования пилотного и старого пула</span><span class="sxs-lookup"><span data-stu-id="eb181-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb181-103">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="eb181-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="eb181-104">После развертывания пилотного пула вам требуется проверить сосуществование двух пулов, воспользовавшись средствами администрирования для просмотра информации о пуле.</span><span class="sxs-lookup"><span data-stu-id="eb181-104">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="eb181-105">Для пулов Lync Server 2013 и устаревших пулов необходимо использовать инструменты панели управления Lync Server 2013 и построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="eb181-105">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="eb181-106">Проверка того, что службы Lync Server 2013 запущены</span><span class="sxs-lookup"><span data-stu-id="eb181-106">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="eb181-107">На сервере переднего плана Lync Server 2013 перейдите к компоненту "Администрирование \\ служб".</span><span class="sxs-lookup"><span data-stu-id="eb181-107">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="eb181-108">Убедитесь, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="eb181-108">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="eb181-109">**Службы Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="eb181-109">**Lync Server 2013 services**</span></span>

<span data-ttu-id="eb181-110">![Список запущенных служб Lync Server](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Список запущенных служб Lync Server")</span><span class="sxs-lookup"><span data-stu-id="eb181-110">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="eb181-111">Открытие панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb181-111">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="eb181-112">На сервере переднего плана в развертывании Lync Server 2013 откройте панель управления Lync Server 2013 и выберите пул Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="eb181-112">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="eb181-113">Повторите процедуру, чтобы открыть пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb181-113">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="eb181-114">**Открытие панели управления Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="eb181-114">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="eb181-115">![Диалоговое окно "Выбор URL-адреса"](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Диалоговое окно "Выбор URL-адреса"")</span><span class="sxs-lookup"><span data-stu-id="eb181-115">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eb181-116">В Lync Server 2013 необходимо обновить Silverlight до Silverlight версии 5, прежде чем использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eb181-116">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="eb181-117">Эта топология теперь включает роли сервера Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb181-117">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="eb181-118">**Страница топологии в панели управления Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="eb181-118">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="eb181-119">![Панель управления Lync Server — страница топологии](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Панель управления Lync Server — страница топологии")</span><span class="sxs-lookup"><span data-stu-id="eb181-119">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="eb181-120">Не пытайтесь открыть топологию в построителе топологий Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="eb181-120">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="eb181-121">При попытке открыть топологию с помощью построителя топологий Lync Server 2010 вы увидите следующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="eb181-121">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="eb181-122">Топологию можно просмотреть только с помощью построителя топологий Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb181-122">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="eb181-123">Для создания пулов для Lync Server 2013 и Lync Server 2010 необходимо использовать построитель топологий Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb181-123">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="eb181-124">**Сообщение об ошибке в построителе топологий Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="eb181-124">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="eb181-125">![Ошибка привязки консоли управления "Построитель топологий Lync Server"](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Ошибка привязки консоли управления "Построитель топологий Lync Server"")</span><span class="sxs-lookup"><span data-stu-id="eb181-125">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

