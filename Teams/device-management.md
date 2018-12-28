---
title: Управление устройствами в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: kelsawi
f1keywords: ms.teamsadmincenter.devicemanagement.overview
description: Сведения об управлении устройств, используемых с группами в организации.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: dff307b1bd4ede3e8999a78a5e6a8df36b8a1411
ms.sourcegitcommit: a378848c5aeb8e2b25300024318de792454d905b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/28/2018
ms.locfileid: "27458552"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="50062-103">Управление устройствами в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="50062-103">Manage your devices in Microsoft Teams</span></span>

 <span data-ttu-id="50062-104">Как администратор управлять всеми устройствами, используемые с группами в организации с группами Майкрософт & Скайп по центру администрирования бизнес.</span><span class="sxs-lookup"><span data-stu-id="50062-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="50062-105">Можно просматривать и управлять Инвентаризация устройств для вашей организации и выполнять задачи, такие как обновление, перезагрузку и диагностика монитор для устройств.</span><span class="sxs-lookup"><span data-stu-id="50062-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="50062-106">Также можно создавать и назначать профили конфигурации устройства или групп устройств.</span><span class="sxs-lookup"><span data-stu-id="50062-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="50062-107">Какие устройства можно управлять?</span><span class="sxs-lookup"><span data-stu-id="50062-107">What devices can you manage?</span></span>
<span data-ttu-id="50062-108">Устройства должны сертифицированный для групп и участвуют в группах.</span><span class="sxs-lookup"><span data-stu-id="50062-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="50062-109">При первом входе пользователя в систему групп на устройстве автоматически регистрации устройство.</span><span class="sxs-lookup"><span data-stu-id="50062-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="50062-110">Список сертифицированных устройства, на которых можно управлять в разделе [телефонах для конференций](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=ddb1bc66-7499-4823-8d2b-a2c6dbe4f716) и [стационарные телефоны](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=c6536b33-f554-4b55-bd3d-c98733ebc017&page=1&filters=).</span><span class="sxs-lookup"><span data-stu-id="50062-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=ddb1bc66-7499-4823-8d2b-a2c6dbe4f716) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=c6536b33-f554-4b55-bd3d-c98733ebc017&page=1&filters=).</span></span>

> [!NOTE]
> <span data-ttu-id="50062-111">При наличии Microsoft Intune устройств, автоматически регистрируются в Intune.</span><span class="sxs-lookup"><span data-stu-id="50062-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="50062-112">После регистрации устройство подтверждено соответствие устройства и применение политик условного доступа к устройству.</span><span class="sxs-lookup"><span data-stu-id="50062-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="50062-113">Управление устройствами в группах</span><span class="sxs-lookup"><span data-stu-id="50062-113">Manage devices in Teams</span></span>

![команды логотип 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="50062-115">Использование групп Майкрософт & Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="50062-115">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="50062-116">В левой области навигации, перейдите к **устройствам** > **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="50062-116">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="50062-117">Выберите **все устройства**.</span><span class="sxs-lookup"><span data-stu-id="50062-117">Select **All devices**.</span></span>  

 <span data-ttu-id="50062-118">Здесь можно просматривать и управлять всеми устройствами, участвуют в группах в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="50062-118">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="50062-119">Сведения, которые вы увидите для каждого устройства включает в себя имя устройства, производителя, модель, пользователя, состояние, действие, видимых последнего и журнал.</span><span class="sxs-lookup"><span data-stu-id="50062-119">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="50062-120">Можно настроить параметры представления для отображения информации, который соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="50062-120">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="50062-121">Вот некоторые примеры того, как можно управлять группами устройств в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="50062-121">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="50062-122">Чтобы сделать это...</span><span class="sxs-lookup"><span data-stu-id="50062-122">To do this...</span></span>  |<span data-ttu-id="50062-123">Это сделать</span><span class="sxs-lookup"><span data-stu-id="50062-123">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="50062-124">Изменение сведений об устройстве</span><span class="sxs-lookup"><span data-stu-id="50062-124">Change device information</span></span>   | <span data-ttu-id="50062-125">Выберите устройство > **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="50062-125">Select a device > **Edit**.</span></span> <span data-ttu-id="50062-126">Можно изменить сведения, например имя устройства, сведения о пользователе, тег активов и добавлять примечания.</span><span class="sxs-lookup"><span data-stu-id="50062-126">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="50062-127">Управление обновлениями программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="50062-127">Manage software updates</span></span>   |<span data-ttu-id="50062-128">Выберите устройство > **обновления**.</span><span class="sxs-lookup"><span data-stu-id="50062-128">Select a device > **Update**.</span></span> <span data-ttu-id="50062-129">Можно просмотреть список обновлений программного обеспечения и микропрограммы, доступны для устройства и выберите обновления для установки.</span><span class="sxs-lookup"><span data-stu-id="50062-129">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="50062-130">Перезапуск устройства</span><span class="sxs-lookup"><span data-stu-id="50062-130">Restart a device</span></span>   |<span data-ttu-id="50062-131">Выберите устройство > **перезапуск**.</span><span class="sxs-lookup"><span data-stu-id="50062-131">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="50062-132">Просмотр журнала устройств</span><span class="sxs-lookup"><span data-stu-id="50062-132">View device history</span></span>  | <span data-ttu-id="50062-133">Выберите устройство > **Журнал**.</span><span class="sxs-lookup"><span data-stu-id="50062-133">Select a device > **History**.</span></span> <span data-ttu-id="50062-134">Можно просмотреть журнал обновления для устройства.</span><span class="sxs-lookup"><span data-stu-id="50062-134">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="50062-135">Диагностика представления</span><span class="sxs-lookup"><span data-stu-id="50062-135">View diagnostics</span></span>  | <span data-ttu-id="50062-136">Выберите устройство > **диагностики**.</span><span class="sxs-lookup"><span data-stu-id="50062-136">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="50062-137">Использование настройки профилей в группах</span><span class="sxs-lookup"><span data-stu-id="50062-137">Use configuration profiles in Teams</span></span>

<span data-ttu-id="50062-138">Используйте профили конфигурации для управления параметры и возможности для групп устройств в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="50062-138">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="50062-139">Можно создать или загрузка профили конфигурации для включения параметров и функций, которые требуется включить или отключить и назначение профиля устройства или группам устройств.</span><span class="sxs-lookup"><span data-stu-id="50062-139">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="50062-140">Создание профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="50062-140">Create a configuration profile</span></span>

![команды логотип 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="50062-142">Использование групп Майкрософт & Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="50062-142">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="50062-143">В левой области навигации, перейдите к **устройствам** > **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="50062-143">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="50062-144">Выберите **профили конфигурации**и выберите **новый профиль конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="50062-144">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="50062-145">Введите имя профиля и если вы хотите добавить понятное описание.</span><span class="sxs-lookup"><span data-stu-id="50062-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="50062-146">Укажите параметры, которые требуются для профиля и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="50062-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="50062-147">Назначение профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="50062-147">Assign a configuration profile</span></span>

![команды логотип 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="50062-149">Использование групп Майкрософт & Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="50062-149">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="50062-150">В левой области навигации, перейдите к **устройствам** > **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="50062-150">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="50062-151">Выберите **профиль конфигурации**и затем в разделе **назначено, чтобы** в профиль, который требуется назначить, щелкните ссылку.</span><span class="sxs-lookup"><span data-stu-id="50062-151">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="50062-152">В области **Назначение устройств для настройки профилей** поиск и выбор устройства, которые необходимо назначить.</span><span class="sxs-lookup"><span data-stu-id="50062-152">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="50062-153">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="50062-153">Click **Save**.</span></span>
