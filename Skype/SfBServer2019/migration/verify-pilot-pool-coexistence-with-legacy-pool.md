---
title: Проверка возможности совместного использования пилотного и старого пула
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Процесс проверки сосуществования пилотного пула с устаревшим пулом.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751661"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="e4462-103">Проверка возможности совместного использования пилотного и старого пула</span><span class="sxs-lookup"><span data-stu-id="e4462-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="e4462-104">**Содержание**</span><span class="sxs-lookup"><span data-stu-id="e4462-104">**In this article**</span></span>
  
[<span data-ttu-id="e4462-105">Проверка того, что службы Skype для бизнеса Server 2019 запущены</span><span class="sxs-lookup"><span data-stu-id="e4462-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="e4462-106">Откройте панель управления Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="e4462-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="e4462-107">Не пытайтесь открыть топологию в устаревшем построителе топологий</span><span class="sxs-lookup"><span data-stu-id="e4462-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="e4462-108">После развертывания пилотного пула вам требуется проверить сосуществование двух пулов, воспользовавшись средствами администрирования для просмотра информации о пуле.</span><span class="sxs-lookup"><span data-stu-id="e4462-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="e4462-109">Для пулов Skype для бизнеса Server 2019 и устаревших пулов необходимо использовать средства построителя топологий и панели управления Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4462-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="e4462-110">Проверка того, что службы Skype для бизнеса Server 2019 запущены</span><span class="sxs-lookup"><span data-stu-id="e4462-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="e4462-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="e4462-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="e4462-112">На сервере переднего плана Skype для бизнеса Server 2019 перейдите к апплету Администрирование средств и служб.</span><span class="sxs-lookup"><span data-stu-id="e4462-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="e4462-113">Убедитесь, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="e4462-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="e4462-114">Агент централизованной службы ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="e4462-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="e4462-115">Совместное использование приложений</span><span class="sxs-lookup"><span data-stu-id="e4462-115">Application Sharing</span></span>
    - <span data-ttu-id="e4462-116">Служба проверки звука</span><span class="sxs-lookup"><span data-stu-id="e4462-116">Audio Test Service</span></span>
    - <span data-ttu-id="e4462-117">Аудио-и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="e4462-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="e4462-118">Парковка вызовов</span><span class="sxs-lookup"><span data-stu-id="e4462-118">Call Park</span></span>
    - <span data-ttu-id="e4462-119">Извещение конференц-связи</span><span class="sxs-lookup"><span data-stu-id="e4462-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="e4462-120">Помощник по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="e4462-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="e4462-121">Внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="e4462-121">Front-End</span></span>
    - <span data-ttu-id="e4462-122">Конференц-связь</span><span class="sxs-lookup"><span data-stu-id="e4462-122">IM Conferencing</span></span>
    - <span data-ttu-id="e4462-123">Сетью</span><span class="sxs-lookup"><span data-stu-id="e4462-123">Mediation</span></span>
    - <span data-ttu-id="e4462-124">Агент репликации реплики</span><span class="sxs-lookup"><span data-stu-id="e4462-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="e4462-125">Группа ответа</span><span class="sxs-lookup"><span data-stu-id="e4462-125">Response Group</span></span>
    - <span data-ttu-id="e4462-126">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="e4462-126">Web Conferencing</span></span>
    - <span data-ttu-id="e4462-127">Шлюз преобразования XMPP</span><span class="sxs-lookup"><span data-stu-id="e4462-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="e4462-128">Откройте панель управления Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="e4462-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="e4462-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="e4462-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="e4462-130">На сервере переднего плана в развертывании Skype для бизнеса Server 2019 откройте панель управления Skype для бизнеса Server 2019 и выберите пул прежних версий.</span><span class="sxs-lookup"><span data-stu-id="e4462-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="e4462-131">Повторите процедуру, чтобы открыть пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4462-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e4462-132">В Skype для бизнеса Server 2019 необходимо обновить Silverlight до Silverlight версии 5, прежде чем использовать панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e4462-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="e4462-133">Эта топология теперь включает устаревшие роли сервера и сервера Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4462-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="e4462-134">Не пытайтесь открыть топологию в устаревшем построителе топологий</span><span class="sxs-lookup"><span data-stu-id="e4462-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="e4462-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="e4462-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="e4462-136">Топологию можно просмотреть только с помощью построителя топологий Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4462-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="e4462-137">Для создания пулов для Skype для бизнеса Server 2019 и установки прежних версий необходимо использовать построитель топологий Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4462-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

