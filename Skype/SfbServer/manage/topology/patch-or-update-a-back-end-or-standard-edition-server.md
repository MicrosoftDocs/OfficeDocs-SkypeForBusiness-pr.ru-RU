---
title: Исправление или обновление сервера обратного или стандартного выпуска Standard в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Сводка: сведения о том, как установить обновление или исправление на сервер с обратной стороны в Skype для бизнеса Server.'
ms.openlocfilehash: b8a0280577147e37c52ab11aa3061541bae27610
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275124"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="14368-103">Исправление или обновление сервера обратного или стандартного выпуска Standard в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="14368-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="14368-104">**Сводка:** Сведения о том, как установить обновление или исправление на сервер с веб-интерфейсом в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="14368-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="14368-105">В этой статье объясняется, как установить обновление на обратном сервере Enterprise Edition или стандартном сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="14368-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="14368-106">Если сервер выходит за частоту не менее 30 минут после его обновления, пользователи могут перейти в режим устойчивости.</span><span class="sxs-lookup"><span data-stu-id="14368-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="14368-107">После завершения обновления и повторного подключения серверов к внешним серверам из пула пользователи будут возвращены в полную функциональность.</span><span class="sxs-lookup"><span data-stu-id="14368-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="14368-108">Если обновление занимает менее 30 минут, оно никак не затронет работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="14368-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="14368-109">Обновление внутреннего сервера или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="14368-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="14368-110">Выполните вход на обновляемый сервер в качестве члена роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="14368-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="14368-111">Загрузите обновление и извлеките его на локальный жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="14368-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="14368-112">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Skype**для бизнеса и щелкните **консоль управления Skype для бизнеса Server**...</span><span class="sxs-lookup"><span data-stu-id="14368-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="14368-113">Остановите службы Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="14368-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="14368-114">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="14368-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="14368-115">Остановите службу Интернета.</span><span class="sxs-lookup"><span data-stu-id="14368-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="14368-116">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="14368-116">At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="14368-117">Закройте все окна командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="14368-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="14368-118">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="14368-118">Install the update.</span></span>
    
8. <span data-ttu-id="14368-119">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Skype**для бизнеса и щелкните **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="14368-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="14368-120">Остановите службы Skype для бизнеса Server, чтобы перехватить сборки d глобального кэша сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="14368-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="14368-121">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="14368-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="14368-p105">Перезапустите службу Интернета. В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="14368-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="14368-124">Примените изменения, внесенные в базы данных SQL Server, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="14368-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="14368-125">Если это сервер выпуска Enterprise Edition и на нем нет размещенных на нем баз данных, таких как архивация и мониторинг баз данных, введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="14368-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="14368-126">Если этот сервер выпуска Enterprise Edition и на нем есть размещенные на сервере базы данных, введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="14368-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="14368-127">Если это сервер Standard Edition, введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="14368-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
