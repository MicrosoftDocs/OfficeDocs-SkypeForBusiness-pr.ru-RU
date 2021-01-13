---
title: Планирование диспетчера статистики в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: Сводка. В этом разделе вы узнаете о диспетчере статистики в Skype для бизнеса Server.
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821829"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="6f35d-103">Планирование диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f35d-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="6f35d-104">**Сводка:** В этом разделе вы узнаете о диспетчере статистики в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6f35d-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="6f35d-105">Диспетчер статистики для Skype для бизнеса Server — это мощное средство, которое позволяет просматривать данные о работоспособности и производительности Skype для бизнеса Server в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="6f35d-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="6f35d-106">Вы можете опросить данные о производительности на нескольких сотнях серверов каждые несколько секунд и мгновенно просмотреть результаты на веб-сайте диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="6f35d-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="6f35d-107">Диспетчер статистики можно использовать для выявления текущих проблем с производительностью, просмотра результатов запланированного изменения среды, отслеживания разрешения с отключений и многое другое.</span><span class="sxs-lookup"><span data-stu-id="6f35d-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="6f35d-108">Диспетчер статистики настроен с порогами ключевого индикатора состояния (KHI) и может быть настроен в соответствии с уникальными потребностями развертывания.</span><span class="sxs-lookup"><span data-stu-id="6f35d-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="6f35d-109">Диспетчер статистики можно развернуть в локальном развертывании, где на одном сервере размещаются все серверные компоненты диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="6f35d-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="6f35d-110">Дополнительные сведения о развертывании диспетчера статистики см. в сведениях о развертывании диспетчера статистики [в Skype для бизнеса Server.](deploy.md)</span><span class="sxs-lookup"><span data-stu-id="6f35d-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="6f35d-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="6f35d-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="6f35d-112">В этом разделе содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="6f35d-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="6f35d-113">Функции и возможности</span><span class="sxs-lookup"><span data-stu-id="6f35d-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="6f35d-114">Новые возможности выпуска 2.0</span><span class="sxs-lookup"><span data-stu-id="6f35d-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="6f35d-115">Компоненты</span><span class="sxs-lookup"><span data-stu-id="6f35d-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="6f35d-116">Локальное развертывание</span><span class="sxs-lookup"><span data-stu-id="6f35d-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="6f35d-117">Требования</span><span class="sxs-lookup"><span data-stu-id="6f35d-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="6f35d-118">Вопросы безопасности</span><span class="sxs-lookup"><span data-stu-id="6f35d-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="6f35d-119">Функции и возможности</span><span class="sxs-lookup"><span data-stu-id="6f35d-119">Features and capabilities</span></span>
<span data-ttu-id="6f35d-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="6f35d-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="6f35d-121">Диспетчер статистики позволяет:</span><span class="sxs-lookup"><span data-stu-id="6f35d-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="6f35d-122">Просмотр необработанных данных для всех серверов в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="6f35d-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="6f35d-123">(Данные высмеяются с очень высокой скоростью и отправляются на веб-сайт менее чем за одну секунду.)</span><span class="sxs-lookup"><span data-stu-id="6f35d-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="6f35d-124">Просмотр данных, агрегированных для определенной роли; например, сервер переднего сервера, сервер-посредник, сервер-посредник и так далее.</span><span class="sxs-lookup"><span data-stu-id="6f35d-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="6f35d-125">Прокрутка для просмотра данных для определенных сайтов, определенных пулов на сайте, а затем для определенных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="6f35d-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="6f35d-126">Создайте пользовательские диаграммы, чтобы выбранные счетчики по умолчанию были показаны.</span><span class="sxs-lookup"><span data-stu-id="6f35d-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="6f35d-127">Масштабирование и панорамирование осей x и y или только на оси X.</span><span class="sxs-lookup"><span data-stu-id="6f35d-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="6f35d-128">Используйте диапазоны дат или точки времени для фильтрации данных.</span><span class="sxs-lookup"><span data-stu-id="6f35d-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="6f35d-129">Просмотр производительности сервера на основе установленных ключевых индикаторов работоспособности (KHIS).</span><span class="sxs-lookup"><span data-stu-id="6f35d-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="6f35d-130">KhIs представляют коллекцию счетчиков производительности с определенным диапазоном работоспособности.</span><span class="sxs-lookup"><span data-stu-id="6f35d-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="6f35d-131">Просмотр подробных метрик для каждого счетчика.</span><span class="sxs-lookup"><span data-stu-id="6f35d-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="6f35d-132">Сравните данные для нескольких пользователей или серверов.</span><span class="sxs-lookup"><span data-stu-id="6f35d-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="6f35d-133">Просмотр отчетов счетчиков с зависанием, чтобы определить агентов, которые не сообщают службе панели мониторинга текущие данные.</span><span class="sxs-lookup"><span data-stu-id="6f35d-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="6f35d-134">Сохраните определенный экземпляр данных диаграммы в файл.</span><span class="sxs-lookup"><span data-stu-id="6f35d-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="6f35d-135">Просмотр KHIS в режиме реального времени, включая обновления.</span><span class="sxs-lookup"><span data-stu-id="6f35d-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="6f35d-136">Если представление истории включено, будут показаны только новые ошибки.</span><span class="sxs-lookup"><span data-stu-id="6f35d-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="6f35d-137">Просмотр всех КХИ за один раз</span><span class="sxs-lookup"><span data-stu-id="6f35d-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="6f35d-138">Просмотр КХИ по серверам (альбомная точка зрения)</span><span class="sxs-lookup"><span data-stu-id="6f35d-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="6f35d-139">Просмотр определений KHI</span><span class="sxs-lookup"><span data-stu-id="6f35d-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="6f35d-140">Новые возможности выпуска 2.0</span><span class="sxs-lookup"><span data-stu-id="6f35d-140">What's new in Release 2.0</span></span>
<span data-ttu-id="6f35d-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="6f35d-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="6f35d-142">Ниже описаны новые возможности выпуска 2.0.</span><span class="sxs-lookup"><span data-stu-id="6f35d-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="6f35d-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="6f35d-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="6f35d-144">Добавлены представления сценариев для сценариев Edge Media, Fabric Health, отбойа пула и регистрации.</span><span class="sxs-lookup"><span data-stu-id="6f35d-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="6f35d-145">Добавлено множество новых счетчиков для SQL серверов, больше счетчиков использования Skype для бизнеса и так далее.</span><span class="sxs-lookup"><span data-stu-id="6f35d-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="6f35d-146">Интеграция узла-watcher для агента диспетчера статистики — если агент установлен на узле-watcher, он будет сообщать статистику искусственных транзакций в качестве счетчиков обратно в диспетчер статистики.</span><span class="sxs-lookup"><span data-stu-id="6f35d-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="6f35d-147">Многочисленные улучшения надежности и производительности.</span><span class="sxs-lookup"><span data-stu-id="6f35d-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="6f35d-148">Чтобы проверить версию веб-сайта диспетчера статистики, вы можете:</span><span class="sxs-lookup"><span data-stu-id="6f35d-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="6f35d-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="6f35d-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="6f35d-150">Щелкните правой кнопкой мыши StatsManHubWebSite.dll и просмотрете его свойства</span><span class="sxs-lookup"><span data-stu-id="6f35d-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="6f35d-151">Версия продукта будет показана в описании.</span><span class="sxs-lookup"><span data-stu-id="6f35d-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="6f35d-152">Компоненты</span><span class="sxs-lookup"><span data-stu-id="6f35d-152">Components</span></span>
<span data-ttu-id="6f35d-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="6f35d-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="6f35d-154">Диспетчер статистики состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="6f35d-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="6f35d-155">**Агент.**</span><span class="sxs-lookup"><span data-stu-id="6f35d-155">**Agent.**</span></span> <span data-ttu-id="6f35d-156">Облегченный агент, который выполняется на каждом отслеживаемом сервере.</span><span class="sxs-lookup"><span data-stu-id="6f35d-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="6f35d-157">Агент позволяет настраивать высокоскоростной опрос счетчиков производительности с помощью локального агрегирования.</span><span class="sxs-lookup"><span data-stu-id="6f35d-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="6f35d-158">**Прослушиватель.**</span><span class="sxs-lookup"><span data-stu-id="6f35d-158">**Listener.**</span></span> <span data-ttu-id="6f35d-159">Серверный API, который получает данные от всех агентов и собирает данные между совокупностями.</span><span class="sxs-lookup"><span data-stu-id="6f35d-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="6f35d-160">**Hub.**</span><span class="sxs-lookup"><span data-stu-id="6f35d-160">**Hub.**</span></span> <span data-ttu-id="6f35d-161">Выступает в качестве клиентского API для системы, работает на веб-серверах и предоставляет обновления данных в режиме реального времени клиентам, подключенным через веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="6f35d-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="6f35d-162">(Концентратор автоматически устанавливается как часть MSI веб-сайта.)</span><span class="sxs-lookup"><span data-stu-id="6f35d-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="6f35d-163">**Веб-сайт.**</span><span class="sxs-lookup"><span data-stu-id="6f35d-163">**Website.**</span></span> <span data-ttu-id="6f35d-164">Пользовательский интерфейс, который объединяет все функции, доступные в системе.</span><span class="sxs-lookup"><span data-stu-id="6f35d-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="6f35d-165">Кроме того, диспетчеру статистики требуется **Redis**, сервер структуры данных с открытым исходным кодом для кэша в памяти.</span><span class="sxs-lookup"><span data-stu-id="6f35d-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="6f35d-166">Дополнительные сведения о загрузке Redis см. в диспетчере [развертывания статистики.](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="6f35d-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="6f35d-167">Локальное развертывание</span><span class="sxs-lookup"><span data-stu-id="6f35d-167">On-premises deployment</span></span>
<span data-ttu-id="6f35d-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="6f35d-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="6f35d-169">В локальном развертывании на одном сервере размещены все серверные компоненты диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="6f35d-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="6f35d-170">На следующей схеме показано локальное развертывание, в котором веб-сайт диспетчера статистики, концентратор, прослушиватель и система кэшации Redis размещены на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6f35d-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="6f35d-171">Диспетчер статистики отслеживает три сервера Skype для бизнеса, каждый из которых имеет один агент, передающий данные прослушивательу.</span><span class="sxs-lookup"><span data-stu-id="6f35d-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="6f35d-172">Пользователи подключаются к одному веб-сайту для просмотра всех данных, агрегированных диспетчером статистики:</span><span class="sxs-lookup"><span data-stu-id="6f35d-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Локальное развертывание диспетчера статистики](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="6f35d-174">Требования</span><span class="sxs-lookup"><span data-stu-id="6f35d-174">Requirements</span></span>
<span data-ttu-id="6f35d-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="6f35d-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="6f35d-176">Перед развертыванием диспетчера статистики необходимо учесть следующие требования к программному обеспечению, сети и оборудованию.</span><span class="sxs-lookup"><span data-stu-id="6f35d-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="6f35d-177">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="6f35d-177">Software requirements</span></span>

- <span data-ttu-id="6f35d-178">Windows Server 2016 и 2019</span><span class="sxs-lookup"><span data-stu-id="6f35d-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="6f35d-179">IIS (автоматически установлено)</span><span class="sxs-lookup"><span data-stu-id="6f35d-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="6f35d-180">Redis</span><span class="sxs-lookup"><span data-stu-id="6f35d-180">Redis</span></span>

- <span data-ttu-id="6f35d-181">Службы диспетчера статистики (автоматически установленные)</span><span class="sxs-lookup"><span data-stu-id="6f35d-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="6f35d-182">PSExec — требуется для развертывания удаленного агента</span><span class="sxs-lookup"><span data-stu-id="6f35d-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="6f35d-183">.NET 4.5 (входит в состав 2012 R2) — требуется для агентов и серверных компонентов</span><span class="sxs-lookup"><span data-stu-id="6f35d-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="6f35d-184">Скачайте [Skype для бизнеса Server Real-Time statistics Manager (64-битная)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="6f35d-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="6f35d-185">Требования к сети</span><span class="sxs-lookup"><span data-stu-id="6f35d-185">Networking requirements</span></span>


|<span data-ttu-id="6f35d-186">**Сервер размещения**</span><span class="sxs-lookup"><span data-stu-id="6f35d-186">**Hosting server**</span></span>|<span data-ttu-id="6f35d-187">**Agents**</span><span class="sxs-lookup"><span data-stu-id="6f35d-187">**Agents**</span></span>|<span data-ttu-id="6f35d-188">**Прослушиватель**</span><span class="sxs-lookup"><span data-stu-id="6f35d-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6f35d-189">Минимальная гигабитная полнодуплексная сеть.</span><span class="sxs-lookup"><span data-stu-id="6f35d-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="6f35d-190">Исходящие TCP-порты 8443 (настраиваемый номер порта) для связи с прослушивательом.</span><span class="sxs-lookup"><span data-stu-id="6f35d-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="6f35d-191">Порт прослушиватель должен быть одинаковым на всех серверах.</span><span class="sxs-lookup"><span data-stu-id="6f35d-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="6f35d-192">Входящий TCP-порт 80 или 443, открытый для сайта.</span><span class="sxs-lookup"><span data-stu-id="6f35d-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="6f35d-193">Входящий TCP-порт 8443 (настраиваемый номер порта) для связи агентов с ним.</span><span class="sxs-lookup"><span data-stu-id="6f35d-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="6f35d-194">Во время установки порты брандмауэра для прослушиватель и веб-сайта создаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="6f35d-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="6f35d-195">Для агентов установка предполагает, что исходящие подключения TCP разрешены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6f35d-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="6f35d-196">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="6f35d-196">Hardware requirements</span></span>

<span data-ttu-id="6f35d-197">В локальном развертывании, где на одном сервере размещены все серверные компоненты диспетчера статистики, сервер с 16 ГБ ОЗУ и 4 ЦП должен поддерживать в среднем около 150 образцов в секунду.</span><span class="sxs-lookup"><span data-stu-id="6f35d-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="6f35d-198">Чтобы определить, сколько счетчиков или агентов можно поддерживать, используйте следующее вычисление:</span><span class="sxs-lookup"><span data-stu-id="6f35d-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="6f35d-199">100 серверов 80 счетчиков по 1 выборке в минуту от каждого агента \* \* / 60 секунд = ~ 133 образцов в секунду.</span><span class="sxs-lookup"><span data-stu-id="6f35d-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="6f35d-200">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="6f35d-200">Security considerations</span></span>
<span data-ttu-id="6f35d-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="6f35d-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="6f35d-202">Весь трафик между серверами шифруется.</span><span class="sxs-lookup"><span data-stu-id="6f35d-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="6f35d-203">Зашифрованный HTTPS-трафик будет отправлен через порт 8443 (по умолчанию) от агента на сервер прослушивателей.</span><span class="sxs-lookup"><span data-stu-id="6f35d-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="6f35d-204">Агент проверит отпечаток SSL на сервере, чтобы убедиться, что сервер прослушиватель является ожидаемым получателем.</span><span class="sxs-lookup"><span data-stu-id="6f35d-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="6f35d-205">Обратите внимание, что агент использует проверку отпечатка сертификата (вместо проверки цепочки).</span><span class="sxs-lookup"><span data-stu-id="6f35d-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="6f35d-206">Он не будет делать полную проверку сертификатов, так как можно использовать самозаверяяние сертификатов.</span><span class="sxs-lookup"><span data-stu-id="6f35d-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="6f35d-207">После того как агент будет удовлетворены проверкой подлинности прослушиватель, агент получит пароль, который затем проверяется прослушивательом.</span><span class="sxs-lookup"><span data-stu-id="6f35d-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="6f35d-208">Агент начинает передавать данные о производительности через подключение к прослушивательу.</span><span class="sxs-lookup"><span data-stu-id="6f35d-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="6f35d-209">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="6f35d-209">For more information</span></span>
<span data-ttu-id="6f35d-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="6f35d-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="6f35d-211">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="6f35d-211">For more information, see the following:</span></span>

- [<span data-ttu-id="6f35d-212">Развертывание диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f35d-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="6f35d-213">Обновление диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f35d-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="6f35d-214">Устранение проблем диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f35d-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
