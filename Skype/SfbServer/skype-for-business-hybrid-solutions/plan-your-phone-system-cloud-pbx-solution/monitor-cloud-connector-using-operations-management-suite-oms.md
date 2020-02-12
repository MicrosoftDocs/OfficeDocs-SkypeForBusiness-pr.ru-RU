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
description: В этой статье рассказывается о том, как отслеживать облачный соединитель версии 2,1 и более поздних версий с помощью Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 6c63baf078dc865a4e3aef574cff30bedabf3819
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888638"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="18421-103">Отслеживание Cloud Connector с помощью Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="18421-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="18421-104">В этой статье рассказывается о том, как отслеживать облачный соединитель версии 2,1 и более поздних версий с помощью Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="18421-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="18421-105">Теперь вы можете наблюдать за развертыванием облачного соединителя версии 2,1 и более поздних версий с помощью Operations Management Suite (OMS), решения для ИТ-управления в облаке (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="18421-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="18421-106">С помощью службы анализа журналов OMS вы можете отслеживать и анализировать доступность и производительность ресурсов, в том числе физических и виртуальных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="18421-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="18421-107">Для получения дополнительных сведений о службе OMS и Analytics log ознакомьтесь со статьей [набор Operations Management Suite (OMS).](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="18421-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="18421-108">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="18421-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="18421-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="18421-109">Prerequisites</span></span>

- <span data-ttu-id="18421-110">Настройка облачного соединителя для использования OMS</span><span class="sxs-lookup"><span data-stu-id="18421-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="18421-111">Настройка OMS</span><span class="sxs-lookup"><span data-stu-id="18421-111">Configure OMS</span></span>

- <span data-ttu-id="18421-112">Анализ оповещений в репозитории аналитических журналов</span><span class="sxs-lookup"><span data-stu-id="18421-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="18421-113">Рекомендуемый параметр наблюдения</span><span class="sxs-lookup"><span data-stu-id="18421-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="18421-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="18421-114">Prerequisites</span></span>

