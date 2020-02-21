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
ms.openlocfilehash: d2403fde7387c1ef5af7d402ad9bc859aa95fe6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="7afaf-102">Операционные зависимости в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7afaf-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7afaf-103">_**Последнее изменение темы:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="7afaf-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="7afaf-104">Эталонная архитектура, которая обсуждается в этом документе, поможет убедиться в том, что у вас есть развертывание Lync Server 2013, которое не только масштабируется в соответствии с требованиями организации, но будет разработано в соответствии с рекомендациями Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7afaf-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="7afaf-105">Так как в этом случае реализация Lync Server 2013 является динамической службой, а как любая другая служба предприятия по-прежнему требует мониторинга и профилактического управления для поддержания высокого уровня доступности и качества обслуживания для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="7afaf-106">Так как Lync Server 2013 становится глубоко недетализированным в повседневной деятельности Организации, важно, чтобы Управление службой было точным и подматериальным.</span><span class="sxs-lookup"><span data-stu-id="7afaf-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="7afaf-107">Архитектура системы Lync может стать сложной и очень интегрированной, а также обеспечивать эффективное управление уровнем обслуживания и устанавливать SLA для Lync Server 2013 он становится критически важным для того, чтобы узнать о зависимостях системы на других платформах и серверах.</span><span class="sxs-lookup"><span data-stu-id="7afaf-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="7afaf-108">Важно отметить, какие бизнес-службы, например интегрированные приложения для голосовой связи и Объединенных коммуникаций, станут зависимыми от Lync.</span><span class="sxs-lookup"><span data-stu-id="7afaf-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="7afaf-109">Lync Server 2013 должен быть установлен, указывая все произнесенные зависимости.</span><span class="sxs-lookup"><span data-stu-id="7afaf-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="7afaf-110">Карта службы позволяет формулировать соглашение об уровне обслуживания между Lync и зависимой службой и предоставляет отправную позицию для согласования SLA.</span><span class="sxs-lookup"><span data-stu-id="7afaf-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="7afaf-111">В следующей таблице перечислены типичные службы зависимости для инфраструктуры Lync.</span><span class="sxs-lookup"><span data-stu-id="7afaf-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="7afaf-112">Каждая из этих технологий должна иметь собственный профилактической мониторинг.</span><span class="sxs-lookup"><span data-stu-id="7afaf-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="7afaf-113">Типичные службы зависимости</span><span class="sxs-lookup"><span data-stu-id="7afaf-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7afaf-114">Служба зависимостей</span><span class="sxs-lookup"><span data-stu-id="7afaf-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-115">Операционные системы</span><span class="sxs-lookup"><span data-stu-id="7afaf-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7afaf-116">Серверное оборудование</span><span class="sxs-lookup"><span data-stu-id="7afaf-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="7afaf-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7afaf-118">Инфраструктура открытых ключей</span><span class="sxs-lookup"><span data-stu-id="7afaf-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-119">Служба именования доменов</span><span class="sxs-lookup"><span data-stu-id="7afaf-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7afaf-120">Службы баз данных</span><span class="sxs-lookup"><span data-stu-id="7afaf-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-121">Службы хранения</span><span class="sxs-lookup"><span data-stu-id="7afaf-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7afaf-122">Управление системой — мониторинг и распределение</span><span class="sxs-lookup"><span data-stu-id="7afaf-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-123">Службы безопасности — антивирусная программа</span><span class="sxs-lookup"><span data-stu-id="7afaf-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7afaf-124">Сетевая инфраструктура — Интернет</span><span class="sxs-lookup"><span data-stu-id="7afaf-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-125">Сетевая инфраструктура — внутренняя (ЛОКАЛЬная сеть/Глобальная сеть)</span><span class="sxs-lookup"><span data-stu-id="7afaf-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7afaf-126">Инфраструктура телефонии — IP-УАТС и шлюзы</span><span class="sxs-lookup"><span data-stu-id="7afaf-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-127">Облачные службы</span><span class="sxs-lookup"><span data-stu-id="7afaf-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7afaf-128">Предполагается, что Организация работает в соответствии с основными функциями управления уровнями обслуживания, такими как изменение, инциденты и управление выпусками, как это было предписано MOF.</span><span class="sxs-lookup"><span data-stu-id="7afaf-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="7afaf-129">Решение Lync должно быть принято в этих функциях и быть подчиняться тем же рабочим процессам управления.</span><span class="sxs-lookup"><span data-stu-id="7afaf-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="7afaf-130">Создание на приведенных выше сведениях теперь повлияет на то, что может повлиять на службу Lync на предприятии.</span><span class="sxs-lookup"><span data-stu-id="7afaf-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="7afaf-131">Чтобы обеспечить доступность и качество службы Lync Server 2013, следующие средства мониторинга должны сопровождаться развертыванием эталонной архитектуры:</span><span class="sxs-lookup"><span data-stu-id="7afaf-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="7afaf-132">Средства отслеживания</span><span class="sxs-lookup"><span data-stu-id="7afaf-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7afaf-133">Компонент</span><span class="sxs-lookup"><span data-stu-id="7afaf-133">Component</span></span></th>
<th><span data-ttu-id="7afaf-134">Описание</span><span class="sxs-lookup"><span data-stu-id="7afaf-134">Description</span></span></th>
<th><span data-ttu-id="7afaf-135">Соответствующий сайт</span><span class="sxs-lookup"><span data-stu-id="7afaf-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-136">Сервер мониторинга Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7afaf-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="7afaf-137">Разверните по крайней мере одну роль сервера мониторинга Lync Server 2013 для каждого центрального сайта и настройте пакет отчетов о качестве качества взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="7afaf-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="7afaf-138">Дополнительные сведения можно найти в документации по развертыванию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7afaf-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="7afaf-139"><a href="lync-server-2013-deploying-monitoring.md">Развертывание мониторинга в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7afaf-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7afaf-140">Центральные сайты</span><span class="sxs-lookup"><span data-stu-id="7afaf-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="7afaf-141">Модем каждый пул в ближайшем экземпляре роли сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="7afaf-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="7afaf-142">Центральные сайты</span><span class="sxs-lookup"><span data-stu-id="7afaf-142">Central sites</span></span></p>
<p><span data-ttu-id="7afaf-143">Сайты филиалов</span><span class="sxs-lookup"><span data-stu-id="7afaf-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="7afaf-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="7afaf-145">System Center Operations Manager 2012 с импортированным пакетом управления Microsoft Lync Server 2013 (MP).</span><span class="sxs-lookup"><span data-stu-id="7afaf-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="7afaf-146">Пакет управления реализует традиционный журнал событий и инструментарий на основе счетчиков производительности, а также обеспечивает поддержку новых инструментирований в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7afaf-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="7afaf-147">Центральные сайты</span><span class="sxs-lookup"><span data-stu-id="7afaf-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="7afaf-148">Убедитесь, что центральное обнаружение для обнаружения ролей и компонентов, которые необходимо отслеживать, выполняется автоматически на основе сценария централизованного обнаружения, считывающего документ топологии, опубликованный в базе данных централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="7afaf-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="7afaf-149">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="7afaf-149">Central Site</span></span></p>
<p><span data-ttu-id="7afaf-150">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="7afaf-150">Branch Site</span></span></p>
<p><span data-ttu-id="7afaf-151">Пограничный сайт</span><span class="sxs-lookup"><span data-stu-id="7afaf-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="7afaf-152">Разверните агенты System Centre Operations Manager 2007 для всех развернутых серверов, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7afaf-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="7afaf-153">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="7afaf-153">Central Site</span></span></p>
<p><span data-ttu-id="7afaf-154">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="7afaf-154">Branch Site</span></span></p>
<p><span data-ttu-id="7afaf-155">Пограничный сайт</span><span class="sxs-lookup"><span data-stu-id="7afaf-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="7afaf-156">Убедитесь, что для уведомлений настроены приоритетные оповещения:</span><span class="sxs-lookup"><span data-stu-id="7afaf-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="7afaf-157">Оповещения с высоким приоритетом</span><span class="sxs-lookup"><span data-stu-id="7afaf-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="7afaf-158">Средний приоритет оповещений</span><span class="sxs-lookup"><span data-stu-id="7afaf-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="7afaf-159">Другие оповещения.</span><span class="sxs-lookup"><span data-stu-id="7afaf-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="7afaf-160">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="7afaf-160">Central Site</span></span></p>
<p><span data-ttu-id="7afaf-161">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="7afaf-161">Branch Site</span></span></p>
<p><span data-ttu-id="7afaf-162">Пограничный сайт</span><span class="sxs-lookup"><span data-stu-id="7afaf-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="7afaf-163">Настройка мониторинга портов для развертывания.</span><span class="sxs-lookup"><span data-stu-id="7afaf-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="7afaf-164">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="7afaf-164">Central Site</span></span></p>
<p><span data-ttu-id="7afaf-165">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="7afaf-165">Branch Site</span></span></p>
<p><span data-ttu-id="7afaf-166">Пограничный сайт</span><span class="sxs-lookup"><span data-stu-id="7afaf-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="7afaf-167">Настройка отслеживания URL-адресов для развертывания</span><span class="sxs-lookup"><span data-stu-id="7afaf-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="7afaf-168">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="7afaf-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-169">Интеграция Lync и System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="7afaf-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="7afaf-170">Развертывание надежности вызовов и Мониторингкалл надежности и мониторинг качества мультимедиа используйте компьютер сервера мониторинга в качестве узла-наблюдателя для мониторинга надежности вызовов и качества мультимедиа для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7afaf-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="7afaf-171">Обе эти функции запрашивают анализ баз данных сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="7afaf-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="7afaf-172">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="7afaf-172">Central Site</span></span></p>
<p><span data-ttu-id="7afaf-173">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="7afaf-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="7afaf-174">Убедитесь, что пороговые значения предупреждений качества мультимедиа настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="7afaf-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="7afaf-175">В приведенной ниже таблице показано, как с помощью кодека обозначаются показатели мнения по всем сетям.</span><span class="sxs-lookup"><span data-stu-id="7afaf-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="7afaf-176">В производственной среде эти показатели необходимо отслеживать в течение заданного периода, и допустимые пороговые значения должны быть установлены на основе оценок NMOS Организации.</span><span class="sxs-lookup"><span data-stu-id="7afaf-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="7afaf-177">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="7afaf-177">Central Site</span></span></p>
<p><span data-ttu-id="7afaf-178">Сайт филиала</span><span class="sxs-lookup"><span data-stu-id="7afaf-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-179">Виртуальная наблюдатель транзакций Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7afaf-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="7afaf-180">Разверните выделенный сервер Lync в качестве наблюдателя искусственной транзакции.</span><span class="sxs-lookup"><span data-stu-id="7afaf-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="7afaf-181">Искусственные транзакции — это командлеты Windows PowerShell Lync Server 2013, автоматически активируемые пакетом управления в предопределенном интервале.</span><span class="sxs-lookup"><span data-stu-id="7afaf-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="7afaf-182">Они выполняются на узле-наблюдателе искусственной транзакции, который является назначенным администратором сервером, ответственным за обнаружение и выполнение STs для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="7afaf-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="7afaf-183">Мы не рекомендуем использовать существующий сервер Microsoft Lync Server 2013 в качестве узла-наблюдателя искусственной транзакции.</span><span class="sxs-lookup"><span data-stu-id="7afaf-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="7afaf-184">Это связано с требованиями к высокой загрузке ЦП и памяти для запуска STs.</span><span class="sxs-lookup"><span data-stu-id="7afaf-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="7afaf-185">Используйте новый серверный компьютер (или виртуальный сервер) для узла-наблюдателя искусственной транзакции.</span><span class="sxs-lookup"><span data-stu-id="7afaf-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="7afaf-186">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="7afaf-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="7afaf-187">Развертывание узла-наблюдателя искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="7afaf-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="7afaf-188">Обратитесь к документу MonitoringCS_withSCOM. docx из документации по УКТАП Connect.</span><span class="sxs-lookup"><span data-stu-id="7afaf-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="7afaf-189">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="7afaf-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="7afaf-190">Максимальное число оценок сети MOS для каждого кодека</span><span class="sxs-lookup"><span data-stu-id="7afaf-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7afaf-191">Сценарий</span><span class="sxs-lookup"><span data-stu-id="7afaf-191">Scenario</span></span></th>
<th><span data-ttu-id="7afaf-192">Кодек</span><span class="sxs-lookup"><span data-stu-id="7afaf-192">Codec</span></span></th>
<th><span data-ttu-id="7afaf-193">Максимальное NMOS</span><span class="sxs-lookup"><span data-stu-id="7afaf-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-194">UC по телефону UC</span><span class="sxs-lookup"><span data-stu-id="7afaf-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="7afaf-195">RTAudio Интернете</span><span class="sxs-lookup"><span data-stu-id="7afaf-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="7afaf-196">4.10</span><span class="sxs-lookup"><span data-stu-id="7afaf-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7afaf-197">UC по телефону UC</span><span class="sxs-lookup"><span data-stu-id="7afaf-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="7afaf-198">RTAudio имена NetBIOS</span><span class="sxs-lookup"><span data-stu-id="7afaf-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="7afaf-199">2,95</span><span class="sxs-lookup"><span data-stu-id="7afaf-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-200">Конференц-связь</span><span class="sxs-lookup"><span data-stu-id="7afaf-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="7afaf-201">Siren</span><span class="sxs-lookup"><span data-stu-id="7afaf-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="7afaf-202">3,72</span><span class="sxs-lookup"><span data-stu-id="7afaf-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7afaf-203">Вызов UC/PSTN</span><span class="sxs-lookup"><span data-stu-id="7afaf-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="7afaf-204">RTAudio имена NetBIOS</span><span class="sxs-lookup"><span data-stu-id="7afaf-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="7afaf-205">2,95</span><span class="sxs-lookup"><span data-stu-id="7afaf-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7afaf-206">Вызов UC/PSTN</span><span class="sxs-lookup"><span data-stu-id="7afaf-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="7afaf-207">G – 711</span><span class="sxs-lookup"><span data-stu-id="7afaf-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="7afaf-208">3,61</span><span class="sxs-lookup"><span data-stu-id="7afaf-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7afaf-209">Над и над предыдущими действиями мониторинга Pro-Active, задачи обслуживания должны выполняться для центральных, пограничных и филиалов на регулярной, еженедельной и ежемесячной основе, как указано в руководстве по работе с центром администрирования Lync.</span><span class="sxs-lookup"><span data-stu-id="7afaf-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

