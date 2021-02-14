---
title: Удаление базы данных SQL Server для сервера архивирования
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После удаления сервера архива можно удалить SQL Server базы данных, в которой были данные пула. Для удаления определений из построитель топологий и удаления файлов базы данных и журналов с сервера баз данных используйте следующие процедуры.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753311"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="d9900-104">Удаление базы данных SQL Server для сервера архивирования</span><span class="sxs-lookup"><span data-stu-id="d9900-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="d9900-105">После удаления сервера архива можно удалить SQL Server баз данных, в которые были велись данные пула.</span><span class="sxs-lookup"><span data-stu-id="d9900-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="d9900-106">Для удаления определений из построитель топологий и удаления файлов базы данных и журналов с сервера баз данных используйте следующие процедуры.</span><span class="sxs-lookup"><span data-stu-id="d9900-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="d9900-107">Удаление базы данных SQL Server с помощью построщика топологий</span><span class="sxs-lookup"><span data-stu-id="d9900-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="d9900-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="d9900-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="d9900-109">В построите топологию перейдите к общим компонентам, а затем SQL Server **Хранилища,** щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером архива, а затем нажмите кнопку **"Удалить".** </span><span class="sxs-lookup"><span data-stu-id="d9900-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="d9900-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="d9900-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="d9900-111">Удаление файлов базы данных из SQL Server</span><span class="sxs-lookup"><span data-stu-id="d9900-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="d9900-112">Чтобы удалять базы данных на SQL Server, необходимо входить в группу системных администраторов сервера SQL Server, на котором удаляются файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="d9900-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="d9900-113">Откройте оболочку управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d9900-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="d9900-114">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d9900-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="d9900-115">Где находится полное доменное имя сервера базы данных и именовалось экземпляром базы данных (то есть, если он  _\<FQDN\>_  _\<instance\>_ был определен).</span><span class="sxs-lookup"><span data-stu-id="d9900-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="d9900-116">Когда  вам будет предложено подтвердить действия, ознакомьтесь с информацией, нажмите Y (или ВВОД), чтобы продолжить, или нажмите кнопку "Н", а затем введите, если необходимо остановить его (если имеются ошибки).</span><span class="sxs-lookup"><span data-stu-id="d9900-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

