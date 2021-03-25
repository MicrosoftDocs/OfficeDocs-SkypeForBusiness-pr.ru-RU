---
title: Конфигурация журнала устройств
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: Веб-служба обновления устройства автоматически создает файлы журналов, которые записывают действия по обновлению устройства. В рамках стратегии управления данными организации может потребоваться установить пороговые значения по размеру кэша данных журнала, размеру файла журнала или времени хранения файла журнала до его чистки. Эти параметры можно изменить в соответствии с требованиями организации. Если веб-служба обновления устройств не требуется автоматически очищать файлы журналов, их можно очистить вручную, если это необходимо. Параметры журналов можно изменять глобально или на уровне сайта.
ms.openlocfilehash: c9bd2c3077325540e6151fabd7bc4127b909a12a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120278"
---
# <a name="device-log-configuration"></a><span data-ttu-id="d73b3-107">Конфигурация журнала устройств</span><span class="sxs-lookup"><span data-stu-id="d73b3-107">Device Log Configuration</span></span>

<span data-ttu-id="d73b3-108">Веб-служба обновления устройства автоматически создает файлы журналов, которые записывают действия по обновлению устройства.</span><span class="sxs-lookup"><span data-stu-id="d73b3-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="d73b3-109">В рамках стратегии управления данными организации может потребоваться установить пороговые значения по размеру кэша данных журнала, размеру файла журнала или времени хранения файла журнала до его чистки.</span><span class="sxs-lookup"><span data-stu-id="d73b3-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="d73b3-110">Эти параметры можно изменить в соответствии с требованиями организации.</span><span class="sxs-lookup"><span data-stu-id="d73b3-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="d73b3-111">Если веб-служба обновления устройств не требуется автоматически очищать файлы журналов, их можно очистить вручную, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="d73b3-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="d73b3-112">Параметры журналов можно изменять глобально или на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="d73b3-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="d73b3-113">Вы также можете настроить время суток, когда необходимо, чтобы веб-служба обновления устройств автоматически удаляла файлы журналов, которые старше количества дней, за которые вы настраивали службу для сохраняния файлов журналов (по умолчанию это файлы журналов, которые старше 10 дней).</span><span class="sxs-lookup"><span data-stu-id="d73b3-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="d73b3-114">Этот параметр нельзя изменить с помощью панели управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="d73b3-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="d73b3-115">Вместо этого необходимо использовать оболочку управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="d73b3-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="d73b3-116">Чтобы указать время суток для удаления просроченных файлов журнала, используйте комлет **New-CsDeviceUpdateConfiguration** с параметром -LogCleanUpTimeOfDay.</span><span class="sxs-lookup"><span data-stu-id="d73b3-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="d73b3-117">Подробнее см. [в материале New-CsDeviceUpdateConfiguration.](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d73b3-117">For details, see [New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="d73b3-p104">Очистка файлов окончательно удаляет их из файловой системы. После очистки файла его уже нельзя восстановить.</span><span class="sxs-lookup"><span data-stu-id="d73b3-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d73b3-120">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="d73b3-120">Tasks you can perform</span></span>

<span data-ttu-id="d73b3-121">Вы можете выполнить следующие задачи на странице **Конфигурация журнала** устройств:</span><span class="sxs-lookup"><span data-stu-id="d73b3-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="d73b3-122">Добавьте конфигурацию журнала устройств глобально или для определенного сайта или пула.</span><span class="sxs-lookup"><span data-stu-id="d73b3-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="d73b3-123">изменить значения для существующих настроек журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="d73b3-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d73b3-124">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="d73b3-124">UI Reference</span></span>

<span data-ttu-id="d73b3-125">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="d73b3-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="d73b3-126">**Новые** Вы можете добавить новую конфигурацию журнала устройств со следующей областью:</span><span class="sxs-lookup"><span data-stu-id="d73b3-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="d73b3-127">Глобальные</span><span class="sxs-lookup"><span data-stu-id="d73b3-127">Global</span></span>

  - <span data-ttu-id="d73b3-128">Site</span><span class="sxs-lookup"><span data-stu-id="d73b3-128">Site</span></span>

- <span data-ttu-id="d73b3-129">**Изменение** В списке можно изменить параметры конфигурации журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="d73b3-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="d73b3-130">С помощью этой команды можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d73b3-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="d73b3-131">**Демонстрация сведений** Этот параметр открывает диалоговое окно, в котором можно изменить параметры конфигурации журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="d73b3-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="d73b3-132">**Выберите все** Этот параметр выбирает всю конфигурацию журнала устройств в списке.</span><span class="sxs-lookup"><span data-stu-id="d73b3-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="d73b3-133">**Удаление** Этот параметр удаляет все выбранные конфигурации журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="d73b3-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="d73b3-134">**Обновление** Вы можете обновить список конфигурации журнала устройств, чтобы проверить состояние параметров всех конфигураций журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="d73b3-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="d73b3-135">См. также</span><span class="sxs-lookup"><span data-stu-id="d73b3-135">See also</span></span>

[<span data-ttu-id="d73b3-136">Изменение параметров файлов журналов для обновления устройств</span><span class="sxs-lookup"><span data-stu-id="d73b3-136">Modify Settings for Log Files of Device Update Activity</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)