---
title: Управление базами данных с помощью группы доступности AlwaysOn в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Сводка: Узнайте, как добавить дополнительные базы данных Skype для бизнеса Server в существующую группу доступности AlwaysOn и ознакомиться с необходимыми дополнительными инструкциями после исправления или обновления сервера, который входит в группу доступности AlwaysOn в Skype для Business Server.'
ms.openlocfilehash: c6d8877448a68aa2331f3c290170418f6dca08ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275187"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="fb0a7-103">Управление базами данных с помощью группы доступности AlwaysOn в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fb0a7-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="fb0a7-104">Выполните действия, описанные в этой статье, чтобы добавить дополнительные базы данных Skype для бизнеса Server в существующую группу доступности AlwaysOn в Skype для бизнеса Server, и ознакомьтесь с необходимыми дополнительными инструкциями после исправления или обновления сервера, который входит в состав AlwaysOn. Группа "доступность" в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="fb0a7-105">Добавление баз данных в группу доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="fb0a7-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="fb0a7-106">Откройте центр SQL Server Management Studio и перейдите в группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="fb0a7-107">Переключиться на основную реплику.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="fb0a7-108">В построителе топологии Настройте полное доменное имя SQL Server группы доступности AlwaysOn на полное доменное имя основного узла этой группы.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="fb0a7-109">Откройте конфигуратор топологии, выберите пункт **загрузить топологию из существующего развертывания**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="fb0a7-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="fb0a7-111">Щелкните правой кнопкой мыши хранилище SQL для новой группы доступности AlwaysOn и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="fb0a7-112">В нижней части страницы в поле **полное доменное имя сервера SQL Server** введите полное доменное имя основного узла группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="fb0a7-113">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-113">Publish the topology.</span></span> <span data-ttu-id="fb0a7-114">В меню **Действие** щелкните **Топология**, затем **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="fb0a7-115">Затем на странице подтверждения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="fb0a7-116">С помощью SQL Server Management Studio вы можете добавить новую базу данных в группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="fb0a7-117">Установка исправления или обновления SQL Server в составе группы доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="fb0a7-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="fb0a7-118">После внесения исправлений на сервер, который входит в группу доступности AlwaysOn, необходимо повторно опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="fb0a7-119">Установите обновления на сервер или серверы Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="fb0a7-120">Выполните следующую команду PowerShell в командной консоли Skype для бизнеса (необходимо выполнить вход с использованием учетной записи с разрешениями на применение изменений к базам данных SQL AlwaysOn).</span><span class="sxs-lookup"><span data-stu-id="fb0a7-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="fb0a7-121">Здесь [sqlpool.contoso.com] заменяется FQDN группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="fb0a7-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
