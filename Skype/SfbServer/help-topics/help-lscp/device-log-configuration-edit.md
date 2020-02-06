---
title: Изменение конфигурации журнала устройств
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Вы можете добавить конфигурацию журнала устройств на страницу изменения параметров журнала, которая определяет максимальный размер кэша журнала, максимальный размер файла журнала или продолжительность хранения файла журнала до его очистки. Вы можете изменить эти параметры в соответствии с требованиями вашей организации.
ms.openlocfilehash: 3ea368c0f3bccd7655d1bca3cb93a98a86b99c47
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822912"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="beb9b-104">Конфигурация журнала устройств: редактирование</span><span class="sxs-lookup"><span data-stu-id="beb9b-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="beb9b-105">Вы можете добавить конфигурацию журнала устройств на страницу **изменения параметров журнала** , которая определяет максимальный размер кэша журнала, максимальный размер файла журнала или продолжительность хранения файла журнала до его очистки.</span><span class="sxs-lookup"><span data-stu-id="beb9b-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="beb9b-106">Вы можете изменить эти параметры в соответствии с требованиями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="beb9b-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="beb9b-p103">Очистка файлов окончательно удаляет их из файловой системы. После очистки файла его уже нельзя восстановить.</span><span class="sxs-lookup"><span data-stu-id="beb9b-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="beb9b-109">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="beb9b-109">Tasks you can perform</span></span>

<span data-ttu-id="beb9b-110">На странице " **Изменение журнала** " можно выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="beb9b-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="beb9b-111">Добавьте глобальную конфигурацию журнала устройств или для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="beb9b-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="beb9b-112">изменить значения для существующих настроек журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="beb9b-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="beb9b-113">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="beb9b-113">UI Reference</span></span>

<span data-ttu-id="beb9b-114">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="beb9b-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="beb9b-115">**Область действия** Определяет область, определенную в конфигурации журнала устройств (глобально или на сайте).</span><span class="sxs-lookup"><span data-stu-id="beb9b-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="beb9b-116">**Name (имя** ) Вы можете добавить или изменить имя конфигурации журнала устройства.</span><span class="sxs-lookup"><span data-stu-id="beb9b-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="beb9b-117">**Максимальный размер файла (в байтах)** Вы можете указать максимальный размер, который может войти в файл журнала, прежде чем он будет очищен.</span><span class="sxs-lookup"><span data-stu-id="beb9b-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="beb9b-118">Значение по умолчанию — 1 024 000 байт (1 МБ).</span><span class="sxs-lookup"><span data-stu-id="beb9b-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="beb9b-119">**Максимальный размер кэша (в байтах)** Вы можете указать максимальный объем данных (в байтах), которые могут храниться в кэше файлов журнала до того, как этот кэш должен быть очищен, и данные записываются в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="beb9b-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="beb9b-120">Значение по умолчанию — 512 000 байт (0,5 МБ).</span><span class="sxs-lookup"><span data-stu-id="beb9b-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="beb9b-121">**Мин (-а) для кэша очистки (1-60)** Вы можете указать, как часто данные, хранящиеся в кэше файлов журнала, записываются в реальный файл журнала.</span><span class="sxs-lookup"><span data-stu-id="beb9b-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="beb9b-122">После того как данные записываются в журнал, кэш очищается.</span><span class="sxs-lookup"><span data-stu-id="beb9b-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="beb9b-123">По умолчанию используется значение 5 минут.</span><span class="sxs-lookup"><span data-stu-id="beb9b-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="beb9b-124">**Число дней для хранения файлов журнала (1-365)** Вы можете указать количество дней хранения файлов журнала, прежде чем они будут очищены.</span><span class="sxs-lookup"><span data-stu-id="beb9b-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="beb9b-125">Значение по умолчанию — 10 дней.</span><span class="sxs-lookup"><span data-stu-id="beb9b-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="beb9b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="beb9b-126">See also</span></span>

[<span data-ttu-id="beb9b-127">Конфигурация журнала устройств</span><span class="sxs-lookup"><span data-stu-id="beb9b-127">Device Log Configuration</span></span>](device-log-configuration.md)
