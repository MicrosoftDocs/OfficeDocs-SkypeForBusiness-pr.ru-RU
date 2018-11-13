---
title: Планирование для диспетчера статистики для Скайп Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/23/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Сводка: Прочитайте сведения о диспетчере статистики для Скайп для Business Server.'
ms.openlocfilehash: b843cf44edf0c566a1c0a8a99a5ba9380d41c306
ms.sourcegitcommit: 8536a34cb13d40b30f84d95e6df10542ef85c36d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26292978"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="d2346-103">Планирование для диспетчера статистики для Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="d2346-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="d2346-104">**Сводка:** В данном разделе приведены сведения о диспетчере статистики для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="d2346-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="d2346-105">Диспетчер статистики для Скайп для Business Server представляет собой мощное средство, которое позволяет просматривать Скайп для данные о работоспособности и производительности Business Server в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="d2346-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="d2346-106">Опрос данные о производительности на серверах сотни раз в несколько секунд и просмотреть результаты мгновенно на веб-сайт диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="d2346-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="d2346-107">Диспетчер Статистика используется для обнаружения проблем производительности системы, просмотреть результаты плановых изменений в среду, отслеживать решение простоев и многое другое.</span><span class="sxs-lookup"><span data-stu-id="d2346-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="d2346-108">По умолчанию Статистика диспетчера следует настроить пороговые значения индикатор работоспособности ключ (KHI) и может быть изменен в соответствии с потребностями вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="d2346-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="d2346-109">Статистика диспетчера можно развернуть в локальном развертывании, в которой один сервер содержит все компоненты диспетчера статистики на сервере.</span><span class="sxs-lookup"><span data-stu-id="d2346-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="d2346-110">Дополнительные сведения о развертывании диспетчера статистики [Развертывание диспетчера статистики для Скайп для Business Server](deploy.md)см.</span><span class="sxs-lookup"><span data-stu-id="d2346-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="d2346-111">Если у вас уже есть существующее развертывание из диспетчера статистики, но вы еще не был обновлен для версии 2.0, просмотрите [новые возможности версии 2.0](plan.md#BKMK_WhatsNew) и [Обновление статистики Manager для Скайп для Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="d2346-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="d2346-112">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="d2346-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="d2346-113">Функции и возможности</span><span class="sxs-lookup"><span data-stu-id="d2346-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="d2346-114">Новые возможности версии 2.0</span><span class="sxs-lookup"><span data-stu-id="d2346-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="d2346-115">Компоненты</span><span class="sxs-lookup"><span data-stu-id="d2346-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="d2346-116">Локальное развертывание</span><span class="sxs-lookup"><span data-stu-id="d2346-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="d2346-117">Требования</span><span class="sxs-lookup"><span data-stu-id="d2346-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="d2346-118">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="d2346-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="d2346-119">Функции и возможности</span><span class="sxs-lookup"><span data-stu-id="d2346-119">Features and capabilities</span></span>
<span data-ttu-id="d2346-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="d2346-120"></span></span>

