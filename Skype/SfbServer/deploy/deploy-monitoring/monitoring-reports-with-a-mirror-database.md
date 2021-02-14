---
title: Связывать отчеты мониторинга с зеркальной базой данных в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: Сводка. Узнайте, как связать отчеты мониторинга с зеркальной базой данных, используемой Skype для бизнеса Server.
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802169"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="165d8-103">Связывать отчеты мониторинга с зеркальной базой данных в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="165d8-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="165d8-104">**Сводка:** Узнайте, как связать отчеты мониторинга с зеркальной базой данных, используемой Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="165d8-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="165d8-105">Мониторинг отчетов с помощью зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="165d8-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="165d8-106">Если вы настроите зеркальное отражение для базы данных мониторинга, эта зеркальная база данных станет основной базой данных в случае от сбойа.</span><span class="sxs-lookup"><span data-stu-id="165d8-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="165d8-107">Однако если вы используете отчеты мониторинга Skype для бизнеса Server и происходит отбой, возможно, ваши отчеты мониторинга не подключаются к зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="165d8-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="165d8-108">Это происходит потому, что при установке отчетов мониторинга указывается только расположение основной базы данных; расположение зеркальной базы данных не указывается.</span><span class="sxs-lookup"><span data-stu-id="165d8-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="165d8-109">Чтобы отчеты мониторинга автоматически переключялись на зеркальную базу данных, необходимо добавить зеркальную базу данных в качестве "партнера по отключаемой обработке" в две базы данных, используемые отчетами мониторинга (одна база данных для данных записи подробных вызовов, а другая для данных качества обслуживания (QoE).</span><span class="sxs-lookup"><span data-stu-id="165d8-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="165d8-110">(Обратите внимание, что этот шаг следует выполнить после установки отчетов мониторинга.) Вы можете добавить сведения о партнере по отоверку, вручную отредактировать значения строк подключения, используемые этими двумя базами данных.</span><span class="sxs-lookup"><span data-stu-id="165d8-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="165d8-111">Для этого выполните следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="165d8-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="165d8-112">Используйте Internet Explorer, чтобы открыть **SQL Server reporting Services.**</span><span class="sxs-lookup"><span data-stu-id="165d8-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="165d8-113">URL-адрес домашней страницы служб Reporting Services включает:</span><span class="sxs-lookup"><span data-stu-id="165d8-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="165d8-114">Префикс **http:**</span><span class="sxs-lookup"><span data-stu-id="165d8-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="165d8-115">Полное доменное имя компьютера, на котором установлены службы reporting Services (например, **atl-sql-001.litwareinc.com).**</span><span class="sxs-lookup"><span data-stu-id="165d8-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="165d8-116">Строка **символов /Reports_**.</span><span class="sxs-lookup"><span data-stu-id="165d8-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="165d8-117">Имя экземпляра базы данных, в котором установлены отчеты мониторинга (например, **archinst).**</span><span class="sxs-lookup"><span data-stu-id="165d8-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="165d8-118">Например, если SQL Server reporting Services был установлен на компьютере atl-sql-001.litwareinc.com а отчеты мониторинга используют архив экземпляра базы данных, URL-адрес домашней страницы будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="165d8-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="165d8-119">После доступа к домашней странице Службы Reporting Services щелкните **ServerReports** и нажмите кнопку **Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="165d8-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="165d8-120">Вы будете перенабираться **на Reports_Content** отчетов мониторинга Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="165d8-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="165d8-121">На странице **Reports_Content** выберите источник данных **CDRDB.**</span><span class="sxs-lookup"><span data-stu-id="165d8-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="165d8-122">На странице **CDRDB на** вкладке **"Свойства"** наберем строку подключения к текстовом **поле.**</span><span class="sxs-lookup"><span data-stu-id="165d8-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="165d8-123">Текущая строка подключения будет выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="165d8-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="165d8-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="165d8-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="165d8-125">Отредактируем строку подключения, включив имя сервера и экземпляр базы данных для зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="165d8-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="165d8-126">Например, если сервер называется atl-mirror-001, а зеркальная база данных находится в экземпляре archinst, необходимо добавить, чтобы указать зеркальную базу данных с помощью этого синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="165d8-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="165d8-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="165d8-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="165d8-128">Измененная строка подключения будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="165d8-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="165d8-129">Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="165d8-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="165d8-130">После обновления строки подключения нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="165d8-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="165d8-131">На странице **CDRDB щелкните** **ссылку** Reports_Content ссылку.</span><span class="sxs-lookup"><span data-stu-id="165d8-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="165d8-132">Щелкните **источник данных QMSDB** и отредактируете строку подключения для базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="165d8-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="165d8-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="165d8-133">For example:</span></span>
    
    <span data-ttu-id="165d8-134">Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="165d8-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="165d8-135">Нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="165d8-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="165d8-136">См. также</span><span class="sxs-lookup"><span data-stu-id="165d8-136">See also</span></span>

[<span data-ttu-id="165d8-137">Установка отчетов мониторинга в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="165d8-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="165d8-138">Использование отчетов мониторинга в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="165d8-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
