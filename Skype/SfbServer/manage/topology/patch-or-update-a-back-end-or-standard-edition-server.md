---
title: Исправление или обновление Тыловой сервер или сервере Standard Edition в Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Сводка: Узнайте, как для установки обновления или исправления на Тыловой сервер в Скайп для Business Server.'
ms.openlocfilehash: 7919d437e5111d32f3f51fa19a1880714800666b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214815"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="1d809-103">Исправление или обновление Тыловой сервер или сервере Standard Edition в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="1d809-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="1d809-104">**Сводка:** Сведения об установке обновления или исправления на Тыловой сервер в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="1d809-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="1d809-105">В этом разделе объясняется, как установить обновление на сервере Standard Edition или Enterprise Edition Тыловой сервер.</span><span class="sxs-lookup"><span data-stu-id="1d809-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="1d809-106">Если Тыловой сервер не работает в течение 30 минут при обновлении ее, пользователи могут зарегистрироваться в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="1d809-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="1d809-107">После завершения обновления и внутренними серверами попытку подключения с сервера переднего плана в пуле, пользователи, возвращаются все функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="1d809-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="1d809-108">Если обновление занимает менее 30 минут, оно никак не затронет работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d809-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="1d809-109">Обновление внутреннего сервера или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="1d809-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="1d809-110">Выполните вход на обновляемый сервер в качестве члена роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1d809-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="1d809-111">Загрузите обновление и извлеките его на локальный жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="1d809-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="1d809-112">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для бизнеса**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="1d809-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="1d809-113">Остановите Скайп для служб Business Server.</span><span class="sxs-lookup"><span data-stu-id="1d809-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="1d809-114">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1d809-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="1d809-115">Остановите службу Интернета.</span><span class="sxs-lookup"><span data-stu-id="1d809-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="1d809-116">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1d809-116">At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="1d809-117">Закройте все Скайп для Business Server Командная консоль windows.</span><span class="sxs-lookup"><span data-stu-id="1d809-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="1d809-118">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="1d809-118">Install the update.</span></span>
    
8. <span data-ttu-id="1d809-119">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для бизнеса**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="1d809-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="1d809-120">Остановите Скайп для служб Business Server еще раз, чтобы захватить -d сборки глобального кэша сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="1d809-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="1d809-121">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1d809-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="1d809-p105">Перезапустите службу Интернета. В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1d809-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="1d809-124">Примените изменения, внесенные в базы данных SQL Server, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="1d809-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="1d809-125">Если это Enterprise Edition Тыловой сервер и нет выровненных баз данных на этом сервере, такие как архивации или баз данных мониторинга, введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="1d809-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="1d809-126">Если это Enterprise Edition Тыловой сервер и есть выровненные базы данных на этом сервере, введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="1d809-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="1d809-127">Если это сервер Standard Edition, введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="1d809-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
