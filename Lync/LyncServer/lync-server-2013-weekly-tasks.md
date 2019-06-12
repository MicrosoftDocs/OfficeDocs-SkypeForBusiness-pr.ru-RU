---
title: 'Lync Server 2013: еженедельные задачи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3128780c456c3f38f306d31f258ce903eb50a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="519a8-102">Еженедельные задачи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="519a8-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="519a8-103">_**Тема последнего изменения:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="519a8-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="519a8-104">Еженедельные задачи обычно связаны с сбором и анализом журналов и отчетов.</span><span class="sxs-lookup"><span data-stu-id="519a8-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="519a8-105">Архивация журналов событий</span><span class="sxs-lookup"><span data-stu-id="519a8-105">Archive event logs</span></span>

<span data-ttu-id="519a8-106">Если журналы событий не настроены на перезапись событий, они должны быть регулярно заархивированы и удалены.</span><span class="sxs-lookup"><span data-stu-id="519a8-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="519a8-107">Это действие особенно важно для журналов безопасности, которые могут потребоваться при исследовании попыток нарушения безопасности.</span><span class="sxs-lookup"><span data-stu-id="519a8-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="519a8-108">Организация должна определять политики и процедуры для архивации журнала.</span><span class="sxs-lookup"><span data-stu-id="519a8-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="519a8-109">Создание отчетов</span><span class="sxs-lookup"><span data-stu-id="519a8-109">Create reports</span></span>

<span data-ttu-id="519a8-110">Создание отчетов о состоянии, помогающих при планировании ресурсов, проверках SLA и анализе производительности.</span><span class="sxs-lookup"><span data-stu-id="519a8-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="519a8-111">Используйте ежедневные данные из журнала событий и системного монитора для создания отчетов об использовании диска, памяти и ЦП.</span><span class="sxs-lookup"><span data-stu-id="519a8-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="519a8-112">С помощью System Center Operations Manager Создавайте отчеты о доступности и работоспособности.</span><span class="sxs-lookup"><span data-stu-id="519a8-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="519a8-113">Организация должна определять политики и процедуры для отчетов о состоянии.</span><span class="sxs-lookup"><span data-stu-id="519a8-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="519a8-114">Отчеты об инцидентах</span><span class="sxs-lookup"><span data-stu-id="519a8-114">Incident reports</span></span>

<span data-ttu-id="519a8-115">Еженедельный аудит отчетов об инцидентах Организации, связанных с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="519a8-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="519a8-116">Этот аудит должен включать в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="519a8-116">This audit should include the following:</span></span>

  - <span data-ttu-id="519a8-117">Самые популярные, разрешенные и незавершенные инциденты.</span><span class="sxs-lookup"><span data-stu-id="519a8-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="519a8-118">Решения для неразрешенных происшествий.</span><span class="sxs-lookup"><span data-stu-id="519a8-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="519a8-119">Обновление отчетов для включения новых билетов на проблемы.</span><span class="sxs-lookup"><span data-stu-id="519a8-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="519a8-120">Обновление репозитория документов для руководств, посвященных устранению неполадок, и публикация неустранимых проблем.</span><span class="sxs-lookup"><span data-stu-id="519a8-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="519a8-121">Поскольку система отслеживания происшествий Организации является вариантом выбора, независимого от Lync Server, некоторые инструкции или указатели недоступны.</span><span class="sxs-lookup"><span data-stu-id="519a8-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="519a8-122">Ознакомьтесь с документацией для системы, выбранной вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="519a8-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="519a8-123">Проверка журналов и производительности IIS</span><span class="sxs-lookup"><span data-stu-id="519a8-123">Check IIS logs and performance</span></span>

