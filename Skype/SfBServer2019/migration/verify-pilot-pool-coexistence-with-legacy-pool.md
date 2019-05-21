---
title: Проверка возможности совместного использования пилотного и старого пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Процесс проверки сосуществования пилотного пула с помощью устаревшего пула.
ms.openlocfilehash: dd2edd2e6ecef26b22ba9bf5c093c631866110ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280655"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="d6743-103">Проверка возможности совместного использования пилотного и старого пула</span><span class="sxs-lookup"><span data-stu-id="d6743-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="d6743-104">**В этой статье**</span><span class="sxs-lookup"><span data-stu-id="d6743-104">**In this article**</span></span>
  
[<span data-ttu-id="d6743-105">Проверка того, что службы Skype для бизнеса Server 2019 были запущены</span><span class="sxs-lookup"><span data-stu-id="d6743-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="d6743-106">Открытие панели управления Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="d6743-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="d6743-107">Не пытайтесь открыть топологию в построителе устаревших топологий</span><span class="sxs-lookup"><span data-stu-id="d6743-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="d6743-108">После развертывания пилотного пула необходимо проверить сосуществование двух пулов с помощью средств администрирования для просмотра сведений о пуле.</span><span class="sxs-lookup"><span data-stu-id="d6743-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="d6743-109">Для пулов и стандартных пулов Skype для бизнеса Server 2019 необходимо использовать инструменты панели управления и Topology Builder Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d6743-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="d6743-110">Проверка того, что службы Skype для бизнеса Server 2019 были запущены</span><span class="sxs-lookup"><span data-stu-id="d6743-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="d6743-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="d6743-111"></span></span>

1. <span data-ttu-id="d6743-112">На сервере переднего плана Skype для бизнеса Server 2019 перейдите в приложение администрирование Тулс\сервицес.</span><span class="sxs-lookup"><span data-stu-id="d6743-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="d6743-113">Убедитесь в том, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="d6743-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="d6743-114">Агент службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="d6743-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="d6743-115">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="d6743-115">Application Sharing</span></span>
    - <span data-ttu-id="d6743-116">Служба проверки звука</span><span class="sxs-lookup"><span data-stu-id="d6743-116">Audio Test Service</span></span>
    - <span data-ttu-id="d6743-117">Аудио-и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="d6743-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="d6743-118">Приостановка вызовов</span><span class="sxs-lookup"><span data-stu-id="d6743-118">Call Park</span></span>
    - <span data-ttu-id="d6743-119">Оповещения для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="d6743-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="d6743-120">Помощник по конференциям</span><span class="sxs-lookup"><span data-stu-id="d6743-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="d6743-121">Интерфейсный сервер</span><span class="sxs-lookup"><span data-stu-id="d6743-121">Front-End</span></span>
    - <span data-ttu-id="d6743-122">Конференции для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="d6743-122">IM Conferencing</span></span>
    - <span data-ttu-id="d6743-123">Посредник</span><span class="sxs-lookup"><span data-stu-id="d6743-123">Mediation</span></span>
    - <span data-ttu-id="d6743-124">Агент репликации реплики</span><span class="sxs-lookup"><span data-stu-id="d6743-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="d6743-125">"Группа ответа"</span><span class="sxs-lookup"><span data-stu-id="d6743-125">Response Group</span></span>
    - <span data-ttu-id="d6743-126">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="d6743-126">Web Conferencing</span></span>
    - <span data-ttu-id="d6743-127">Шлюз для перевода КСМПП</span><span class="sxs-lookup"><span data-stu-id="d6743-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="d6743-128">Открытие панели управления Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="d6743-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="d6743-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="d6743-129"></span></span>

<span data-ttu-id="d6743-130">На сервере переднего плана в развертывании Skype для бизнеса Server 2019 откройте панель управления "Skype для бизнеса Server 2019" и выберите пул устаревших пользователей.</span><span class="sxs-lookup"><span data-stu-id="d6743-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="d6743-131">Повторите процедуру, чтобы открыть пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d6743-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d6743-132">В Skype для бизнеса Server 2019 необходимо обновить Silverlight до Silverlight версии 5, прежде чем использовать панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d6743-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="d6743-133">Эта топология теперь включает устаревшие роли и сервер Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d6743-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="d6743-134">Не пытайтесь открыть топологию в построителе устаревших топологий</span><span class="sxs-lookup"><span data-stu-id="d6743-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="d6743-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="d6743-135"></span></span>

<span data-ttu-id="d6743-136">Если вы попытаетесь открыть топологию с помощью устаревшей построителя топологии, вам будет выдано следующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d6743-136">If you attempt to open the topology using the legacy Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="d6743-137">Топологию можно просмотреть только с помощью построителя топологии Skype для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d6743-137">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="d6743-138">Для создания пулов как в Skype для бизнеса Server 2019, так и в устаревшей версии, необходимо использовать построитель топологии Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d6743-138">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

