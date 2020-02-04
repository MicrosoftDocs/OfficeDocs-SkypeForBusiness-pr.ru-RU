---
title: 'Lync Server 2013: операционные зависимости'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26e7de821dee778d4b0b1e9aa105669635abaf6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="9ca34-102">Операционные зависимости в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ca34-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ca34-103">_**Тема последнего изменения:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="9ca34-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="9ca34-104">Эталонная архитектура, обсуждаемая в этом документе, поможет вам убедиться в том, что у вас есть развертывание Lync Server 2013, которое не только масштабируется по требованиям Организации, но является архитектором в соответствии с рекомендациями Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9ca34-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="9ca34-105">Это может быть так, что в случае, если реализация Lync Server 2013 является динамической службой, а также в любой другой службе в предприятии для обеспечения высокого уровня доступности и качества обслуживания для бизнеса требуется мониторинг и профилактическое управление.</span><span class="sxs-lookup"><span data-stu-id="9ca34-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="9ca34-106">Поскольку Lync Server 2013 становится детально неструктурированными в повседневной деятельности Организации, важно, чтобы служба управлялась точным и материальным уровнем обслуживания.</span><span class="sxs-lookup"><span data-stu-id="9ca34-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="9ca34-107">Архитектура системы Lync может быть сложной и интегрированной, а также для обеспечения эффективной управления уровнем обслуживания и определения соглашений об оценках эффективности для Lync Server 2013, что важно для понимания зависимостей системы на других платформах и серверах.</span><span class="sxs-lookup"><span data-stu-id="9ca34-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="9ca34-108">Важно отметить, какие бизнес-службы, например интегрированные приложения для голосовой связи и Объединенных коммуникаций, стали зависеть от Lync.</span><span class="sxs-lookup"><span data-stu-id="9ca34-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="9ca34-109">Необходимо установить Lync Server 2013, указывая все просказанные зависимости.</span><span class="sxs-lookup"><span data-stu-id="9ca34-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="9ca34-110">Карта обслуживания позволит вам сформулировать соглашение об уровне обслуживания между Lync и зависимой службой, а также предоставить начальное место для согласования SLA.</span><span class="sxs-lookup"><span data-stu-id="9ca34-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="9ca34-111">В следующей таблице перечислены типичные службы зависимостей для инфраструктуры Lync.</span><span class="sxs-lookup"><span data-stu-id="9ca34-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="9ca34-112">Каждая из этих технологий должна иметь собственный активный мониторинг.</span><span class="sxs-lookup"><span data-stu-id="9ca34-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="9ca34-113">Типичные службы зависимостей</span><span class="sxs-lookup"><span data-stu-id="9ca34-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ca34-114">Служба зависимостей</span><span class="sxs-lookup"><span data-stu-id="9ca34-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-115">Операционные системы</span><span class="sxs-lookup"><span data-stu-id="9ca34-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca34-116">Оборудование сервера</span><span class="sxs-lookup"><span data-stu-id="9ca34-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="9ca34-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca34-118">Инфраструктура открытых ключей</span><span class="sxs-lookup"><span data-stu-id="9ca34-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-119">Служба именования доменов</span><span class="sxs-lookup"><span data-stu-id="9ca34-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca34-120">Службы баз данных</span><span class="sxs-lookup"><span data-stu-id="9ca34-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-121">Службы хранилища</span><span class="sxs-lookup"><span data-stu-id="9ca34-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca34-122">Управление системой — мониторинг и распространение</span><span class="sxs-lookup"><span data-stu-id="9ca34-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-123">Службы безопасности — антивирусная программа</span><span class="sxs-lookup"><span data-stu-id="9ca34-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca34-124">Сетевая инфраструктура — Интернет</span><span class="sxs-lookup"><span data-stu-id="9ca34-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-125">Сетевая инфраструктура – внутренняя (ЛВС/WAN)</span><span class="sxs-lookup"><span data-stu-id="9ca34-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca34-126">Инфраструктура телефонии — IP-УАТС и шлюзы</span><span class="sxs-lookup"><span data-stu-id="9ca34-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-127">Облачные службы</span><span class="sxs-lookup"><span data-stu-id="9ca34-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9ca34-128">Предполагается, что Организация работает в соответствии с основными функциями управления уровнем обслуживания, такими как изменение, инцидент и управление выпуском, как это было предписано MOF.</span><span class="sxs-lookup"><span data-stu-id="9ca34-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="9ca34-129">Решение Lync должно быть принято с помощью этих функций и может быть подвергнуто тем же процессам управления в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="9ca34-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="9ca34-130">Создание на приведенных выше данных позволяет получить более общее представление о том, что может повлиять на работу службы Lync в предприятии.</span><span class="sxs-lookup"><span data-stu-id="9ca34-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="9ca34-131">Чтобы обеспечить доступность и качество обслуживания в Lync Server 2013, следующие средства мониторинга должны сопровождаться развертыванием эталонной архитектуры.</span><span class="sxs-lookup"><span data-stu-id="9ca34-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="9ca34-132">Средства наблюдения</span><span class="sxs-lookup"><span data-stu-id="9ca34-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ca34-133">Компонент</span><span class="sxs-lookup"><span data-stu-id="9ca34-133">Component</span></span></th>
<th><span data-ttu-id="9ca34-134">Описание</span><span class="sxs-lookup"><span data-stu-id="9ca34-134">Description</span></span></th>
<th><span data-ttu-id="9ca34-135">Соответствующий сайт</span><span class="sxs-lookup"><span data-stu-id="9ca34-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-136">Сервер мониторинга Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ca34-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="9ca34-137">Разверните по крайней мере одну роль сервера Lync Server 2013 для каждого центрального сайта и настройте пакет подготовки отчетов о качестве опыта работы (QoE).</span><span class="sxs-lookup"><span data-stu-id="9ca34-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="9ca34-138">Дополнительные сведения можно найти в документации по развертыванию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ca34-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="9ca34-139"><a href="lync-server-2013-deploying-monitoring.md">Развертывание мониторинга в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ca34-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ca34-140">Центральные сайты</span><span class="sxs-lookup"><span data-stu-id="9ca34-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9ca34-141">Модем каждый из них является ближайшим экземпляром роли сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="9ca34-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="9ca34-142">Центральные сайты</span><span class="sxs-lookup"><span data-stu-id="9ca34-142">Central sites</span></span></p>
<p><span data-ttu-id="9ca34-143">Сайты филиалов</span><span class="sxs-lookup"><span data-stu-id="9ca34-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="9ca34-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="9ca34-145">System Center Operations Manager 2012 с импортированным пакетом управления Microsoft Lync Server 2013 (MP).</span><span class="sxs-lookup"><span data-stu-id="9ca34-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="9ca34-146">Пакет управления реализует традиционный журнал событий и инструментарий на основе счетчиков производительности, а также возможность для новых доступных инструментов в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ca34-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="9ca34-147">Центральные сайты</span><span class="sxs-lookup"><span data-stu-id="9ca34-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9ca34-148">Убедитесь, что центральное обнаружение для обнаружения ролей и компонентов, которые необходимо отслеживать, выполняется автоматически на основе основного сценария обнаружения, который считывает документ Topology, опубликованный в базе данных централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="9ca34-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="9ca34-149">Центральный сайт</span><span class="sxs-lookup"><span data-stu-id="9ca34-149">Central Site</span></span></p>
<p><span data-ttu-id="9ca34-150">Сайт ветви</span><span class="sxs-lookup"><span data-stu-id="9ca34-150">Branch Site</span></span></p>
<p><span data-ttu-id="9ca34-151">Сайт Edge</span><span class="sxs-lookup"><span data-stu-id="9ca34-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="9ca34-152">Развертывание агентов System Centre Operations Manager 2007 для всех развернутых серверов с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ca34-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="9ca34-153">Центральный сайт</span><span class="sxs-lookup"><span data-stu-id="9ca34-153">Central Site</span></span></p>
<p><span data-ttu-id="9ca34-154">Сайт ветви</span><span class="sxs-lookup"><span data-stu-id="9ca34-154">Branch Site</span></span></p>
<p><span data-ttu-id="9ca34-155">Сайт Edge</span><span class="sxs-lookup"><span data-stu-id="9ca34-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9ca34-156">Убедитесь, что для уведомлений заданы приоритеты оповещений:</span><span class="sxs-lookup"><span data-stu-id="9ca34-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="9ca34-157">Оповещения с высоким приоритетом</span><span class="sxs-lookup"><span data-stu-id="9ca34-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="9ca34-158">Оповещения среднего приоритета</span><span class="sxs-lookup"><span data-stu-id="9ca34-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="9ca34-159">Другие оповещения.</span><span class="sxs-lookup"><span data-stu-id="9ca34-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="9ca34-160">Центральный сайт</span><span class="sxs-lookup"><span data-stu-id="9ca34-160">Central Site</span></span></p>
<p><span data-ttu-id="9ca34-161">Сайт ветви</span><span class="sxs-lookup"><span data-stu-id="9ca34-161">Branch Site</span></span></p>
<p><span data-ttu-id="9ca34-162">Сайт Edge</span><span class="sxs-lookup"><span data-stu-id="9ca34-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="9ca34-163">Настройте мониторинг порта для развертывания.</span><span class="sxs-lookup"><span data-stu-id="9ca34-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="9ca34-164">Центральный сайт</span><span class="sxs-lookup"><span data-stu-id="9ca34-164">Central Site</span></span></p>
<p><span data-ttu-id="9ca34-165">Сайт ветви</span><span class="sxs-lookup"><span data-stu-id="9ca34-165">Branch Site</span></span></p>
<p><span data-ttu-id="9ca34-166">Сайт Edge</span><span class="sxs-lookup"><span data-stu-id="9ca34-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9ca34-167">Настройка мониторинга URL-адресов для развертывания</span><span class="sxs-lookup"><span data-stu-id="9ca34-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="9ca34-168">Центральный сайт</span><span class="sxs-lookup"><span data-stu-id="9ca34-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-169">Интеграция Lync и System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="9ca34-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="9ca34-170">Развертывание повышает надежность и качество цветопередачи Мониторингкалл надежность и контроль качества мультимедиа. для наблюдения за надежностью и качеством звонков для Lync Server используйте компьютер сервера мониторинга в качестве узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="9ca34-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="9ca34-171">Обе эти функции запрашивают анализ баз данных сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="9ca34-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="9ca34-172">Центральный сайт</span><span class="sxs-lookup"><span data-stu-id="9ca34-172">Central Site</span></span></p>
<p><span data-ttu-id="9ca34-173">Сайт ветви</span><span class="sxs-lookup"><span data-stu-id="9ca34-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9ca34-174">Убедитесь в том, что пороговые значения предупреждений для качества мультимедиа заданы правильно.</span><span class="sxs-lookup"><span data-stu-id="9ca34-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="9ca34-175">В приведенной ниже таблице показано, как с помощью кодека узнать о максимальном прохождении в сети.</span><span class="sxs-lookup"><span data-stu-id="9ca34-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="9ca34-176">В производстве эти показатели следует отслеживать в течение установленного периода, а приемлемые пороги должны быть установлены на основе НМОСных показателей Организации.</span><span class="sxs-lookup"><span data-stu-id="9ca34-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="9ca34-177">Центральный сайт</span><span class="sxs-lookup"><span data-stu-id="9ca34-177">Central Site</span></span></p>
<p><span data-ttu-id="9ca34-178">Сайт ветви</span><span class="sxs-lookup"><span data-stu-id="9ca34-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-179">Наблюдатель виртуальных транзакций Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ca34-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="9ca34-180">Развертывание выделенного сервера Lync Server для использования в качестве средства наблюдения за искусственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="9ca34-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="9ca34-181">Синтетические транзакции — это Lync Server 2013 командлеты Windows PowerShell, которые автоматически инициируются пакетом управления в предопределенном интервале.</span><span class="sxs-lookup"><span data-stu-id="9ca34-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="9ca34-182">Эти данные выполняются на узле наблюдения искусственных транзакций, который является назначенным администратором сервером, ответственным за обнаружение и выполнение STs для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="9ca34-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="9ca34-183">Мы не рекомендуем использовать существующий сервер Microsoft Lync Server 2013 в качестве искусственного узла наблюдения за транзакциями.</span><span class="sxs-lookup"><span data-stu-id="9ca34-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="9ca34-184">Это происходит из-за высокой требований к использованию памяти и ЦП для работы STs.</span><span class="sxs-lookup"><span data-stu-id="9ca34-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="9ca34-185">Используйте новый серверный компьютер (или виртуальный сервер) для узла контрольных виртуальных транзакций.</span><span class="sxs-lookup"><span data-stu-id="9ca34-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="9ca34-186">Центральный сайт</span><span class="sxs-lookup"><span data-stu-id="9ca34-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9ca34-187">Развертывание узла наблюдателя виртуальных транзакций.</span><span class="sxs-lookup"><span data-stu-id="9ca34-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="9ca34-188">Обратитесь к документу MonitoringCS_withSCOM. docx из документации по УКТАП Connect.</span><span class="sxs-lookup"><span data-stu-id="9ca34-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="9ca34-189">Центральный сайт</span><span class="sxs-lookup"><span data-stu-id="9ca34-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="9ca34-190">Максимальная оценка сетевого MOS на кодек</span><span class="sxs-lookup"><span data-stu-id="9ca34-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ca34-191">Сценарий</span><span class="sxs-lookup"><span data-stu-id="9ca34-191">Scenario</span></span></th>
<th><span data-ttu-id="9ca34-192">Кодек</span><span class="sxs-lookup"><span data-stu-id="9ca34-192">Codec</span></span></th>
<th><span data-ttu-id="9ca34-193">Максимальная НМОС</span><span class="sxs-lookup"><span data-stu-id="9ca34-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-194">Звонок UC</span><span class="sxs-lookup"><span data-stu-id="9ca34-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="9ca34-195">Ртаудио ВБ</span><span class="sxs-lookup"><span data-stu-id="9ca34-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="9ca34-196">4,10</span><span class="sxs-lookup"><span data-stu-id="9ca34-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca34-197">Звонок UC</span><span class="sxs-lookup"><span data-stu-id="9ca34-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="9ca34-198">Ртаудио имена NetBIOS</span><span class="sxs-lookup"><span data-stu-id="9ca34-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="9ca34-199">2,95</span><span class="sxs-lookup"><span data-stu-id="9ca34-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-200">Конференц-связь</span><span class="sxs-lookup"><span data-stu-id="9ca34-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="9ca34-201">Siren</span><span class="sxs-lookup"><span data-stu-id="9ca34-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="9ca34-202">3,72</span><span class="sxs-lookup"><span data-stu-id="9ca34-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca34-203">Звонок UC-КТСОП</span><span class="sxs-lookup"><span data-stu-id="9ca34-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="9ca34-204">Ртаудио имена NetBIOS</span><span class="sxs-lookup"><span data-stu-id="9ca34-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="9ca34-205">2,95</span><span class="sxs-lookup"><span data-stu-id="9ca34-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca34-206">Звонок UC-КТСОП</span><span class="sxs-lookup"><span data-stu-id="9ca34-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="9ca34-207">G-711</span><span class="sxs-lookup"><span data-stu-id="9ca34-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="9ca34-208">3,61</span><span class="sxs-lookup"><span data-stu-id="9ca34-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9ca34-209">Более ранние и более поздние версии. задачи обслуживания должны выполняться для центральных, краевых и посторонних сайтов на повторяющиеся ежедневные, еженедельные и ежемесячные данные, определенные в руководстве по работе с Lync RA.</span><span class="sxs-lookup"><span data-stu-id="9ca34-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

