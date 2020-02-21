---
title: Удаление базы данных SQL Server для сервера мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f175f17b41a72c63aba77e6eb59aadce985ced82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="22c5f-102">Удаление базы данных SQL Server для сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="22c5f-102">Remove the SQL Server database for a Monitoring server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22c5f-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="22c5f-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="22c5f-104">После удаления сервера мониторинга Microsoft Lync Server 2010 можно удалить базы данных SQL Server, в которых размещены данные сервера.</span><span class="sxs-lookup"><span data-stu-id="22c5f-104">After you remove a Microsoft Lync Server 2010 Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="22c5f-105">Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="22c5f-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="22c5f-106">Удаление базы данных SQL Server с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="22c5f-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="22c5f-107">На сервере переднего плана Lync Server 2013 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="22c5f-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="22c5f-108">В построителе топологий перейдите к разделу **Общие компоненты** , а затем к **хранилищу SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером мониторинга, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="22c5f-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="22c5f-109">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="22c5f-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="22c5f-110">Удаление файлов базы данных из SQL Server</span><span class="sxs-lookup"><span data-stu-id="22c5f-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="22c5f-111">Для удаления баз данных на сервере SQL Server вы должны быть членом группы администраторов системы SQL Server на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="22c5f-111">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>

2.  <span data-ttu-id="22c5f-112">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22c5f-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="22c5f-113">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="22c5f-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="22c5f-114">Где \<полное\> доменное имя — это полное доменное имя сервера базы данных, а \<экземпляр\> — это необязательный именованный экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="22c5f-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the optional named database instance.</span></span>

4.  <span data-ttu-id="22c5f-115">Когда командлетом **Uninstall-CsDataBase** выводится приглашение подтвердить действия, прочитайте информацию и нажмите клавишу **Y** (или нажмите клавишу ВВОД), чтобы продолжить, или нажмите клавишу **N**, а затем — клавишу ВВОД, если хотите остановить выполнение командлета (т. е., в случае ошибок).</span><span class="sxs-lookup"><span data-stu-id="22c5f-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

