---
title: 'Lync Server 2013: Связывание отчетов мониторинга с зеркальной базой данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93e5f10e3e4bd3c063cafcb2fd984098482ebf22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="13581-102">Связывание отчетов мониторинга с зеркальной базой данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13581-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13581-103">_**Тема последнего изменения:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="13581-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="13581-104">Если для базы данных мониторинга настроена зеркальная база данных, то в случае отказа зеркальная база данных примет на себя функции основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="13581-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="13581-105">Однако если вы используете отчеты мониторинга в Lync Server и произйдете переход на другой ресурс, возможно, вы обнаружите, что отчеты мониторинга не подключаются к зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="13581-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="13581-106">Причиной этого является то, что при установке Отчетов о мониторинге вы указываете только местоположение основной базы данных, но не указываете местоположение зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="13581-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="13581-p102">Для того чтобы Отчеты о мониторинге автоматически переключались на зеркальную базу данных, необходимо добавить зеркальную базу данных как "партнера по обеспечению отработки отказа" к двум базам данных, используемым в Отчетах о мониторинге (одна база данных – сбор данных и создание отчетов для детализации звонков, другая база - для сбора данных и создания отчетов о качестве взаимодействия (QoE)). (Обратите внимание, что этот шаг должен выполняться только после установки Отчетов о мониторинге.) Сведения о партнере по обеспечению отработки отказа можно добавить вручную с помощью редактирования значений строк подключения этих двух баз данных. Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="13581-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="13581-p103">В браузере Internet Explorer откройте главную страницу служб **SQL Server Reporting Services**. URL-адрес главной страницы служб Reporting Services состоит из следующих частей:</span><span class="sxs-lookup"><span data-stu-id="13581-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="13581-112">Префикс **http:**.</span><span class="sxs-lookup"><span data-stu-id="13581-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="13581-113">Полное доменное имя (FQDN) компьютера, на который устанавливаются службы Reporting Services (например, **atl-sql-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="13581-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="13581-114">Строка символов **/Репортс\_**.</span><span class="sxs-lookup"><span data-stu-id="13581-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="13581-115">Имя экземпляра базы данных, в которой устанавливаются Отчеты о мониторинге (например, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="13581-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="13581-116">Например, если служба SQL Server Reporting Services была установлена на компьютере atl-sql-001.litwareinc.com, а в Отчетах о мониторинге используется экземпляр базы данных с именем archinst, то URL-адрес главной страницы будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="13581-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="13581-117">После доступа к домашней странице служб Reporting Services щелкните **линксерверрепортс**, а затем выберите пункт **содержимое\_отчета**.</span><span class="sxs-lookup"><span data-stu-id="13581-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="13581-118">Откроется страница " **данные отчетов\_** " для отчетов мониторинга Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13581-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="13581-119">На странице **"\_содержимое отчетов** " щелкните источник данных **кдрдб** .</span><span class="sxs-lookup"><span data-stu-id="13581-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="13581-p105">На странице **CDRDB**, на вкладке **Свойства**, найдите текстовое окно с именем **Строка подключения**. Текущая строка подключения будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="13581-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="13581-122">**Источник данных = (local)\\арчинст; Initial Catalog = лкскдр**</span><span class="sxs-lookup"><span data-stu-id="13581-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="13581-p106">Добавьте в эту строку подключения имя сервера и экземпляр базы данных для зеркальной базы данных. Например, если имя сервера atl-mirror-001, а зеркальная база данных представлена экземпляром archinst, то для указания зеркальной базы данных применяется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="13581-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="13581-125">**Партнер по резервному отношению = ATL-\\Mirror-001 арчинст**</span><span class="sxs-lookup"><span data-stu-id="13581-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="13581-126">Отредактированная строка подключения будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="13581-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="13581-127">**Источник данных = (локальный)\\арчинст; Резервный партнер = ATL-Mirror-\\001 арчинст; Initial Catalog = лкскдр**</span><span class="sxs-lookup"><span data-stu-id="13581-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="13581-128">После внесения изменений в строку подключения нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="13581-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="13581-129">На странице **кдрдб** щелкните ссылку **содержимое отчетов\_** .</span><span class="sxs-lookup"><span data-stu-id="13581-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="13581-130">Выберите источник данных **QMSDB**, затем отредактируйте строку подключения для базы данных о качестве взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="13581-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="13581-131">Например:</span><span class="sxs-lookup"><span data-stu-id="13581-131">For example:</span></span>
    
    <span data-ttu-id="13581-132">**Источник данных = (локальный)\\арчинст; Резервный партнер = ATL-Mirror-\\001 арчинст; Initial Catalog = коеметрикс**</span><span class="sxs-lookup"><span data-stu-id="13581-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="13581-133">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="13581-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="13581-134">См. также</span><span class="sxs-lookup"><span data-stu-id="13581-134">See Also</span></span>


[<span data-ttu-id="13581-135">Установка отчетов мониторинга Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13581-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="13581-136">Использование отчетов мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13581-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

