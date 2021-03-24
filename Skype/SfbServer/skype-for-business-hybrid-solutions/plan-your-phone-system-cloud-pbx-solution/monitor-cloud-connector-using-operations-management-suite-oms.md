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
description: Ознакомьтесь с этой темой, чтобы узнать, как отслеживать развертывание облачной версии 2.1 и более позднее развертывание с помощью пакета управления операциями Майкрософт (OMS).
ms.openlocfilehash: 55685aae01bdcc3c7c979627dbba910bb33203fa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098545"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="48e8e-103">Отслеживание Cloud Connector с помощью Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="48e8e-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="48e8e-104">Cloud Connector Edition завершит карьеру 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="48e8e-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="48e8e-105">После обновления организации до Teams узнайте, как подключить сеть локальной телефонии к Teams с помощью прямой [маршрутизации.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="48e8e-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="48e8e-106">Ознакомьтесь с этой темой, чтобы узнать, как отслеживать развертывание облачной версии 2.1 и более позднее развертывание с помощью пакета управления операциями Майкрософт (OMS).</span><span class="sxs-lookup"><span data-stu-id="48e8e-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="48e8e-107">Теперь вы можете отслеживать развертывание облачной соединители версии 2.1 и более поздней версии с помощью пакета управления операциями (OMS) — решения для управления облачными ИТ-службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="48e8e-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="48e8e-108">OmS Log Analytics позволяет отслеживать и анализировать доступность и производительность ресурсов, включая физические и виртуальные машины.</span><span class="sxs-lookup"><span data-stu-id="48e8e-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="48e8e-109">Дополнительные сведения о oms и log Analytics см. в обзоре [What is Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="48e8e-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="48e8e-110">В этом разделе содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="48e8e-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="48e8e-111">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="48e8e-111">Prerequisites</span></span>

- <span data-ttu-id="48e8e-112">Настройка облачного соединитетеля для использования OMS</span><span class="sxs-lookup"><span data-stu-id="48e8e-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="48e8e-113">Настройка OMS</span><span class="sxs-lookup"><span data-stu-id="48e8e-113">Configure OMS</span></span>

- <span data-ttu-id="48e8e-114">Анализ оповещений в репозитории Log Analytics</span><span class="sxs-lookup"><span data-stu-id="48e8e-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="48e8e-115">Рекомендуемый набор мониторинга</span><span class="sxs-lookup"><span data-stu-id="48e8e-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48e8e-116">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="48e8e-116">Prerequisites</span></span>

