---
title: Конфигурация журнала устройств
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: Веб-служба обновления устройств автоматически создает файл журнала, в котором регистрируются операции по обновлению устройства. В рамках стратегии управления данными вашей организации можно задать пороговые значения размера кэша данных журнала, размер файла журнала или продолжительность хранения файла журнала до его удаления. Можно изменить эти параметры в соответствии с потребностями организации. Если вы не хотите, чтобы веб-служба обновления устройств автоматически очищала файлы журналов, то можете очищать их вручную по мере необходимости. Параметры журнала можно изменять на глобальном уровне или для отдельных сайтов.
ms.openlocfilehash: 68e5e7d569f3a0436f80bb081b0785e5278bcb0d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892394"
---
# <a name="device-log-configuration"></a><span data-ttu-id="81201-107">Конфигурация журнала устройств</span><span class="sxs-lookup"><span data-stu-id="81201-107">Device Log Configuration</span></span>

<span data-ttu-id="81201-108">Веб-служба обновления устройств автоматически создает файл журнала, в котором регистрируются операции по обновлению устройства.</span><span class="sxs-lookup"><span data-stu-id="81201-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="81201-109">В рамках стратегии управления данными вашей организации можно задать пороговые значения размера кэша данных журнала, размер файла журнала или продолжительность хранения файла журнала до его удаления.</span><span class="sxs-lookup"><span data-stu-id="81201-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="81201-110">Можно изменить эти параметры в соответствии с потребностями организации.</span><span class="sxs-lookup"><span data-stu-id="81201-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="81201-111">Если вы не хотите, чтобы веб-служба обновления устройств автоматически очищала файлы журналов, то можете очищать их вручную по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="81201-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="81201-112">Параметры журнала можно изменять на глобальном уровне или для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="81201-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="81201-113">Вы также можете задать время дня, когда веб-служба обновления устройств будет автоматически удалять файлы журналов, которые старше заданного вами периода хранения журналов в днях (по умолчанию это файлы журналов, которые старше 10 дней).</span><span class="sxs-lookup"><span data-stu-id="81201-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="81201-114">Этот параметр нельзя изменить с помощью Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="81201-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="81201-115">Вместо этого необходимо использовать Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="81201-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="81201-116">Чтобы указать время суток для удаления файлов с истекшим сроком хранения журнала, используйте командлет **New-CsDeviceUpdateConfiguration** совместно с параметром - LogCleanUpTimeOfDay.</span><span class="sxs-lookup"><span data-stu-id="81201-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="81201-117">Дополнительные сведения см [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="81201-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="81201-p104">Очистка файлов окончательно удаляет их из файловой системы. После очистки файла его уже нельзя восстановить.</span><span class="sxs-lookup"><span data-stu-id="81201-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="81201-120">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="81201-120">Tasks you can perform</span></span>

<span data-ttu-id="81201-121">На странице **Настройка журнала устройств** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="81201-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="81201-122">добавить настройку журнала устройств на глобальном уровне или для отдельного сайта или пула;</span><span class="sxs-lookup"><span data-stu-id="81201-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="81201-123">изменить значения для существующих настроек журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="81201-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="81201-124">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="81201-124">UI Reference</span></span>

<span data-ttu-id="81201-125">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="81201-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="81201-126">**Новые** Можно добавить новую настройку журнала устройств со следующей областью:</span><span class="sxs-lookup"><span data-stu-id="81201-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="81201-127">Глобальный</span><span class="sxs-lookup"><span data-stu-id="81201-127">Global</span></span>

  - <span data-ttu-id="81201-128">Сайт</span><span class="sxs-lookup"><span data-stu-id="81201-128">Site</span></span>

- <span data-ttu-id="81201-129">**Изменение** Можно изменить параметры настройки журнала устройств в списке.</span><span class="sxs-lookup"><span data-stu-id="81201-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="81201-130">С помощью этого параметра можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="81201-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="81201-131">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры для настройки журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="81201-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="81201-132">**Выделить все** Этот параметр выбирает настройку журнала всех устройств в списке.</span><span class="sxs-lookup"><span data-stu-id="81201-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="81201-133">**Удаление** Этот параметр удаляет настройку журнала всех выбранных устройств.</span><span class="sxs-lookup"><span data-stu-id="81201-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="81201-134">**Обновление** Вы можете обновить список настройки журнала устройств, чтобы проверить состояние параметров для настройки журнала всех устройств.</span><span class="sxs-lookup"><span data-stu-id="81201-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="81201-135">См. также</span><span class="sxs-lookup"><span data-stu-id="81201-135">See also</span></span>

[<span data-ttu-id="81201-136">Modify Settings for Log Files of Device Update Activity</span><span class="sxs-lookup"><span data-stu-id="81201-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
