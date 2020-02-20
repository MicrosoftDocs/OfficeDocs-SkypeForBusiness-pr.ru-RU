---
title: 'Lync Server 2013: сопоставление отчетов мониторинга с зеркальной базой данных'
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
ms.openlocfilehash: 48dbf5530a071bc1f23f9d2c05d82e151f51f645
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="c7fc6-102">Связывание отчетов мониторинга с зеркальной базой данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc6-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7fc6-103">_**Последнее изменение темы:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="c7fc6-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="c7fc6-104">Если вы настроили зеркальную копию для базы данных мониторинга, эта зеркальная база данных будет перенимать основную базу данных в случае отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="c7fc6-105">Тем не менее, если вы используете отчеты мониторинга Lync Server и происходит отработка отказа, вы можете обнаружить, что отчеты мониторинга не подключаются к зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="c7fc6-106">Это вызвано тем, что при установке отчетов мониторинга необходимо указать только расположение базы данных-источника. Вы не указываете расположение зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="c7fc6-107">Чтобы получать отчеты мониторинга для автоматической отработки отказа в зеркальной базе данных, необходимо добавить зеркальную базу данных в качестве отказоустойчивого участника в две базы данных, которые используются отчетами мониторинга (одна база данных для данных записи сведений о вызовах, а другая — для качества Данные взаимодействия (QoE)).</span><span class="sxs-lookup"><span data-stu-id="c7fc6-107">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="c7fc6-108">(Обратите внимание, что это действие следует выполнить после установки отчетов мониторинга.) Вы можете добавить сведения о партнере для отработки отказа, вручную отредактировав значения строки подключения, используемые этими двумя базами данных.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-108">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="c7fc6-109">Для этого выполните следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="c7fc6-109">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="c7fc6-110">С помощью Internet Explorer откройте домашнюю страницу **служб отчетов SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="c7fc6-110">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="c7fc6-111">URL-адрес домашней страницы служб отчетов включает:</span><span class="sxs-lookup"><span data-stu-id="c7fc6-111">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="c7fc6-112">Префикс **http:** .</span><span class="sxs-lookup"><span data-stu-id="c7fc6-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="c7fc6-113">Полное доменное имя (FQDN) компьютера, на котором установлены службы отчетов (например, **ATL-SQL-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="c7fc6-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="c7fc6-114">Строка символов **/Репортс\_**.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="c7fc6-115">Имя экземпляра базы данных, в котором установлены отчеты мониторинга (например, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="c7fc6-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="c7fc6-116">Например, если службы SQL Server Reporting Services установлены на компьютере atl-sql-001.litwareinc.com, а отчеты мониторинга используют экземпляр базы данных archinst, то URL-адрес домашней страницы будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c7fc6-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="c7fc6-117">После получения доступа к домашней странице служб отчетов нажмите кнопку **элемент lyncserverreports**, а затем выберите элемент **отчеты\_**.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="c7fc6-118">Откроется страница " **отчеты\_** " для отчетов мониторинга Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="c7fc6-119">На странице **"\_содержимое отчетов** " щелкните источник данных **CDRDB** .</span><span class="sxs-lookup"><span data-stu-id="c7fc6-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="c7fc6-120">На странице **CDRDB** на вкладке **свойства** найдите текстовое поле с подписью **строка подключения**.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-120">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="c7fc6-121">Текущая строка подключения будет выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="c7fc6-121">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="c7fc6-122">**Источник данных = (local)\\archinst; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="c7fc6-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="c7fc6-123">Измените строку подключения, чтобы включить имя сервера и экземпляр базы данных для зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-123">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="c7fc6-124">Например, если сервер имеет имя ATL-Mirror-001, а зеркальная база данных находится в экземпляре archinst, необходимо добавить зеркальную базу данных с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="c7fc6-124">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="c7fc6-125">**Отказоустойчивый партнер = ATL-archinst-\\001-001**</span><span class="sxs-lookup"><span data-stu-id="c7fc6-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="c7fc6-126">Измененная строка подключения будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c7fc6-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="c7fc6-127">**Источник данных = (local)\\archinst; Резервный партнер = ATL-Mirror-\\001 archinst; начальный каталог = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="c7fc6-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="c7fc6-128">После обновления строки подключения нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="c7fc6-129">На странице **CDRDB** щелкните ссылку **содержимое отчетов\_** .</span><span class="sxs-lookup"><span data-stu-id="c7fc6-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="c7fc6-130">Щелкните источник данных **кмсдб** , а затем измените строку подключения для базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="c7fc6-131">Например:</span><span class="sxs-lookup"><span data-stu-id="c7fc6-131">For example:</span></span>
    
    <span data-ttu-id="c7fc6-132">**Источник данных = (local)\\archinst; Резервный партнер = ATL-Mirror-\\001 archinst; начальный каталог = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="c7fc6-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="c7fc6-133">Нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="c7fc6-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c7fc6-134">См. также</span><span class="sxs-lookup"><span data-stu-id="c7fc6-134">See Also</span></span>


[<span data-ttu-id="c7fc6-135">Установка отчетов мониторинга Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc6-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="c7fc6-136">Использование отчетов мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc6-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

