---
title: Изменить настройки журнала устройств
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Можно добавить настройку журнала устройств на странице Изменение параметров журнала, который определяет максимальный размер кэша, максимальный размер файла журнала или время хранения файла журнала до его удаления. Можно изменить эти параметры в соответствии с потребностями организации.
ms.openlocfilehash: 09d0bc24ad61be98864fd1f37964c01f1fba84ba
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888268"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="3e38b-104">Конфигурация журнала устройств: редактирование</span><span class="sxs-lookup"><span data-stu-id="3e38b-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="3e38b-105">Можно добавить настройку журнала устройств на странице **Изменение параметров журнала** , который определяет максимальный размер кэша, максимальный размер файла журнала или время хранения файла журнала до его удаления.</span><span class="sxs-lookup"><span data-stu-id="3e38b-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="3e38b-106">Можно изменить эти параметры в соответствии с потребностями организации.</span><span class="sxs-lookup"><span data-stu-id="3e38b-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3e38b-p103">Очистка файлов окончательно удаляет их из файловой системы. После очистки файла его уже нельзя восстановить.</span><span class="sxs-lookup"><span data-stu-id="3e38b-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="3e38b-109">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="3e38b-109">Tasks you can perform</span></span>

<span data-ttu-id="3e38b-110">На странице **Изменение параметров журнала** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="3e38b-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="3e38b-111">Добавьте настройку журнала устройств глобальном уровне или для отдельного сайта.</span><span class="sxs-lookup"><span data-stu-id="3e38b-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="3e38b-112">изменить значения для существующих настроек журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="3e38b-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="3e38b-113">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="3e38b-113">UI Reference</span></span>

<span data-ttu-id="3e38b-114">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="3e38b-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="3e38b-115">**Область** Определяет область (глобальную или сайт) настройки журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="3e38b-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="3e38b-116">**Имя** Вы можете добавить или изменить имя настройки журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="3e38b-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="3e38b-117">**Максимальный размер файла (в байтах)** Можно указать максимальный размер файла журнала может стать до его удаления.</span><span class="sxs-lookup"><span data-stu-id="3e38b-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="3e38b-118">Значение по умолчанию — 1,024,000 байт (1 МБ).</span><span class="sxs-lookup"><span data-stu-id="3e38b-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="3e38b-119">**Максимальный размер кэша (байт)** Можно указать максимальный объем данных (в байтах), который может храниться в кэше файла журнала перед, что необходимо очистить кэш и данные записываются в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="3e38b-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="3e38b-120">Значение по умолчанию — 512,000 байт (0,5 МБ).</span><span class="sxs-lookup"><span data-stu-id="3e38b-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="3e38b-121">**Минут для очистки кэша (1-60)** Можно указать, как часто данные, хранящиеся в кэше файла журнала, записывается в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="3e38b-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="3e38b-122">После занесения в журнал данных очистить кэш.</span><span class="sxs-lookup"><span data-stu-id="3e38b-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="3e38b-123">Значение по умолчанию — 5 минут.</span><span class="sxs-lookup"><span data-stu-id="3e38b-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="3e38b-124">**Число дней хранения файлов журнала (1-365)** Можно указать количество дней хранения файлов журнала сохраняются в прежнем прежде чем они будут очищены.</span><span class="sxs-lookup"><span data-stu-id="3e38b-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="3e38b-125">Значение по умолчанию — 10 дней.</span><span class="sxs-lookup"><span data-stu-id="3e38b-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3e38b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3e38b-126">See also</span></span>

[<span data-ttu-id="3e38b-127">Конфигурация журнала устройств</span><span class="sxs-lookup"><span data-stu-id="3e38b-127">Device Log Configuration</span></span>](device-log-configuration.md)
