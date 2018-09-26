---
title: Проверка возможности совместного использования пилотного пула прежних версий
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Процесс проверка возможности совместного использования пилотного пула прежних версий.
ms.openlocfilehash: 717726acd3654abb2296d622afc5a4d45009430e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028693"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="a043f-103">Проверка возможности совместного использования пилотного пула прежних версий</span><span class="sxs-lookup"><span data-stu-id="a043f-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="a043f-104">**В этой статье**</span><span class="sxs-lookup"><span data-stu-id="a043f-104">**In this article**</span></span>
  
[<span data-ttu-id="a043f-105">Проверка запуска Скайп для служб Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a043f-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="a043f-106">Откройте Скайп для панели управления Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a043f-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="a043f-107">Не пытайтесь открыть данную топологию в построителе топологии прежних версий</span><span class="sxs-lookup"><span data-stu-id="a043f-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="a043f-108">После развертывания пилотного пула необходимо проверить сосуществования двух пулов с помощью средства администрирования, чтобы просмотреть сведения о пуле.</span><span class="sxs-lookup"><span data-stu-id="a043f-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="a043f-109">Для Скайп для пулов Business Server 2019 и старых пулов необходимо использовать Скайп средства панели управления 2019 Business Server и построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="a043f-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="a043f-110">Проверка запуска Скайп для служб Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a043f-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="a043f-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="a043f-111"></span></span>

1. <span data-ttu-id="a043f-112">Из Скайп для сервера переднего плана Business Server 2019 перейдите в приложение административных средств и служб.</span><span class="sxs-lookup"><span data-stu-id="a043f-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="a043f-113">Убедитесь, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="a043f-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="a043f-114">Агент службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="a043f-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="a043f-115">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="a043f-115">Application Sharing</span></span>
    - <span data-ttu-id="a043f-116">Служба проверки звука</span><span class="sxs-lookup"><span data-stu-id="a043f-116">Audio Test Service</span></span>
    - <span data-ttu-id="a043f-117">Аудио-и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="a043f-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="a043f-118">Приостановка вызовов</span><span class="sxs-lookup"><span data-stu-id="a043f-118">Call Park</span></span>
    - <span data-ttu-id="a043f-119">Оповещения для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="a043f-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="a043f-120">Помощник по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="a043f-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="a043f-121">Переднего плана</span><span class="sxs-lookup"><span data-stu-id="a043f-121">Front-End</span></span>
    - <span data-ttu-id="a043f-122">Обмен мгновенными Сообщениями конференц-связи</span><span class="sxs-lookup"><span data-stu-id="a043f-122">IM Conferencing</span></span>
    - <span data-ttu-id="a043f-123">Посредник</span><span class="sxs-lookup"><span data-stu-id="a043f-123">Mediation</span></span>
    - <span data-ttu-id="a043f-124">Агент репликации реплики</span><span class="sxs-lookup"><span data-stu-id="a043f-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="a043f-125">"Группа ответа"</span><span class="sxs-lookup"><span data-stu-id="a043f-125">Response Group</span></span>
    - <span data-ttu-id="a043f-126">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="a043f-126">Web Conferencing</span></span>
    - <span data-ttu-id="a043f-127">Перевод шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="a043f-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="a043f-128">Откройте Скайп для панели управления Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a043f-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="a043f-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="a043f-129"></span></span>

<span data-ttu-id="a043f-130">С сервера переднего плана в вашей Скайп Business Server 2019 развертывания откройте Скайп для панели управления 2019 Business Server и выберите устаревшего пула.</span><span class="sxs-lookup"><span data-stu-id="a043f-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="a043f-131">Повторите процедуру, чтобы открыть Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a043f-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a043f-132">На Скайп для Business Server 2019 следует обновить продукт Silverlight до версии 5 перед использованием Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="a043f-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="a043f-133">Эта топология теперь включает прежних версий и Скайп для ролей сервера Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a043f-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="a043f-134">Не пытайтесь открыть данную топологию в построителе топологии прежних версий</span><span class="sxs-lookup"><span data-stu-id="a043f-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="a043f-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="a043f-135"></span></span>

<span data-ttu-id="a043f-136">При попытке открыть топологии, с помощью устаревшего Topology Builder возникнет ошибка ниже.</span><span class="sxs-lookup"><span data-stu-id="a043f-136">If you attempt to open the topology using the legacy Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="a043f-137">Топология можно просматривать только с помощью Скайп for Business Server 2019 Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="a043f-137">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="a043f-138">Скайп для Business Server 2019 Topology Builder необходимо используется для создания пулов для Скайп для Business Server 2019 и установки прежних версий.</span><span class="sxs-lookup"><span data-stu-id="a043f-138">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

