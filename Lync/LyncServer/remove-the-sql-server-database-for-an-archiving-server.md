---
title: Удаление базы данных SQL Server для сервера архивирования
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fab9cefc3fff51267426fd26263f9e2ec20a85ee
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518106"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="2f338-102">Удаление базы данных SQL Server для сервера архивирования</span><span class="sxs-lookup"><span data-stu-id="2f338-102">Remove the SQL Server database for an Archiving server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f338-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="2f338-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="2f338-104">После удаления сервера архивации Microsoft Lync Server 2010 вы можете удалить базы данных SQL Server, на которых размещены данные пула.</span><span class="sxs-lookup"><span data-stu-id="2f338-104">After you remove a Microsoft Lync Server 2010 Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="2f338-105">Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="2f338-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="2f338-106">Удаление базы данных SQL Server с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="2f338-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="2f338-107">На сервере переднего плана Lync Server 2013 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="2f338-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="2f338-108">В построителе топологий перейдите к разделу **Общие компоненты** , а затем к **хранилищу SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером архивации, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2f338-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="2f338-109">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="2f338-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="2f338-110">Удаление файлов базы данных из SQL Server</span><span class="sxs-lookup"><span data-stu-id="2f338-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="2f338-111">Чтобы удалять базы данных на SQL Server, необходимо входить в группу системных администраторов сервера SQL Server, на котором удаляются файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="2f338-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="2f338-112">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f338-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="2f338-113">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2f338-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="2f338-114">Где \<FQDN\> — полное доменное имя сервера базы данных, а \<instance\> — это именованный экземпляр базы данных (то есть, если он определен).</span><span class="sxs-lookup"><span data-stu-id="2f338-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="2f338-115">Когда командлетом **Uninstall-CsDataBase** выводится приглашение подтвердить действия, прочитайте информацию и нажмите клавишу **Y** (или нажмите клавишу ВВОД), чтобы продолжить, или нажмите клавишу **N**, а затем — клавишу ВВОД, если хотите остановить выполнение командлета (т. е., в случае ошибок).</span><span class="sxs-lookup"><span data-stu-id="2f338-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