<span data-ttu-id="d2346-121">Статистика диспетчера позволяет:</span><span class="sxs-lookup"><span data-stu-id="d2346-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="d2346-122">Просмотр исходных данных для всех серверов в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="d2346-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="d2346-123">(Данные составляет очень высокая частота и отправляются на веб-сайт в менее одной секунды.)</span><span class="sxs-lookup"><span data-stu-id="d2346-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="d2346-124">Просмотр данных, который собирается для определенной роли; к примеру сервера переднего плана, сервер-посредник, пограничного сервера и т. д.</span><span class="sxs-lookup"><span data-stu-id="d2346-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="d2346-125">Перейти на просмотр данных для конкретных узлов, определенных пулы на сайте и затем конкретных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="d2346-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="d2346-126">Создание настраиваемых диаграмм, выбранный счетчики отображаемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d2346-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="d2346-127">Изменение масштаба и сдвиг на обоих x и y оси или на оси x только.</span><span class="sxs-lookup"><span data-stu-id="d2346-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="d2346-128">Используйте диапазонов или точек времени для фильтрации данных.</span><span class="sxs-lookup"><span data-stu-id="d2346-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="d2346-129">Просмотр производительности сервера, на основании показателей работоспособности установленного ключа (KHIs).</span><span class="sxs-lookup"><span data-stu-id="d2346-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="d2346-130">KHIs представления коллекции счетчиков производительности с помощью определенного диапазона работоспособны.</span><span class="sxs-lookup"><span data-stu-id="d2346-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="d2346-131">Просмотрите подробные показатели для каждого счетчика.</span><span class="sxs-lookup"><span data-stu-id="d2346-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="d2346-132">Сравнение данных в нескольких заполнение или серверов.</span><span class="sxs-lookup"><span data-stu-id="d2346-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="d2346-133">Просмотр скрытых счетчик отчетов для идентификации агентов, которые не являются отчетность текущих данных в службу панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d2346-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="d2346-134">Сохраните конкретный экземпляр данных диаграммы в файл.</span><span class="sxs-lookup"><span data-stu-id="d2346-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="d2346-135">Просмотр KHIs в режиме реального времени, включая обновления.</span><span class="sxs-lookup"><span data-stu-id="d2346-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="d2346-136">Если включено представление журнала, отображаются только новых ошибок.</span><span class="sxs-lookup"><span data-stu-id="d2346-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="d2346-137">Просмотр всех KHIs за один раз</span><span class="sxs-lookup"><span data-stu-id="d2346-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="d2346-138">Просмотр KHIs с сервера (альбомная view)</span><span class="sxs-lookup"><span data-stu-id="d2346-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="d2346-139">Определения представлений KHI</span><span class="sxs-lookup"><span data-stu-id="d2346-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="d2346-140">Новые возможности версии 2.0</span><span class="sxs-lookup"><span data-stu-id="d2346-140">What's new in Release 2.0</span></span>
<span data-ttu-id="d2346-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="d2346-141"></span></span>

<span data-ttu-id="d2346-142">Ниже описаны новые возможности версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="d2346-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="d2346-143">Если у вас есть существующее развертывание из диспетчера статистики и еще не было выполнено обновление, см.: [Обновление статистики диспетчер для Скайп для Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="d2346-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="d2346-144">Сценарий представления были добавлены для пограничного сервера мультимедиа, состояния Fabric, отработки отказа и регистрации сценариев.</span><span class="sxs-lookup"><span data-stu-id="d2346-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="d2346-145">Многие новые счетчики были добавлены к серверу SQL Server, более Скайп для счетчики использования бизнес и т. д.</span><span class="sxs-lookup"><span data-stu-id="d2346-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="d2346-146">Интеграция узел наблюдателя для агента диспетчера статистики - при агент установлен на узел-наблюдатель, регистрируются статистики искусственная транзакция как счетчики обратно к диспетчеру статистики.</span><span class="sxs-lookup"><span data-stu-id="d2346-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="d2346-147">Множество улучшений надежности и производительности.</span><span class="sxs-lookup"><span data-stu-id="d2346-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="d2346-148">Для проверки версии выполняется веб-сайт диспетчера статистики:</span><span class="sxs-lookup"><span data-stu-id="d2346-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="d2346-149">Откройте в обозревателе файлов (каталог по умолчанию) C:\Program Files\Skype для Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="d2346-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="d2346-150">Щелкните правой кнопкой мыши на StatsManHubWebSite.dll и просмотрите его свойства</span><span class="sxs-lookup"><span data-stu-id="d2346-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="d2346-151">Версия продукта будет показана в сведениях описания.</span><span class="sxs-lookup"><span data-stu-id="d2346-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="d2346-152">Компоненты</span><span class="sxs-lookup"><span data-stu-id="d2346-152">Components</span></span>
<span data-ttu-id="d2346-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="d2346-153"></span></span>

