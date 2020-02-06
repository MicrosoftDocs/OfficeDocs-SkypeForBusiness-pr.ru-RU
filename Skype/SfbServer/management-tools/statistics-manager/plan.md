---
title: Планирование диспетчера статистики в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Аннотация: Ознакомьтесь с этим разделом, чтобы узнать о диспетчере статистики для Skype для бизнеса Server.'
ms.openlocfilehash: 0bf7a5366047a0f4435a98cd8bca75eeb3ebc8d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816238"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="e8a86-103">Планирование диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e8a86-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="e8a86-104">**Сводка:** Прочтите этот раздел, чтобы узнать о диспетчере статистики для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e8a86-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="e8a86-105">Диспетчер статистики в Skype для бизнеса Server — это эффективный инструмент, который позволяет просматривать данные о состоянии и производительности Skype для бизнеса Server в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="e8a86-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="e8a86-106">Вы можете вести опрос данных о производительности нескольких сотен серверов каждые несколько секунд и мгновенно просматривать результаты на веб-сайте диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="e8a86-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="e8a86-107">С помощью диспетчера статистики можно выявлять текущие проблемы с производительностью, просматривать результаты запланированных изменений в среде, устранять разрешения и многое другое.</span><span class="sxs-lookup"><span data-stu-id="e8a86-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="e8a86-108">Из этого поля диспетчер статистики настраивается с помощью пороговых значений индикатор работоспособности (КХИ), и его можно настроить в соответствии с уникальными потребностями развертывания.</span><span class="sxs-lookup"><span data-stu-id="e8a86-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="e8a86-109">Вы можете развернуть диспетчер статистики в локальной среде, в которой на одном сервере размещаются все компоненты диспетчера статистики на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="e8a86-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="e8a86-110">Дополнительные сведения о развертывании диспетчера статистики можно найти в разделе [Развертывание диспетчера статистики для Skype для бизнеса Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="e8a86-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="e8a86-111">Если у вас уже есть развертывание диспетчера статистики, но вы еще не выполнили обновление до выпуска 2,0, ознакомьтесь с [новыми возможностями, выпущенными в Выпуске 2,0](plan.md#BKMK_WhatsNew) и [обновлением диспетчера статистики для Skype для бизнеса Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="e8a86-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="e8a86-112">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="e8a86-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="e8a86-113">Возможности и возможности</span><span class="sxs-lookup"><span data-stu-id="e8a86-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="e8a86-114">Новые возможности выпуска 2,0</span><span class="sxs-lookup"><span data-stu-id="e8a86-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="e8a86-115">Компоненты</span><span class="sxs-lookup"><span data-stu-id="e8a86-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="e8a86-116">Локальное развертывание</span><span class="sxs-lookup"><span data-stu-id="e8a86-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="e8a86-117">Требования</span><span class="sxs-lookup"><span data-stu-id="e8a86-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="e8a86-118">Вопросы безопасности</span><span class="sxs-lookup"><span data-stu-id="e8a86-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="e8a86-119">Возможности и возможности</span><span class="sxs-lookup"><span data-stu-id="e8a86-119">Features and capabilities</span></span>
<span data-ttu-id="e8a86-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="e8a86-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="e8a86-121">Диспетчер статистики позволяет выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e8a86-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="e8a86-122">Просмотр необработанных данных для всех серверов в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="e8a86-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="e8a86-123">(Данные выдаются с очень высокой частотой и отправляются на веб-сайт менее чем за одну секунду).</span><span class="sxs-lookup"><span data-stu-id="e8a86-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="e8a86-124">Просмотр данных, агрегированных для определенной роли; Например, сервер переднего плана, сервер обновлений, пограничный сервер и т. д.</span><span class="sxs-lookup"><span data-stu-id="e8a86-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="e8a86-125">Детализация для просмотра данных конкретных сайтов, определенных пулов на сайте и отдельных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="e8a86-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="e8a86-126">Создание настраиваемых диаграмм для отображения выбранных счетчиков по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8a86-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="e8a86-127">Масштабирование и сдвиг на осях x и y либо только на оси x.</span><span class="sxs-lookup"><span data-stu-id="e8a86-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="e8a86-128">Используйте диапазоны дат или точки времени для фильтрации данных.</span><span class="sxs-lookup"><span data-stu-id="e8a86-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="e8a86-129">Просмотр производительности сервера на основе установленных индикаторов работоспособности ключа (Кхис).</span><span class="sxs-lookup"><span data-stu-id="e8a86-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="e8a86-130">Кхис представляет коллекцию счетчиков производительности с определенным работоспособным диапазоном.</span><span class="sxs-lookup"><span data-stu-id="e8a86-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="e8a86-131">Просмотр подробных метрик для каждого счетчика.</span><span class="sxs-lookup"><span data-stu-id="e8a86-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="e8a86-132">Сравнение данных на нескольких Генеральной совокупности или серверах.</span><span class="sxs-lookup"><span data-stu-id="e8a86-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="e8a86-133">Просматривайте отчеты о скрытых счетчиках, чтобы определить агенты, которые не сообщают текущие данные службе панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="e8a86-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="e8a86-134">Сохранение определенного экземпляра данных диаграммы в файле.</span><span class="sxs-lookup"><span data-stu-id="e8a86-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="e8a86-135">Просматривайте Кхис в режиме реального времени, включая обновления.</span><span class="sxs-lookup"><span data-stu-id="e8a86-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="e8a86-136">Если включено представление журнала, отображаются только новые ошибки.</span><span class="sxs-lookup"><span data-stu-id="e8a86-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="e8a86-137">Просмотр всех Кхисов за один раз</span><span class="sxs-lookup"><span data-stu-id="e8a86-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="e8a86-138">Просмотр Кхис по серверам (альбомный вид)</span><span class="sxs-lookup"><span data-stu-id="e8a86-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="e8a86-139">Просмотр определений КХИ</span><span class="sxs-lookup"><span data-stu-id="e8a86-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="e8a86-140">Новые возможности выпуска 2,0</span><span class="sxs-lookup"><span data-stu-id="e8a86-140">What's new in Release 2.0</span></span>
<span data-ttu-id="e8a86-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="e8a86-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="e8a86-142">Ниже описаны новые возможности в версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="e8a86-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="e8a86-143">Если у вас уже есть развертывание диспетчера статистики и вы еще не обновили его, ознакомьтесь со сведениями об [обновлении диспетчера статистики для Skype для бизнеса Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="e8a86-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="e8a86-144">Представления сценария добавлены для пограничного мультимедиа, работоспособность структуры, отказа в пуле и сценарии регистрации.</span><span class="sxs-lookup"><span data-stu-id="e8a86-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="e8a86-145">Для серверов SQL Server Добавлено много новых счетчиков, счетчиков использования Skype для бизнеса и т. д.</span><span class="sxs-lookup"><span data-stu-id="e8a86-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="e8a86-146">Интеграция с узлом-наблюдателем для агента диспетчера статистики — если агент установлен на узле наблюдателя, он будет сообщать о виртуальных транзакциях в качестве счетчиков назад в диспетчере статистики.</span><span class="sxs-lookup"><span data-stu-id="e8a86-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="e8a86-147">Многочисленные улучшения надежности и производительности.</span><span class="sxs-lookup"><span data-stu-id="e8a86-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="e8a86-148">Чтобы проверить версию веб-сайта диспетчера статистики, который вы используете, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e8a86-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="e8a86-149">В проводнике открыть (каталог по умолчанию) C:\Program Филес\скипе для Business Server stats Вебсите\бин</span><span class="sxs-lookup"><span data-stu-id="e8a86-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="e8a86-150">Щелкните правой кнопкой мыши Статсманхубвебсите. dll и просмотрите свойства</span><span class="sxs-lookup"><span data-stu-id="e8a86-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="e8a86-151">Версия продукта будет показана в сведениях описания.</span><span class="sxs-lookup"><span data-stu-id="e8a86-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="e8a86-152">Компоненты</span><span class="sxs-lookup"><span data-stu-id="e8a86-152">Components</span></span>
<span data-ttu-id="e8a86-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="e8a86-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="e8a86-154">Диспетчер статистики состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="e8a86-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="e8a86-155">**Без.**</span><span class="sxs-lookup"><span data-stu-id="e8a86-155">**Agent.**</span></span> <span data-ttu-id="e8a86-156">Упрощенный агент, который выполняется на каждом отслеживаемом сервере.</span><span class="sxs-lookup"><span data-stu-id="e8a86-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="e8a86-157">Агент позволяет настроить высокоскоростные опросы счетчиков производительности с помощью локального агрегата.</span><span class="sxs-lookup"><span data-stu-id="e8a86-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="e8a86-158">**Средство.**</span><span class="sxs-lookup"><span data-stu-id="e8a86-158">**Listener.**</span></span> <span data-ttu-id="e8a86-159">Серверный API-интерфейс, который получает данные от всех агентов и объединяет данные за пределы Генеральной совокупности.</span><span class="sxs-lookup"><span data-stu-id="e8a86-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="e8a86-160">**Ступиц.**</span><span class="sxs-lookup"><span data-stu-id="e8a86-160">**Hub.**</span></span> <span data-ttu-id="e8a86-161">Служит клиентским API для системы, выполняется на веб-серверах и предоставляет обновления данных в режиме реального времени для клиентов, подключенных через веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="e8a86-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="e8a86-162">(Центр автоматически устанавливается как часть файла MSI веб-сайта.)</span><span class="sxs-lookup"><span data-stu-id="e8a86-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="e8a86-163">**Веб-сайта.**</span><span class="sxs-lookup"><span data-stu-id="e8a86-163">**Website.**</span></span> <span data-ttu-id="e8a86-164">Пользовательский интерфейс, который собирает вместе все возможности, доступные в системе.</span><span class="sxs-lookup"><span data-stu-id="e8a86-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="e8a86-165">Кроме того, диспетчеру статистики требуется **Redis**— сервер структуры данных с открытым исходным кодом для кэширования в памяти.</span><span class="sxs-lookup"><span data-stu-id="e8a86-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="e8a86-166">Дополнительные сведения о том, как скачать Redis, можно найти в разделе [Развертывание диспетчера статистики](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="e8a86-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="e8a86-167">Локальное развертывание</span><span class="sxs-lookup"><span data-stu-id="e8a86-167">On-premises deployment</span></span>
<span data-ttu-id="e8a86-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="e8a86-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="e8a86-169">В локальном развертывании на одном сервере размещаются все компоненты диспетчера статистики на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="e8a86-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="e8a86-170">На приведенной ниже схеме показано локальное развертывание, в котором система управления статистикой веб-сайта, центра, прослушивателя и системы кэширования Redis размещаются на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e8a86-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="e8a86-171">Диспетчер статистических данных отслеживает три сервера Skype для бизнеса, каждый из которых содержит один агент, передающий данные прослушивателю.</span><span class="sxs-lookup"><span data-stu-id="e8a86-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="e8a86-172">Пользователи подключаются к отдельному веб-сайту для просмотра всех данных, агрегированных с помощью диспетчера статистики:</span><span class="sxs-lookup"><span data-stu-id="e8a86-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Диспетчер статистики: локальное развертывание](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="e8a86-174">Требования</span><span class="sxs-lookup"><span data-stu-id="e8a86-174">Requirements</span></span>
<span data-ttu-id="e8a86-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="e8a86-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="e8a86-176">Прежде чем развертывать диспетчер статистических данных, необходимо принять следующие требования к программному обеспечению, сети и аппаратному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="e8a86-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="e8a86-177">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="e8a86-177">Software requirements</span></span>

- <span data-ttu-id="e8a86-178">Windows Server 2016 и 2019</span><span class="sxs-lookup"><span data-stu-id="e8a86-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="e8a86-179">Службы IIS (автоматически установлены)</span><span class="sxs-lookup"><span data-stu-id="e8a86-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="e8a86-180">Redis</span><span class="sxs-lookup"><span data-stu-id="e8a86-180">Redis</span></span>

- <span data-ttu-id="e8a86-181">Службы диспетчера статистики (устанавливаются автоматически)</span><span class="sxs-lookup"><span data-stu-id="e8a86-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="e8a86-182">PSExec — требуется для удаленного развертывания агента</span><span class="sxs-lookup"><span data-stu-id="e8a86-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="e8a86-183">.NET 4,5 (входит в состав 2012 R2) — требуется для агентов и серверных компонентов</span><span class="sxs-lookup"><span data-stu-id="e8a86-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="e8a86-184">Скачайте [Skype для бизнеса Server, диспетчер статистики в реальном времени (64-разрядная версия)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="e8a86-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="e8a86-185">Требования к сети</span><span class="sxs-lookup"><span data-stu-id="e8a86-185">Networking requirements</span></span>


|<span data-ttu-id="e8a86-186">**Сервер размещения**</span><span class="sxs-lookup"><span data-stu-id="e8a86-186">**Hosting server**</span></span>|<span data-ttu-id="e8a86-187">**Агенты**</span><span class="sxs-lookup"><span data-stu-id="e8a86-187">**Agents**</span></span>|<span data-ttu-id="e8a86-188">**Средство**</span><span class="sxs-lookup"><span data-stu-id="e8a86-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8a86-189">Минимальная гигабитная полная дуплексная сеть.</span><span class="sxs-lookup"><span data-stu-id="e8a86-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="e8a86-190">Исходящий TCP-порт 8443 (настраиваемый номер порта) для связи с прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="e8a86-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="e8a86-191">Порт прослушивателя должен быть одинаковым на всех серверах.</span><span class="sxs-lookup"><span data-stu-id="e8a86-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="e8a86-192">Для размещения веб-сайта требуется порт 80 или 443 для входящего порта TCP.</span><span class="sxs-lookup"><span data-stu-id="e8a86-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="e8a86-193">Входящий TCP-порт 8443 (настраиваемый номер порта) для связи между агентами.</span><span class="sxs-lookup"><span data-stu-id="e8a86-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="e8a86-194">Во время установки порты брандмауэра для прослушивателя и веб-сайта создаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="e8a86-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="e8a86-195">Для агентов установка предполагает, что исходящие подключения по протоколу TCP разрешены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8a86-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="e8a86-196">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="e8a86-196">Hardware requirements</span></span>

<span data-ttu-id="e8a86-197">В локальной среде, в которой на одном сервере размещены все компоненты диспетчера статистики на стороне сервера, сервер с 16 ГБ оперативной памяти и 4 ЦП должен поддерживаться в среднем на 150 в течение секунды.</span><span class="sxs-lookup"><span data-stu-id="e8a86-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="e8a86-198">Чтобы определить, какое количество счетчиков и операторов можно поддерживать, выполните указанные ниже расчеты.</span><span class="sxs-lookup"><span data-stu-id="e8a86-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="e8a86-199">100 Servers \*80 \* счетчики 1 в минуту от каждого агента/60 секунд = ~ 133 образцов в секунду.</span><span class="sxs-lookup"><span data-stu-id="e8a86-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="e8a86-200">Вопросы безопасности</span><span class="sxs-lookup"><span data-stu-id="e8a86-200">Security considerations</span></span>
<span data-ttu-id="e8a86-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="e8a86-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="e8a86-202">Весь трафик между серверами шифруется.</span><span class="sxs-lookup"><span data-stu-id="e8a86-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="e8a86-203">Зашифрованный HTTPS-трафик будет отправляться через порт 8443 (по умолчанию) от агента на сервер прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="e8a86-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="e8a86-204">Агент проверит отпечаток SSL на сервере, чтобы убедиться, что сервер прослушивателя является ожидаемым получателем.</span><span class="sxs-lookup"><span data-stu-id="e8a86-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="e8a86-205">Обратите внимание, что агент использует проверку по отпечатку сертификата (вместо проверки цепочки сертификатов).</span><span class="sxs-lookup"><span data-stu-id="e8a86-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="e8a86-206">Он не будет выполнять полную проверку сертификатов, так как возможно использование самозаверяющих сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e8a86-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="e8a86-207">После того как агент доверит, что прослушиватель является достоверным, пароль будет представлен агентом, который затем проверяется прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="e8a86-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="e8a86-208">Агент начинает передачу данных о производительности через соединение с прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="e8a86-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="e8a86-209">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e8a86-209">For more information</span></span>
<span data-ttu-id="e8a86-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="e8a86-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="e8a86-211">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="e8a86-211">For more information, see the following:</span></span>

- [<span data-ttu-id="e8a86-212">Развертывание диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e8a86-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="e8a86-213">Обновление диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e8a86-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="e8a86-214">Устранение проблем диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e8a86-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
