---
title: Сопоставление отчетов мониторинга с зеркальной базы данных в Скайп для Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Сводка: Узнайте, как связать отчетов мониторинга с зеркальной базы данных, используемые Скайп для Business Server 2015.'
ms.openlocfilehash: 246f16fd54133e2a6cf1e26a8126d0ec546bd686
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server-2015"></a><span data-ttu-id="05b9e-103">Сопоставление отчетов мониторинга с зеркальной базы данных в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="05b9e-103">Associate Monitoring Reports with a mirror database in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="05b9e-104">**Сводка:** Узнайте, как связать отчетов мониторинга с зеркальной базы данных, используемые Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="05b9e-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server 2015.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="05b9e-105">Отчеты по отслеживанию с зеркальной базой данных</span><span class="sxs-lookup"><span data-stu-id="05b9e-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="05b9e-106">Если для базы данных мониторинга настроена зеркальная база данных, то в случае отказа зеркальная база данных примет на себя функции основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="05b9e-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="05b9e-107">Тем не менее при использовании Скайп для отчетов мониторинга Business Server и перехода, которые могут оказаться, что отчетов мониторинга не подключаетесь зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="05b9e-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="05b9e-108">Причиной этого является то, что при установке Отчетов о мониторинге вы указываете только местоположение основной базы данных, но не указываете местоположение зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="05b9e-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="05b9e-p102">Для того чтобы Отчеты о мониторинге автоматически переключались на зеркальную базу данных, необходимо добавить зеркальную базу данных как "партнера по обеспечению отработки отказа" к двум базам данных, используемым в Отчетах о мониторинге (одна база данных – сбор данных и создание отчетов для детализации звонков, другая база - для сбора данных и создания отчетов о качестве взаимодействия (QoE)). (Обратите внимание, что этот шаг должен выполняться только после установки Отчетов о мониторинге.) Сведения о партнере по обеспечению отработки отказа можно добавить вручную с помощью редактирования значений строк подключения этих двух баз данных. Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="05b9e-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="05b9e-p103">В браузере Internet Explorer откройте главную страницу служб **SQL Server Reporting Services**. URL-адрес главной страницы служб Reporting Services состоит из следующих частей:</span><span class="sxs-lookup"><span data-stu-id="05b9e-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="05b9e-114">Префикс **http:**.</span><span class="sxs-lookup"><span data-stu-id="05b9e-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="05b9e-115">Полное доменное имя (FQDN) компьютера, на который устанавливаются службы Reporting Services (например, **atl-sql-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="05b9e-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="05b9e-116">Строка символов **/Reports_**.</span><span class="sxs-lookup"><span data-stu-id="05b9e-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="05b9e-117">Имя экземпляра базы данных, в которой устанавливаются Отчеты о мониторинге (например, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="05b9e-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="05b9e-118">Например, если служба SQL Server Reporting Services была установлена на компьютере atl-sql-001.litwareinc.com, а в Отчетах о мониторинге используется экземпляр базы данных с именем archinst, то URL-адрес главной страницы будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="05b9e-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="05b9e-119">Выполнив переход на главную страницу службы Reporting Services, щелкните ссылку **ServerReports**, затем - **Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="05b9e-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="05b9e-120">Вы перейдете к странице **Reports_Content** для Скайп для отчетов мониторинга Business Server.</span><span class="sxs-lookup"><span data-stu-id="05b9e-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="05b9e-121">На странице **Reports_Content** выберите источник данных **CDRDB**.</span><span class="sxs-lookup"><span data-stu-id="05b9e-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="05b9e-p105">На странице **CDRDB**, на вкладке **Свойства**, найдите текстовое окно с именем **Строка подключения**. Текущая строка подключения будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="05b9e-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="05b9e-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="05b9e-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="05b9e-p106">Добавьте в эту строку подключения имя сервера и экземпляр базы данных для зеркальной базы данных. Например, если имя сервера atl-mirror-001, а зеркальная база данных представлена экземпляром archinst, то для указания зеркальной базы данных применяется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="05b9e-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="05b9e-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="05b9e-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="05b9e-128">Отредактированная строка подключения будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="05b9e-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="05b9e-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="05b9e-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="05b9e-130">После внесения изменений в строку подключения нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="05b9e-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="05b9e-p107">На странице **CDRDB** щелкните ссылку **Reports_Content**. Выберите источник данных **QMSDB**, затем отредактируйте строку подключения для базы данных о качестве взаимодействия (QoE). Например:</span><span class="sxs-lookup"><span data-stu-id="05b9e-p107">On the **CDRDB** page, click the **Reports_Content** link. Click the **QMSDB** data source, and then edit the connection string for the QoE database. For example:</span></span>
    
    <span data-ttu-id="05b9e-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="05b9e-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="05b9e-135">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="05b9e-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="05b9e-136">См. также</span><span class="sxs-lookup"><span data-stu-id="05b9e-136">See also</span></span>

#### 

[<span data-ttu-id="05b9e-137">Установка отчетов в Скайп мониторинга для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="05b9e-137">Install Monitoring Reports in Skype for Business Server 2015</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="05b9e-138">С помощью отчетов в Скайп мониторинга для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="05b9e-138">Using Monitoring Reports in Skype for Business Server 2015</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)

