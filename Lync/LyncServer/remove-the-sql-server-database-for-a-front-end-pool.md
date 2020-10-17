---
title: Удаление базы данных SQL Server для пула переднего плана
description: Удалите базу данных SQL Server для пула переднего плана.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c5d47e4c52197c5792fa3b7770da7bbd1b26cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551265"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="414fa-103">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="414fa-103">Remove the SQL Server database for a Front End pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="414fa-104">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="414fa-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="414fa-105">После удаления интерфейсного пула Microsoft Lync Server 2010 или повторной настройки пула для использования другой базы данных можно удалить базы данных SQL Server, на которых размещены данные пула.</span><span class="sxs-lookup"><span data-stu-id="414fa-105">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="414fa-106">Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="414fa-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="414fa-107">Удаление базы данных SQL Server с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="414fa-107">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="414fa-108">На сервере переднего плана Lync Server 2013 откройте построитель топологий и скачайте существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="414fa-108">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="414fa-109">В построителе топологий перейдите к разделу **Общие компоненты** , а затем к **хранилищу SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным интерфейсным пулом, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="414fa-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="414fa-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="414fa-110">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="414fa-111">Удаление базы данных пользователей и базы данных приложений из SQL Server</span><span class="sxs-lookup"><span data-stu-id="414fa-111">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="414fa-112">Чтобы удалять базы данных на SQL Server, необходимо входить в группу системных администраторов сервера SQL Server, на котором удаляются файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="414fa-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="414fa-113">Открытие консоли управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="414fa-113">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="414fa-114">Чтобы удалить базу данных для хранилища пользователей пула, введите:</span><span class="sxs-lookup"><span data-stu-id="414fa-114">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="414fa-115">Где \<FQDN\> — полное доменное имя сервера базы данных, а \<instance\> — это именованный экземпляр базы данных (то есть, если он определен).</span><span class="sxs-lookup"><span data-stu-id="414fa-115">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="414fa-116">Чтобы удалить базу данных для хранилища приложений пула, введите:</span><span class="sxs-lookup"><span data-stu-id="414fa-116">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="414fa-117">Где \<FQDN\> — полное доменное имя сервера базы данных, а \<instance\> — это именованный экземпляр базы данных (то есть, если он определен).</span><span class="sxs-lookup"><span data-stu-id="414fa-117">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="414fa-118">Когда командлетом **Uninstall-CsDataBase** выводится приглашение подтвердить действия, прочитайте информацию и нажмите клавишу **Y** (или нажмите клавишу ВВОД), чтобы продолжить, или нажмите клавишу **N**, а затем — клавишу ВВОД, если хотите остановить выполнение командлета (т. е., в случае ошибок).</span><span class="sxs-lookup"><span data-stu-id="414fa-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

