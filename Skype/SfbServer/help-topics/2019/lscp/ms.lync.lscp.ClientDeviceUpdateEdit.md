---
title: Изменение конфигурации журнала устройств
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: Вы можете добавить на страницу Изменение настройки журнала настройку журнала устройств, определяющую максимальный размер кэша журнала, максимальный размер файла журнала или длительность хранения файла журнала перед очисткой. Эти параметры можно изменить в соответствии с требованиями организации.
ms.openlocfilehash: ac6c341460d0e196548a86620d89f67bc51d7b4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830299"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="3ccf8-104">Конфигурация журнала устройств: редактирование</span><span class="sxs-lookup"><span data-stu-id="3ccf8-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="3ccf8-105">Вы можете добавить на страницу **Изменение настройки журнала** настройку журнала устройств, определяющую максимальный размер кэша журнала, максимальный размер файла журнала или длительность хранения файла журнала перед очисткой.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="3ccf8-106">Эти параметры можно изменить в соответствии с требованиями организации.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3ccf8-p103">Очистка файлов окончательно удаляет их из файловой системы. После очистки файла его уже нельзя восстановить.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="3ccf8-109">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="3ccf8-109">Tasks you can perform</span></span>

<span data-ttu-id="3ccf8-110">На странице **Изменение настройки журнала** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="3ccf8-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="3ccf8-111">добавить настройку журнала устройств на глобальном уровне или для отдельного сайта;</span><span class="sxs-lookup"><span data-stu-id="3ccf8-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="3ccf8-112">изменить значения для существующих настроек журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="3ccf8-113">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="3ccf8-113">UI Reference</span></span>

<span data-ttu-id="3ccf8-114">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="3ccf8-115">**Область действия** Определяет область (глобальную или на уровне сайта) конфигурации журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="3ccf8-116">**Имя** Можно добавить или изменить имя конфигурации журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="3ccf8-117">**Максимальный размер файла (в ветвях)** Вы можете указать максимальный размер файла журнала перед его истоской.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="3ccf8-118">Значение по умолчанию — 1 024 000 (1 МБ).</span><span class="sxs-lookup"><span data-stu-id="3ccf8-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="3ccf8-119">**Максимальный размер кэша (вбайтах)** Вы можете указать максимальный объем данных (в файлах), которые могут быть хранимы в кэше файлов журнала, прежде чем этот кэш будет очищен и данные будут записаны в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="3ccf8-120">Значение по умолчанию — 512 000 (0,5 МБ).</span><span class="sxs-lookup"><span data-stu-id="3ccf8-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="3ccf8-121">**Минуты для очистки кэша (1–60)** Можно указать, как часто данные, хранимые в кэше файлов журнала, записываются в фактический файл журнала.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="3ccf8-122">После записи данных кэш очищается.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="3ccf8-123">Значение по умолчанию — пять минут.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="3ccf8-124">**Дни для сохраняемого файла журнала (1–365)** Можно указать количество дней, в течение которые файлы журналов будут храниться до их сойки.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="3ccf8-125">Значение по умолчанию — 10 дней.</span><span class="sxs-lookup"><span data-stu-id="3ccf8-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3ccf8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3ccf8-126">See also</span></span>

[<span data-ttu-id="3ccf8-127">Конфигурация журнала устройств</span><span class="sxs-lookup"><span data-stu-id="3ccf8-127">Device Log Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)
