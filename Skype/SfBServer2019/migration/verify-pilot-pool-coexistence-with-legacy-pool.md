---
title: Проверка возможности совместного использования пилотного и старого пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Процесс проверки сосуществования пилотного пула с помощью устаревшего пула.
ms.openlocfilehash: e71160a2a20d4a80979e3c3c4875c19db181f2da
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243752"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="5ea55-103">Проверка возможности совместного использования пилотного и старого пула</span><span class="sxs-lookup"><span data-stu-id="5ea55-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="5ea55-104">**В этой статье**</span><span class="sxs-lookup"><span data-stu-id="5ea55-104">**In this article**</span></span>
  
[<span data-ttu-id="5ea55-105">Проверка того, что службы Skype для бизнеса Server 2019 были запущены</span><span class="sxs-lookup"><span data-stu-id="5ea55-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="5ea55-106">Открытие панели управления Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="5ea55-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="5ea55-107">Не пытайтесь открыть топологию в построителе устаревших топологий</span><span class="sxs-lookup"><span data-stu-id="5ea55-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="5ea55-108">После развертывания пилотного пула необходимо проверить сосуществование двух пулов с помощью средств администрирования для просмотра сведений о пуле.</span><span class="sxs-lookup"><span data-stu-id="5ea55-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="5ea55-109">Для пулов и стандартных пулов Skype для бизнеса Server 2019 необходимо использовать инструменты панели управления и Topology Builder Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5ea55-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="5ea55-110">Проверка того, что службы Skype для бизнеса Server 2019 были запущены</span><span class="sxs-lookup"><span data-stu-id="5ea55-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="5ea55-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="5ea55-111"></span></span>

1. <span data-ttu-id="5ea55-112">На сервере переднего плана Skype для бизнеса Server 2019 перейдите в приложение администрирование Тулс\сервицес.</span><span class="sxs-lookup"><span data-stu-id="5ea55-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="5ea55-113">Убедитесь в том, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="5ea55-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="5ea55-114">Агент службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="5ea55-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="5ea55-115">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="5ea55-115">Application Sharing</span></span>
    - <span data-ttu-id="5ea55-116">Служба проверки звука</span><span class="sxs-lookup"><span data-stu-id="5ea55-116">Audio Test Service</span></span>
    - <span data-ttu-id="5ea55-117">Аудио-и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="5ea55-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="5ea55-118">Приостановка вызовов</span><span class="sxs-lookup"><span data-stu-id="5ea55-118">Call Park</span></span>
    - <span data-ttu-id="5ea55-119">Оповещения для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="5ea55-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="5ea55-120">Помощник по конференциям</span><span class="sxs-lookup"><span data-stu-id="5ea55-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="5ea55-121">Интерфейсный сервер</span><span class="sxs-lookup"><span data-stu-id="5ea55-121">Front-End</span></span>
    - <span data-ttu-id="5ea55-122">Конференции для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="5ea55-122">IM Conferencing</span></span>
    - <span data-ttu-id="5ea55-123">Посредник</span><span class="sxs-lookup"><span data-stu-id="5ea55-123">Mediation</span></span>
    - <span data-ttu-id="5ea55-124">Агент репликации реплики</span><span class="sxs-lookup"><span data-stu-id="5ea55-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="5ea55-125">"Группа ответа"</span><span class="sxs-lookup"><span data-stu-id="5ea55-125">Response Group</span></span>
    - <span data-ttu-id="5ea55-126">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="5ea55-126">Web Conferencing</span></span>
    - <span data-ttu-id="5ea55-127">Шлюз для перевода КСМПП</span><span class="sxs-lookup"><span data-stu-id="5ea55-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="5ea55-128">Открытие панели управления Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="5ea55-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="5ea55-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="5ea55-129"></span></span>

<span data-ttu-id="5ea55-130">На сервере переднего плана в развертывании Skype для бизнеса Server 2019 откройте панель управления "Skype для бизнеса Server 2019" и выберите пул устаревших пользователей.</span><span class="sxs-lookup"><span data-stu-id="5ea55-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="5ea55-131">Повторите процедуру, чтобы открыть пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5ea55-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5ea55-132">В Skype для бизнеса Server 2019 необходимо обновить Silverlight до Silverlight версии 5, прежде чем использовать панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5ea55-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="5ea55-133">Эта топология теперь включает устаревшие роли и сервер Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5ea55-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="5ea55-134">Не пытайтесь открыть топологию в построителе устаревших топологий</span><span class="sxs-lookup"><span data-stu-id="5ea55-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="5ea55-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="5ea55-135"></span></span>

<span data-ttu-id="5ea55-136">Топологию можно просмотреть только с помощью построителя топологии Skype для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5ea55-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="5ea55-137">Для создания пулов как в Skype для бизнеса Server 2019, так и в устаревшей версии, необходимо использовать построитель топологии Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5ea55-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

