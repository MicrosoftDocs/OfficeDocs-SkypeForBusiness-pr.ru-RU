---
title: Конфигурация журнала устройств
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Веб-служба обновления устройств автоматически создает файл журнала, в котором регистрируются операции по обновлению устройства. В рамках стратегии управления данными Организации может потребоваться установить пороговые значения для размера кэша данных журнала, размера файла журнала или продолжительности хранения файла журнала до его очистки. Вы можете изменить эти параметры в соответствии с требованиями вашей организации. Если вы не хотите, чтобы веб-служба обновления устройств автоматически очищала файлы журналов, то можете очищать их вручную по мере необходимости. Параметры журнала можно изменять на глобальном уровне или для отдельных сайтов.
ms.openlocfilehash: 43fc784113a81038469099807770945ee2fbcc3b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794558"
---
# <a name="device-log-configuration"></a><span data-ttu-id="d7890-107">Конфигурация журнала устройств</span><span class="sxs-lookup"><span data-stu-id="d7890-107">Device Log Configuration</span></span>

<span data-ttu-id="d7890-108">Веб-служба обновления устройств автоматически создает файл журнала, в котором регистрируются операции по обновлению устройства.</span><span class="sxs-lookup"><span data-stu-id="d7890-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="d7890-109">В рамках стратегии управления данными Организации может потребоваться установить пороговые значения для размера кэша данных журнала, размера файла журнала или продолжительности хранения файла журнала до его очистки.</span><span class="sxs-lookup"><span data-stu-id="d7890-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="d7890-110">Вы можете изменить эти параметры в соответствии с требованиями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d7890-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="d7890-111">Если вы не хотите, чтобы веб-служба обновления устройств автоматически очищала файлы журналов, то можете очищать их вручную по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="d7890-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="d7890-112">Параметры журнала можно изменять на глобальном уровне или для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="d7890-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="d7890-113">Вы также можете задать время дня, когда веб-служба обновления устройств будет автоматически удалять файлы журналов, которые старше заданного вами периода хранения журналов в днях (по умолчанию это файлы журналов, которые старше 10 дней).</span><span class="sxs-lookup"><span data-stu-id="d7890-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="d7890-114">Этот параметр нельзя изменить с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d7890-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="d7890-115">Вместо этого необходимо использовать консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d7890-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="d7890-116">Чтобы задать время суток для удаления файлов журнала с истекшим сроком действия, используйте командлет **New-ксдевицеупдатеконфигуратион** с параметром-логклеануптимеофдай.</span><span class="sxs-lookup"><span data-stu-id="d7890-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="d7890-117">Подробности можно найти в разделе [New-ксдевицеупдатеконфигуратион](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d7890-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="d7890-p104">Очистка файлов окончательно удаляет их из файловой системы. После очистки файла его уже нельзя восстановить.</span><span class="sxs-lookup"><span data-stu-id="d7890-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d7890-120">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="d7890-120">Tasks you can perform</span></span>

<span data-ttu-id="d7890-121">На странице **Настройка журнала устройств** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d7890-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="d7890-122">добавить настройку журнала устройств на глобальном уровне или для отдельного сайта или пула;</span><span class="sxs-lookup"><span data-stu-id="d7890-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="d7890-123">изменить значения для существующих настроек журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="d7890-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d7890-124">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="d7890-124">UI Reference</span></span>

<span data-ttu-id="d7890-125">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="d7890-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="d7890-126">**Новые** Вы можете добавить новую конфигурацию журнала устройств в следующей области:</span><span class="sxs-lookup"><span data-stu-id="d7890-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="d7890-127">Глобальный</span><span class="sxs-lookup"><span data-stu-id="d7890-127">Global</span></span>

  - <span data-ttu-id="d7890-128">Сайт</span><span class="sxs-lookup"><span data-stu-id="d7890-128">Site</span></span>

- <span data-ttu-id="d7890-129">**Изменить** Вы можете изменить параметры конфигурации журнала устройств в списке.</span><span class="sxs-lookup"><span data-stu-id="d7890-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="d7890-130">С помощью этого параметра можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="d7890-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="d7890-131">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры конфигурации журнала устройства.</span><span class="sxs-lookup"><span data-stu-id="d7890-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="d7890-132">**Выделить все** Этот параметр позволяет выбрать в списке всю конфигурацию журнала устройств.</span><span class="sxs-lookup"><span data-stu-id="d7890-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="d7890-133">**Delete (удалить** ) Этот параметр удаляет все выбранные настройки журнала устройства.</span><span class="sxs-lookup"><span data-stu-id="d7890-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="d7890-134">**Обновить** Вы можете обновить список конфигурации журнала устройств, чтобы проверить состояние параметров конфигурации всех журналов устройств.</span><span class="sxs-lookup"><span data-stu-id="d7890-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7890-135">См. также</span><span class="sxs-lookup"><span data-stu-id="d7890-135">See also</span></span>

[<span data-ttu-id="d7890-136">Modify Settings for Log Files of Device Update Activity</span><span class="sxs-lookup"><span data-stu-id="d7890-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