<span data-ttu-id="519a8-124">Еженедельное рецензирование журналов служб IIS и производительность.</span><span class="sxs-lookup"><span data-stu-id="519a8-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="519a8-125">Дополнительные сведения о мониторинге журналов и производительности IIS можно найти в статье [Обзор ведения журнала событий служб IIS для Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=36077).</span><span class="sxs-lookup"><span data-stu-id="519a8-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](http://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="519a8-126">Проверка должна включать следующее:</span><span class="sxs-lookup"><span data-stu-id="519a8-126">The review should include the following:</span></span>

  - <span data-ttu-id="519a8-127">Счетчики кэша веб-службы для контроля кэша службы WWW.</span><span class="sxs-lookup"><span data-stu-id="519a8-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="519a8-128">Счетчики ASP-страниц (АСПС) для наблюдения за приложениями, которые выполняются как АСПС.</span><span class="sxs-lookup"><span data-stu-id="519a8-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="519a8-129">Создание отчетов базы данных</span><span class="sxs-lookup"><span data-stu-id="519a8-129">Generate database reports</span></span>

<span data-ttu-id="519a8-130">**Создание отчетов в базе данных SQL**</span><span class="sxs-lookup"><span data-stu-id="519a8-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="519a8-131">Откройте Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="519a8-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="519a8-132">В дереве консоли разверните узел леса, разверните **Пулы предприятий**и выберите пул, для которого требуется создать отчет базы данных.</span><span class="sxs-lookup"><span data-stu-id="519a8-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="519a8-133">В области сведений откройте вкладку **база данных** .</span><span class="sxs-lookup"><span data-stu-id="519a8-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="519a8-134">На вкладке **база данных** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="519a8-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="519a8-135">Чтобы просмотреть имя базы данных, разверните раздел **Общие параметры**и просмотрите имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="519a8-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="519a8-136">Чтобы получить сводную статистику текущего пользователя для пула, разверните раздел **Сводные отчеты пользователей**, нажмите кнопку **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="519a8-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="519a8-137">Чтобы получить текущие данные пользователя для одного пользователя пула, разверните раздел **отчеты для каждого пользователя**, введите URI SIP пользователя, нажмите кнопку **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="519a8-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="519a8-138">Чтобы получить текущую сводную статистику для пула, разверните **Сводные отчеты по**конференциям, нажмите кнопку **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="519a8-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="519a8-139">Проверка обновлений для системы безопасности и Lync Server</span><span class="sxs-lookup"><span data-stu-id="519a8-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="519a8-140">Определите новые пакеты обновления, исправления и обновления.</span><span class="sxs-lookup"><span data-stu-id="519a8-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="519a8-141">При необходимости проверьте эти данные в тестовой лаборатории и используйте процедуры управления изменениями для упорядочения развертывания на рабочих серверах.</span><span class="sxs-lookup"><span data-stu-id="519a8-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="519a8-142">Кроме того, обновления компонентов Lync Server теперь доступны в составе центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="519a8-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="519a8-143">Все обновления компонентов Lync Server необходимо обновлять одновременно на всех серверах, на которых работает Lync Server, для которых применимы обновления.</span><span class="sxs-lookup"><span data-stu-id="519a8-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="519a8-144">Запуск анализатора соответствия рекомендациям для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="519a8-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="519a8-145">Анализатор соответствия рекомендациям для Lync Server 2013 — средство диагностики, которое собирает сведения о конфигурации и определяет, задана ли конфигурация согласно рекомендациям Microsoft.</span><span class="sxs-lookup"><span data-stu-id="519a8-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="519a8-146">Документация по этому средству — [анализатор соответствия рекомендациям для Lync Server 2013](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="519a8-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="519a8-147">Это средство сравнивает данные конфигурации развертывания с набором предопределенных правил для Lync Server и сообщает о потенциальных проблемах.</span><span class="sxs-lookup"><span data-stu-id="519a8-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="519a8-148">Для каждой обнаруженной ошибки средство предоставляет текущую конфигурацию в среде Lync Server и рекомендуемую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="519a8-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="519a8-149">При правильном доступе к сети средство может проанализировать службы AD DS и серверы, на которых работает Lync Server 2013, и выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="519a8-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="519a8-150">Упреждающее выполнение проверок работоспособности, проверка настройки конфигурации согласно рекомендуемым рекомендациям</span><span class="sxs-lookup"><span data-stu-id="519a8-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="519a8-151">Создание списка проблем (например, неоптимальных параметров конфигурации или неподдерживаемых или рекомендуемых параметров)</span><span class="sxs-lookup"><span data-stu-id="519a8-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="519a8-152">Оценить общее состояние системы</span><span class="sxs-lookup"><span data-stu-id="519a8-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="519a8-153">Помощь в устранении конкретных проблем</span><span class="sxs-lookup"><span data-stu-id="519a8-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="519a8-154">Запрос на скачивание обновлений (если они доступны)</span><span class="sxs-lookup"><span data-stu-id="519a8-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="519a8-155">Предоставление сведений об ошибках, связанных с электронной и локальной документацией, и включение советов по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="519a8-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="519a8-156">Создание сведений о конфигурации, которые можно записать для последующего просмотра</span><span class="sxs-lookup"><span data-stu-id="519a8-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="519a8-157">Убедитесь, что на всех серверах Lync Server 2013 установлен флажок РТКБПА. msi, и создайте еженедельный отчет о работоспособности.</span><span class="sxs-lookup"><span data-stu-id="519a8-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="519a8-158">Обратите внимание на результаты и, при необходимости, правильность.</span><span class="sxs-lookup"><span data-stu-id="519a8-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="519a8-159">Проверка показателей эффективности соглашения об уровне обслуживания</span><span class="sxs-lookup"><span data-stu-id="519a8-159">Review SLA performance figures</span></span>

<span data-ttu-id="519a8-160">Проверьте ключевые данные о производительности за предыдущую неделю.</span><span class="sxs-lookup"><span data-stu-id="519a8-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="519a8-161">Просматривайте производительность в соответствии с требованиями соглашения об уровне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="519a8-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="519a8-162">Определите тенденции и элементы, которые не соответствуют их целям.</span><span class="sxs-lookup"><span data-stu-id="519a8-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="519a8-163">Просмотр отчетов по пакету управления System Center Operations Manager и улучшения качества обслуживания</span><span class="sxs-lookup"><span data-stu-id="519a8-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="519a8-164">Получите и ознакомьтесь с отчетами по пакету управления Lync Server 2013 и качественным опытом.</span><span class="sxs-lookup"><span data-stu-id="519a8-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="519a8-165">Создание и просмотр отчетов базы данных для корпоративных пулов</span><span class="sxs-lookup"><span data-stu-id="519a8-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="519a8-166">**Создание отчетов пула**</span><span class="sxs-lookup"><span data-stu-id="519a8-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="519a8-167">Откройте Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="519a8-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="519a8-168">В дереве консоли разверните узел леса, разверните **Пулы предприятий**и выберите пул, для которого требуется создать отчет базы данных.</span><span class="sxs-lookup"><span data-stu-id="519a8-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="519a8-169">В области сведений откройте вкладку **база данных** .</span><span class="sxs-lookup"><span data-stu-id="519a8-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="519a8-170">На вкладке **база данных** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="519a8-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="519a8-171">Чтобы просмотреть имя базы данных, разверните раздел **Общие параметры**и просмотрите имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="519a8-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="519a8-172">Чтобы получить сводную статистику текущего пользователя для пула, разверните раздел **Сводные отчеты пользователей**, нажмите кнопку **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="519a8-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="519a8-173">Чтобы получить текущие данные пользователя для одного пользователя пула, разверните раздел **отчеты для каждого пользователя**, введите URI SIP пользователя, нажмите кнопку **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="519a8-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="519a8-174">Чтобы получить текущую сводную статистику для пула, разверните **Сводные отчеты по**конференциям, нажмите кнопку **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="519a8-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="519a8-175">Для каждого пула предприятий администраторы могут использовать вкладку **Database (база данных** ) для просмотра имени базы данных, а также для получения и просмотра отчетов из этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="519a8-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="519a8-176">Отчеты и описания баз данных</span><span class="sxs-lookup"><span data-stu-id="519a8-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="519a8-177">Раздел</span><span class="sxs-lookup"><span data-stu-id="519a8-177">Section</span></span></th>
<th><span data-ttu-id="519a8-178">Описание</span><span class="sxs-lookup"><span data-stu-id="519a8-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="519a8-179">Сводные отчеты пользователей</span><span class="sxs-lookup"><span data-stu-id="519a8-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="519a8-180">Дбанализе/v/репорт: DIAG [/склсервер: значение]</span><span class="sxs-lookup"><span data-stu-id="519a8-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="519a8-181">В этом разделе выводятся обобщенные сведения о пользователях в пуле, например количество включенных пользователей, среднее количество контактов на пользователя и количество пользователей для определенных функций.</span><span class="sxs-lookup"><span data-stu-id="519a8-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="519a8-182">При использовании этих отчетов могут быть полезны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="519a8-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="519a8-183">Включенный пользователь — это пользователь, который поддерживает Lync Server 2013 с помощью оснастки "пользователи и компьютеры Active Directory".</span><span class="sxs-lookup"><span data-stu-id="519a8-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="519a8-184">Активный пользователь — это пользователь, который вошел в систему или зарегистрировался.</span><span class="sxs-lookup"><span data-stu-id="519a8-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="519a8-185">Сводные отчеты также предлагают набор статистических сведений о контактах.</span><span class="sxs-lookup"><span data-stu-id="519a8-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="519a8-186">Эти статистические данные действительны только для совокупности пользователей, которые вошли хотя бы один раз, и у кого есть хотя бы один контакт.</span><span class="sxs-lookup"><span data-stu-id="519a8-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="519a8-187">Как правило, вы обычно не видите минимальное количество контактов, равное 0.</span><span class="sxs-lookup"><span data-stu-id="519a8-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="519a8-188">Из-за такого поведения в случае, если пользователь не имеет контактных данных (но активен, зарегистрирован ли пользователь), для некоторых полей статистики &lt;можно&gt; увидеть: пусто.</span><span class="sxs-lookup"><span data-stu-id="519a8-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="519a8-189">Отчеты для каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="519a8-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="519a8-190">Дбанализе/v/репорт: диск [/склсервер: значение]</span><span class="sxs-lookup"><span data-stu-id="519a8-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="519a8-191">В отличие от сводных отчетов, которые рассчитываются по Генеральной совокупности пользователей, они представляют собой отчеты об определенном пользователе.</span><span class="sxs-lookup"><span data-stu-id="519a8-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="519a8-192">Сводные отчеты по конференциям</span><span class="sxs-lookup"><span data-stu-id="519a8-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="519a8-193">Дбанализе/v/репорт: conf [/склсервер: значение]</span><span class="sxs-lookup"><span data-stu-id="519a8-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="519a8-194">В этом разделе выводятся общие сведения о статистике собраний для пула, например количество активных конференций и общее количество участников.</span><span class="sxs-lookup"><span data-stu-id="519a8-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="519a8-195">Запуск анализатора использования пропускной способности</span><span class="sxs-lookup"><span data-stu-id="519a8-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="519a8-196">Анализатор использования полосы пропускания — это средство, которое создает отчеты о различных аспектах использования полосы пропускания каналов глобальной сети конечными точками объединенных коммуникаций в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="519a8-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="519a8-197">Эти отчеты можно использовать для понимания текущего шаблона потребления для пропускной способности и для планирования пропускной способности по мощности.</span><span class="sxs-lookup"><span data-stu-id="519a8-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="519a8-198">Оно также позволяет просматривать полосу пропускания, назначенную различным каналам.</span><span class="sxs-lookup"><span data-stu-id="519a8-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="519a8-199">Это средство предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="519a8-199">This tool does the following:</span></span>

  - <span data-ttu-id="519a8-200">Создание специальных отчетов по использованию звука в сети</span><span class="sxs-lookup"><span data-stu-id="519a8-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="519a8-201">позволяет более эффективно планировать емкость и распределять полосы пропускания, назначенные различным каналам.</span><span class="sxs-lookup"><span data-stu-id="519a8-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="519a8-202">Анализатор использования пропускной способности может создавать графические представления о емкости и отчетах об использовании пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="519a8-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="519a8-203">Они перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="519a8-203">They are as follows:</span></span>

  - <span data-ttu-id="519a8-204">для всех каналов глобальной сети в корпоративной сети;</span><span class="sxs-lookup"><span data-stu-id="519a8-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="519a8-205">Отфильтровано по выбранным глобальным каналам связи</span><span class="sxs-lookup"><span data-stu-id="519a8-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="519a8-206">для каналов глобальной сети, емкость которых превышена;</span><span class="sxs-lookup"><span data-stu-id="519a8-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="519a8-207">Фильтрация по каналам глобальной сети, которые использовали подготовленную пропускную способность</span><span class="sxs-lookup"><span data-stu-id="519a8-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="519a8-208">Фильтрация по глобальным каналам связи (использование пропускной способности, превышающее 90 процента пропускной способности ссылки WAN)</span><span class="sxs-lookup"><span data-stu-id="519a8-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="519a8-209">Фильтрация по типу ссылки WAN — ссылки на сайты, межсетевые ссылки и ссылки на сайте</span><span class="sxs-lookup"><span data-stu-id="519a8-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="519a8-210">с фильтрацией по области сети.</span><span class="sxs-lookup"><span data-stu-id="519a8-210">Filtered by network region</span></span>

<span data-ttu-id="519a8-211">Документация по этому средству можно найти в документации по средствам для [Lync Server 2013 Resource Kit](http://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="519a8-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](http://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="519a8-212">См. также</span><span class="sxs-lookup"><span data-stu-id="519a8-212">See Also</span></span>


[<span data-ttu-id="519a8-213">Контрольный список для еженедельных задач</span><span class="sxs-lookup"><span data-stu-id="519a8-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

