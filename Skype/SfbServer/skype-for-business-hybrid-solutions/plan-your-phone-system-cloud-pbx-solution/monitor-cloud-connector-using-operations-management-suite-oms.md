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
description: В этом разделе рассказывается, как отслеживать развертывание Cloud Connector версии 2,1 и более поздних версий с помощью Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359095"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="99dcc-103">Отслеживание Cloud Connector с помощью Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="99dcc-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="99dcc-104">Cloud Connector Edition выйдет 31 июля 2021 вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="99dcc-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="99dcc-105">После обновления вашей организации до Teams Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="99dcc-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="99dcc-106">В этом разделе рассказывается, как отслеживать развертывание Cloud Connector версии 2,1 и более поздних версий с помощью Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="99dcc-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="99dcc-107">Теперь вы можете отслеживать развертывание Cloud Connector версии 2,1 и более поздней версии с помощью Operations Management Suite (OMS), решения для ИТ-управления в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="99dcc-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="99dcc-108">Анализ журналов OMS позволяет отслеживать и анализировать доступность и производительность ресурсов, включая физические и виртуальные машины.</span><span class="sxs-lookup"><span data-stu-id="99dcc-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="99dcc-109">Для получения дополнительных сведений о OMS и службе анализа журналов посмотрите, [что представляет собой набор Operations Management Suite (OMS).](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="99dcc-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="99dcc-110">В этом разделе содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="99dcc-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="99dcc-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="99dcc-111">Prerequisites</span></span>

- <span data-ttu-id="99dcc-112">Настройка Cloud Connector для использования OMS</span><span class="sxs-lookup"><span data-stu-id="99dcc-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="99dcc-113">Настройка OMS</span><span class="sxs-lookup"><span data-stu-id="99dcc-113">Configure OMS</span></span>

- <span data-ttu-id="99dcc-114">Анализ оповещений в репозитории анализа журналов</span><span class="sxs-lookup"><span data-stu-id="99dcc-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="99dcc-115">Рекомендуемый набор мониторинга</span><span class="sxs-lookup"><span data-stu-id="99dcc-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="99dcc-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="99dcc-116">Prerequisites</span></span>

