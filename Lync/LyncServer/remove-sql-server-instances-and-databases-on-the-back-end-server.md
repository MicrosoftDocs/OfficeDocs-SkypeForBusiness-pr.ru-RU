---
title: Удаление экземпляров и баз данных SQL Server на внутреннем сервере
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbd5a681be1395038116be32b3267be07213af1b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="52e1b-102">Удаление экземпляров и баз данных SQL Server на внутреннем сервере</span><span class="sxs-lookup"><span data-stu-id="52e1b-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52e1b-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="52e1b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="52e1b-104">Вы удаляете базы данных и экземпляры Microsoft SQL Server после удаления серверов, на которых работает Lync Server 2010, которые зависят от них, или после перенастройки серверов, на которых работает Lync Server 2010, использовать другую базу данных.</span><span class="sxs-lookup"><span data-stu-id="52e1b-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="52e1b-105">Выполните процедуру, описанную в этом разделе, при отмене текущего сервера SQL Server или перенастройке текущего сервера, на котором работает Lync Server 2010, таким образом, чтобы они отображали устаревшие или недоступные базы данных.</span><span class="sxs-lookup"><span data-stu-id="52e1b-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="52e1b-106">Чтобы удалить базы данных или экземпляры сервера архивирования или сервера мониторинга, сначала необходимо удалить роль сервера.</span><span class="sxs-lookup"><span data-stu-id="52e1b-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="52e1b-107">Аналогичным образом, чтобы удалить экземпляры или базы данных для интерфейсного пула, необходимо сначала удалить или перенастроить роль зависимого сервера.</span><span class="sxs-lookup"><span data-stu-id="52e1b-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="52e1b-108">Эти процедуры одинаково подходят для баз данных с выровненным размещением и отдельных экземпляров, относящихся к серверам.</span><span class="sxs-lookup"><span data-stu-id="52e1b-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="52e1b-109">Выровненное размещение баз данных не влияет на выполнение этих процедур.</span><span class="sxs-lookup"><span data-stu-id="52e1b-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="52e1b-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="52e1b-110">In This Section</span></span>

  - [<span data-ttu-id="52e1b-111">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="52e1b-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="52e1b-112">Удаление базы данных SQL Server для сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="52e1b-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="52e1b-113">Удаление базы данных SQL Server для сервера архивирования</span><span class="sxs-lookup"><span data-stu-id="52e1b-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

