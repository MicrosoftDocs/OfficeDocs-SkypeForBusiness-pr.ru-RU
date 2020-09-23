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
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Чтобы изменить свойства базы данных SQL Server, необходимо изменить экземпляр базы данных SQL Server. Вы не можете использовать диалоговое окно Изменение свойств для выполнения таких задач, как перемещение базы данных сервера архивации с одного компьютера на другой. Кроме того, диалоговое окно Изменение свойств нельзя использовать для изменения экземпляра SQL Server, на котором размещается центральное хранилище управления.
ms.openlocfilehash: e3b16d8c6eab4f4918ef39b3c4f1ab4d0c6fc057
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219614"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="1db99-105">Расширитель параметров хранилища SQL</span><span class="sxs-lookup"><span data-stu-id="1db99-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="1db99-106">Чтобы изменить свойства базы данных SQL Server, необходимо изменить экземпляр базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1db99-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="1db99-107">Вы не можете использовать диалоговое окно **Изменение свойств** для выполнения таких задач, как перемещение базы данных сервера архивации с одного компьютера на другой.</span><span class="sxs-lookup"><span data-stu-id="1db99-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="1db99-108">Кроме того, диалоговое окно **изменение свойств** нельзя использовать для изменения экземпляра SQL Server, на котором размещается центральное хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="1db99-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="1db99-109">Изменение свойств базы данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="1db99-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="1db99-110">Чтобы изменить экземпляр SQL Server, используемый любой базой данных, отличной от центрального хранилища управления, выполните следующую процедуру в построителе топологий:</span><span class="sxs-lookup"><span data-stu-id="1db99-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="1db99-111">Изменение экземпляра SQL Server</span><span class="sxs-lookup"><span data-stu-id="1db99-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="1db99-112">Выберите соответствующую базу данных в узле **Хранилища SQL**, а затем щелкните элемент **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="1db99-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="1db99-113">В диалоговом окне **Изменение свойств** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1db99-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="1db99-114">Чтобы использовать экземпляр SQL Server по умолчанию, выберите **экземпляр по умолчанию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1db99-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="1db99-115">Чтобы использовать именованный экземпляр базы данных, выберите элемент **Именованный экземпляр**, введите имя экземпляра в текстовом поле и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1db99-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="1db99-116">Необходимо ввести только имя экземпляра (например, Арчивингинстанце), а не весь путь SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1db99-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="1db99-117">При работе в диалоговом окне **изменение свойств** построитель топологий не проверяет, что введенный экземпляр базы данных является допустимым экземпляром.</span><span class="sxs-lookup"><span data-stu-id="1db99-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="1db99-118">Например, если вы случайно Типеарчивингинстанеки в качестве имени экземпляра, а затем нажмите кнопку **ОК**, построитель топологий будет принимать этот недопустимый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1db99-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="1db99-119">Чтобы опубликовать эту топологию, необходимо исправить эту ошибку: если не удается найти экземпляр SQL Server, построитель топологий не создаст этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1db99-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