<span data-ttu-id="18421-115">Прежде чем вы сможете использовать OMS для наблюдения за развертыванием облачного соединителя, вам потребуется выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="18421-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="18421-116">**Учетная запись Azure и Рабочая область OMS.**</span><span class="sxs-lookup"><span data-stu-id="18421-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="18421-117">Если у вас еще нет учетной записи Azure, вам потребуется создать ее для использования службы ведения журналов OMS.</span><span class="sxs-lookup"><span data-stu-id="18421-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="18421-118">Сведения о том, как создать учетную запись Azure и настроить рабочую область OMS, можно найти в разделе [Начало работы с рабочей областью службы анализа журналов](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="18421-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="18421-119">**Облачный соединитель версии 2,1 или более поздней**</span><span class="sxs-lookup"><span data-stu-id="18421-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="18421-120">Для мониторинга облачного соединителя требуется **Новый поиск журнала** в службе аналитики.</span><span class="sxs-lookup"><span data-stu-id="18421-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="18421-121">Дополнительные сведения можно найти [в разделе Обновление рабочей области службы анализа журналов Azure для нового поиска в журнале](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="18421-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="18421-122">Настройка облачного соединителя для использования OMS</span><span class="sxs-lookup"><span data-stu-id="18421-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="18421-123">Для использования OMS необходимо настроить локальную среду облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="18421-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="18421-124">Для этого вам потребуется идентификатор рабочей области OMS и ключ, который можно найти с помощью портала OMS, как описано ниже: параметры--\>подключенные источники — серверы\> Windows.</span><span class="sxs-lookup"><span data-stu-id="18421-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Снимок экрана OMS в Cloud Connector](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="18421-126">Способ настройки облачного соединителя для использования OMS зависит от вашего сценария.</span><span class="sxs-lookup"><span data-stu-id="18421-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="18421-127">**Если при установке нового устройства с облаком соединительной линии требуется повторное развертывание устройства**, выполните следующие действия перед выполнением Install-ккапплианце:</span><span class="sxs-lookup"><span data-stu-id="18421-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="18421-128">В разделе файл Клаудконнектор. ini [Common] установите для параметра Омсенаблед значение true.</span><span class="sxs-lookup"><span data-stu-id="18421-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="18421-129">Каждый раз, когда облачный соединитель разворачивается или обновляется, он попытается автоматически установить агент OMS на виртуальных машинах.</span><span class="sxs-lookup"><span data-stu-id="18421-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="18421-130">Включите эту функцию, чтобы агент OMS мог содержаться в автоматическом обновлении облачной соединительной линии.</span><span class="sxs-lookup"><span data-stu-id="18421-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="18421-131">Для настройки идентификатора OMS и ключа выполните Set-Кккредентиал-AccountType Омсворкспаце.</span><span class="sxs-lookup"><span data-stu-id="18421-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="18421-132">**Если вы устанавливаете агент OMS на существующем устройстве облачного соединителя**, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="18421-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="18421-133">В разделе файл Клаудконнектор. ini [Common] установите Омсенаблед = true.</span><span class="sxs-lookup"><span data-stu-id="18421-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="18421-134">Запустите Import-Ккконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="18421-134">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="18421-135">Запустите Install-Ккомсажент.</span><span class="sxs-lookup"><span data-stu-id="18421-135">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="18421-136">Если учетные данные Омсворкспаце никогда не были заданы, при запуске Install-Ккомсажент вам будет предложено ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="18421-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="18421-137">**Если вы хотите обновить идентификатор или ключ рабочей области OMS на устройстве облачного соединителя, на котором уже установлен агент OMS, выполните указанные ниже действия.**</span><span class="sxs-lookup"><span data-stu-id="18421-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="18421-138">Для настройки идентификатора OMS и ключа выполните Set-Кккредентиал-AccountType Омсворкспаце.</span><span class="sxs-lookup"><span data-stu-id="18421-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="18421-139">Чтобы применить обновления, запустите Install-Ккомсажент.</span><span class="sxs-lookup"><span data-stu-id="18421-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="18421-140">**Для всех сценариев убедитесь, что агенты подключены следующим образом:**</span><span class="sxs-lookup"><span data-stu-id="18421-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="18421-141">На портале OMS перейдите в раздел Параметры —\> подключенные источники\> — серверы Windows.</span><span class="sxs-lookup"><span data-stu-id="18421-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="18421-142">Вы увидите список подключенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="18421-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="18421-143">Настройка OMS</span><span class="sxs-lookup"><span data-stu-id="18421-143">Configure OMS</span></span>

<span data-ttu-id="18421-144">После этого вам нужно будет указать конфигурацию OMS с помощью портала OMS.</span><span class="sxs-lookup"><span data-stu-id="18421-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="18421-145">В частности, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="18421-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="18421-146">Укажите сведения о журналах событий и счетчиках производительности.</span><span class="sxs-lookup"><span data-stu-id="18421-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="18421-147">Создание оповещений.</span><span class="sxs-lookup"><span data-stu-id="18421-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="18421-148">Указание сведений о журналах событий и счетчиках производительности</span><span class="sxs-lookup"><span data-stu-id="18421-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="18421-149">На портале OMS вы должны указать сведения о журналах событий и счетчиках производительности, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="18421-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="18421-150">Перейдите в раздел настройки\>— журналы\>событий Windows и добавьте журналы событий для:</span><span class="sxs-lookup"><span data-stu-id="18421-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="18421-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="18421-151">Lync Server</span></span>

   - <span data-ttu-id="18421-152">Приложение</span><span class="sxs-lookup"><span data-stu-id="18421-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="18421-153">Вы должны вручную ввести в текстовом поле Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18421-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="18421-154">Этот параметр не отображается в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="18421-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="18421-155">Дополнительные сведения можно найти [в разделе источники данных журнала событий Windows в службе анализа журналов](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="18421-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="18421-156">Выберите параметры-\>счетчики производительности\> Windows для данных и добавьте счетчики производительности для:</span><span class="sxs-lookup"><span data-stu-id="18421-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="18421-157">**Счетчики уровня ОС**.</span><span class="sxs-lookup"><span data-stu-id="18421-157">**OS level counters**.</span></span> <span data-ttu-id="18421-158">Вы можете добавить счетчики уровня операционной системы, такие как использование процессора, использование памяти, использование сети или использование существующих решений, таких как производительность и производительность, монитор производительности сети без явного добавления счетчиков.</span><span class="sxs-lookup"><span data-stu-id="18421-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="18421-159">Независимо от того, как вы решите следить за их работой, корпорация Майкрософт рекомендует наблюдать за этими счетчиками операционной системы.</span><span class="sxs-lookup"><span data-stu-id="18421-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="18421-160">**Счетчики Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="18421-160">**Skype for Business counters**.</span></span> <span data-ttu-id="18421-161">В Skype для бизнеса предусмотрено множество счетчиков.</span><span class="sxs-lookup"><span data-stu-id="18421-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="18421-162">Эти счетчики можно найти, войдя на любой сервер и открыв системный монитор.</span><span class="sxs-lookup"><span data-stu-id="18421-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="18421-163">Эти счетчики начинаются с "LS:".</span><span class="sxs-lookup"><span data-stu-id="18421-163">These counters start with "LS:".</span></span> <span data-ttu-id="18421-164">Корпорация Майкрософт рекомендует использовать как минимум указанные ниже счетчики мощности и добавить еще более интересные.</span><span class="sxs-lookup"><span data-stu-id="18421-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="18421-165">Общее количество активных звонков:</span><span class="sxs-lookup"><span data-stu-id="18421-165">Total active calls:</span></span>

       - <span data-ttu-id="18421-166">LS: Медиатионсервер — текущие входящие звонки (_Total\- )</span><span class="sxs-lookup"><span data-stu-id="18421-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="18421-167">LS: Медиатионсервер — текущие исходящие вызовы (\- _Total)</span><span class="sxs-lookup"><span data-stu-id="18421-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="18421-168">Общее количество активных звонков на обход мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="18421-168">Total active media bypass calls:</span></span>

       - <span data-ttu-id="18421-169">LS: Медиатионсервер – входящие звонки (_Total)\- вызовы обхода активных мультимедиа</span><span class="sxs-lookup"><span data-stu-id="18421-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="18421-170">LS: Медиатионсервер-исходящие вызовы (_Total\- ) вызовы обхода активных мультимедиа</span><span class="sxs-lookup"><span data-stu-id="18421-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="18421-171">Вы должны вручную вводить в текстовом поле счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="18421-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="18421-172">Они не отображаются в виде параметров в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="18421-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="18421-173">Дополнительные сведения можно найти [в разделе источники данных о производительности Windows и Linux в службе анализа журналов](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="18421-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="18421-174">Создание оповещений</span><span class="sxs-lookup"><span data-stu-id="18421-174">Create alerts</span></span>

<span data-ttu-id="18421-175">В OMS есть два типа оповещений: количество оповещений о результатах и оповещения об измерении показателей.</span><span class="sxs-lookup"><span data-stu-id="18421-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="18421-176">Дополнительные сведения о создании оповещений можно найти [в разделе Работа с правилами оповещения в службе анализа журналов](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="18421-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="18421-177">При создании оповещений вы должны иметь в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="18421-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="18421-178">Убедитесь, что оповещение является оповещением с результатами, которое является выбором по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="18421-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="18421-179">Для демонстрационных запросов требуется, чтобы для параметра "число результатов" было задано значение "больше 0".</span><span class="sxs-lookup"><span data-stu-id="18421-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="18421-180">Рекомендуется установить как для интервала времени, так и для частоты оповещений, равным 5 минутам.</span><span class="sxs-lookup"><span data-stu-id="18421-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="18421-181">Не рекомендуется включать функцию "отключить оповещения" для демонстрационных оповещений.</span><span class="sxs-lookup"><span data-stu-id="18421-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="18421-182">Для типичных ситуаций с оповещениями Корпорация Майкрософт рекомендует создавать пары оповещений: одно сообщение об ошибке и одно оповещение о сбросе.</span><span class="sxs-lookup"><span data-stu-id="18421-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="18421-183">Для оповещения об ошибке выберите критический уровень серьезности. для оповещения о сбросе выберите уровень серьезности.</span><span class="sxs-lookup"><span data-stu-id="18421-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="18421-184">В следующих разделах описано, как создавать образцы оповещений.</span><span class="sxs-lookup"><span data-stu-id="18421-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="18421-185">**Создание пары оповещений: "РТКМЕДСРВ не работает на серверах исправлений", а "РТКМЕДСРВ работает на серверах исправлений"**</span><span class="sxs-lookup"><span data-stu-id="18421-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="18421-186">Чтобы создать эту пару оповещений:</span><span class="sxs-lookup"><span data-stu-id="18421-186">To create this alert pair:</span></span>

- <span data-ttu-id="18421-187">Запрос на сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="18421-187">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="18421-188">Запрос использует фильтр компьютера, на *котором компьютер содержит "медиатионсервер"* .</span><span class="sxs-lookup"><span data-stu-id="18421-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="18421-189">Фильтр выбирает только компьютер, имя которого включает строку "Медиатионсервер".</span><span class="sxs-lookup"><span data-stu-id="18421-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="18421-190">Вы можете заменить фильтр на собственный фильтр компьютера или просто удалить его.</span><span class="sxs-lookup"><span data-stu-id="18421-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="18421-191">Вы можете создавать сложные фильтры строк без регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="18421-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="18421-192">Дополнительные сведения можно найти в разделе [Операторы строковых операторов](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="18421-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="18421-193">Вы также можете выбрать использование регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="18421-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="18421-194">Кроме того, вы можете создать группу компьютеров, сохранив поисковый запрос и используя эту группу в качестве фильтра на компьютере в запросе на оповещение.</span><span class="sxs-lookup"><span data-stu-id="18421-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="18421-195">Дополнительные сведения можно найти [в разделе группы компьютеров в поиске журнала службы анализа журналов](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="18421-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="18421-196">Для каждого компьютера запрос об ошибке получит журнал последних событий для запуска службы РТКМЕДСРВ и остановки службы.</span><span class="sxs-lookup"><span data-stu-id="18421-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="18421-197">Если Последнее событие является событием остановки службы, будет возвращен один журнал. Если Последнее событие является событием запуска службы, будет возвращено значение Nothing.</span><span class="sxs-lookup"><span data-stu-id="18421-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="18421-198">Коротко говоря, запрос вернет список серверов, в которых РТКМЕДСРВ остановлен в окне времени.</span><span class="sxs-lookup"><span data-stu-id="18421-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="18421-199">Запрос на оповещение о сбросе:</span><span class="sxs-lookup"><span data-stu-id="18421-199">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="18421-200">Запрос на сброс — это противоположный результат запроса об ошибке.</span><span class="sxs-lookup"><span data-stu-id="18421-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="18421-201">Для каждого компьютера он возвратит один из них, если Последнее событие является событием запуска службы; Если Последнее событие является событием остановки службы, будет возвращено значение Nothing.</span><span class="sxs-lookup"><span data-stu-id="18421-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="18421-202">**Создание пары оповещений: "слишком много одновременных звонков на серверы исправлений" и "одновременные звонки возвращаются к обычной загрузке"**</span><span class="sxs-lookup"><span data-stu-id="18421-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="18421-203">Чтобы создать это оповещение, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="18421-203">To create this alert:</span></span>

- <span data-ttu-id="18421-204">Запрос на сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="18421-204">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="18421-205">Для каждого компьютера запрос получит последние счетчики входящего и исходящего звонка, а затем сложить эти два значения.</span><span class="sxs-lookup"><span data-stu-id="18421-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="18421-206">Если сумма превышает 500, будет возвращен один журнал. Если это не так, она возвратит ничего.</span><span class="sxs-lookup"><span data-stu-id="18421-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="18421-207">Коротко говоря, запрос вернет список серверов, одновременные звонки которых слишком много в окне времени.</span><span class="sxs-lookup"><span data-stu-id="18421-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="18421-208">Запрос на оповещение о сбросе:</span><span class="sxs-lookup"><span data-stu-id="18421-208">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="18421-209">Запрос на сброс — это противоположный результат запроса об ошибке.</span><span class="sxs-lookup"><span data-stu-id="18421-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="18421-210">Для каждого компьютера запрос получит последние счетчики входящего и исходящего звонка, а затем сложить эти два значения.</span><span class="sxs-lookup"><span data-stu-id="18421-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="18421-211">Если сумма превышает 500, она вернет один журнал. в противном случае он вернет Nothing.</span><span class="sxs-lookup"><span data-stu-id="18421-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="18421-212">**Создание оповещения: "Загрузка ЦП \> 90 или рткмедиарелай остановлена на серверах"**</span><span class="sxs-lookup"><span data-stu-id="18421-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="18421-213">Чтобы создать это оповещение, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="18421-213">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="18421-214">Запрос возвращает все счетчики использования процессора и остановку служб со всех компьютеров и возвращают один журнал, если загрузка процессора превышает 90% или служба когда-либо прекратится.</span><span class="sxs-lookup"><span data-stu-id="18421-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="18421-215">Анализ оповещений в репозитории аналитических журналов</span><span class="sxs-lookup"><span data-stu-id="18421-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="18421-216">Чтобы проанализировать оповещения в репозитории, используйте решение для управления оповещениями.</span><span class="sxs-lookup"><span data-stu-id="18421-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="18421-217">Дополнительные сведения можно найти [в разделе решение для управления оповещениями в Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="18421-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="18421-218">Рекомендуемый минимальный набор контрольных данных</span><span class="sxs-lookup"><span data-stu-id="18421-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="18421-219">Чтобы выявить проблемы с журналами событий и счетчиками производительности, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="18421-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="18421-220">**Журналы событий.**</span><span class="sxs-lookup"><span data-stu-id="18421-220">**Event logs.**</span></span> <span data-ttu-id="18421-221">Для любой проблемы должна существовать пара событий с одним набором событий, указывающая на то, что что-то пошло не так, а другое указывает на то, что все правильно.</span><span class="sxs-lookup"><span data-stu-id="18421-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="18421-222">Для любого определенного периода времени это последнее записанное событие, которое показывает, является ли что-либо неправильным для этого периода времени.</span><span class="sxs-lookup"><span data-stu-id="18421-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="18421-223">**Счетчики производительности.**</span><span class="sxs-lookup"><span data-stu-id="18421-223">**Performance Counters.**</span></span> <span data-ttu-id="18421-224">Для наблюдаемых счетчиков должно быть пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="18421-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="18421-225">В следующей таблице перечислены службы, которые корпорация Майкрософт рекомендует отслеживать, указывая коды событий Stop и Start:</span><span class="sxs-lookup"><span data-stu-id="18421-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="18421-226">Название услуги</span><span class="sxs-lookup"><span data-stu-id="18421-226">Service Name</span></span>  <br/> |<span data-ttu-id="18421-227">Роль целевого сервера</span><span class="sxs-lookup"><span data-stu-id="18421-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="18421-228">Код события остановки</span><span class="sxs-lookup"><span data-stu-id="18421-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="18421-229">Код события запуска</span><span class="sxs-lookup"><span data-stu-id="18421-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="18421-230">рткмедсрв</span><span class="sxs-lookup"><span data-stu-id="18421-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="18421-231">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="18421-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="18421-232">25003</span><span class="sxs-lookup"><span data-stu-id="18421-232">25003</span></span>  <br/> |<span data-ttu-id="18421-233">25002</span><span class="sxs-lookup"><span data-stu-id="18421-233">25002</span></span>  <br/> |
|<span data-ttu-id="18421-234">ртксрв</span><span class="sxs-lookup"><span data-stu-id="18421-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="18421-235">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="18421-235">Edge Server</span></span>  <br/> |<span data-ttu-id="18421-236">12289</span><span class="sxs-lookup"><span data-stu-id="18421-236">12289</span></span>  <br/> |<span data-ttu-id="18421-237">12288</span><span class="sxs-lookup"><span data-stu-id="18421-237">12288</span></span>  <br/> |
|<span data-ttu-id="18421-238">рткмраус</span><span class="sxs-lookup"><span data-stu-id="18421-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="18421-239">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="18421-239">Edge Server</span></span>  <br/> |<span data-ttu-id="18421-240">19003</span><span class="sxs-lookup"><span data-stu-id="18421-240">19003</span></span>  <br/> |<span data-ttu-id="18421-241">19002</span><span class="sxs-lookup"><span data-stu-id="18421-241">19002</span></span>  <br/> |
|<span data-ttu-id="18421-242">рткмедиарелай</span><span class="sxs-lookup"><span data-stu-id="18421-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="18421-243">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="18421-243">Edge Server</span></span>  <br/> |<span data-ttu-id="18421-244">22003</span><span class="sxs-lookup"><span data-stu-id="18421-244">22003</span></span>  <br/> |<span data-ttu-id="18421-245">22002</span><span class="sxs-lookup"><span data-stu-id="18421-245">22002</span></span>  <br/> |

<span data-ttu-id="18421-246">В таблице ниже перечислены сетевые проблемы, которые корпорация Майкрософт рекомендует отслеживать.</span><span class="sxs-lookup"><span data-stu-id="18421-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="18421-247">Имя монитора</span><span class="sxs-lookup"><span data-stu-id="18421-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="18421-248">Роль целевого сервера</span><span class="sxs-lookup"><span data-stu-id="18421-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="18421-249">Выражение с кодом события "успех"</span><span class="sxs-lookup"><span data-stu-id="18421-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="18421-250">Выражение с кодом события ошибки</span><span class="sxs-lookup"><span data-stu-id="18421-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="18421-251">Пример сбоя</span><span class="sxs-lookup"><span data-stu-id="18421-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="18421-252">Ошибка подключения сервера обновлений к шлюзу</span><span class="sxs-lookup"><span data-stu-id="18421-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="18421-253">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="18421-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="18421-254">25062</span><span class="sxs-lookup"><span data-stu-id="18421-254">25062</span></span>                              |                                  | <span data-ttu-id="18421-255">25002</span><span class="sxs-lookup"><span data-stu-id="18421-255">25002</span></span>  <br/>           |
| <span data-ttu-id="18421-256">Сбой завершения вызова сервера обновлений до шлюза</span><span class="sxs-lookup"><span data-stu-id="18421-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="18421-257">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="18421-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="18421-258">25064</span><span class="sxs-lookup"><span data-stu-id="18421-258">25064</span></span>                              |                                  | <span data-ttu-id="18421-259">25002</span><span class="sxs-lookup"><span data-stu-id="18421-259">25002</span></span>  <br/>           |
| <span data-ttu-id="18421-260">Критические проблемы с сетью</span><span class="sxs-lookup"><span data-stu-id="18421-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="18421-261">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="18421-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="18421-262">14353</span><span class="sxs-lookup"><span data-stu-id="18421-262">14353</span></span>                              |                                  | <span data-ttu-id="18421-263">12288</span><span class="sxs-lookup"><span data-stu-id="18421-263">12288</span></span>  <br/>           |

<span data-ttu-id="18421-264">Ниже перечислены счетчики мощности звонков, которые нужно отслеживать.</span><span class="sxs-lookup"><span data-stu-id="18421-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="18421-265">Эти номера должны быть меньше, чем 500 для облачного соединителя Standard Edition. менее 50 для облачного соединителя (минимум).</span><span class="sxs-lookup"><span data-stu-id="18421-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="18421-266">LS: Медиатионсервер — текущие входящие звонки (_Total\- )</span><span class="sxs-lookup"><span data-stu-id="18421-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="18421-267">LS: Медиатионсервер — текущие исходящие вызовы (\- _Total)</span><span class="sxs-lookup"><span data-stu-id="18421-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="18421-268">LS: Медиатионсервер – входящие звонки (_Total)\- вызовы обхода активных мультимедиа</span><span class="sxs-lookup"><span data-stu-id="18421-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="18421-269">LS: Медиатионсервер-исходящие вызовы (_Total\- ) вызовы обхода активных мультимедиа</span><span class="sxs-lookup"><span data-stu-id="18421-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="18421-270">См. также</span><span class="sxs-lookup"><span data-stu-id="18421-270">See also</span></span>

<span data-ttu-id="18421-271">Дополнительные сведения о работе с OMS можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="18421-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="18421-272">Поиск данных с помощью поиска по журналу в службе анализа журналов</span><span class="sxs-lookup"><span data-stu-id="18421-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="18421-273">Справочник по языку Azure log Analytics</span><span class="sxs-lookup"><span data-stu-id="18421-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="18421-274">Общие сведения об оповещениях в службе анализа журналов</span><span class="sxs-lookup"><span data-stu-id="18421-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="18421-275">Подключение компьютеров с Windows к службе Analytics log в Azure</span><span class="sxs-lookup"><span data-stu-id="18421-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


