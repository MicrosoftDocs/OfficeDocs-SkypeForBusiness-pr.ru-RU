---
title: Добавление баз данных в группы обеспечения доступности AlwaysOn в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Сводка: Узнайте, как добавить дополнительные Скайп для сервера баз данных для существующей группы обеспечения доступности AlwaysOn в Скайп для Business Server.'
ms.openlocfilehash: f055466788494f10575b7bd3710705a138c456b2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976326"
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="a4346-103">Добавление баз данных в группы обеспечения доступности AlwaysOn в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="a4346-103">Add databases to an AlwaysOn Availability Group in Skype for Business Server</span></span>
 
<span data-ttu-id="a4346-104">**Сводка:** Узнайте, как добавить дополнительные Скайп для сервера баз данных в существующей группы обеспечения доступности AlwaysOn в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="a4346-104">**Summary:** Learn how to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="a4346-105">Добавление баз данных для группы обеспечения доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="a4346-105">Adding databases to an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="a4346-106">Откройте SQL Server Management Studio и перейдите к группе обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="a4346-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="a4346-107">Сбое в первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="a4346-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="a4346-108">В построителе топологий задайте полное доменное имя SQL Server из группы обеспечения доступности AlwaysOn полное доменное имя основного узел этой группы.</span><span class="sxs-lookup"><span data-stu-id="a4346-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
  - <span data-ttu-id="a4346-109">Откройте построитель топологий, выберите **загрузить топологию из существующего развертывания**и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="a4346-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
  - <span data-ttu-id="a4346-110">Разверните Скайп для сервера, топологии и **Хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a4346-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="a4346-111">Щелкните правой кнопкой мыши хранилище SQL для создания группы обеспечения доступности AlwaysOn и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="a4346-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
  - <span data-ttu-id="a4346-112">В нижней части страницы в поле **Полное доменное имя SQL Server** введите в поле полное имя основного узла группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="a4346-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="a4346-p103">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. После этого нажмите кнопку **Далее** на странице подтверждения.</span><span class="sxs-lookup"><span data-stu-id="a4346-p103">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="a4346-116">Используйте для добавления новой базы данных к группе обеспечения доступности AlwaysOn SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="a4346-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    

