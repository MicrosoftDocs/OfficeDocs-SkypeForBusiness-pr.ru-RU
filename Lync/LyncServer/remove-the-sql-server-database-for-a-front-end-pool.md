---
title: Удаление базы данных SQL Server для пула переднего плана
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 853b52c6f6a06d05f106114ab6b59ebc52129fc3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="7218d-102">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="7218d-102">Remove the SQL Server database for a Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7218d-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="7218d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="7218d-104">После удаления пула переднего плана Microsoft Lync Server 2010 или повторной настройки пула для использования другой базы данных вы можете удалить базы данных SQL Server, на которых размещены данные пула.</span><span class="sxs-lookup"><span data-stu-id="7218d-104">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="7218d-105">Используйте описанные ниже процедуры для удаления определений из построителя топологии и удаления файлов базы данных и журнала с сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="7218d-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="7218d-106">Удаление базы данных SQL Server с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="7218d-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="7218d-107">На сервере переднего плана Lync Server 2013 откройте "Построитель топологии" и скачайте существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="7218d-107">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="7218d-108">В построителе топологии выберите **Общие компоненты** , а затем — **хранилище SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным пулом переднего плана, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7218d-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="7218d-109">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="7218d-109">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="7218d-110">Удаление баз данных пользователей и приложений из SQL Server</span><span class="sxs-lookup"><span data-stu-id="7218d-110">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="7218d-111">Для удаления баз данных на сервере SQL Server необходимо быть членом группы "Администраторы SQL Server" для сервера SQL Server, на котором нужно удалить файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="7218d-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="7218d-112">Открытие командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="7218d-112">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="7218d-113">Чтобы удалить базу данных из хранилища пользователей пула, введите:</span><span class="sxs-lookup"><span data-stu-id="7218d-113">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="7218d-114">Где \<FQDN\> — полное доменное имя сервера базы данных, а \<экземпляр\> — это именованный экземпляр базы данных (то есть, если он определен).</span><span class="sxs-lookup"><span data-stu-id="7218d-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="7218d-115">Чтобы удалить базу данных из хранилища приложений пула, введите:</span><span class="sxs-lookup"><span data-stu-id="7218d-115">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="7218d-116">Где \<FQDN\> — полное доменное имя сервера базы данных, \<а\> экземпляр — это именованный экземпляр базы данных (то есть, если он определен).</span><span class="sxs-lookup"><span data-stu-id="7218d-116">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="7218d-117">Когда командлет **uninstall-ксдатабасе** предложит вам подтвердить действия, прочтите информацию, а затем нажмите клавишу **Y** (или клавишу ВВОД), чтобы продолжить, **или клавишу с, чтобы** остановить командлет (то есть ошибки).</span><span class="sxs-lookup"><span data-stu-id="7218d-117">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

