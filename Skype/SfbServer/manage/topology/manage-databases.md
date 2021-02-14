---
title: Управление базами данных с помощью группы доступности AlwaysOn в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: Сводка. Узнайте, как добавить дополнительные базы данных Skype для бизнеса Server в существующую группу доступности AlwaysOn и узнать о необходимых дополнительных действиях после исправления или обновления тылого сервера, который входит в группу доступности AlwaysOn в Skype для бизнеса Server.
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826369"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="cd383-103">Управление базами данных с помощью группы доступности AlwaysOn в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="cd383-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="cd383-104">Воспользуйтесь действиями в этой статье, чтобы добавить дополнительные базы данных Skype для бизнеса Server в существующую группу доступности AlwaysOn в Skype для бизнеса Server, а также узнать о необходимых дополнительных действиях после исправления или обновления тылого сервера, который входит в группу доступности AlwaysOn в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cd383-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="cd383-105">Добавление баз данных в группу доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="cd383-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="cd383-106">Откройте SQL Server Management Studio и перейдите в группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="cd383-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="cd383-107">Перенаправь его в первичную реплику.</span><span class="sxs-lookup"><span data-stu-id="cd383-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="cd383-108">В построителе топологий SQL Server FQDN группы доступности AlwaysOn в качестве FQDN основного узла этой группы.</span><span class="sxs-lookup"><span data-stu-id="cd383-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="cd383-109">Откройте построитель топологий, выберите **"Загрузить топологию" из** существующего развертывания и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="cd383-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="cd383-110">Разверите Skype для бизнеса Server, развяйте топологию и SQL Server **хранилищах.**</span><span class="sxs-lookup"><span data-stu-id="cd383-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="cd383-111">Щелкните правой кнопкой мыши SQL новой группы доступности AlwaysOn и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="cd383-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="cd383-112">В нижней части страницы в поле **SQL Server Введите FQDN** основного узла группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="cd383-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="cd383-113">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="cd383-113">Publish the topology.</span></span> <span data-ttu-id="cd383-114">В меню **"Действие"** **щелкните "Топология",** а затем **"Опубликовать".**</span><span class="sxs-lookup"><span data-stu-id="cd383-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="cd383-115">Затем на странице подтверждения нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="cd383-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="cd383-116">Используйте SQL Server Management Studio для добавления новой базы данных в группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="cd383-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="cd383-117">Исправление или обновление SQL Server в группе доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="cd383-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="cd383-118">После исправления тыловых серверов, в которые входит группа доступности AlwaysOn, необходимо повторно опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="cd383-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="cd383-119">Установите обновление на сервер или серверы Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cd383-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="cd383-120">Выполните следующую команду PowerShell в командной оболочке Skype для бизнеса (во время входа с использованием учетной записи, которая имеет соответствующее разрешение на применение изменений к базам данных AlwaysOn SQL) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cd383-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="cd383-121">Где [sqlpool.contoso.com] заменяется на полное доменное имя группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="cd383-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