<span data-ttu-id="99dcc-117">Прежде чем вы сможете использовать OMS для мониторинга развертывания Cloud Connector, вам потребуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="99dcc-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="99dcc-118">**Учетная запись Azure и Рабочая область OMS.**</span><span class="sxs-lookup"><span data-stu-id="99dcc-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="99dcc-119">Если у вас еще нет учетной записи Azure, вам потребуется создать ее для использования службы анализа журналов OMS.</span><span class="sxs-lookup"><span data-stu-id="99dcc-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="99dcc-120">Сведения о том, как создать учетную запись Azure и настроить рабочую область OMS, можно найти в статье [Начало работы с рабочей областью анализа журналов](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="99dcc-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="99dcc-121">**Cloud Connector версии 2,1 или более поздней**</span><span class="sxs-lookup"><span data-stu-id="99dcc-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="99dcc-122">**Журнал анализа журналов** для мониторинга Cloud Connector необходим новый поиск журнала.</span><span class="sxs-lookup"><span data-stu-id="99dcc-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="99dcc-123">Дополнительные сведения см. [в статье обновление рабочей области службы анализа журналов Azure до нового поиска в журнале](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="99dcc-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="99dcc-124">Настройка Cloud Connector для использования OMS</span><span class="sxs-lookup"><span data-stu-id="99dcc-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="99dcc-125">Вам потребуется настроить локальную среду Cloud Connector для использования OMS.</span><span class="sxs-lookup"><span data-stu-id="99dcc-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="99dcc-126">Для этого вам потребуется идентификатор и ключ вашей рабочей области OMS, которые можно найти с помощью портала OMS: Settings — \> подключенные источники — \> серверы Windows:</span><span class="sxs-lookup"><span data-stu-id="99dcc-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Снимок экрана OMS для Cloud Connector](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="99dcc-128">Способ настройки Cloud Connector для использования OMS зависит от сценария.</span><span class="sxs-lookup"><span data-stu-id="99dcc-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="99dcc-129">**Если вы устанавливаете новое устройство Cloud Connector или хотите повторно развернуть устройство**, выполните следующие действия перед выполнением командлета Install — CcAppliance:</span><span class="sxs-lookup"><span data-stu-id="99dcc-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="99dcc-130">В разделе CloudConnector.ini файл [Common] задайте для параметра Омсенаблед значение true.</span><span class="sxs-lookup"><span data-stu-id="99dcc-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="99dcc-131">Каждый раз, когда Cloud Connector разворачивается или обновляется, он попытается автоматически установить агент OMS на виртуальных машинах.</span><span class="sxs-lookup"><span data-stu-id="99dcc-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="99dcc-132">Включите эту функцию, чтобы агент OMS мог продолжать автоматическое обновление Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="99dcc-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="99dcc-133">Чтобы настроить идентификатор и ключ OMS, выполните командлет Set – CcCredential – AccountType Омсворкспаце.</span><span class="sxs-lookup"><span data-stu-id="99dcc-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="99dcc-134">**Если вы устанавливаете агент OMS на существующем устройстве Cloud Connector**, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="99dcc-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="99dcc-135">В разделе CloudConnector.ini файл [Common] задайте Омсенаблед = true.</span><span class="sxs-lookup"><span data-stu-id="99dcc-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="99dcc-136">Выполните командлет Import – CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="99dcc-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="99dcc-137">Выполните командлет Install — Ккомсажент.</span><span class="sxs-lookup"><span data-stu-id="99dcc-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="99dcc-138">Если учетные данные Омсворкспаце никогда не были заданы, при выполнении командлета Install — Ккомсажент вам потребуется ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="99dcc-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="99dcc-139">**Если вы хотите обновить идентификатор или ключ рабочей области OMS на устройстве Cloud Connector, на котором уже установлен агент OMS, выполните следующие действия:**</span><span class="sxs-lookup"><span data-stu-id="99dcc-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="99dcc-140">Чтобы настроить идентификатор и ключ OMS, выполните командлет Set – CcCredential – AccountType Омсворкспаце.</span><span class="sxs-lookup"><span data-stu-id="99dcc-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="99dcc-141">Чтобы применить обновления, выполните командлет Install – Ккомсажент.</span><span class="sxs-lookup"><span data-stu-id="99dcc-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="99dcc-142">**Для всех сценариев убедитесь, что агенты подключены следующим образом:**</span><span class="sxs-lookup"><span data-stu-id="99dcc-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="99dcc-143">На портале OMS перейдите в раздел Параметры — \> подключенные источники — \> серверы Windows.</span><span class="sxs-lookup"><span data-stu-id="99dcc-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="99dcc-144">Вы увидите список подключенных машин.</span><span class="sxs-lookup"><span data-stu-id="99dcc-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="99dcc-145">Настройка OMS</span><span class="sxs-lookup"><span data-stu-id="99dcc-145">Configure OMS</span></span>

<span data-ttu-id="99dcc-146">Далее необходимо указать конфигурацию OMS с помощью портала OMS.</span><span class="sxs-lookup"><span data-stu-id="99dcc-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="99dcc-147">В частности, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="99dcc-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="99dcc-148">Укажите сведения о журналах событий и счетчиках производительности.</span><span class="sxs-lookup"><span data-stu-id="99dcc-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="99dcc-149">Создание оповещений</span><span class="sxs-lookup"><span data-stu-id="99dcc-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="99dcc-150">Указание сведений о журналах событий и счетчиках производительности</span><span class="sxs-lookup"><span data-stu-id="99dcc-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="99dcc-151">На портале OMS необходимо указать сведения о журналах событий и счетчиках производительности следующим образом:</span><span class="sxs-lookup"><span data-stu-id="99dcc-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="99dcc-152">Перейдите в раздел Параметры — \> \> журналы событий Windows и добавьте журналы событий для:</span><span class="sxs-lookup"><span data-stu-id="99dcc-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="99dcc-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="99dcc-153">Lync Server</span></span>

   - <span data-ttu-id="99dcc-154">Для приложений</span><span class="sxs-lookup"><span data-stu-id="99dcc-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="99dcc-155">Необходимо вручную ввести Lync Server в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="99dcc-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="99dcc-156">В раскрывающемся списке этот параметр не отображается.</span><span class="sxs-lookup"><span data-stu-id="99dcc-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="99dcc-157">Дополнительные сведения см. в статье " [Источники данных журнала событий Windows" в службе анализа журналов](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="99dcc-157">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="99dcc-158">Выберите параметры — \> \> счетчики производительности Windows для данных и добавьте счетчики производительности для:</span><span class="sxs-lookup"><span data-stu-id="99dcc-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="99dcc-159">**Счетчики уровня ОС**.</span><span class="sxs-lookup"><span data-stu-id="99dcc-159">**OS level counters**.</span></span> <span data-ttu-id="99dcc-160">Можно добавить счетчики уровня операционной системы, такие как использование процессора, использование памяти, использование сети, или можно использовать существующие решения, такие как производительность и производительность, сетевой монитор, не добавляя счетчики явным образом.</span><span class="sxs-lookup"><span data-stu-id="99dcc-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="99dcc-161">Независимо от того, как вы решите отслеживать их, корпорация Майкрософт рекомендует отслеживать эти счетчики ОС.</span><span class="sxs-lookup"><span data-stu-id="99dcc-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="99dcc-162">**Счетчики Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="99dcc-162">**Skype for Business counters**.</span></span> <span data-ttu-id="99dcc-163">Skype для бизнеса предоставляет множество счетчиков.</span><span class="sxs-lookup"><span data-stu-id="99dcc-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="99dcc-164">Эти счетчики можно найти, выполнив вход на любой сервер-посредник и открыв системный монитор.</span><span class="sxs-lookup"><span data-stu-id="99dcc-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="99dcc-165">Эти счетчики начинаются с "LS:".</span><span class="sxs-lookup"><span data-stu-id="99dcc-165">These counters start with "LS:".</span></span> <span data-ttu-id="99dcc-166">Корпорация Майкрософт рекомендует использовать следующие счетчики мощности как минимум и добавить нужные еще нужные значения.</span><span class="sxs-lookup"><span data-stu-id="99dcc-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="99dcc-167">Общее количество активных вызовов:</span><span class="sxs-lookup"><span data-stu-id="99dcc-167">Total active calls:</span></span>

       - <span data-ttu-id="99dcc-168">LS: MediationServer — текущие входящие вызовы (_Total) \-</span><span class="sxs-lookup"><span data-stu-id="99dcc-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="99dcc-169">LS: MediationServer — текущие исходящие вызовы (_Total) \-</span><span class="sxs-lookup"><span data-stu-id="99dcc-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="99dcc-170">Общее количество активных вызовов обхода мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="99dcc-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="99dcc-171">LS: MediationServer — входящие вызовы (_Total) \- активные вызовы обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="99dcc-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="99dcc-172">LS: MediationServer-исходящие вызовы (_Total) \- активные вызовы обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="99dcc-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="99dcc-173">Необходимо вручную вводить счетчики производительности в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="99dcc-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="99dcc-174">Они не отображаются в виде параметров в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="99dcc-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="99dcc-175">Дополнительные сведения о [источниках данных производительности Windows и Linux в службе анализа журналов](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="99dcc-175">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="99dcc-176">Создание оповещений</span><span class="sxs-lookup"><span data-stu-id="99dcc-176">Create alerts</span></span>

<span data-ttu-id="99dcc-177">В OMS существует два типа оповещений: количество оповещений о результатах и оповещений об измерении показателей.</span><span class="sxs-lookup"><span data-stu-id="99dcc-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="99dcc-178">Дополнительные сведения о создании оповещений можно найти [в статье работа с правилами оповещения в службе анализа журналов](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="99dcc-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="99dcc-179">При создании оповещений следует учитывать следующее:</span><span class="sxs-lookup"><span data-stu-id="99dcc-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="99dcc-180">Убедитесь, что оповещение является предупреждением о результатах, которое является выбором по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="99dcc-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="99dcc-181">В демонстрационных запросах необходимо, чтобы для параметра "число результатов" было задано значение "больше 0".</span><span class="sxs-lookup"><span data-stu-id="99dcc-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="99dcc-182">Рекомендуется устанавливать для интервала времени и частоты оповещений значение 5 минут.</span><span class="sxs-lookup"><span data-stu-id="99dcc-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="99dcc-183">Не рекомендуется включать "подавлять оповещения" для демонстрационных оповещений.</span><span class="sxs-lookup"><span data-stu-id="99dcc-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="99dcc-184">Для типичных сценариев оповещений Корпорация Майкрософт рекомендует создать единую комбинацию оповещений: одно сообщение об ошибке и одно оповещение о сбросе.</span><span class="sxs-lookup"><span data-stu-id="99dcc-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="99dcc-185">Для оповещения об ошибке выберите критический уровень серьезности. для оповещения о сбросе выберите информационный уровень серьезности.</span><span class="sxs-lookup"><span data-stu-id="99dcc-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="99dcc-186">В следующих разделах описано, как создавать образцы оповещений.</span><span class="sxs-lookup"><span data-stu-id="99dcc-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="99dcc-187">**Создание записи оповещения: "РТКМЕДСРВ не работает на серверах-посредниках" и "РТКМЕДСРВ работает на серверах-посредниках"**</span><span class="sxs-lookup"><span data-stu-id="99dcc-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="99dcc-188">Чтобы создать эту комбинацию оповещений:</span><span class="sxs-lookup"><span data-stu-id="99dcc-188">To create this alert pair:</span></span>

- <span data-ttu-id="99dcc-189">Запрос на оповещение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="99dcc-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="99dcc-190">В запросе используется фильтр компьютера,  *где компьютер содержит "MediationServer"*  .</span><span class="sxs-lookup"><span data-stu-id="99dcc-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="99dcc-191">Фильтр выбирает только компьютер, имя которого содержит строку "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="99dcc-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="99dcc-192">Фильтр можно заменить на собственный фильтр компьютера или просто удалить.</span><span class="sxs-lookup"><span data-stu-id="99dcc-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="99dcc-193">Можно создавать сложные строковые фильтры без регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="99dcc-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="99dcc-194">Более подробную информацию можно узнать в статье [Операторы String](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="99dcc-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="99dcc-195">Вы также можете использовать регулярные выражения.</span><span class="sxs-lookup"><span data-stu-id="99dcc-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="99dcc-196">Кроме того, вы можете создать группу компьютеров, сохранив поисковый запрос и используя эту группу в качестве фильтра компьютера в запросе оповещения.</span><span class="sxs-lookup"><span data-stu-id="99dcc-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="99dcc-197">Дополнительные сведения см. [в разделе группы компьютеров в поиске журналов службы анализа журналов](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)</span><span class="sxs-lookup"><span data-stu-id="99dcc-197">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="99dcc-198">Для каждого компьютера запрос об ошибке будет получать последний журнал событий для запуска службы РТКМЕДСРВ и остановки службы.</span><span class="sxs-lookup"><span data-stu-id="99dcc-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="99dcc-199">Если Последнее событие является событием остановки службы, будет возвращен один журнал; Если Последнее событие является событием запуска службы, оно возвратит значение Nothing.</span><span class="sxs-lookup"><span data-stu-id="99dcc-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="99dcc-200">Коротко говоря, запрос вернет список серверов, РТКМЕДСРВ которых остановлен в окне времени.</span><span class="sxs-lookup"><span data-stu-id="99dcc-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="99dcc-201">Запрос на оповещение о сбросе:</span><span class="sxs-lookup"><span data-stu-id="99dcc-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="99dcc-202">Запрос Reset выполняет в точности то же самое обратное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="99dcc-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="99dcc-203">Для каждого компьютера возвращается один, если последним событием является событие запуска службы; Если Последнее событие является событием остановки службы, оно возвратит значение Nothing.</span><span class="sxs-lookup"><span data-stu-id="99dcc-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="99dcc-204">**Создание записи оповещения: "слишком много одновременных вызовов на серверах-посредниках" и "одновременные вызовы отходятся до нормально загруженного"**</span><span class="sxs-lookup"><span data-stu-id="99dcc-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="99dcc-205">Чтобы создать это оповещение:</span><span class="sxs-lookup"><span data-stu-id="99dcc-205">To create this alert:</span></span>

- <span data-ttu-id="99dcc-206">Запрос на оповещение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="99dcc-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="99dcc-207">Для каждого компьютера запрос получает последние счетчики входящего и исходящего звонка, а также выводит эти два значения.</span><span class="sxs-lookup"><span data-stu-id="99dcc-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="99dcc-208">Он возвратит один журнал, если сумма превышает 500; Если это не так, он возвратит значение Nothing.</span><span class="sxs-lookup"><span data-stu-id="99dcc-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="99dcc-209">Коротко говоря, запрос возвращает список серверов, одновременные вызовы которых слишком много в окне времени.</span><span class="sxs-lookup"><span data-stu-id="99dcc-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="99dcc-210">Запрос на оповещение о сбросе:</span><span class="sxs-lookup"><span data-stu-id="99dcc-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="99dcc-211">Запрос Reset выполняет в точности то же самое обратное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="99dcc-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="99dcc-212">Для каждого компьютера запрос получает последние счетчики входящего и исходящего звонка, а также выводит эти два значения.</span><span class="sxs-lookup"><span data-stu-id="99dcc-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="99dcc-213">Он возвратит один журнал, если значение sum меньше 500; в противном случае он возвратит значение Nothing.</span><span class="sxs-lookup"><span data-stu-id="99dcc-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="99dcc-214">**Создание оповещения: "предупреждение об использовании ЦП \> 90 или рткмедиарелай остановлено на серверах"**</span><span class="sxs-lookup"><span data-stu-id="99dcc-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="99dcc-215">Для создания этого оповещения используется следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="99dcc-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="99dcc-216">Запрос будет получать все события счетчика использования процессора и остановки службы со всех компьютеров и возвращать один журнал, если загрузка процессора превышает 90% или служба когда-либо останавливается.</span><span class="sxs-lookup"><span data-stu-id="99dcc-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="99dcc-217">Анализ оповещений в репозитории анализа журналов</span><span class="sxs-lookup"><span data-stu-id="99dcc-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="99dcc-218">Чтобы проанализировать оповещения в репозитории, используйте решение для управления оповещениями.</span><span class="sxs-lookup"><span data-stu-id="99dcc-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="99dcc-219">Дополнительные сведения: решение для [управления оповещениями в Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="99dcc-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="99dcc-220">Рекомендуемый минимальный набор мониторинга</span><span class="sxs-lookup"><span data-stu-id="99dcc-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="99dcc-221">Чтобы определить проблемы с журналами событий и счетчиками производительности, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="99dcc-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="99dcc-222">**Журналы событий.**</span><span class="sxs-lookup"><span data-stu-id="99dcc-222">**Event logs.**</span></span> <span data-ttu-id="99dcc-223">При возникновении любой проблемы должна быть сопоставлена одна и та же группа событий, в которой один набор событий указывает на то, что что-то не так, а другое указывает на то, что все правильно.</span><span class="sxs-lookup"><span data-stu-id="99dcc-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="99dcc-224">Для любого определенного периода времени это последнее записанное событие, которое указывает, является ли что-либо амисс для этого периода времени.</span><span class="sxs-lookup"><span data-stu-id="99dcc-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="99dcc-225">**Счетчики производительности.**</span><span class="sxs-lookup"><span data-stu-id="99dcc-225">**Performance Counters.**</span></span> <span data-ttu-id="99dcc-226">Для наблюдаемых счетчиков должно быть задано пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="99dcc-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="99dcc-227">В следующей таблице перечислены службы, которые корпорация Майкрософт рекомендует отслеживать, указывая идентификаторы событий Stop и Start:</span><span class="sxs-lookup"><span data-stu-id="99dcc-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="99dcc-228">Имя службы</span><span class="sxs-lookup"><span data-stu-id="99dcc-228">Service Name</span></span>  <br/> |<span data-ttu-id="99dcc-229">Роль целевого сервера</span><span class="sxs-lookup"><span data-stu-id="99dcc-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="99dcc-230">Код события Stop</span><span class="sxs-lookup"><span data-stu-id="99dcc-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="99dcc-231">Код события запуска</span><span class="sxs-lookup"><span data-stu-id="99dcc-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="99dcc-232">рткмедсрв</span><span class="sxs-lookup"><span data-stu-id="99dcc-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="99dcc-233">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="99dcc-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="99dcc-234">25003</span><span class="sxs-lookup"><span data-stu-id="99dcc-234">25003</span></span>  <br/> |<span data-ttu-id="99dcc-235">25002</span><span class="sxs-lookup"><span data-stu-id="99dcc-235">25002</span></span>  <br/> |
|<span data-ttu-id="99dcc-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="99dcc-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="99dcc-237">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="99dcc-237">Edge Server</span></span>  <br/> |<span data-ttu-id="99dcc-238">12289</span><span class="sxs-lookup"><span data-stu-id="99dcc-238">12289</span></span>  <br/> |<span data-ttu-id="99dcc-239">12288</span><span class="sxs-lookup"><span data-stu-id="99dcc-239">12288</span></span>  <br/> |
|<span data-ttu-id="99dcc-240">рткмраус</span><span class="sxs-lookup"><span data-stu-id="99dcc-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="99dcc-241">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="99dcc-241">Edge Server</span></span>  <br/> |<span data-ttu-id="99dcc-242">19003</span><span class="sxs-lookup"><span data-stu-id="99dcc-242">19003</span></span>  <br/> |<span data-ttu-id="99dcc-243">19002</span><span class="sxs-lookup"><span data-stu-id="99dcc-243">19002</span></span>  <br/> |
|<span data-ttu-id="99dcc-244">рткмедиарелай</span><span class="sxs-lookup"><span data-stu-id="99dcc-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="99dcc-245">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="99dcc-245">Edge Server</span></span>  <br/> |<span data-ttu-id="99dcc-246">22003</span><span class="sxs-lookup"><span data-stu-id="99dcc-246">22003</span></span>  <br/> |<span data-ttu-id="99dcc-247">22002</span><span class="sxs-lookup"><span data-stu-id="99dcc-247">22002</span></span>  <br/> |

<span data-ttu-id="99dcc-248">В следующей таблице перечислены сетевые проблемы, которые корпорация Майкрософт рекомендует отслеживать:</span><span class="sxs-lookup"><span data-stu-id="99dcc-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="99dcc-249">Имя монитора</span><span class="sxs-lookup"><span data-stu-id="99dcc-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="99dcc-250">Роль целевого сервера</span><span class="sxs-lookup"><span data-stu-id="99dcc-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="99dcc-251">Выражение идентификатора события Success</span><span class="sxs-lookup"><span data-stu-id="99dcc-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="99dcc-252">Выражение идентификатора события ошибки</span><span class="sxs-lookup"><span data-stu-id="99dcc-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="99dcc-253">Пример ошибки</span><span class="sxs-lookup"><span data-stu-id="99dcc-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="99dcc-254">Ошибка подключения сервера-посредника к шлюзу</span><span class="sxs-lookup"><span data-stu-id="99dcc-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="99dcc-255">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="99dcc-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="99dcc-256">25062</span><span class="sxs-lookup"><span data-stu-id="99dcc-256">25062</span></span>                              |                                  | <span data-ttu-id="99dcc-257">25002</span><span class="sxs-lookup"><span data-stu-id="99dcc-257">25002</span></span>  <br/>           |
| <span data-ttu-id="99dcc-258">Сбой при завершении вызова сервера-посредника на шлюз</span><span class="sxs-lookup"><span data-stu-id="99dcc-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="99dcc-259">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="99dcc-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="99dcc-260">25064</span><span class="sxs-lookup"><span data-stu-id="99dcc-260">25064</span></span>                              |                                  | <span data-ttu-id="99dcc-261">25002</span><span class="sxs-lookup"><span data-stu-id="99dcc-261">25002</span></span>  <br/>           |
| <span data-ttu-id="99dcc-262">Критические проблемы с сетью</span><span class="sxs-lookup"><span data-stu-id="99dcc-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="99dcc-263">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="99dcc-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="99dcc-264">14353</span><span class="sxs-lookup"><span data-stu-id="99dcc-264">14353</span></span>                              |                                  | <span data-ttu-id="99dcc-265">12288</span><span class="sxs-lookup"><span data-stu-id="99dcc-265">12288</span></span>  <br/>           |

<span data-ttu-id="99dcc-266">Ниже перечислены счетчики мощности звонков, которые необходимо отслеживать.</span><span class="sxs-lookup"><span data-stu-id="99dcc-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="99dcc-267">Эти номера должны быть меньше, чем 500 для выпуска Cloud Connector Standard Edition; меньше 50 для минимального выпуска Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="99dcc-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="99dcc-268">LS: MediationServer — текущие входящие вызовы (_Total) \-</span><span class="sxs-lookup"><span data-stu-id="99dcc-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="99dcc-269">LS: MediationServer — текущие исходящие вызовы (_Total) \-</span><span class="sxs-lookup"><span data-stu-id="99dcc-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="99dcc-270">LS: MediationServer — входящие вызовы (_Total) \- активные вызовы обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="99dcc-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="99dcc-271">LS: MediationServer-исходящие вызовы (_Total) \- активные вызовы обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="99dcc-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="99dcc-272">См. также</span><span class="sxs-lookup"><span data-stu-id="99dcc-272">See also</span></span>

<span data-ttu-id="99dcc-273">Дополнительные сведения о работе с OMS можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="99dcc-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="99dcc-274">Поиск данных с помощью поиска в журнале в службе анализа журналов</span><span class="sxs-lookup"><span data-stu-id="99dcc-274">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="99dcc-275">Справочник по языку службы анализа журналов Azure</span><span class="sxs-lookup"><span data-stu-id="99dcc-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="99dcc-276">Общие сведения об оповещениях в службе анализа журналов</span><span class="sxs-lookup"><span data-stu-id="99dcc-276">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="99dcc-277">Подключение компьютеров Windows к службе анализа журналов в Azure</span><span class="sxs-lookup"><span data-stu-id="99dcc-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


