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
description: После удаления сервера архивации можно удалить базы данных SQL Server, на которых размещены данные пула. Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753311"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="52eb4-104">Удаление базы данных SQL Server для сервера архивирования</span><span class="sxs-lookup"><span data-stu-id="52eb4-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="52eb4-105">После удаления сервера архивации можно удалить базы данных SQL Server, на которых размещены данные пула.</span><span class="sxs-lookup"><span data-stu-id="52eb4-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="52eb4-106">Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="52eb4-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="52eb4-107">Удаление базы данных SQL Server с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="52eb4-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="52eb4-108">На сервере переднего плана Skype для бизнеса Server 2019 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="52eb4-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="52eb4-109">В построителе топологий перейдите к разделу **Общие компоненты** , а затем к **хранилищу SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером архивации, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="52eb4-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="52eb4-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="52eb4-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="52eb4-111">Удаление файлов базы данных из SQL Server</span><span class="sxs-lookup"><span data-stu-id="52eb4-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="52eb4-112">Чтобы удалять базы данных на SQL Server, необходимо входить в группу системных администраторов сервера SQL Server, на котором удаляются файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="52eb4-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="52eb4-113">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="52eb4-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="52eb4-114">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="52eb4-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="52eb4-115">Где _\<FQDN\>_ — полное доменное имя сервера базы данных, а _\<instance\>_ — это именованный экземпляр базы данных (то есть, если он определен).</span><span class="sxs-lookup"><span data-stu-id="52eb4-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="52eb4-116">Когда командлет **uninstall-CsDataBase** запрашивает подтверждение действий, прочитайте информацию, а затем нажмите клавишу Y (или ввод), чтобы продолжить, или нажмите клавишу N, а затем ВВОД, чтобы остановить командлет (при наличии ошибок).</span><span class="sxs-lookup"><span data-stu-id="52eb4-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

