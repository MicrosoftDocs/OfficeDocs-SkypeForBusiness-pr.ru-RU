---
title: Исправление или обновление тыл сервера или сервера Standard Edition в Skype для бизнеса Server
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
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: Сводка. Узнайте, как установить обновление или исправление на тыловом сервере в Skype для бизнеса Server.
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826309"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="24d7b-103">Исправление или обновление тыл сервера или сервера Standard Edition в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="24d7b-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="24d7b-104">**Сводка:** Узнайте, как установить обновление или исправление на тыловом сервере в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="24d7b-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="24d7b-105">В этом разделе объясняется, как установить обновление на тылевом сервере Enterprise Edition или сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="24d7b-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="24d7b-p101">Если во время обновления внутренний сервер отключается хотя бы на 30 минут, пользователи могут перейти в режим устойчивости. После завершения обновления и подключения внутреннего сервера к серверам переднего плана в пуле пользователи снова получают полный набор функциональных возможностей. Если обновление занимает менее 30 минут, оно никак не затронет работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="24d7b-p101">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode. When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality. If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="24d7b-109">Обновление тыл сервера или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="24d7b-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="24d7b-110">Выполните вход на обновляемый сервер в качестве члена роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="24d7b-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="24d7b-111">Загрузите обновление и извлеките его на локальный жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="24d7b-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="24d7b-112">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", **"Skype** для бизнеса" и "Skype для бизнеса **Server Management Shell".** </span><span class="sxs-lookup"><span data-stu-id="24d7b-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="24d7b-113">Остановите службы Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="24d7b-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="24d7b-114">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="24d7b-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="24d7b-115">Остановите службу Интернета.</span><span class="sxs-lookup"><span data-stu-id="24d7b-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="24d7b-116">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="24d7b-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="24d7b-117">Закроем все окна в оболочке управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="24d7b-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="24d7b-118">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="24d7b-118">Install the update.</span></span>
    
8. <span data-ttu-id="24d7b-119">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", **"Skype** для бизнеса" и "Skype для бизнеса **Server Management Shell".** </span><span class="sxs-lookup"><span data-stu-id="24d7b-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="24d7b-120">Снова остановите службы Skype для бизнеса Server, чтобы перехватить сборки -d глобального кэша сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="24d7b-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="24d7b-121">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="24d7b-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="24d7b-122">Перезапустите службу Интернета.</span><span class="sxs-lookup"><span data-stu-id="24d7b-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="24d7b-123">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="24d7b-123">At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="24d7b-124">Применив изменения, внесенные SQL Server баз данных, с помощью одного из следующих ок.</span><span class="sxs-lookup"><span data-stu-id="24d7b-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="24d7b-125">Если это тыловый сервер Enterprise Edition и на этом сервере нет совместок баз данных, таких как базы данных архива или мониторинга, введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="24d7b-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="24d7b-126">Если это сервер Enterprise Edition с размещенной базой данных на этом сервере, введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="24d7b-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="24d7b-127">Если это сервер Standard Edition, введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="24d7b-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
