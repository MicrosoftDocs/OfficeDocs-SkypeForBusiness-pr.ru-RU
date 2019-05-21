---
title: Обновление устройств
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Корпорация Microsoft периодически выпускает новые обновления встроенного по устройства для Skype для бизнеса Phone Edition, которые можно импортировать на серверы и распространить среди пользователей. Вы можете получить последний набор правил обновления устройства, перейдя на страницу справки и поддержки на веб-сайте Майкрософт и выполнив поиск в Форфоне Edition. Скачайте последнюю версию пакета обновления и извлеките файлы в папку на компьютере, на котором нужно отправить обновления. После извлечения вы можете воспользоваться командлетом Import-CsDeviceUpdate для импорта правил обновления устройств из извлеченного файла CAB (он имеет имя UCUpdates.cab). Подробности можно найти в разделе import-Ксдевицеупдате.
ms.openlocfilehash: b387a24d88ab0b65c3df43a8ca5dd25d582a4827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285927"
---
# <a name="device-update"></a><span data-ttu-id="3248a-106">Обновление устройства</span><span class="sxs-lookup"><span data-stu-id="3248a-106">Device Update</span></span>

<span data-ttu-id="3248a-107">Корпорация Microsoft периодически выпускает новые обновления встроенного по устройства для Skype для бизнеса Phone Edition, которые можно импортировать на серверы и распространить среди пользователей.</span><span class="sxs-lookup"><span data-stu-id="3248a-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="3248a-108">Вы можете получить самые новые наборы правил обновления устройств, перейдя на страницу "Справка и поддержка" веб-сайта Майкрософт и выполнив поиск словосочетания "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="3248a-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="3248a-109">Загрузите самый новый пакет обновлений и извлеките файлы в папку на компьютере, куда собираетесь отправить обновления.</span><span class="sxs-lookup"><span data-stu-id="3248a-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="3248a-110">После извлечения вы можете воспользоваться командлетом **Import-CsDeviceUpdate** для импорта правил обновления устройств из извлеченного файла CAB (он имеет имя UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="3248a-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="3248a-111">Подробности можно найти в разделе [Import-ксдевицеупдате](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3248a-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="3248a-112">После того как правила обновления для устройства будут импортированы, вы можете просматривать эти правила для устройств организации и управлять ими с помощью страницы " **обновление устройства** ".</span><span class="sxs-lookup"><span data-stu-id="3248a-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="3248a-113">Вы можете протестировать обновления встроенного ПО и затем, если тестирование завершилось успешно, распространить их на все соответствующие устройства в организации.</span><span class="sxs-lookup"><span data-stu-id="3248a-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="3248a-114">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="3248a-114">Tasks you can perform</span></span>

<span data-ttu-id="3248a-115">На странице **Обновление устройства** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="3248a-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="3248a-116">утвердить обновления устройств в списке;</span><span class="sxs-lookup"><span data-stu-id="3248a-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="3248a-117">отменить или восстановить отложенные обновления устройств;</span><span class="sxs-lookup"><span data-stu-id="3248a-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="3248a-118">удалить обновления устройств из списка.</span><span class="sxs-lookup"><span data-stu-id="3248a-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="3248a-119">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="3248a-119">UI Reference</span></span>

<span data-ttu-id="3248a-120">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="3248a-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="3248a-121">**Изменить** С помощью этого параметра можно выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3248a-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="3248a-122">**Выделить все** Этот параметр позволяет выбрать все обновления устройства в списке.</span><span class="sxs-lookup"><span data-stu-id="3248a-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="3248a-123">**Delete (удалить** ) Этот параметр удаляет все выбранные обновления для устройств.</span><span class="sxs-lookup"><span data-stu-id="3248a-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="3248a-124">**Действие** Вы можете выбрать одно или несколько обновлений в списке и выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3248a-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="3248a-125">**Отмена ожидающих обновлений** Этот параметр препятствует развернутому выбранному обновлению на устройствах вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3248a-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="3248a-126">**Утвердить** Этот параметр позволяет развернуть выбранное обновление на устройствах вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3248a-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="3248a-127">**Восстановление** Этот параметр позволяет разворачивать ранее утвержденное обновление на устройствах Организации</span><span class="sxs-lookup"><span data-stu-id="3248a-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="3248a-128">**Обновить** Вы можете обновить список, чтобы проверить состояние всех обновлений устройства.</span><span class="sxs-lookup"><span data-stu-id="3248a-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="3248a-129">Дополнительные сведения веб-службе обновления устройств см. в разделе [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="3248a-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="3248a-130">См. также</span><span class="sxs-lookup"><span data-stu-id="3248a-130">See also</span></span>

[<span data-ttu-id="3248a-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="3248a-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
