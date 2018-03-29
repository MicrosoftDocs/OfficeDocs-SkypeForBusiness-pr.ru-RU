---
title: Установка исправления или обновления SQL Server в составе группы доступности AlwaysOn в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 'Сводка: Узнайте о необходимости дополнительных действий после обновления вы или обновить Тыловой сервер, который является частью группы обеспечения доступности AlwaysOn в Скайп для Business Server.'
ms.openlocfilehash: 8f5c9131e59ccedd7f590f696fe53aa6c18c7d22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server-2015"></a><span data-ttu-id="496b5-103">Установка исправления или обновления SQL Server в составе группы доступности AlwaysOn в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="496b5-103">Patch or update a SQL Server in an AlwaysOn Availability Group in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="496b5-104">**Сводка:** Узнайте о необходимости дополнительные действия, после исправлений или обновления Тыловой сервер, который является частью группы обеспечения доступности AlwaysOn в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="496b5-104">**Summary:** Find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
<span data-ttu-id="496b5-105">После установки исправлений Тыловой сервер, который является частью группы обеспечения доступности AlwaysOn, необходимо повторно опубликовать эту топологию.</span><span class="sxs-lookup"><span data-stu-id="496b5-105">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a><span data-ttu-id="496b5-106">Установка исправления или обновления SQL Server в составе группы доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="496b5-106">Patching or updating a SQL Server that is part of an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="496b5-107">Установите обновления на сервер или серверы Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="496b5-107">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="496b5-108">Выполните следующую команду PowerShell в командной консоли Skype для бизнеса (необходимо выполнить вход с использованием учетной записи с разрешениями на применение изменений к базам данных SQL AlwaysOn).</span><span class="sxs-lookup"><span data-stu-id="496b5-108">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="496b5-109">Здесь [sqlpool.contoso.com] заменяется FQDN группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="496b5-109">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
    

