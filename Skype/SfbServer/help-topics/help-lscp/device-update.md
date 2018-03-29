---
title: Обновление устройств
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Периодически корпорация Майкрософт выпускает новый набор обновления встроенного устройства для Скайп для Business Phone Edition, который можно импортировать на серверах и распространения для пользователей. Можно получить последние версии из правила обновления устройств, перейдя на страницу справки и поддержки на веб-сайте Microsoft и поиск forPhone Edition.Download последнюю версию пакета обновления и извлеките файлы в папку на компьютере, на которых требуется отправить обновления. После извлечения файлы затем можно использовать командлет Import-CsDeviceUpdate для импорта правил обновления устройств, обнаруженных в извлеченные. CAB-файл (который будет иметь имя UCUpdates.cab). Дополнительные сведения см Import-CsDeviceUpdate.
ms.openlocfilehash: 584c04e8169eec4621c91c469127b99388f4820a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="device-update"></a><span data-ttu-id="dbe3e-106">Обновление устройства</span><span class="sxs-lookup"><span data-stu-id="dbe3e-106">Device Update</span></span>
 
<span data-ttu-id="dbe3e-107">Периодически корпорация Майкрософт выпускает новый набор обновления встроенного устройства для Скайп для Business Phone Edition, который можно импортировать на серверах и распространения для пользователей.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="dbe3e-108">Вы можете получить самые новые наборы правил обновления устройств, перейдя на страницу "Справка и поддержка" веб-сайта Майкрософт и выполнив поиск словосочетания "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="dbe3e-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="dbe3e-109">Загрузите самый новый пакет обновлений и извлеките файлы в папку на компьютере, куда собираетесь отправить обновления.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="dbe3e-110">После извлечения вы можете воспользоваться командлетом **Import-CsDeviceUpdate** для импорта правил обновления устройств из извлеченного файла CAB (он имеет имя UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="dbe3e-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="dbe3e-111">Дополнительные сведения см [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dbe3e-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>
  
<span data-ttu-id="dbe3e-112">После завершения импорта правил обновления устройств можно использовать страницу **Обновление устройства** для просмотра и управления эти правила для устройств вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>
  
> [!TIP]
> <span data-ttu-id="dbe3e-113">Вы можете протестировать обновления встроенного ПО и затем, если тестирование завершилось успешно, распространить их на все соответствующие устройства в организации.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="dbe3e-114">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="dbe3e-114">Tasks you can perform</span></span>

<span data-ttu-id="dbe3e-115">На странице **Обновление устройства** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="dbe3e-115">You can perform the following tasks on the **Device Update** page:</span></span>
  
- <span data-ttu-id="dbe3e-116">утвердить обновления устройств в списке;</span><span class="sxs-lookup"><span data-stu-id="dbe3e-116">Approve device updates in the list.</span></span>
    
- <span data-ttu-id="dbe3e-117">отменить или восстановить отложенные обновления устройств;</span><span class="sxs-lookup"><span data-stu-id="dbe3e-117">Cancel or restore pending device updates.</span></span>
    
- <span data-ttu-id="dbe3e-118">удалить обновления устройств из списка.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-118">Delete device updates from the list.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="dbe3e-119">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="dbe3e-119">UI Reference</span></span>

<span data-ttu-id="dbe3e-120">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="dbe3e-121">**Изменение** Этот параметр можно использовать для выполнения следующих:</span><span class="sxs-lookup"><span data-stu-id="dbe3e-121">**Edit** You can use this option to do the following:</span></span>
    
  - <span data-ttu-id="dbe3e-122">**Выделить все** Этот параметр выбирает все обновления устройств в списке.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-122">**Select All** This option selects all device updates in the list.</span></span>
    
  - <span data-ttu-id="dbe3e-123">**Удаление** Этот параметр удаляет все выбранные обновления устройств.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-123">**Delete** This option deletes all selected device updates.</span></span>
    
- <span data-ttu-id="dbe3e-124">**Действие** Можно выбрать одно или несколько обновлений в списке и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="dbe3e-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>
    
  - <span data-ttu-id="dbe3e-125">**Отменить ожидающие обновления** Этот параметр запрещает выбранного обновления при развертывании на устройствах вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>
    
  - <span data-ttu-id="dbe3e-126">**Утверждение** Этот параметр позволяет выбранного обновления для развертывания на устройствах вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>
    
  - <span data-ttu-id="dbe3e-127">**Восстановление** Этот параметр позволяет ранее утвержденного обновления для развертывания на устройствах вашей организации</span><span class="sxs-lookup"><span data-stu-id="dbe3e-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>
    
- <span data-ttu-id="dbe3e-128">**Обновление** Вы можете обновить список, чтобы проверить состояние всех обновлений устройств.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>
    
<span data-ttu-id="dbe3e-129">Для получения дополнительных сведений об устройстве веб-службе обновления видеть [Просмотр обновлений программного обеспечения для устройств в вашей организации](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="dbe3e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="dbe3e-130">See also</span></span>

#### 

[<span data-ttu-id="dbe3e-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="dbe3e-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)

