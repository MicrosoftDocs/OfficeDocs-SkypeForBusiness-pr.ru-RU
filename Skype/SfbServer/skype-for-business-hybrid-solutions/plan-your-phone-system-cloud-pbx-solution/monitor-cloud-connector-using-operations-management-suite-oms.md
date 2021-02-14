---
title: Отслеживание Cloud Connector с помощью Operations Management Suite (OMS)
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: В этом разделе вы узнаете, как отслеживать развертывание Cloud Connector версии 2.1 и более поздних версий с помощью Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359095"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="89cac-103">Отслеживание Cloud Connector с помощью Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="89cac-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="89cac-104">Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="89cac-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="89cac-105">После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="89cac-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="89cac-106">В этом разделе вы узнаете, как отслеживать развертывание Cloud Connector версии 2.1 и более поздних версий с помощью Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="89cac-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="89cac-107">Теперь вы можете отслеживать развертывание Cloud Connector версии 2.1 и более поздних версий с помощью Operations Management Suite (OMS), решения для управления облачными ИТ-ресурсами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="89cac-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="89cac-108">Аналитика журналов OMS позволяет отслеживать и анализировать доступность и производительность ресурсов, включая физические и виртуальные машины.</span><span class="sxs-lookup"><span data-stu-id="89cac-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="89cac-109">Дополнительные сведения об OMS и Log Analytics см. в подмносях "Что такое [Operations Management Suite (OMS)"?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="89cac-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="89cac-110">В этом разделе содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="89cac-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="89cac-111">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="89cac-111">Prerequisites</span></span>

- <span data-ttu-id="89cac-112">Настройка Cloud Connector для использования OMS</span><span class="sxs-lookup"><span data-stu-id="89cac-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="89cac-113">Настройка OMS</span><span class="sxs-lookup"><span data-stu-id="89cac-113">Configure OMS</span></span>

- <span data-ttu-id="89cac-114">Анализ оповещений в репозитории Log Analytics</span><span class="sxs-lookup"><span data-stu-id="89cac-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="89cac-115">Рекомендуемый набор мониторинга</span><span class="sxs-lookup"><span data-stu-id="89cac-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="89cac-116">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="89cac-116">Prerequisites</span></span>

<span data-ttu-id="89cac-117">Прежде чем использовать OMS для отслеживания развертывания Cloud Connector, необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="89cac-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="89cac-118">**Учетная запись Azure и рабочее пространство OMS.**</span><span class="sxs-lookup"><span data-stu-id="89cac-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="89cac-119">Если у вас еще нет учетной записи Azure, ее необходимо создать, чтобы использовать аналитику журнала OMS.</span><span class="sxs-lookup"><span data-stu-id="89cac-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="89cac-120">Сведения о создании учетной записи Azure и создании рабочей области OMS см. в записи "Начало работы с рабочей областью [Log Analytics".](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)</span><span class="sxs-lookup"><span data-stu-id="89cac-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="89cac-121">**Cloud Connector версии 2.1 или более поздней**</span><span class="sxs-lookup"><span data-stu-id="89cac-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="89cac-122">**Для мониторинга Cloud Connector** требуется поиск в журнале Аналитика журналов.</span><span class="sxs-lookup"><span data-stu-id="89cac-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="89cac-123">Дополнительные сведения см. в записи об обновлении рабочей области [Azure Log Analytics до поиска в новых журналах.](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)</span><span class="sxs-lookup"><span data-stu-id="89cac-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="89cac-124">Настройка Cloud Connector для использования OMS</span><span class="sxs-lookup"><span data-stu-id="89cac-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="89cac-125">Вам потребуется настроить облачную среду Connector для использования OMS.</span><span class="sxs-lookup"><span data-stu-id="89cac-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="89cac-126">Для этого вам потребуется ваш ИД рабочей области OMS и ключ, которые можно найти на портале OMS следующим образом: Параметры -- Подключенные источники \> — \> Windows Servers:</span><span class="sxs-lookup"><span data-stu-id="89cac-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Снимок экрана для OMS Cloud Connector](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="89cac-128">Настройка Cloud Connector для использования OMS зависит от вашего сценария:</span><span class="sxs-lookup"><span data-stu-id="89cac-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="89cac-129">**Если вы устанавливаете новое** устройство Cloud Connector или хотите повторно развернуть его, выполните следующие действия перед запуском Install-CcAppliance:</span><span class="sxs-lookup"><span data-stu-id="89cac-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="89cac-130">В разделе CloudConnector.ini [Common] установите для параметра OMSEnabled параметр True.</span><span class="sxs-lookup"><span data-stu-id="89cac-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="89cac-131">При каждом развертывании или обновлении Cloud Connector будет пытаться автоматически установить агент OMS на ВМ.</span><span class="sxs-lookup"><span data-stu-id="89cac-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="89cac-132">Включив эту функцию, агент OMS сможет выдержать автоматическое обновление Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="89cac-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="89cac-133">Чтобы настроить ИД OMS и ключ, запустите Set-CcCredential -AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="89cac-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="89cac-134">**При установке агента OMS** на существующее устройство Cloud Connector выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="89cac-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="89cac-135">В разделе CloudConnector.ini [Common] установите OMSEnabled=true.</span><span class="sxs-lookup"><span data-stu-id="89cac-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="89cac-136">Запустите import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="89cac-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="89cac-137">Запустите install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="89cac-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="89cac-138">Если учетные данные OMSWorkspace никогда не задавались, при запуске командной системы Install-CcOMSAgent вам будет предложено в этом случае в этом случае.</span><span class="sxs-lookup"><span data-stu-id="89cac-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="89cac-139">**Если вы хотите обновить ИД или ключ рабочей области OMS на устройстве Cloud Connector, на которое уже установлен агент OMS:**</span><span class="sxs-lookup"><span data-stu-id="89cac-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="89cac-140">Чтобы настроить ИД OMS и ключ, запустите Set-CcCredential -AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="89cac-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="89cac-141">Чтобы применить обновления, запустите install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="89cac-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="89cac-142">**Для всех сценариев убедитесь, что агенты подключены следующим образом:**</span><span class="sxs-lookup"><span data-stu-id="89cac-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="89cac-143">На портале OMS перейдите в "Параметры — \> подключенные источники — \> серверы Windows".</span><span class="sxs-lookup"><span data-stu-id="89cac-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="89cac-144">Вы увидите список подключенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="89cac-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="89cac-145">Настройка OMS</span><span class="sxs-lookup"><span data-stu-id="89cac-145">Configure OMS</span></span>

<span data-ttu-id="89cac-146">Затем необходимо указать конфигурацию OMS с помощью портала OMS.</span><span class="sxs-lookup"><span data-stu-id="89cac-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="89cac-147">В частности, вам потребуется:</span><span class="sxs-lookup"><span data-stu-id="89cac-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="89cac-148">Укажите сведения о журналах событий и счетчиках производительности.</span><span class="sxs-lookup"><span data-stu-id="89cac-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="89cac-149">Создание оповещений</span><span class="sxs-lookup"><span data-stu-id="89cac-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="89cac-150">Указание сведений о журналах событий и счетчиках производительности</span><span class="sxs-lookup"><span data-stu-id="89cac-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="89cac-151">На портале OMS необходимо указать сведения о журналах событий и счетчиках производительности следующим образом:</span><span class="sxs-lookup"><span data-stu-id="89cac-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="89cac-152">Перейдите в "Параметры- Журналы событий Windows" и добавьте \> \> журналы событий для:</span><span class="sxs-lookup"><span data-stu-id="89cac-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="89cac-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="89cac-153">Lync Server</span></span>

   - <span data-ttu-id="89cac-154">Для приложений</span><span class="sxs-lookup"><span data-stu-id="89cac-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="89cac-155">В текстовом поле необходимо вручную ввести Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89cac-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="89cac-156">Он не появляется в качестве параметра в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="89cac-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="89cac-157">Дополнительные сведения см. в источниках [данных журнала событий Windows в Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="89cac-157">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="89cac-158">Перейдите в "Параметры" \> "Данные: \> счетчики производительности Windows" и добавьте счетчики производительности для:</span><span class="sxs-lookup"><span data-stu-id="89cac-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="89cac-159">**Счетчики уровня ОС.**</span><span class="sxs-lookup"><span data-stu-id="89cac-159">**OS level counters**.</span></span> <span data-ttu-id="89cac-160">Можно добавить счетчики уровня ОС, такие как использование процессора, использование памяти, использование сети или использовать существующие решения, такие как емкость и производительность, сетевой монитор производительности без явного добавления счетчиков.</span><span class="sxs-lookup"><span data-stu-id="89cac-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="89cac-161">Независимо от того, как вы решите отслеживать их, Майкрософт рекомендует отслеживать эти счетчики ОС.</span><span class="sxs-lookup"><span data-stu-id="89cac-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="89cac-162">**Счетчики Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="89cac-162">**Skype for Business counters**.</span></span> <span data-ttu-id="89cac-163">Skype для бизнеса предоставляет множество счетчиков.</span><span class="sxs-lookup"><span data-stu-id="89cac-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="89cac-164">Эти счетчики можно найти, войдя на любой сервер-посредник и открыв монитор производительности.</span><span class="sxs-lookup"><span data-stu-id="89cac-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="89cac-165">Эти счетчики начинаются со "LS:".</span><span class="sxs-lookup"><span data-stu-id="89cac-165">These counters start with "LS:".</span></span> <span data-ttu-id="89cac-166">Корпорация Майкрософт рекомендует как минимум начать со следующих счетчиков емкости и добавить другие счетчики, которые могут быть интересны:</span><span class="sxs-lookup"><span data-stu-id="89cac-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="89cac-167">Общее количество активных вызовов:</span><span class="sxs-lookup"><span data-stu-id="89cac-167">Total active calls:</span></span>

       - <span data-ttu-id="89cac-168">LS:MediationServer — текущие входящие вызовы \- (_Total)</span><span class="sxs-lookup"><span data-stu-id="89cac-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="89cac-169">LS:MediationServer — текущие исходящие вызовы \- (_Total)</span><span class="sxs-lookup"><span data-stu-id="89cac-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="89cac-170">Общее количество активных вызовов обхода мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="89cac-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="89cac-171">LS:MediationServer — входящие вызовы (_Total) \- активные вызовы обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="89cac-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="89cac-172">LS:MediationServer — исходящие вызовы (_Total) \- Активные вызовы обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="89cac-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="89cac-173">В текстовом поле необходимо вручную ввести счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="89cac-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="89cac-174">Они не отображаются в качестве параметров в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="89cac-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="89cac-175">Дополнительные сведения см. в источниках данных о производительности Windows и [Linux в log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="89cac-175">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="89cac-176">Создание оповещений</span><span class="sxs-lookup"><span data-stu-id="89cac-176">Create alerts</span></span>

<span data-ttu-id="89cac-177">В OMS существует два типа оповещений: количество оповещений о результатах и оповещения показателей.</span><span class="sxs-lookup"><span data-stu-id="89cac-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="89cac-178">Дополнительные сведения о создании оповещений см. в анализе журнала "Работа с правилами [оповещений".](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)</span><span class="sxs-lookup"><span data-stu-id="89cac-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="89cac-179">При создании оповещений следует учитывать следующее:</span><span class="sxs-lookup"><span data-stu-id="89cac-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="89cac-180">Убедитесь, что оповещение является оповещением "Число результатов", которое является выбором по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="89cac-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="89cac-181">Для демонстрационных запросов требуется, чтобы для "Число результатов" было установлено "Больше 0".</span><span class="sxs-lookup"><span data-stu-id="89cac-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="89cac-182">Рекомендуется установить для окне времени и частоты оповещений 5 минут.</span><span class="sxs-lookup"><span data-stu-id="89cac-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="89cac-183">Не рекомендуется включить "Подавление оповещений" для демонстрационных оповещений.</span><span class="sxs-lookup"><span data-stu-id="89cac-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="89cac-184">Для типичных сценариев оповещений Корпорация Майкрософт рекомендует создать пару оповещений: одно оповещение об ошибке и одно оповещение о сбросе.</span><span class="sxs-lookup"><span data-stu-id="89cac-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="89cac-185">Для оповещения об ошибке выберите "Критический уровень серьезности"; для оповещения о сбросе выберите "Информационный уровень серьезности".</span><span class="sxs-lookup"><span data-stu-id="89cac-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="89cac-186">В следующих разделах описывается создание примеров оповещений.</span><span class="sxs-lookup"><span data-stu-id="89cac-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="89cac-187">**Создайте пару оповещений: "RTCMEDSRV НЕ работает на серверах-посредниках" и "RTCMEDSRV снова работает на серверах-посредниках"**</span><span class="sxs-lookup"><span data-stu-id="89cac-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="89cac-188">Чтобы создать эту пару оповещений:</span><span class="sxs-lookup"><span data-stu-id="89cac-188">To create this alert pair:</span></span>

- <span data-ttu-id="89cac-189">Запрос оповещения об ошибке:</span><span class="sxs-lookup"><span data-stu-id="89cac-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="89cac-190">Запрос использует фильтр компьютера,  *где компьютер содержит "MediationServer"*  .</span><span class="sxs-lookup"><span data-stu-id="89cac-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="89cac-191">Фильтр выбирает только компьютер, имя которого содержит строку "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="89cac-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="89cac-192">Необходимо заменить фильтр собственным фильтром компьютера или просто удалить его.</span><span class="sxs-lookup"><span data-stu-id="89cac-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="89cac-193">Сложные строки можно создавать без регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="89cac-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="89cac-194">Дополнительные сведения см. в [операторе String.](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)</span><span class="sxs-lookup"><span data-stu-id="89cac-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="89cac-195">Вы также можете использовать регулярные выражения.</span><span class="sxs-lookup"><span data-stu-id="89cac-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="89cac-196">Кроме того, можно создать группу компьютеров, сэкономив поисковый запрос и используя эту группу в качестве фильтра компьютера в запросе оповещения.</span><span class="sxs-lookup"><span data-stu-id="89cac-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="89cac-197">Дополнительные сведения [см. в группах компьютеров при поиске в журнале Log Analytics.](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)</span><span class="sxs-lookup"><span data-stu-id="89cac-197">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="89cac-198">Для каждого компьютера запрос об ошибке получит последний журнал событий для запуска и остановки службы RTCMEDSRV.</span><span class="sxs-lookup"><span data-stu-id="89cac-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="89cac-199">Он возвращает один журнал, если последним событием является событие остановки службы; Он не возвращает ничего, если последним событием является событие запуска службы.</span><span class="sxs-lookup"><span data-stu-id="89cac-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="89cac-200">Одним словом, запрос возвратит список серверов, RTCMEDSRV которых остановлен в окне времени.</span><span class="sxs-lookup"><span data-stu-id="89cac-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="89cac-201">Запрос оповещения о сбросе:</span><span class="sxs-lookup"><span data-stu-id="89cac-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="89cac-202">Запрос на сброс делает именно противоположное, что и запрос об ошибке.</span><span class="sxs-lookup"><span data-stu-id="89cac-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="89cac-203">Для каждого компьютера он возвращает одно событие, если последним событием является событие запуска службы; Он не возвращает ничего, если последним событием является событие остановки службы.</span><span class="sxs-lookup"><span data-stu-id="89cac-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="89cac-204">**Создайте пару оповещений: "Слишком много одновременно звонков на серверах-посредниках" и "Одновременное выполнение вызовов возвращается к обычной нагрузке"**</span><span class="sxs-lookup"><span data-stu-id="89cac-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="89cac-205">Чтобы создать это оповещение:</span><span class="sxs-lookup"><span data-stu-id="89cac-205">To create this alert:</span></span>

- <span data-ttu-id="89cac-206">Запрос оповещения об ошибке:</span><span class="sxs-lookup"><span data-stu-id="89cac-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="89cac-207">Для каждого компьютера запрос получит последние счетчики для входящий и исходящие вызовы и суммирует эти два значения.</span><span class="sxs-lookup"><span data-stu-id="89cac-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="89cac-208">Он возвращает один журнал, если сумма превышает 500; Если этого не сделать, он не возвратит ничего.</span><span class="sxs-lookup"><span data-stu-id="89cac-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="89cac-209">Одним словом, запрос возвратит список серверов, количество одновременно звонков которых слишком много в течение окне времени.</span><span class="sxs-lookup"><span data-stu-id="89cac-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="89cac-210">Запрос оповещения о сбросе:</span><span class="sxs-lookup"><span data-stu-id="89cac-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="89cac-211">Запрос на сброс делает именно противоположное, что и запрос об ошибке.</span><span class="sxs-lookup"><span data-stu-id="89cac-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="89cac-212">Для каждого компьютера запрос получит последние счетчики для входящий и исходящие вызовы и суммирует эти два значения.</span><span class="sxs-lookup"><span data-stu-id="89cac-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="89cac-213">Он возвращает один журнал, если сумма меньше 500; В противном случае ничего не будет возвращено.</span><span class="sxs-lookup"><span data-stu-id="89cac-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="89cac-214">**Создание оповещения: "Использование ЦП \> 90 или RTCMEDIARELAY остановлено на серверах"**</span><span class="sxs-lookup"><span data-stu-id="89cac-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="89cac-215">Чтобы создать это оповещение, запрос:</span><span class="sxs-lookup"><span data-stu-id="89cac-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="89cac-216">Запрос будет получать все события счетчика использования процессора и остановки службы со всех компьютеров и возвращать один журнал, если использование процессора превышает 90 % или служба когда-либо останавливается.</span><span class="sxs-lookup"><span data-stu-id="89cac-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="89cac-217">Анализ оповещений в репозитории Log Analytics</span><span class="sxs-lookup"><span data-stu-id="89cac-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="89cac-218">Для анализа оповещений в репозитории используйте решение управления оповещениями.</span><span class="sxs-lookup"><span data-stu-id="89cac-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="89cac-219">Дополнительные сведения см. в решении [управления оповещениями в Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="89cac-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="89cac-220">Рекомендуемый минимальный набор мониторинга</span><span class="sxs-lookup"><span data-stu-id="89cac-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="89cac-221">Чтобы выявить проблемы с журналами событий и счетчиками производительности:</span><span class="sxs-lookup"><span data-stu-id="89cac-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="89cac-222">**Журналы событий.**</span><span class="sxs-lookup"><span data-stu-id="89cac-222">**Event logs.**</span></span> <span data-ttu-id="89cac-223">Для любой проблемы должна быть пара событий с одним набором событий, чтобы указать на то, что что-то не так, а с другой стороны, это означает, что все в порядке.</span><span class="sxs-lookup"><span data-stu-id="89cac-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="89cac-224">Для любого заданного периода времени это последнее записанное событие, которое указывает, не является ли что-то недопустимым для этого периода времени.</span><span class="sxs-lookup"><span data-stu-id="89cac-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="89cac-225">**Счетчики производительности.**</span><span class="sxs-lookup"><span data-stu-id="89cac-225">**Performance Counters.**</span></span> <span data-ttu-id="89cac-226">Для отслеживаемой счетчики должно быть пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="89cac-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="89cac-227">В следующей таблице перечислены службы, которые корпорация Майкрософт рекомендует контролировать, перечисляя ид событий остановки и запуска:</span><span class="sxs-lookup"><span data-stu-id="89cac-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="89cac-228">Имя службы</span><span class="sxs-lookup"><span data-stu-id="89cac-228">Service Name</span></span>  <br/> |<span data-ttu-id="89cac-229">Роль целевого сервера</span><span class="sxs-lookup"><span data-stu-id="89cac-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="89cac-230">Stop Event ID</span><span class="sxs-lookup"><span data-stu-id="89cac-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="89cac-231">ИД события запуска</span><span class="sxs-lookup"><span data-stu-id="89cac-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="89cac-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="89cac-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="89cac-233">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="89cac-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="89cac-234">25003</span><span class="sxs-lookup"><span data-stu-id="89cac-234">25003</span></span>  <br/> |<span data-ttu-id="89cac-235">25002</span><span class="sxs-lookup"><span data-stu-id="89cac-235">25002</span></span>  <br/> |
|<span data-ttu-id="89cac-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="89cac-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="89cac-237">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="89cac-237">Edge Server</span></span>  <br/> |<span data-ttu-id="89cac-238">12289</span><span class="sxs-lookup"><span data-stu-id="89cac-238">12289</span></span>  <br/> |<span data-ttu-id="89cac-239">12288</span><span class="sxs-lookup"><span data-stu-id="89cac-239">12288</span></span>  <br/> |
|<span data-ttu-id="89cac-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="89cac-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="89cac-241">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="89cac-241">Edge Server</span></span>  <br/> |<span data-ttu-id="89cac-242">19003</span><span class="sxs-lookup"><span data-stu-id="89cac-242">19003</span></span>  <br/> |<span data-ttu-id="89cac-243">19002</span><span class="sxs-lookup"><span data-stu-id="89cac-243">19002</span></span>  <br/> |
|<span data-ttu-id="89cac-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="89cac-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="89cac-245">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="89cac-245">Edge Server</span></span>  <br/> |<span data-ttu-id="89cac-246">22003</span><span class="sxs-lookup"><span data-stu-id="89cac-246">22003</span></span>  <br/> |<span data-ttu-id="89cac-247">22002</span><span class="sxs-lookup"><span data-stu-id="89cac-247">22002</span></span>  <br/> |

<span data-ttu-id="89cac-248">В следующей таблице перечислены проблемы сети, которые корпорация Майкрософт рекомендует контролировать:</span><span class="sxs-lookup"><span data-stu-id="89cac-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="89cac-249">Имя монитора</span><span class="sxs-lookup"><span data-stu-id="89cac-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="89cac-250">Роль целевого сервера</span><span class="sxs-lookup"><span data-stu-id="89cac-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="89cac-251">Выражение "Success Event ID" (Событие успешной работы)</span><span class="sxs-lookup"><span data-stu-id="89cac-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="89cac-252">Выражение error Event ID</span><span class="sxs-lookup"><span data-stu-id="89cac-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="89cac-253">Пример сбоя</span><span class="sxs-lookup"><span data-stu-id="89cac-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="89cac-254">Сбой подключения сервера-посредника к шлюзу</span><span class="sxs-lookup"><span data-stu-id="89cac-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="89cac-255">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="89cac-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="89cac-256">25062</span><span class="sxs-lookup"><span data-stu-id="89cac-256">25062</span></span>                              |                                  | <span data-ttu-id="89cac-257">25002</span><span class="sxs-lookup"><span data-stu-id="89cac-257">25002</span></span>  <br/>           |
| <span data-ttu-id="89cac-258">Сбой завершения вызова между сервером-посредником</span><span class="sxs-lookup"><span data-stu-id="89cac-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="89cac-259">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="89cac-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="89cac-260">25064</span><span class="sxs-lookup"><span data-stu-id="89cac-260">25064</span></span>                              |                                  | <span data-ttu-id="89cac-261">25002</span><span class="sxs-lookup"><span data-stu-id="89cac-261">25002</span></span>  <br/>           |
| <span data-ttu-id="89cac-262">Критические проблемы с сетью</span><span class="sxs-lookup"><span data-stu-id="89cac-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="89cac-263">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="89cac-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="89cac-264">14353</span><span class="sxs-lookup"><span data-stu-id="89cac-264">14353</span></span>                              |                                  | <span data-ttu-id="89cac-265">12288</span><span class="sxs-lookup"><span data-stu-id="89cac-265">12288</span></span>  <br/>           |

<span data-ttu-id="89cac-266">Ниже перечислены счетчики емкости вызовов, которые необходимо отслеживать.</span><span class="sxs-lookup"><span data-stu-id="89cac-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="89cac-267">Эти числа должны быть меньше 500 для выпуска Cloud Connector standard; менее 50 для минимального выпуска Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="89cac-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="89cac-268">LS:MediationServer — текущие входящие вызовы \- (_Total)</span><span class="sxs-lookup"><span data-stu-id="89cac-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="89cac-269">LS:MediationServer — текущие исходящие вызовы \- (_Total)</span><span class="sxs-lookup"><span data-stu-id="89cac-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="89cac-270">LS:MediationServer — входящие вызовы (_Total) \- активные вызовы обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="89cac-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="89cac-271">LS:MediationServer — исходящие вызовы (_Total) \- Активные вызовы обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="89cac-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="89cac-272">См. также</span><span class="sxs-lookup"><span data-stu-id="89cac-272">See also</span></span>

<span data-ttu-id="89cac-273">Дополнительные сведения о работе с OMS см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="89cac-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="89cac-274">Поиск данных с помощью поиска в журнале Аналитика</span><span class="sxs-lookup"><span data-stu-id="89cac-274">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="89cac-275">Справочник по языку Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="89cac-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="89cac-276">Понимание оповещений в log Analytics</span><span class="sxs-lookup"><span data-stu-id="89cac-276">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="89cac-277">Подключение компьютеров Windows к службе Log Analytics в Azure</span><span class="sxs-lookup"><span data-stu-id="89cac-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


