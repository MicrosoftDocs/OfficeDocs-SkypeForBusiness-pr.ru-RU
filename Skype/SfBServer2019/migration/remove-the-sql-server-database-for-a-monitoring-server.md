---
title: Удаление базы данных SQL Server для сервера мониторинга
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
description: После удаления сервера мониторинга можно удалить базы данных SQL Server, в которых размещены данные сервера. Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753331"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="cecbc-104">Удаление базы данных SQL Server для сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="cecbc-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="cecbc-105">После удаления сервера мониторинга можно удалить базы данных SQL Server, в которых размещены данные сервера.</span><span class="sxs-lookup"><span data-stu-id="cecbc-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="cecbc-106">Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="cecbc-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="cecbc-107">Удаление базы данных SQL Server с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="cecbc-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="cecbc-108">На сервере переднего плана Skype для бизнеса Server 2019 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="cecbc-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="cecbc-109">В построителе топологий перейдите к разделу **Общие компоненты** , а затем к **хранилищу SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером мониторинга, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="cecbc-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="cecbc-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="cecbc-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="cecbc-111">Удаление файлов базы данных из SQL Server</span><span class="sxs-lookup"><span data-stu-id="cecbc-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="cecbc-112">Для удаления баз данных на сервере SQL Server вы должны быть членом группы администраторов системы SQL Server на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="cecbc-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="cecbc-113">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cecbc-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="cecbc-114">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cecbc-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="cecbc-115">Здесь _\<FQDN\>_ — полное доменное имя сервера базы данных, а _\<instance\>_ также необязательный именованный экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="cecbc-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="cecbc-116">Когда командлет **uninstall-CsDataBase** запрашивает подтверждение действий, прочитайте информацию, а затем нажмите клавишу Y (или ввод), чтобы продолжить, или нажмите клавишу N, а затем ВВОД, чтобы остановить командлет (при наличии ошибок).</span><span class="sxs-lookup"><span data-stu-id="cecbc-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

