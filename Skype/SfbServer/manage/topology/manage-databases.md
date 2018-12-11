---
title: Управление базами данных с помощью группы обеспечения доступности AlwaysOn в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Сводка: Узнайте, как добавить дополнительные Скайп для сервера баз данных в существующей группы обеспечения доступности AlwaysOn и сведения о необходимости дополнительных действий после обновления вы или обновление Тыловой сервер, который является частью группы обеспечения доступности AlwaysOn в Скайп для Business Server.'
ms.openlocfilehash: ca7a792e001c29e087b9b6ac1637029c90ea1ae9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222809"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="8c3e8-103">Управление базами данных с помощью группы обеспечения доступности AlwaysOn в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="8c3e8-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="8c3e8-104">Выполните действия, описанные в этой статье для добавления дополнительные Скайп для сервера баз данных для существующей группы обеспечения доступности AlwaysOn в Скайп для Business Server и узнайте о необходимости дополнительных шагов после исправлений или обновления Тыловой сервер, который является частью AlwaysOn Группы обеспечения доступности в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="8c3e8-105">Добавление баз данных для группы обеспечения доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="8c3e8-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="8c3e8-106">Откройте SQL Server Management Studio и перейдите к группе обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="8c3e8-107">Сбое в первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="8c3e8-108">В построителе топологий задайте полное доменное имя SQL Server из группы обеспечения доступности AlwaysOn полное доменное имя основного узел этой группы.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="8c3e8-109">Откройте построитель топологий, выберите **загрузить топологию из существующего развертывания**и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="8c3e8-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="8c3e8-111">Щелкните правой кнопкой мыши хранилище SQL для создания группы обеспечения доступности AlwaysOn и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="8c3e8-112">В нижней части страницы в поле **Полное доменное имя SQL Server** введите в поле полное имя основного узла группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="8c3e8-113">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-113">Publish the topology.</span></span> <span data-ttu-id="8c3e8-114">В меню **Действие** щелкните **Топология**, затем **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="8c3e8-115">Затем на странице подтверждения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="8c3e8-116">Используйте для добавления новой базы данных к группе обеспечения доступности AlwaysOn SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="8c3e8-117">Установка исправления или обновления SQL Server в составе группы доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="8c3e8-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="8c3e8-118">После установки исправлений Тыловой сервер, который является частью группы обеспечения доступности AlwaysOn, необходимо повторно опубликовать эту топологию.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="8c3e8-119">Установите обновления на сервер или серверы Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="8c3e8-120">Выполните следующую команду PowerShell в командной консоли Skype для бизнеса (необходимо выполнить вход с использованием учетной записи с разрешениями на применение изменений к базам данных SQL AlwaysOn).</span><span class="sxs-lookup"><span data-stu-id="8c3e8-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="8c3e8-121">Здесь [sqlpool.contoso.com] заменяется FQDN группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8c3e8-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>