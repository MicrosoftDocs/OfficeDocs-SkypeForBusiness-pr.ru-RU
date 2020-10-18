---
title: 'Lync Server 2013: операционные зависимости'
description: 'Lync Server 2013: операционные зависимости.'
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
ms.openlocfilehash: 4e240981f5dfded7c27f123c8483794ea3ffedff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579195"
---
# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="f6a91-103">Операционные зависимости в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6a91-103">Operational dependencies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6a91-104">_**Последнее изменение темы:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="f6a91-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="f6a91-105">Эталонная архитектура, которая обсуждается в этом документе, поможет убедиться в том, что у вас есть развертывание Lync Server 2013, которое не только масштабируется в соответствии с требованиями организации, но будет разработано в соответствии с рекомендациями Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6a91-105">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="f6a91-106">Так как в этом случае реализация Lync Server 2013 является динамической службой, а как любая другая служба предприятия по-прежнему требует мониторинга и профилактического управления для поддержания высокого уровня доступности и качества обслуживания для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f6a91-106">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="f6a91-107">Так как Lync Server 2013 становится глубоко недетализированным в повседневной деятельности Организации, важно, чтобы Управление службой было точным и подматериальным.</span><span class="sxs-lookup"><span data-stu-id="f6a91-107">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="f6a91-108">Архитектура системы Lync может стать сложной и очень интегрированной, а также обеспечивать эффективное управление уровнем обслуживания и устанавливать SLA для Lync Server 2013 он становится критически важным для того, чтобы узнать о зависимостях системы на других платформах и серверах.</span><span class="sxs-lookup"><span data-stu-id="f6a91-108">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="f6a91-109">Важно отметить, какие бизнес-службы, например интегрированные приложения для голосовой связи и Объединенных коммуникаций, станут зависимыми от Lync.</span><span class="sxs-lookup"><span data-stu-id="f6a91-109">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="f6a91-110">Lync Server 2013 должен быть установлен, указывая все произнесенные зависимости.</span><span class="sxs-lookup"><span data-stu-id="f6a91-110">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="f6a91-111">Карта службы позволяет формулировать соглашение об уровне обслуживания между Lync и зависимой службой и предоставляет отправную позицию для согласования SLA.</span><span class="sxs-lookup"><span data-stu-id="f6a91-111">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="f6a91-112">В следующей таблице перечислены типичные службы зависимости для инфраструктуры Lync.</span><span class="sxs-lookup"><span data-stu-id="f6a91-112">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="f6a91-113">Каждая из этих технологий должна иметь собственный профилактической мониторинг.</span><span class="sxs-lookup"><span data-stu-id="f6a91-113">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="f6a91-114">Типичные службы зависимости</span><span class="sxs-lookup"><span data-stu-id="f6a91-114">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6a91-115">Служба зависимостей</span><span class="sxs-lookup"><span data-stu-id="f6a91-115">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-116">Операционные системы</span><span class="sxs-lookup"><span data-stu-id="f6a91-116">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a91-117">Серверное оборудование</span><span class="sxs-lookup"><span data-stu-id="f6a91-117">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-118">Active Directory</span><span class="sxs-lookup"><span data-stu-id="f6a91-118">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a91-119">Инфраструктура открытых ключей</span><span class="sxs-lookup"><span data-stu-id="f6a91-119">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-120">Служба именования доменов</span><span class="sxs-lookup"><span data-stu-id="f6a91-120">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a91-121">Службы баз данных</span><span class="sxs-lookup"><span data-stu-id="f6a91-121">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-122">Службы хранения</span><span class="sxs-lookup"><span data-stu-id="f6a91-122">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a91-123">Управление системой — мониторинг и распределение</span><span class="sxs-lookup"><span data-stu-id="f6a91-123">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-124">Службы безопасности — антивирусная программа</span><span class="sxs-lookup"><span data-stu-id="f6a91-124">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a91-125">Сетевая инфраструктура — Интернет</span><span class="sxs-lookup"><span data-stu-id="f6a91-125">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-126">Сетевая инфраструктура — внутренняя (ЛОКАЛЬная сеть/Глобальная сеть)</span><span class="sxs-lookup"><span data-stu-id="f6a91-126">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a91-127">Инфраструктура телефонии — IP-УАТС и шлюзы</span><span class="sxs-lookup"><span data-stu-id="f6a91-127">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-128">Облачные службы</span><span class="sxs-lookup"><span data-stu-id="f6a91-128">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f6a91-129">Предполагается, что Организация работает в соответствии с основными функциями управления уровнями обслуживания, такими как изменение, инциденты и управление выпусками, как это было предписано MOF.</span><span class="sxs-lookup"><span data-stu-id="f6a91-129">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="f6a91-130">Решение Lync должно быть принято в этих функциях и быть подчиняться тем же рабочим процессам управления.</span><span class="sxs-lookup"><span data-stu-id="f6a91-130">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="f6a91-131">Создание на приведенных выше сведениях теперь повлияет на то, что может повлиять на службу Lync на предприятии.</span><span class="sxs-lookup"><span data-stu-id="f6a91-131">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="f6a91-132">Чтобы обеспечить доступность и качество службы Lync Server 2013, следующие средства мониторинга должны сопровождаться развертыванием эталонной архитектуры:</span><span class="sxs-lookup"><span data-stu-id="f6a91-132">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="f6a91-133">Средства отслеживания</span><span class="sxs-lookup"><span data-stu-id="f6a91-133">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6a91-134">Компонент</span><span class="sxs-lookup"><span data-stu-id="f6a91-134">Component</span></span></th>
<th><span data-ttu-id="f6a91-135">Описание</span><span class="sxs-lookup"><span data-stu-id="f6a91-135">Description</span></span></th>
<th><span data-ttu-id="f6a91-136">Соответствующий сайт</span><span class="sxs-lookup"><span data-stu-id="f6a91-136">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-137">Сервер мониторинга Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6a91-137">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="f6a91-138">Разверните по крайней мере одну роль сервера мониторинга Lync Server 2013 для каждого центрального сайта и настройте пакет отчетов о качестве качества взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="f6a91-138">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="f6a91-139">Дополнительные сведения можно найти в документации по развертыванию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6a91-139">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="f6a91-140"><a href="lync-server-2013-deploying-monitoring.md">Развертывание мониторинга в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f6a91-140"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f6a91-141">Центральные сайты</span><span class="sxs-lookup"><span data-stu-id="f6a91-141">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="f6a91-142">Модем каждый пул в ближайшем экземпляре роли сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f6a91-142">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="f6a91-143">Центральные сайты</span><span class="sxs-lookup"><span data-stu-id="f6a91-143">Central sites</span></span></p>
<p><span data-ttu-id="f6a91-144">Сайты филиалов</span><span class="sxs-lookup"><span data-stu-id="f6a91-144">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-145">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="f6a91-145">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="f6a91-146">System Center Operations Manager 2012 с импортированным пакетом управления Microsoft Lync Server 2013 (MP).</span><span class="sxs-lookup"><span data-stu-id="f6a91-146">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="f6a91-147">Пакет управления реализует традиционный журнал событий и инструментарий на основе счетчиков производительности, а также обеспечивает поддержку новых инструментирований в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6a91-147">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="f6a91-148">Центральные сайты</span><span class="sxs-lookup"><span data-stu-id="f6a91-148">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="f6a91-149">Убедитесь, что центральное обнаружение для обнаружения ролей и компонентов, которые необходимо отслеживать, выполняется автоматически на основе сценария централизованного обнаружения, считывающего документ топологии, опубликованный в базе данных централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="f6a91-149">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="f6a91-150">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="f6a91-150">Central Site</span></span></p>
<p><span data-ttu-id="f6a91-151">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="f6a91-151">Branch Site</span></span></p>
<p><span data-ttu-id="f6a91-152">Пограничный сайт</span><span class="sxs-lookup"><span data-stu-id="f6a91-152">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="f6a91-153">Разверните агенты System Centre Operations Manager 2007 для всех развернутых серверов, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6a91-153">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="f6a91-154">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="f6a91-154">Central Site</span></span></p>
<p><span data-ttu-id="f6a91-155">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="f6a91-155">Branch Site</span></span></p>
<p><span data-ttu-id="f6a91-156">Пограничный сайт</span><span class="sxs-lookup"><span data-stu-id="f6a91-156">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="f6a91-157">Убедитесь, что для уведомлений настроены приоритетные оповещения:</span><span class="sxs-lookup"><span data-stu-id="f6a91-157">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="f6a91-158">Оповещения с высоким приоритетом</span><span class="sxs-lookup"><span data-stu-id="f6a91-158">High Priority Alerts</span></span></p>
<p><span data-ttu-id="f6a91-159">Средний приоритет оповещений</span><span class="sxs-lookup"><span data-stu-id="f6a91-159">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="f6a91-160">Другие оповещения.</span><span class="sxs-lookup"><span data-stu-id="f6a91-160">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="f6a91-161">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="f6a91-161">Central Site</span></span></p>
<p><span data-ttu-id="f6a91-162">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="f6a91-162">Branch Site</span></span></p>
<p><span data-ttu-id="f6a91-163">Пограничный сайт</span><span class="sxs-lookup"><span data-stu-id="f6a91-163">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="f6a91-164">Настройка мониторинга портов для развертывания.</span><span class="sxs-lookup"><span data-stu-id="f6a91-164">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="f6a91-165">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="f6a91-165">Central Site</span></span></p>
<p><span data-ttu-id="f6a91-166">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="f6a91-166">Branch Site</span></span></p>
<p><span data-ttu-id="f6a91-167">Пограничный сайт</span><span class="sxs-lookup"><span data-stu-id="f6a91-167">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="f6a91-168">Настройка отслеживания URL-адресов для развертывания</span><span class="sxs-lookup"><span data-stu-id="f6a91-168">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="f6a91-169">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="f6a91-169">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-170">Интеграция Lync и System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="f6a91-170">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="f6a91-171">Развертывание надежности вызовов и Мониторингкалл надежности и мониторинг качества мультимедиа используйте компьютер сервера мониторинга в качестве узла-наблюдателя для мониторинга надежности вызовов и качества мультимедиа для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6a91-171">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="f6a91-172">Обе эти функции запрашивают анализ баз данных сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f6a91-172">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="f6a91-173">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="f6a91-173">Central Site</span></span></p>
<p><span data-ttu-id="f6a91-174">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="f6a91-174">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="f6a91-175">Убедитесь, что пороговые значения предупреждений качества мультимедиа настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="f6a91-175">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="f6a91-176">В приведенной ниже таблице показано, как с помощью кодека обозначаются показатели мнения по всем сетям.</span><span class="sxs-lookup"><span data-stu-id="f6a91-176">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="f6a91-177">В производственной среде эти показатели необходимо отслеживать в течение заданного периода, и допустимые пороговые значения должны быть установлены на основе оценок NMOS Организации.</span><span class="sxs-lookup"><span data-stu-id="f6a91-177">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="f6a91-178">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="f6a91-178">Central Site</span></span></p>
<p><span data-ttu-id="f6a91-179">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="f6a91-179">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-180">Виртуальная наблюдатель транзакций Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6a91-180">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="f6a91-181">Разверните выделенный сервер Lync в качестве наблюдателя искусственной транзакции.</span><span class="sxs-lookup"><span data-stu-id="f6a91-181">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="f6a91-182">Искусственные транзакции — это командлеты Windows PowerShell Lync Server 2013, автоматически активируемые пакетом управления в предопределенном интервале.</span><span class="sxs-lookup"><span data-stu-id="f6a91-182">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="f6a91-183">Они выполняются на узле-наблюдателе искусственной транзакции, который является назначенным администратором сервером, ответственным за обнаружение и выполнение STs для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="f6a91-183">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="f6a91-184">Мы не рекомендуем использовать существующий сервер Microsoft Lync Server 2013 в качестве узла-наблюдателя искусственной транзакции.</span><span class="sxs-lookup"><span data-stu-id="f6a91-184">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="f6a91-185">Это связано с требованиями к высокой загрузке ЦП и памяти для запуска STs.</span><span class="sxs-lookup"><span data-stu-id="f6a91-185">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="f6a91-186">Используйте новый серверный компьютер (или виртуальный сервер) для узла-наблюдателя искусственной транзакции.</span><span class="sxs-lookup"><span data-stu-id="f6a91-186">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="f6a91-187">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="f6a91-187">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="f6a91-188">Развертывание узла-наблюдателя искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="f6a91-188">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="f6a91-189">Обратитесь к MonitoringCS_withSCOM.docx документу из документации по УКТАП Connect.</span><span class="sxs-lookup"><span data-stu-id="f6a91-189">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="f6a91-190">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="f6a91-190">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="f6a91-191">Максимальное число оценок сети MOS для каждого кодека</span><span class="sxs-lookup"><span data-stu-id="f6a91-191">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6a91-192">Сценарий</span><span class="sxs-lookup"><span data-stu-id="f6a91-192">Scenario</span></span></th>
<th><span data-ttu-id="f6a91-193">Кодек</span><span class="sxs-lookup"><span data-stu-id="f6a91-193">Codec</span></span></th>
<th><span data-ttu-id="f6a91-194">Максимальное NMOS</span><span class="sxs-lookup"><span data-stu-id="f6a91-194">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-195">UC по телефону UC</span><span class="sxs-lookup"><span data-stu-id="f6a91-195">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="f6a91-196">RTAudio Интернете</span><span class="sxs-lookup"><span data-stu-id="f6a91-196">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="f6a91-197">4.10</span><span class="sxs-lookup"><span data-stu-id="f6a91-197">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a91-198">UC по телефону UC</span><span class="sxs-lookup"><span data-stu-id="f6a91-198">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="f6a91-199">RTAudio имена NetBIOS</span><span class="sxs-lookup"><span data-stu-id="f6a91-199">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="f6a91-200">2,95</span><span class="sxs-lookup"><span data-stu-id="f6a91-200">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-201">Конференц-связь</span><span class="sxs-lookup"><span data-stu-id="f6a91-201">Conference call</span></span></p></td>
<td><p><span data-ttu-id="f6a91-202">Siren</span><span class="sxs-lookup"><span data-stu-id="f6a91-202">Siren</span></span></p></td>
<td><p><span data-ttu-id="f6a91-203">3,72</span><span class="sxs-lookup"><span data-stu-id="f6a91-203">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a91-204">Вызов UC/PSTN</span><span class="sxs-lookup"><span data-stu-id="f6a91-204">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="f6a91-205">RTAudio имена NetBIOS</span><span class="sxs-lookup"><span data-stu-id="f6a91-205">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="f6a91-206">2,95</span><span class="sxs-lookup"><span data-stu-id="f6a91-206">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a91-207">Вызов UC/PSTN</span><span class="sxs-lookup"><span data-stu-id="f6a91-207">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="f6a91-208">G – 711</span><span class="sxs-lookup"><span data-stu-id="f6a91-208">G-711</span></span></p></td>
<td><p><span data-ttu-id="f6a91-209">3,61</span><span class="sxs-lookup"><span data-stu-id="f6a91-209">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f6a91-210">Над и над предыдущими действиями мониторинга Pro-Active, задачи обслуживания должны выполняться для центральных, пограничных и филиалов на регулярной, еженедельной и ежемесячной основе, как указано в руководстве по работе с центром администрирования Lync.</span><span class="sxs-lookup"><span data-stu-id="f6a91-210">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