<span data-ttu-id="d2346-154">Статистика диспетчера состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="d2346-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="d2346-155">**Агент.**</span><span class="sxs-lookup"><span data-stu-id="d2346-155">**Agent.**</span></span> <span data-ttu-id="d2346-156">Упрощенный агентов, на котором выполняется на каждом сервере, отслеживаемые.</span><span class="sxs-lookup"><span data-stu-id="d2346-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="d2346-157">Агент позволяет настраиваемая высокая частота опроса счетчиков производительности с помощью локального статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="d2346-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="d2346-158">**Прослушиватель.**</span><span class="sxs-lookup"><span data-stu-id="d2346-158">**Listener.**</span></span> <span data-ttu-id="d2346-159">API со стороны сервера, который получает данные из всех агентов и сводит воедино данные в совокупности.</span><span class="sxs-lookup"><span data-stu-id="d2346-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="d2346-160">**Сервер-концентратор.**</span><span class="sxs-lookup"><span data-stu-id="d2346-160">**Hub.**</span></span> <span data-ttu-id="d2346-161">Служит в качестве клиентского интерфейса API для системы, запускается на веб-серверах и для клиентов, подключенных через веб-сайт содержит обновления данных в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="d2346-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="d2346-162">(Сервер-концентратор автоматически устанавливается как часть веб-сайта msi).</span><span class="sxs-lookup"><span data-stu-id="d2346-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="d2346-163">**Веб-сайта.**</span><span class="sxs-lookup"><span data-stu-id="d2346-163">**Website.**</span></span> <span data-ttu-id="d2346-164">Пользовательский интерфейс, который собирает все функции, доступные в системе.</span><span class="sxs-lookup"><span data-stu-id="d2346-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="d2346-165">Кроме того диспетчер статистики требует **Redis**, сервер структуры данных покупать открыть для кэширования в памяти.</span><span class="sxs-lookup"><span data-stu-id="d2346-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="d2346-166">Дополнительные сведения о загрузке Redis [Развертывание диспетчера статистики](deploy.md#BKMK_Deploy) см.</span><span class="sxs-lookup"><span data-stu-id="d2346-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="d2346-167">Локальное развертывание</span><span class="sxs-lookup"><span data-stu-id="d2346-167">On-premises deployment</span></span>
<span data-ttu-id="d2346-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="d2346-168"></span></span>

<span data-ttu-id="d2346-169">При локальном развертывании одного сервера служит для размещения всех компонентов диспетчера статистики на сервере.</span><span class="sxs-lookup"><span data-stu-id="d2346-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="d2346-170">На следующей схеме показано локальное развертывание, в котором размещаются веб-сайт диспетчера статистики, сервер-концентратор, прослушиватель и Redis кэширование системы на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d2346-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="d2346-171">Статистика диспетчера мониторинга три Скайп бизнеса на серверах, каждый из которых имеет один агент передачи данных в прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="d2346-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="d2346-172">Пользователи подключаться к одного веб-сайта, чтобы просмотреть все данные, собранные диспетчером статистики:</span><span class="sxs-lookup"><span data-stu-id="d2346-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Диспетчер статистики: локальное развертывание](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="d2346-174">Требования</span><span class="sxs-lookup"><span data-stu-id="d2346-174">Requirements</span></span>
<span data-ttu-id="d2346-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="d2346-175"></span></span>

<span data-ttu-id="d2346-176">Необходимо будет необходимо учитывать следующие требования к программному обеспечению, сети и оборудования, перед развертыванием диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="d2346-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="d2346-177">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="d2346-177">Software requirements</span></span>

- <span data-ttu-id="d2346-178">Windows Server 2016 и 2019</span><span class="sxs-lookup"><span data-stu-id="d2346-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="d2346-179">Службы IIS (автоматически)</span><span class="sxs-lookup"><span data-stu-id="d2346-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="d2346-180">Redis</span><span class="sxs-lookup"><span data-stu-id="d2346-180">Redis</span></span>

- <span data-ttu-id="d2346-181">Статистика диспетчера служб (автоматически устанавливается)</span><span class="sxs-lookup"><span data-stu-id="d2346-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="d2346-182">PSExec - требуется агент удаленного развертывания</span><span class="sxs-lookup"><span data-stu-id="d2346-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="d2346-183">.NET 4.5 (входит в состав 2012 R2) - необходимые для агентов и компоненты на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="d2346-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="d2346-184">Требования к сети</span><span class="sxs-lookup"><span data-stu-id="d2346-184">Networking requirements</span></span>


|<span data-ttu-id="d2346-185">**Размещение сервера**</span><span class="sxs-lookup"><span data-stu-id="d2346-185">**Hosting server**</span></span>|<span data-ttu-id="d2346-186">**Агенты**</span><span class="sxs-lookup"><span data-stu-id="d2346-186">**Agents**</span></span>|<span data-ttu-id="d2346-187">**Прослушиватель**</span><span class="sxs-lookup"><span data-stu-id="d2346-187">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d2346-188">Минимальные гигабит полнодуплексную сети.</span><span class="sxs-lookup"><span data-stu-id="d2346-188">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="d2346-189">Исходящие TCP-порт 8443 (настраиваемые порт номер) для взаимодействия с прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="d2346-189">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="d2346-190">Прослушивающий порт должны быть одинаковыми на всех серверах.</span><span class="sxs-lookup"><span data-stu-id="d2346-190">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="d2346-191">Входящий трафик TCP-порт 80 или 443 open для размещения веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="d2346-191">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="d2346-192">Входящий трафик TCP-порт 8443 (номер порта настраиваемые) для агентов для связи с ним.</span><span class="sxs-lookup"><span data-stu-id="d2346-192">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="d2346-193">Во время установки автоматически создаются для прослушиватель и веб-сайт, порты брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="d2346-193">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="d2346-194">Для агентов установки предполагается, что исходящие подключения TCP, разрешены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d2346-194">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="d2346-195">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="d2346-195">Hardware requirements</span></span>

<span data-ttu-id="d2346-196">В локальном развертывании, в которой один сервер содержит все компоненты диспетчера статистики на сервере, на сервере с 16 ГБ оперативной памяти и 4 Процессора должна появиться возможность поддержки в среднем около 150 примеры в секунду.</span><span class="sxs-lookup"><span data-stu-id="d2346-196">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="d2346-197">Чтобы определить, сколько может поддерживать счетчики/агенты, используйте следующие вычисления:</span><span class="sxs-lookup"><span data-stu-id="d2346-197">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="d2346-198">100 серверов \*80 счетчики \* 1 примера в минуту из каждого агента аудио- и 60 секунд = ~ 133 примеры в секунду.</span><span class="sxs-lookup"><span data-stu-id="d2346-198">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="d2346-199">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="d2346-199">Security considerations</span></span>
<span data-ttu-id="d2346-200"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="d2346-200"></span></span>

<span data-ttu-id="d2346-201">Шифрования трафика между серверами.</span><span class="sxs-lookup"><span data-stu-id="d2346-201">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="d2346-202">Зашифрованный HTTPS-трафик будут отправляться через порт 8443 (по умолчанию) от агента на сервере прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="d2346-202">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="d2346-203">Агент проверит отпечаток SSL на сервере, чтобы убедиться, что сервер прослушивателя не ожидается получателя.</span><span class="sxs-lookup"><span data-stu-id="d2346-203">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="d2346-204">Обратите внимание, что агент использует проверку по отпечатку сертификата (вместо проверки цепочки сертификатов).</span><span class="sxs-lookup"><span data-stu-id="d2346-204">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="d2346-205">Он не будет выполнять полную проверку сертификатов, так как возможно использование самозаверяющих сертификатов.</span><span class="sxs-lookup"><span data-stu-id="d2346-205">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="d2346-206">После агент соблюдены прослушиватель подлинный, пароль будут представлены агентом, который затем проверяется прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="d2346-206">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="d2346-207">Агент начинается передачи данных производительности через подключение к прослушивателю.</span><span class="sxs-lookup"><span data-stu-id="d2346-207">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d2346-208">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="d2346-208">For more information</span></span>
<span data-ttu-id="d2346-209"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="d2346-209"></span></span>

<span data-ttu-id="d2346-210">Дополнительные сведения приведены далее.</span><span class="sxs-lookup"><span data-stu-id="d2346-210">For more information, see the following:</span></span>

- [<span data-ttu-id="d2346-211">Развертывание диспетчера статистики для Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="d2346-211">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="d2346-212">Обновление статистики Manager для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="d2346-212">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="d2346-213">Устранение неполадок в диспетчер статистики для Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="d2346-213">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)

- [<span data-ttu-id="d2346-214">Блог, посвященный диспетчеру статистики Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d2346-214">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/dodeitte/2015/10/24/skype-for-business-server-real-time-statistics-manager)


