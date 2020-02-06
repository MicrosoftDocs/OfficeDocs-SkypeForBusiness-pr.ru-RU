---
title: Расширитель параметров хранилища SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Чтобы изменить свойства базы данных SQL Server, необходимо изменить экземпляр базы данных SQL Server. Диалоговое окно "изменение свойств" нельзя использовать для выполнения таких задач, как перемещение базы данных сервера архивации с одного компьютера на другой. Кроме того, нельзя использовать диалоговое окно "изменение свойств" для изменения экземпляра SQL Server, на котором размещается хранилище Центрального управления.
ms.openlocfilehash: 654b1727badf9c0f08bcab9e181b301b72bd1299
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819201"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="21d57-105">Расширитель параметров хранилища SQL</span><span class="sxs-lookup"><span data-stu-id="21d57-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="21d57-106">Чтобы изменить свойства базы данных SQL Server, необходимо изменить экземпляр базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="21d57-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="21d57-107">Диалоговое окно " **изменение свойств** " нельзя использовать для выполнения таких задач, как перемещение базы данных сервера архивации с одного компьютера на другой.</span><span class="sxs-lookup"><span data-stu-id="21d57-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="21d57-108">Кроме того, нельзя использовать диалоговое окно " **изменение свойств** " для изменения экземпляра SQL Server, на котором размещается хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="21d57-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="21d57-109">Изменение свойств базы данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="21d57-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="21d57-110">Чтобы изменить экземпляр SQL Server, используемый базой данных, отличной от хранилища центрального управления, выполните указанные ниже действия в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="21d57-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="21d57-111">Изменение экземпляра SQL Server</span><span class="sxs-lookup"><span data-stu-id="21d57-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="21d57-112">Выберите нужную базу данных под узлом **хранилища SQL** и нажмите кнопку **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="21d57-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="21d57-113">В диалоговом окне **изменение свойств** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="21d57-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="21d57-114">Чтобы использовать экземпляр SQL Server по умолчанию, выберите **экземпляр по умолчанию** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="21d57-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="21d57-115">Чтобы использовать именованный экземпляр базы данных, выберите **именованный экземпляр**, введите имя экземпляра в текстовом поле, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="21d57-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="21d57-116">Необходимо ввести только имя экземпляра (например, Арчивингинстанце), а не весь путь SQL Server.</span><span class="sxs-lookup"><span data-stu-id="21d57-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="21d57-117">При работе в диалоговом окне " **изменение свойств** " Построитель топологии не будет проверять, правильно ли указан экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="21d57-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="21d57-118">Например, если вы случайно Типеарчивингинстанеки в качестве имени экземпляра и нажмите кнопку **ОК**, построитель топологии будет допускать этот недопустимый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="21d57-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="21d57-119">Прежде чем вы сможете опубликовать эту топологию, необходимо исправить эту ошибку: Если экземпляр SQL Server не удается найти, построитель топологии не создаст этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="21d57-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