<span data-ttu-id="48e8e-117">Прежде чем использовать OMS для мониторинга развертывания облачного соединитетеля, вам потребуется следующее:</span><span class="sxs-lookup"><span data-stu-id="48e8e-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="48e8e-118">**Учетная запись Azure и рабочее пространство OMS.**</span><span class="sxs-lookup"><span data-stu-id="48e8e-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="48e8e-119">Если у вас еще нет учетной записи Azure, необходимо создать ее для использования omS Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="48e8e-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="48e8e-120">Сведения о создании учетной записи Azure и создании рабочего пространства OMS см. в журнале [Get started with a Log Analytics workspace.](/azure/log-analytics/log-analytics-get-started)</span><span class="sxs-lookup"><span data-stu-id="48e8e-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="48e8e-121">**Cloud Connector версии 2.1 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="48e8e-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="48e8e-122">**Для мониторинга облачного** соединитетеля необходим новый поиск журнала Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="48e8e-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="48e8e-123">Дополнительные сведения см. в [журнале Upgrade your Azure Log Analytics workspace to new log search.](/azure/log-analytics/log-analytics-log-search-upgrade)</span><span class="sxs-lookup"><span data-stu-id="48e8e-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="48e8e-124">Настройка облачного соединитетеля для использования OMS</span><span class="sxs-lookup"><span data-stu-id="48e8e-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="48e8e-125">Вам потребуется настроить локальное окружение облачного соединитетеля для использования OMS.</span><span class="sxs-lookup"><span data-stu-id="48e8e-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="48e8e-126">Для этого вам потребуется свой ИД рабочего пространства OMS и ключ, который можно найти с помощью портала OMS следующим образом: Параметры -- Подключенные источники \> -- \> Windows Servers:</span><span class="sxs-lookup"><span data-stu-id="48e8e-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Снимок экрана для OMS облачного соединитела](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="48e8e-128">Настройка облачного соединитетеля для использования OMS зависит от вашего сценария:</span><span class="sxs-lookup"><span data-stu-id="48e8e-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="48e8e-129">**Если вы устанавливаете** новый прибор облачного соединителя или хотите повторно развернуть устройство, выполните следующие действия перед запуском Install-CcAppliance:</span><span class="sxs-lookup"><span data-stu-id="48e8e-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="48e8e-130">В разделе CloudConnector.ini файл [Common] задай параметр OMSEnabled true.</span><span class="sxs-lookup"><span data-stu-id="48e8e-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="48e8e-131">Каждый раз, когда облачный соединитатель развернут или обновлен, он будет пытаться установить агент OMS автоматически на VMs.</span><span class="sxs-lookup"><span data-stu-id="48e8e-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="48e8e-132">Включи эту функцию, чтобы агент OMS выдержал автоматическое обновление облачного соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="48e8e-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="48e8e-133">Чтобы настроить oms ID и ключ, запустите Set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="48e8e-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="48e8e-134">**Если вы устанавливаете** агент OMS на существующее устройство облачного соединителя, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="48e8e-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="48e8e-135">В разделе CloudConnector.ini файл [Общие] установите OMSEnabled=true.</span><span class="sxs-lookup"><span data-stu-id="48e8e-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="48e8e-136">Запустите Import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="48e8e-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="48e8e-137">Запустите Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="48e8e-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="48e8e-138">Если учетные данные OMSWorkspace никогда не задавались, вам будет предложено выполнить установку-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="48e8e-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="48e8e-139">**Если вы хотите обновить ID рабочего пространства OMS или ключ в устройстве облачного соединиттеля, который уже установил агент OMS:**</span><span class="sxs-lookup"><span data-stu-id="48e8e-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="48e8e-140">Чтобы настроить oms ID и ключ, запустите Set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="48e8e-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="48e8e-141">Чтобы применить обновления, запустите Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="48e8e-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="48e8e-142">**Во всех сценариях убедитесь, что агенты подключены следующим образом:**</span><span class="sxs-lookup"><span data-stu-id="48e8e-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="48e8e-143">На портале OMS перейдите в параметры — \> Подключенные источники — \> Windows Servers.</span><span class="sxs-lookup"><span data-stu-id="48e8e-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="48e8e-144">Вы увидите список подключенных машин.</span><span class="sxs-lookup"><span data-stu-id="48e8e-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="48e8e-145">Настройка OMS</span><span class="sxs-lookup"><span data-stu-id="48e8e-145">Configure OMS</span></span>

<span data-ttu-id="48e8e-146">Далее необходимо указать конфигурацию OMS с помощью портала OMS.</span><span class="sxs-lookup"><span data-stu-id="48e8e-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="48e8e-147">В частности, необходимо:</span><span class="sxs-lookup"><span data-stu-id="48e8e-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="48e8e-148">Укажите сведения о журналах событий и счетчиках производительности.</span><span class="sxs-lookup"><span data-stu-id="48e8e-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="48e8e-149">Создание оповещений</span><span class="sxs-lookup"><span data-stu-id="48e8e-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="48e8e-150">Укажите сведения о журналах событий и счетчиках производительности</span><span class="sxs-lookup"><span data-stu-id="48e8e-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="48e8e-151">На портале OMS необходимо указать сведения о журналах событий и счетчиках производительности следующим образом:</span><span class="sxs-lookup"><span data-stu-id="48e8e-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="48e8e-152">Перейдите в журналы событий \> Settings- \> Data-Windows и добавьте журналы событий для:</span><span class="sxs-lookup"><span data-stu-id="48e8e-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="48e8e-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="48e8e-153">Lync Server</span></span>

   - <span data-ttu-id="48e8e-154">Приложение</span><span class="sxs-lookup"><span data-stu-id="48e8e-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="48e8e-155">Необходимо вручную ввести Lync Server в текстовом окне.</span><span class="sxs-lookup"><span data-stu-id="48e8e-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="48e8e-156">Он не появляется в качестве параметра в списке выпаданий.</span><span class="sxs-lookup"><span data-stu-id="48e8e-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="48e8e-157">Дополнительные сведения см. в журнале данных журнала событий [Windows в журнале Log Analytics.](/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="48e8e-157">For more information, see [Windows event log data sources in Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="48e8e-158">Перейдите к счетчикам производительности \> \> Settings- Data-Windows и добавьте счетчики производительности для:</span><span class="sxs-lookup"><span data-stu-id="48e8e-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="48e8e-159">**Счетчики уровня ОС.**</span><span class="sxs-lookup"><span data-stu-id="48e8e-159">**OS level counters**.</span></span> <span data-ttu-id="48e8e-160">Можно добавить счетчики уровня ОС, такие как использование процессора, использование памяти, использование сети или использование существующих решений, таких как Capacity и Performance, Network Performance Monitor, без явного добавления счетчиков.</span><span class="sxs-lookup"><span data-stu-id="48e8e-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="48e8e-161">Независимо от того, как вы решите отслеживать их, Корпорация Майкрософт рекомендует отслеживать эти счетчики ОС.</span><span class="sxs-lookup"><span data-stu-id="48e8e-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="48e8e-162">**Счетчики Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="48e8e-162">**Skype for Business counters**.</span></span> <span data-ttu-id="48e8e-163">Существует множество счетчиков, предоставляемых Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="48e8e-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="48e8e-164">Эти счетчики можно найти, войдя на любой сервер-посредник и открыв монитор производительности.</span><span class="sxs-lookup"><span data-stu-id="48e8e-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="48e8e-165">Эти счетчики начинаются с "LS:".</span><span class="sxs-lookup"><span data-stu-id="48e8e-165">These counters start with "LS:".</span></span> <span data-ttu-id="48e8e-166">Корпорация Майкрософт рекомендует как минимум начинать со следующих счетчиков емкости и добавлять другие интересные:</span><span class="sxs-lookup"><span data-stu-id="48e8e-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="48e8e-167">Общее количество активных вызовов:</span><span class="sxs-lookup"><span data-stu-id="48e8e-167">Total active calls:</span></span>

       - <span data-ttu-id="48e8e-168">LS:MediationServer — входящие вызовы \- (_Total)</span><span class="sxs-lookup"><span data-stu-id="48e8e-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="48e8e-169">LS:MediationServer — исходящие вызовы \- (_Total)</span><span class="sxs-lookup"><span data-stu-id="48e8e-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="48e8e-170">Общее количество звонков об обхода активных средств массовой информации:</span><span class="sxs-lookup"><span data-stu-id="48e8e-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="48e8e-171">LS:MediationServer — входящие вызовы (_Total) \- активные вызовы обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="48e8e-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="48e8e-172">LS:MediationServer — исходящие вызовы (_Total) \- активные вызовы обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="48e8e-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="48e8e-173">Необходимо вручную ввести счетчики производительности в текстовом окне.</span><span class="sxs-lookup"><span data-stu-id="48e8e-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="48e8e-174">Они не отображаются в качестве параметров в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="48e8e-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="48e8e-175">Дополнительные сведения см. в источниках данных о производительности Windows и [Linux в журнале Analytics.](/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="48e8e-175">For more information, see [Windows and Linux performance data sources in Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="48e8e-176">Создание оповещений</span><span class="sxs-lookup"><span data-stu-id="48e8e-176">Create alerts</span></span>

<span data-ttu-id="48e8e-177">В OMS есть два типа оповещений: количество оповещений о результатах и оповещений об измерении показателей.</span><span class="sxs-lookup"><span data-stu-id="48e8e-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="48e8e-178">Дополнительные сведения о создании оповещений см. в журнале [Working with alert rules in Log Analytics.](/azure/log-analytics/log-analytics-alerts-creating)</span><span class="sxs-lookup"><span data-stu-id="48e8e-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="48e8e-179">При создании оповещений следует учитывать следующее:</span><span class="sxs-lookup"><span data-stu-id="48e8e-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="48e8e-180">Убедитесь, что оповещение является оповещением о количестве результатов, которое является выбором по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="48e8e-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="48e8e-181">В демо-запросах требуется, чтобы "Количество результатов" было установлено как "Больше 0".</span><span class="sxs-lookup"><span data-stu-id="48e8e-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="48e8e-182">Рекомендуется установить периодичность времени и частоты оповещений до 5 минут.</span><span class="sxs-lookup"><span data-stu-id="48e8e-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="48e8e-183">Рекомендуется не включить "Подавления оповещений" для демонстрационных оповещений.</span><span class="sxs-lookup"><span data-stu-id="48e8e-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="48e8e-184">Для типичных сценариев оповещения Корпорация Майкрософт рекомендует создать пару оповещений: одно оповещение об ошибке и одно оповещение об сбросе.</span><span class="sxs-lookup"><span data-stu-id="48e8e-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="48e8e-185">Для оповещений об ошибке выберите критический уровень серьезности; для оповещения об сбросе выберите информационный уровень серьезности .</span><span class="sxs-lookup"><span data-stu-id="48e8e-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="48e8e-186">В следующих разделах описано, как создавать примеры оповещений.</span><span class="sxs-lookup"><span data-stu-id="48e8e-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="48e8e-187">**Создайте пару оповещений: "RTCMEDSRV не работает на серверах-посредниках" и "RTCMEDSRV снова запущен в серверах-посредниках"**</span><span class="sxs-lookup"><span data-stu-id="48e8e-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="48e8e-188">Чтобы создать эту пару оповещений:</span><span class="sxs-lookup"><span data-stu-id="48e8e-188">To create this alert pair:</span></span>

- <span data-ttu-id="48e8e-189">Запрос оповещения об ошибке:</span><span class="sxs-lookup"><span data-stu-id="48e8e-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="48e8e-190">В запросе используется компьютерный *фильтр, в котором Компьютер содержит "MediationServer".*</span><span class="sxs-lookup"><span data-stu-id="48e8e-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="48e8e-191">Фильтр выбирает только компьютер, имя которого содержит строку "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="48e8e-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="48e8e-192">Вы замените фильтр собственным компьютерным фильтром или просто удалите его.</span><span class="sxs-lookup"><span data-stu-id="48e8e-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="48e8e-193">Можно создавать сложные фильтры строк без регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="48e8e-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="48e8e-194">Дополнительные сведения см. в [стряхтовом операторе.](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)</span><span class="sxs-lookup"><span data-stu-id="48e8e-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="48e8e-195">Вы также можете использовать регулярные выражения.</span><span class="sxs-lookup"><span data-stu-id="48e8e-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="48e8e-196">Кроме того, можно создать компьютерную группу, сэкономив поисковый запрос и используя ее в качестве фильтра компьютера в запросе оповещений.</span><span class="sxs-lookup"><span data-stu-id="48e8e-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="48e8e-197">Дополнительные сведения см. в [журнале Computer groups in Log Analytics.](/azure/log-analytics/log-analytics-computer-groups)</span><span class="sxs-lookup"><span data-stu-id="48e8e-197">For more information, see [Computer groups in Log Analytics log searches](/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="48e8e-198">Для каждого компьютера запрос об ошибке получит последний журнал событий как для запуска службы RTCMEDSRV, так и для остановки службы.</span><span class="sxs-lookup"><span data-stu-id="48e8e-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="48e8e-199">Он возвращает один журнал, если последним событием является событие остановки службы; он не возвращает ничего, если последним событием является событие запуска службы.</span><span class="sxs-lookup"><span data-stu-id="48e8e-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="48e8e-200">Короче говоря, запрос возвращает список серверов, RTCMEDSRV которых остановлен в окне времени.</span><span class="sxs-lookup"><span data-stu-id="48e8e-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="48e8e-201">Запрос для оповещений об сбросе:</span><span class="sxs-lookup"><span data-stu-id="48e8e-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="48e8e-202">Запрос сброса делает ровно противоположное тому, что происходит с запросом об ошибке.</span><span class="sxs-lookup"><span data-stu-id="48e8e-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="48e8e-203">Для каждого компьютера он возвращает одно событие, если последним событием является событие запуска службы; он не возвращает ничего, если последним событием является событие остановки службы.</span><span class="sxs-lookup"><span data-stu-id="48e8e-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="48e8e-204">**Создайте пару оповещений: "Слишком много одновременно вызовов в серверах-посредниках" и "Одновременное выполнение вызовов возвращается к нормальной нагрузке"**</span><span class="sxs-lookup"><span data-stu-id="48e8e-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="48e8e-205">Чтобы создать это предупреждение:</span><span class="sxs-lookup"><span data-stu-id="48e8e-205">To create this alert:</span></span>

- <span data-ttu-id="48e8e-206">Запрос оповещения об ошибке:</span><span class="sxs-lookup"><span data-stu-id="48e8e-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="48e8e-207">На каждом компьютере запрос получит последние счетчики входящие вызовы и исходящие вызовы и суммирует эти два значения.</span><span class="sxs-lookup"><span data-stu-id="48e8e-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="48e8e-208">Он возвращает один журнал, если значение суммы превышает 500; он ничего не возвращает, если этого не делается.</span><span class="sxs-lookup"><span data-stu-id="48e8e-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="48e8e-209">Короче говоря, запрос возвращает список серверов, чьи одновременно вызовы слишком много в окне времени.</span><span class="sxs-lookup"><span data-stu-id="48e8e-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="48e8e-210">Запрос для оповещений об сбросе:</span><span class="sxs-lookup"><span data-stu-id="48e8e-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="48e8e-211">Запрос сброса делает ровно противоположное тому, что происходит с запросом об ошибке.</span><span class="sxs-lookup"><span data-stu-id="48e8e-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="48e8e-212">На каждом компьютере запрос получит последние счетчики входящие вызовы и исходящие вызовы и суммирует эти два значения.</span><span class="sxs-lookup"><span data-stu-id="48e8e-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="48e8e-213">Он возвращает один журнал, если значение суммы меньше 500; иначе ничего не будет возвращаться.</span><span class="sxs-lookup"><span data-stu-id="48e8e-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="48e8e-214">**Создание оповещений: "Использование \> ЦП 90 или RTCMEDIARELAY остановлено на серверах" оповещение**</span><span class="sxs-lookup"><span data-stu-id="48e8e-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="48e8e-215">Чтобы создать это оповещение, запрос:</span><span class="sxs-lookup"><span data-stu-id="48e8e-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="48e8e-216">Запрос будет получать все счетчик использования процессора и событие остановки службы со всех компьютеров и возвращать один журнал, если использование процессора превышает 90% или служба когда-либо остановлена.</span><span class="sxs-lookup"><span data-stu-id="48e8e-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="48e8e-217">Анализ оповещений в репозитории Log Analytics</span><span class="sxs-lookup"><span data-stu-id="48e8e-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="48e8e-218">Для анализа оповещений в репозитории используйте решение Alert Management.</span><span class="sxs-lookup"><span data-stu-id="48e8e-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="48e8e-219">Дополнительные сведения см. в решении Alert Management в пакете управления операциями [(OMS)](/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="48e8e-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="48e8e-220">Рекомендуемый минимальный набор мониторинга</span><span class="sxs-lookup"><span data-stu-id="48e8e-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="48e8e-221">Определение проблем с журналами событий и счетчиками производительности:</span><span class="sxs-lookup"><span data-stu-id="48e8e-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="48e8e-222">**Журналы событий.**</span><span class="sxs-lookup"><span data-stu-id="48e8e-222">**Event logs.**</span></span> <span data-ttu-id="48e8e-223">Для любой проблемы должна быть пара событий с одним набором событий, чтобы указать, что что-то не так, в то время как другой указывает, что все хорошо.</span><span class="sxs-lookup"><span data-stu-id="48e8e-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="48e8e-224">Для любого определенного периода времени это последнее записанное событие, которое указывает, является ли что-то недопустимым для этого периода времени.</span><span class="sxs-lookup"><span data-stu-id="48e8e-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="48e8e-225">**Счетчики производительности.**</span><span class="sxs-lookup"><span data-stu-id="48e8e-225">**Performance Counters.**</span></span> <span data-ttu-id="48e8e-226">Для контрольных счетчиков должен быть порог.</span><span class="sxs-lookup"><span data-stu-id="48e8e-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="48e8e-227">В следующей таблице перечислены службы, которые Корпорация Майкрософт рекомендует контролировать, перечисляя стоп-и запуск ID событий:</span><span class="sxs-lookup"><span data-stu-id="48e8e-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="48e8e-228">Имя службы</span><span class="sxs-lookup"><span data-stu-id="48e8e-228">Service Name</span></span>  <br/> |<span data-ttu-id="48e8e-229">Роль целевого сервера</span><span class="sxs-lookup"><span data-stu-id="48e8e-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="48e8e-230">Stop Event ID</span><span class="sxs-lookup"><span data-stu-id="48e8e-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="48e8e-231">Start Event ID</span><span class="sxs-lookup"><span data-stu-id="48e8e-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="48e8e-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="48e8e-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="48e8e-233">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="48e8e-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="48e8e-234">25003</span><span class="sxs-lookup"><span data-stu-id="48e8e-234">25003</span></span>  <br/> |<span data-ttu-id="48e8e-235">25002</span><span class="sxs-lookup"><span data-stu-id="48e8e-235">25002</span></span>  <br/> |
|<span data-ttu-id="48e8e-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="48e8e-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="48e8e-237">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="48e8e-237">Edge Server</span></span>  <br/> |<span data-ttu-id="48e8e-238">12289</span><span class="sxs-lookup"><span data-stu-id="48e8e-238">12289</span></span>  <br/> |<span data-ttu-id="48e8e-239">12288</span><span class="sxs-lookup"><span data-stu-id="48e8e-239">12288</span></span>  <br/> |
|<span data-ttu-id="48e8e-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="48e8e-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="48e8e-241">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="48e8e-241">Edge Server</span></span>  <br/> |<span data-ttu-id="48e8e-242">19003</span><span class="sxs-lookup"><span data-stu-id="48e8e-242">19003</span></span>  <br/> |<span data-ttu-id="48e8e-243">19002</span><span class="sxs-lookup"><span data-stu-id="48e8e-243">19002</span></span>  <br/> |
|<span data-ttu-id="48e8e-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="48e8e-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="48e8e-245">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="48e8e-245">Edge Server</span></span>  <br/> |<span data-ttu-id="48e8e-246">22003</span><span class="sxs-lookup"><span data-stu-id="48e8e-246">22003</span></span>  <br/> |<span data-ttu-id="48e8e-247">22002</span><span class="sxs-lookup"><span data-stu-id="48e8e-247">22002</span></span>  <br/> |

<span data-ttu-id="48e8e-248">В следующей таблице перечислены сетевые проблемы, которые корпорация Майкрософт рекомендует контролировать:</span><span class="sxs-lookup"><span data-stu-id="48e8e-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="48e8e-249">Имя монитора</span><span class="sxs-lookup"><span data-stu-id="48e8e-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="48e8e-250">Роль целевого сервера</span><span class="sxs-lookup"><span data-stu-id="48e8e-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="48e8e-251">Выражение ID событий успеха</span><span class="sxs-lookup"><span data-stu-id="48e8e-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="48e8e-252">Выражение ID событий ошибки</span><span class="sxs-lookup"><span data-stu-id="48e8e-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="48e8e-253">Пример отказа</span><span class="sxs-lookup"><span data-stu-id="48e8e-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="48e8e-254">Сервер-посредник для сбоя подключения к шлюзу</span><span class="sxs-lookup"><span data-stu-id="48e8e-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="48e8e-255">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="48e8e-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="48e8e-256">25062</span><span class="sxs-lookup"><span data-stu-id="48e8e-256">25062</span></span>                              |                                  | <span data-ttu-id="48e8e-257">25002</span><span class="sxs-lookup"><span data-stu-id="48e8e-257">25002</span></span>  <br/>           |
| <span data-ttu-id="48e8e-258">Сервер-посредник для сбоя завершения вызова шлюза</span><span class="sxs-lookup"><span data-stu-id="48e8e-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="48e8e-259">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="48e8e-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="48e8e-260">25064</span><span class="sxs-lookup"><span data-stu-id="48e8e-260">25064</span></span>                              |                                  | <span data-ttu-id="48e8e-261">25002</span><span class="sxs-lookup"><span data-stu-id="48e8e-261">25002</span></span>  <br/>           |
| <span data-ttu-id="48e8e-262">Критические сетевые проблемы</span><span class="sxs-lookup"><span data-stu-id="48e8e-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="48e8e-263">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="48e8e-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="48e8e-264">14353</span><span class="sxs-lookup"><span data-stu-id="48e8e-264">14353</span></span>                              |                                  | <span data-ttu-id="48e8e-265">12288</span><span class="sxs-lookup"><span data-stu-id="48e8e-265">12288</span></span>  <br/>           |

<span data-ttu-id="48e8e-266">Ниже перечислены счетчики емкости вызовов, которые необходимо отслеживать.</span><span class="sxs-lookup"><span data-stu-id="48e8e-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="48e8e-267">Эти цифры должны быть меньше 500 для стандартного выпуска Cloud Connector; менее 50 для минимального выпуска cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="48e8e-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="48e8e-268">LS:MediationServer — входящие вызовы \- (_Total)</span><span class="sxs-lookup"><span data-stu-id="48e8e-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="48e8e-269">LS:MediationServer — исходящие вызовы \- (_Total)</span><span class="sxs-lookup"><span data-stu-id="48e8e-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="48e8e-270">LS:MediationServer — входящие вызовы (_Total) \- активные вызовы обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="48e8e-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="48e8e-271">LS:MediationServer — исходящие вызовы (_Total) \- активные вызовы обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="48e8e-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="48e8e-272">См. также</span><span class="sxs-lookup"><span data-stu-id="48e8e-272">See also</span></span>

<span data-ttu-id="48e8e-273">Дополнительные сведения о работе с OMS см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="48e8e-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="48e8e-274">Поиск данных с помощью поиска журналов в журнале Analytics</span><span class="sxs-lookup"><span data-stu-id="48e8e-274">Find data using log searches in Log Analytics</span></span>](/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="48e8e-275">Языковая ссылка Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="48e8e-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="48e8e-276">Понимание оповещений в журнале Analytics</span><span class="sxs-lookup"><span data-stu-id="48e8e-276">Understanding alerts in Log Analytics</span></span>](/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="48e8e-277">Подключение компьютеров Windows к службе аналитики журналов в Azure</span><span class="sxs-lookup"><span data-stu-id="48e8e-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](/azure/log-analytics/log-analytics-windows-agents)