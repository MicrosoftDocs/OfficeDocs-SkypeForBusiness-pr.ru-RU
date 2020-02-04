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
ms.openlocfilehash: 0f877f7d8d1ade4d260ed137f52046c21f29cf11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="c0dc7-102">Удаление базы данных SQL Server для сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="c0dc7-102">Remove the SQL Server database for a Monitoring server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0dc7-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="c0dc7-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="c0dc7-104">После удаления сервера мониторинга Microsoft Lync Server 2010 вы можете удалить базы данных SQL Server, на которых размещены данные сервера.</span><span class="sxs-lookup"><span data-stu-id="c0dc7-104">After you remove a Microsoft Lync Server 2010 Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="c0dc7-105">Используйте описанные ниже процедуры для удаления определений из построителя топологии и удаления файлов базы данных и журнала с сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="c0dc7-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="c0dc7-106">Удаление базы данных SQL Server с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="c0dc7-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="c0dc7-107">На сервере переднего плана Lync Server 2013 откройте "Построитель топологии".</span><span class="sxs-lookup"><span data-stu-id="c0dc7-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="c0dc7-108">В построителе топологии откройте раздел **Общие компоненты** , а затем — **хранилище SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером мониторинга, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c0dc7-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="c0dc7-109">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="c0dc7-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="c0dc7-110">Удаление файлов базы данных из SQL Server</span><span class="sxs-lookup"><span data-stu-id="c0dc7-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="c0dc7-111">Для удаления баз данных на сервере SQL Server необходимо быть членом группы "Администраторы SQL Server" для сервера SQL Server, на котором нужно удалить файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="c0dc7-111">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>

2.  <span data-ttu-id="c0dc7-112">Откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c0dc7-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="c0dc7-113">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c0dc7-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="c0dc7-114">Где \<FQDN\> — полное доменное имя сервера базы данных, а \<экземпляр\> — это необязательный именованный экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="c0dc7-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the optional named database instance.</span></span>

4.  <span data-ttu-id="c0dc7-115">Когда командлет **uninstall-ксдатабасе** предложит вам подтвердить действия, прочтите информацию, а затем нажмите клавишу **Y** (или клавишу ВВОД), чтобы продолжить, **или клавишу с, чтобы** остановить командлет (то есть ошибки).</span><span class="sxs-lookup"><span data-stu-id="c0dc7-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

