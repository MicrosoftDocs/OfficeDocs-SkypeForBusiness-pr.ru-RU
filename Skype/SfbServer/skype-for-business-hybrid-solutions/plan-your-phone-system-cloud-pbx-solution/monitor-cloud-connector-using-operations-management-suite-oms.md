---
title: Мониторинг соединителя облако с помощью пакетов управления Operations (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Прочтите этот раздел, чтобы узнать, как мониторинг соединителя облачных версии 2.1 и последующего развертывания с помощью пакетов управления Microsoft операции (OMS).
ms.openlocfilehash: 19946c0d7701d2fd31c1b41cae58e08cfdf4c52d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372190"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="051eb-103">Мониторинг соединителя облако с помощью пакетов управления Operations (OMS)</span><span class="sxs-lookup"><span data-stu-id="051eb-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="051eb-104">Прочтите этот раздел, чтобы узнать, как мониторинг соединителя облачных версии 2.1 и последующего развертывания с помощью пакетов управления Microsoft операции (OMS).</span><span class="sxs-lookup"><span data-stu-id="051eb-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="051eb-105">Теперь могут отслеживать соединителя облачных версии 2.1 и последующего развертывания с помощью операции управления Suite (OMS), Microsoft cloud решения по управлению ИТ.</span><span class="sxs-lookup"><span data-stu-id="051eb-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="051eb-106">Аналитика журнала OMS позволяет вам для мониторинга и анализа доступность и производительность ресурсов, включая физических и виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="051eb-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="051eb-107">Дополнительные сведения об OMS и анализа журнала можно [возможности пакет управления Operations (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="051eb-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span></span>

<span data-ttu-id="051eb-108">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="051eb-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="051eb-109">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="051eb-109">Prerequisites</span></span>

- <span data-ttu-id="051eb-110">Настройка соединителя облака для использования OMS</span><span class="sxs-lookup"><span data-stu-id="051eb-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="051eb-111">Настройка OMS</span><span class="sxs-lookup"><span data-stu-id="051eb-111">Configure OMS</span></span>

- <span data-ttu-id="051eb-112">Анализ оповещений в репозиторий анализа журнала</span><span class="sxs-lookup"><span data-stu-id="051eb-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="051eb-113">Рекомендуемый набор мониторинга</span><span class="sxs-lookup"><span data-stu-id="051eb-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="051eb-114">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="051eb-114">Prerequisites</span></span>

<span data-ttu-id="051eb-115">Прежде чем использовать OMS мониторинг развертывания облака соединителя, необходимо будет следующее:</span><span class="sxs-lookup"><span data-stu-id="051eb-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="051eb-116">**Учетная запись Azure и рабочей области OMS.**</span><span class="sxs-lookup"><span data-stu-id="051eb-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="051eb-117">Если нет учетной записи Azure, необходимо создать новое анализа журнала OMS.</span><span class="sxs-lookup"><span data-stu-id="051eb-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="051eb-118">Сведения о том, как создать учетную запись Azure и настройка OMS рабочей области в разделе [Начало работы с рабочей области для анализа журнала](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="051eb-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="051eb-119">**Соединитель облачных 2.1 или более поздняя версия**</span><span class="sxs-lookup"><span data-stu-id="051eb-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="051eb-120">**Новый поиск журнала анализа журнала** является обязательным для мониторинга облачных соединителя.</span><span class="sxs-lookup"><span data-stu-id="051eb-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="051eb-121">Дополнительные сведения содержатся в разделе [обновление рабочей области анализа журнала Azure новый поиск журнала](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="051eb-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="051eb-122">Настройка соединителя облака для использования OMS</span><span class="sxs-lookup"><span data-stu-id="051eb-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="051eb-123">Вам потребуется настроить вашей соединителя облака в локальную среду для использования OMS.</span><span class="sxs-lookup"><span data-stu-id="051eb-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="051eb-124">Для этого необходимо будет идентификатор рабочей области OMS и ключ, который можно найти с помощью портала OMS следующим образом: параметры--\>подключенных источников--\> серверов Windows:</span><span class="sxs-lookup"><span data-stu-id="051eb-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Снимок экрана OMS в Cloud Connector](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="051eb-126">Как настроить соединитель облака для использования OMS зависит от используемого сценария.</span><span class="sxs-lookup"><span data-stu-id="051eb-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="051eb-127">**При установке нового устройства соединителя облака или необходимо повторно развернуть устройства**, необходимо выполнить следующие действия перед запуском CcAppliance установки:</span><span class="sxs-lookup"><span data-stu-id="051eb-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

1. <span data-ttu-id="051eb-128">В файле CloudConnector.ini [распространенных] раздел установите для параметра OMSEnabled значение True.</span><span class="sxs-lookup"><span data-stu-id="051eb-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

    <span data-ttu-id="051eb-129">Каждый раз соединителя облачных развертывания или обновления, он будет попробуйте установить агента OMS автоматически на виртуальных машинах.</span><span class="sxs-lookup"><span data-stu-id="051eb-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="051eb-130">Эта функция включена, поэтому агент OMS, способное соединителя облачных автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="051eb-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

2. <span data-ttu-id="051eb-131">Чтобы настроить OMS идентификатор и ключ, выполните Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="051eb-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="051eb-132">**При установке агент OMS на существующего устройства облачных соединителя**, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="051eb-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

1. <span data-ttu-id="051eb-133">В файле CloudConnector.ini [распространенных] раздел задать OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="051eb-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

2. <span data-ttu-id="051eb-134">Выполните импорт CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="051eb-134">Run Import-CcConfiguration.</span></span> 

3. <span data-ttu-id="051eb-135">Запуск установки CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="051eb-135">Run Install-CcOMSAgent.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="051eb-136">Если учетные данные OMSWorkspace никогда не были установлены, предлагается для учетных данных при запуске install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="051eb-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="051eb-137">**Если вы хотите обновить OMS рабочей области идентификатор или ключ в облаке соединителя устройстве, который уже установлено агент OMS:**</span><span class="sxs-lookup"><span data-stu-id="051eb-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

1. <span data-ttu-id="051eb-138">Чтобы настроить OMS идентификатор и ключ, выполните Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="051eb-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

2. <span data-ttu-id="051eb-139">Чтобы применить обновления, запустите Install CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="051eb-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="051eb-140">**Для всех сценариев убедитесь, что агентам подключенные следующим образом:**</span><span class="sxs-lookup"><span data-stu-id="051eb-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="051eb-141">На портале OMS перейдите в раздел Параметры -\> подключенных источников -\> серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="051eb-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="051eb-142">Появится список подключенных устройствах.</span><span class="sxs-lookup"><span data-stu-id="051eb-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="051eb-143">Настройка OMS</span><span class="sxs-lookup"><span data-stu-id="051eb-143">Configure OMS</span></span>

<span data-ttu-id="051eb-144">Затем необходимо указать конфигурации OMS с помощью портала OMS.</span><span class="sxs-lookup"><span data-stu-id="051eb-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="051eb-145">В частности необходимо:</span><span class="sxs-lookup"><span data-stu-id="051eb-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="051eb-146">Укажите сведения о журналы событий и счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="051eb-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="051eb-147">Создание оповещений.</span><span class="sxs-lookup"><span data-stu-id="051eb-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="051eb-148">Укажите сведения о журналы событий и счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="051eb-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="051eb-149">На портале OMS необходимо указать сведения о журналы событий и счетчики производительности следующим образом:</span><span class="sxs-lookup"><span data-stu-id="051eb-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="051eb-150">Последовательно выберите пункты Параметры -\>данных -\>журналы событий Windows и добавьте в журналах событий:</span><span class="sxs-lookup"><span data-stu-id="051eb-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="051eb-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="051eb-151">Lync Server</span></span>

   - <span data-ttu-id="051eb-152">Приложение</span><span class="sxs-lookup"><span data-stu-id="051eb-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="051eb-153">Lync Server необходимо вручную ввести в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="051eb-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="051eb-154">Не отображается как параметр в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="051eb-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="051eb-155">Для получения дополнительных сведений см [источников данных журнала событий Windows в аналитике журнала](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="051eb-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="051eb-156">Последовательно выберите пункты Параметры -\>данных -\> счетчики производительности Windows, и добавьте счетчики производительности для:</span><span class="sxs-lookup"><span data-stu-id="051eb-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="051eb-157">На **уровне операционной системы счетчики**.</span><span class="sxs-lookup"><span data-stu-id="051eb-157">**OS level counters**.</span></span> <span data-ttu-id="051eb-158">Вы можете добавить счетчики уровня операционной системы, как использования процессора, использование памяти, использование сети, или можно использовать существующие решения, такие как емкости и производительности, сетевого монитора производительности без добавления счетчики явным образом.</span><span class="sxs-lookup"><span data-stu-id="051eb-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="051eb-159">Независимо от того, как вы решили отслеживать их Корпорация Майкрософт рекомендует наблюдения за эти счетчики операционной системы.</span><span class="sxs-lookup"><span data-stu-id="051eb-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="051eb-160">**Скайп счетчиков бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="051eb-160">**Skype for Business counters**.</span></span> <span data-ttu-id="051eb-161">Существует множество счетчиков, автор Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="051eb-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="051eb-162">Вход в систему для любого сервера-посредника и открытие монитора производительности можно найти эти счетчики.</span><span class="sxs-lookup"><span data-stu-id="051eb-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="051eb-163">Эти счетчики начинаются с «LS:».</span><span class="sxs-lookup"><span data-stu-id="051eb-163">These counters start with "LS:".</span></span> <span data-ttu-id="051eb-164">Корпорация Майкрософт рекомендует запустить с помощью следующих счетчиков емкости по крайней мере и добавить других пользователей, которые могут представлять интерес.</span><span class="sxs-lookup"><span data-stu-id="051eb-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="051eb-165">Всего активных вызовов:</span><span class="sxs-lookup"><span data-stu-id="051eb-165">Total active calls:</span></span>

   - <span data-ttu-id="051eb-166">LS:MediationServer - входящий Calls(_Total)\- текущей</span><span class="sxs-lookup"><span data-stu-id="051eb-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

   - <span data-ttu-id="051eb-167">LS:MediationServer - исходящий Calls(_Total)\- текущей</span><span class="sxs-lookup"><span data-stu-id="051eb-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="051eb-168">Общее active сервера-посредника вызовов:</span><span class="sxs-lookup"><span data-stu-id="051eb-168">Total active media bypass calls:</span></span>

   - <span data-ttu-id="051eb-169">LS:MediationServer - входящий Calls(_Total)\- активных вызовов сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="051eb-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

   - <span data-ttu-id="051eb-170">LS:MediationServer - исходящий Calls(_Total)\- активных вызовов сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="051eb-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="051eb-171">Счетчики производительности необходимо вручную ввести в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="051eb-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="051eb-172">Они не отображаются как параметры в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="051eb-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="051eb-173">Для получения дополнительных сведений см [Windows и Linux источники данных производительности в аналитике журнала](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="051eb-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="051eb-174">Создание оповещений</span><span class="sxs-lookup"><span data-stu-id="051eb-174">Create alerts</span></span>

<span data-ttu-id="051eb-175">Существует два типа оповещения в OMS: число результатов оповещения и уведомления метрики измерения.</span><span class="sxs-lookup"><span data-stu-id="051eb-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="051eb-176">Дополнительные сведения о создании оповещений см [правила оповещений в аналитике журнала](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="051eb-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="051eb-177">При создании оповещений необходимо учитывать следующее:</span><span class="sxs-lookup"><span data-stu-id="051eb-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="051eb-178">Убедитесь в том, что оповещение число результатов в вариант по умолчанию — это оповещение.</span><span class="sxs-lookup"><span data-stu-id="051eb-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="051eb-179">Демонстрация запросов требуется, что «Количество результатов» имеет значение, чтобы «больше 0".</span><span class="sxs-lookup"><span data-stu-id="051eb-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="051eb-180">Рекомендуется установить интервал времени и частоты оповещений до 5 минут.</span><span class="sxs-lookup"><span data-stu-id="051eb-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="051eb-181">Рекомендуется не включайте «Отмена» оповещения для демонстрации оповещений.</span><span class="sxs-lookup"><span data-stu-id="051eb-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="051eb-182">В скриптах оповещения, рекомендуется создавать пары оповещения: сообщение об ошибке один и один reset оповещение.</span><span class="sxs-lookup"><span data-stu-id="051eb-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="051eb-183">Сообщение об ошибке выберите уровень серьезности критическое; для сброса оповещение выберите уровень серьезности информационное.</span><span class="sxs-lookup"><span data-stu-id="051eb-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="051eb-184">В следующих разделах описывается создание образца оповещения.</span><span class="sxs-lookup"><span data-stu-id="051eb-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="051eb-185">**Создание оповещения пары: «RTCMEDSRV не работает в серверов-посредников» и «RTCMEDSRV является обратно по запуску в серверов-посредников»**</span><span class="sxs-lookup"><span data-stu-id="051eb-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="051eb-186">Для создания этой пары оповещения:</span><span class="sxs-lookup"><span data-stu-id="051eb-186">To create this alert pair:</span></span>

- <span data-ttu-id="051eb-187">— Это запрос для сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="051eb-187">The query for the error alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="051eb-188">В запросе используется фильтр компьютер, *где компьютер содержит «MediationServer»* .</span><span class="sxs-lookup"><span data-stu-id="051eb-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="051eb-189">Фильтр выбирает только на компьютере, имя которого содержит строку «MediationServer».</span><span class="sxs-lookup"><span data-stu-id="051eb-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="051eb-190">Будет заменить фильтр фильтра компьютера или просто удалите его.</span><span class="sxs-lookup"><span data-stu-id="051eb-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="051eb-191">Можно создавать фильтры сложных строки без регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="051eb-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="051eb-192">Для получения дополнительных сведений см [операторов строки](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="051eb-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="051eb-193">Можно также использовать регулярные выражения.</span><span class="sxs-lookup"><span data-stu-id="051eb-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="051eb-194">Кроме того можно создать группу компьютеров путем сохранения поискового запроса и использование этой группы в качестве фильтра компьютера в запросе оповещения.</span><span class="sxs-lookup"><span data-stu-id="051eb-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="051eb-195">Для получения дополнительных сведений см. [группы компьютеров в аналитике журнала операций поиска](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="051eb-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="051eb-196">Для каждого компьютера Ошибочный запрос будет получить последние журнала событий для службы начальная RTCMEDSRV службы и остановить.</span><span class="sxs-lookup"><span data-stu-id="051eb-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="051eb-197">Возвращает один вход, если последний событие события остановки службы; он возвращает nothing, если последний событие — запустить службы.</span><span class="sxs-lookup"><span data-stu-id="051eb-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="051eb-198">Вкратце запрос возвращает список серверов, RTCMEDSRV остановлена в окне времени.</span><span class="sxs-lookup"><span data-stu-id="051eb-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="051eb-199">— Это запрос для сброса оповещения:</span><span class="sxs-lookup"><span data-stu-id="051eb-199">The query for the reset alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="051eb-200">Сброс запросов выполняет точно положительно запроса об ошибках.</span><span class="sxs-lookup"><span data-stu-id="051eb-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="051eb-201">Для каждого компьютера он будет возвращать один Если последний событий — это служба запуска события; он возвращает nothing, если последний событие — остановить службу.</span><span class="sxs-lookup"><span data-stu-id="051eb-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

  <span data-ttu-id="051eb-202">**Создание оповещения пары: "слишком много одновременных звонков в серверов-посредников» и «одновременных звонков обычной нагрузки»**</span><span class="sxs-lookup"><span data-stu-id="051eb-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="051eb-203">Чтобы создать это предупреждение:</span><span class="sxs-lookup"><span data-stu-id="051eb-203">To create this alert:</span></span>

- <span data-ttu-id="051eb-204">— Это запрос для сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="051eb-204">The query for the error alert is:</span></span>

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="051eb-205">Для каждого компьютера запрос будет получать последние счетчики для входящих звонков и исходящих вызовов и суммы этих двух значений.</span><span class="sxs-lookup"><span data-stu-id="051eb-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="051eb-206">Возвращает один вход, если суммарное значение превышает 500; он возвращает nothing, если это не так.</span><span class="sxs-lookup"><span data-stu-id="051eb-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="051eb-207">Вкратце запрос возвращает список серверов, одновременных звонков слишком большого числа в интервал времени.</span><span class="sxs-lookup"><span data-stu-id="051eb-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="051eb-208">— Это запрос для сброса оповещения:</span><span class="sxs-lookup"><span data-stu-id="051eb-208">The query for the reset alert is:</span></span>

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="051eb-209">Сброс запросов выполняет точно положительно запроса об ошибках.</span><span class="sxs-lookup"><span data-stu-id="051eb-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="051eb-210">Для каждого компьютера запрос будет получать последние счетчики для входящих звонков и исходящих вызовов и суммы этих двух значений.</span><span class="sxs-lookup"><span data-stu-id="051eb-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="051eb-211">Возвращает один журнала, если значение сумма меньше, чем значение 500; в противном случае будет возвращено значение nothing.</span><span class="sxs-lookup"><span data-stu-id="051eb-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

  <span data-ttu-id="051eb-212">**Создание оповещения: «использование ресурсов ЦП \> 90 или RTCMEDIARELAY остановленной на серверах» оповещения**</span><span class="sxs-lookup"><span data-stu-id="051eb-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="051eb-213">Чтобы создать это предупреждение, — это запрос:</span><span class="sxs-lookup"><span data-stu-id="051eb-213">To create this alert, the query is:</span></span>

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="051eb-214">Запрос будет возвращать все счетчика использования процессора и события остановки службы из всех компьютеров и прибыли, когда-либо остановлена одного журнала, если либо использования процессора превышает 90% или службы.</span><span class="sxs-lookup"><span data-stu-id="051eb-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="051eb-215">Анализ оповещений в репозиторий анализа журнала</span><span class="sxs-lookup"><span data-stu-id="051eb-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="051eb-216">Для анализа оповещений в репозиторий, использующих решение управления предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="051eb-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="051eb-217">Для получения дополнительных сведений см [решения по управлению оповещения в пакет управления Operations (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="051eb-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="051eb-218">Рекомендуемый минимальный набор мониторинга</span><span class="sxs-lookup"><span data-stu-id="051eb-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="051eb-219">Чтобы определить проблемы с журналы событий и счетчики производительности:</span><span class="sxs-lookup"><span data-stu-id="051eb-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="051eb-220">**Журналы событий.**</span><span class="sxs-lookup"><span data-stu-id="051eb-220">**Event logs.**</span></span> <span data-ttu-id="051eb-221">Для любой проблемы должны быть пара событий с помощью одного набора событий, чтобы указать, что дает сбой, а другое указывает, что все работает хорошо.</span><span class="sxs-lookup"><span data-stu-id="051eb-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="051eb-222">Для любого заданного периода это последний записанного события, появится сообщение о том, является ли что-то amiss для этого периода времени.</span><span class="sxs-lookup"><span data-stu-id="051eb-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="051eb-223">**Счетчики производительности.**</span><span class="sxs-lookup"><span data-stu-id="051eb-223">**Performance Counters.**</span></span> <span data-ttu-id="051eb-224">Должна быть пороговое значение для отслеживаемых счетчиков.</span><span class="sxs-lookup"><span data-stu-id="051eb-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="051eb-225">В следующей таблице перечислены службы, корпорация Майкрософт рекомендует мониторинга, указав остановка и запуск коды событий:</span><span class="sxs-lookup"><span data-stu-id="051eb-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="051eb-226">Имя службы</span><span class="sxs-lookup"><span data-stu-id="051eb-226">Service Name</span></span>  <br/> |<span data-ttu-id="051eb-227">Роль конечного сервера</span><span class="sxs-lookup"><span data-stu-id="051eb-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="051eb-228">Остановка событие с кодом</span><span class="sxs-lookup"><span data-stu-id="051eb-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="051eb-229">Запустите код события</span><span class="sxs-lookup"><span data-stu-id="051eb-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="051eb-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="051eb-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="051eb-231">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="051eb-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="051eb-232">25003</span><span class="sxs-lookup"><span data-stu-id="051eb-232">25003</span></span>  <br/> |<span data-ttu-id="051eb-233">25002</span><span class="sxs-lookup"><span data-stu-id="051eb-233">25002</span></span>  <br/> |
|<span data-ttu-id="051eb-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="051eb-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="051eb-235">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="051eb-235">Edge Server</span></span>  <br/> |<span data-ttu-id="051eb-236">12289</span><span class="sxs-lookup"><span data-stu-id="051eb-236">12289</span></span>  <br/> |<span data-ttu-id="051eb-237">12288</span><span class="sxs-lookup"><span data-stu-id="051eb-237">12288</span></span>  <br/> |
|<span data-ttu-id="051eb-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="051eb-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="051eb-239">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="051eb-239">Edge Server</span></span>  <br/> |<span data-ttu-id="051eb-240">19003</span><span class="sxs-lookup"><span data-stu-id="051eb-240">19003</span></span>  <br/> |<span data-ttu-id="051eb-241">19002</span><span class="sxs-lookup"><span data-stu-id="051eb-241">19002</span></span>  <br/> |
|<span data-ttu-id="051eb-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="051eb-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="051eb-243">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="051eb-243">Edge Server</span></span>  <br/> |<span data-ttu-id="051eb-244">22003</span><span class="sxs-lookup"><span data-stu-id="051eb-244">22003</span></span>  <br/> |<span data-ttu-id="051eb-245">22002</span><span class="sxs-lookup"><span data-stu-id="051eb-245">22002</span></span>  <br/> |

<span data-ttu-id="051eb-246">В следующей таблице перечислены проблемы сети, корпорация Майкрософт рекомендует мониторинга:</span><span class="sxs-lookup"><span data-stu-id="051eb-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="051eb-247">Имя монитора</span><span class="sxs-lookup"><span data-stu-id="051eb-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="051eb-248">Роль конечного сервера</span><span class="sxs-lookup"><span data-stu-id="051eb-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="051eb-249">Идентификатор события выражение успеха</span><span class="sxs-lookup"><span data-stu-id="051eb-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="051eb-250">Идентификатор события ошибки выражения</span><span class="sxs-lookup"><span data-stu-id="051eb-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="051eb-251">Пример сбоя</span><span class="sxs-lookup"><span data-stu-id="051eb-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="051eb-252">Сбой подключения к шлюза сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="051eb-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="051eb-253">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="051eb-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="051eb-254">25062</span><span class="sxs-lookup"><span data-stu-id="051eb-254">25062</span></span>                              |                                  | <span data-ttu-id="051eb-255">25002</span><span class="sxs-lookup"><span data-stu-id="051eb-255">25002</span></span>  <br/>           |
| <span data-ttu-id="051eb-256">Ошибка завершения вызова сервера-посредника к шлюзу</span><span class="sxs-lookup"><span data-stu-id="051eb-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="051eb-257">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="051eb-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="051eb-258">25064</span><span class="sxs-lookup"><span data-stu-id="051eb-258">25064</span></span>                              |                                  | <span data-ttu-id="051eb-259">25002</span><span class="sxs-lookup"><span data-stu-id="051eb-259">25002</span></span>  <br/>           |
| <span data-ttu-id="051eb-260">Критические проблемы в сети</span><span class="sxs-lookup"><span data-stu-id="051eb-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="051eb-261">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="051eb-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="051eb-262">14353</span><span class="sxs-lookup"><span data-stu-id="051eb-262">14353</span></span>                              |                                  | <span data-ttu-id="051eb-263">12288</span><span class="sxs-lookup"><span data-stu-id="051eb-263">12288</span></span>  <br/>           |

<span data-ttu-id="051eb-264">В следующем списке перечислены счетчики емкости вызовов, которые должны отслеживаться.</span><span class="sxs-lookup"><span data-stu-id="051eb-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="051eb-265">Эти номера должен быть меньше, 500 для соединителя облачных standard edition; меньше 50 для соединителя облачных минимальные edition.</span><span class="sxs-lookup"><span data-stu-id="051eb-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="051eb-266">LS:MediationServer - входящий Calls(_Total)\- текущей</span><span class="sxs-lookup"><span data-stu-id="051eb-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="051eb-267">LS:MediationServer - исходящий Calls(_Total)\- текущей</span><span class="sxs-lookup"><span data-stu-id="051eb-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="051eb-268">LS:MediationServer - входящий Calls(_Total)\- активных вызовов сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="051eb-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="051eb-269">LS:MediationServer - исходящий Calls(_Total)\- активных вызовов сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="051eb-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="051eb-270">См. также</span><span class="sxs-lookup"><span data-stu-id="051eb-270">See also</span></span>

<span data-ttu-id="051eb-271">Дополнительные сведения о работе с OMS см.:</span><span class="sxs-lookup"><span data-stu-id="051eb-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="051eb-272">Поиск данных с помощью поисков в журнале в аналитике журнала</span><span class="sxs-lookup"><span data-stu-id="051eb-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="051eb-273">Справочник по языку Analytics Azure журнала</span><span class="sxs-lookup"><span data-stu-id="051eb-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="051eb-274">Общее представление о оповещений в аналитике журнала</span><span class="sxs-lookup"><span data-stu-id="051eb-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="051eb-275">Подключения компьютеров Windows к службе анализа журнала в Azure</span><span class="sxs-lookup"><span data-stu-id="051eb-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)


