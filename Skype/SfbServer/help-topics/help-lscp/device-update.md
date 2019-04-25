---
title: Обновление устройств
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Периодически корпорация Майкрософт выпускает новый набор обновления встроенного устройства для Скайп для Business Phone Edition, который можно импортировать на серверах и распространения для пользователей. Можно получить последние версии из правила обновления устройств, перейдя на страницу справки и поддержки на веб-сайте Microsoft и поиск forPhone Edition.Download последнюю версию пакета обновления и извлеките файлы в папку на компьютере, на которых требуется отправить обновления. После извлечения вы можете воспользоваться командлетом Import-CsDeviceUpdate для импорта правил обновления устройств из извлеченного файла CAB (он имеет имя UCUpdates.cab). Дополнительные сведения см Import-CsDeviceUpdate.
ms.openlocfilehash: 271803e5a04f09ceda1fb98aced4501d3a08183e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234652"
---
# <a name="device-update"></a><span data-ttu-id="5bbf0-106">Обновление устройства</span><span class="sxs-lookup"><span data-stu-id="5bbf0-106">Device Update</span></span>

<span data-ttu-id="5bbf0-107">Периодически корпорация Майкрософт выпускает новый набор обновления встроенного устройства для Скайп для Business Phone Edition, который можно импортировать на серверах и распространения для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="5bbf0-108">Вы можете получить самые новые наборы правил обновления устройств, перейдя на страницу "Справка и поддержка" веб-сайта Майкрософт и выполнив поиск словосочетания "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="5bbf0-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="5bbf0-109">Загрузите самый новый пакет обновлений и извлеките файлы в папку на компьютере, куда собираетесь отправить обновления.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="5bbf0-110">После извлечения вы можете воспользоваться командлетом **Import-CsDeviceUpdate** для импорта правил обновления устройств из извлеченного файла CAB (он имеет имя UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="5bbf0-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="5bbf0-111">Дополнительные сведения см [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5bbf0-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="5bbf0-112">После завершения импорта правил обновления устройств можно использовать страницу **Обновление устройства** для просмотра и управления эти правила для устройств вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="5bbf0-113">Вы можете протестировать обновления встроенного ПО и затем, если тестирование завершилось успешно, распространить их на все соответствующие устройства в организации.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="5bbf0-114">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="5bbf0-114">Tasks you can perform</span></span>

<span data-ttu-id="5bbf0-115">На странице **Обновление устройства** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="5bbf0-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="5bbf0-116">утвердить обновления устройств в списке;</span><span class="sxs-lookup"><span data-stu-id="5bbf0-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="5bbf0-117">отменить или восстановить отложенные обновления устройств;</span><span class="sxs-lookup"><span data-stu-id="5bbf0-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="5bbf0-118">удалить обновления устройств из списка.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5bbf0-119">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="5bbf0-119">UI Reference</span></span>

<span data-ttu-id="5bbf0-120">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="5bbf0-121">**Изменение** Этот параметр можно использовать для выполнения следующих:</span><span class="sxs-lookup"><span data-stu-id="5bbf0-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="5bbf0-122">**Выделить все** Этот параметр выбирает все обновления устройств в списке.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="5bbf0-123">**Удаление** Этот параметр удаляет все выбранные обновления устройств.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="5bbf0-124">**Действие** Можно выбрать одно или несколько обновлений в списке и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5bbf0-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="5bbf0-125">**Отменить ожидающие обновления** Этот параметр запрещает выбранного обновления при развертывании на устройствах вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="5bbf0-126">**Утверждение** Этот параметр позволяет выбранного обновления для развертывания на устройствах вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="5bbf0-127">**Восстановление** Этот параметр позволяет ранее утвержденного обновления для развертывания на устройствах вашей организации</span><span class="sxs-lookup"><span data-stu-id="5bbf0-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="5bbf0-128">**Обновление** Вы можете обновить список, чтобы проверить состояние всех обновлений устройств.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="5bbf0-129">Дополнительные сведения веб-службе обновления устройств см. в разделе [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="5bbf0-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="5bbf0-130">См. также</span><span class="sxs-lookup"><span data-stu-id="5bbf0-130">See also</span></span>

[<span data-ttu-id="5bbf0-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="5bbf0-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
