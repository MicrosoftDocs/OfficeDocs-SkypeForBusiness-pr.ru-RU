---
title: Управление устройствами в Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Здесь вы узнаете, как управлять устройствами, используемыми в вашей организации с помощью Teams.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366a24706a80f6fe96cc8a3733022cc64f78ba7e
ms.sourcegitcommit: 3ed779277540589eabef745685ab6c67d8a8ff90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "44281720"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="aa71d-103">Управление устройствами в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aa71d-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="aa71d-104">Администраторы могут управлять устройствами, используемыми в Организации с помощью Teams, в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="aa71d-104">As an admin, you can manage devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="aa71d-105">Вы можете просматривать и управлять инвентаризацией устройств для вашей организации, а также выполнять такие задачи, как обновление, перезапуск и мониторинг диагностики для устройств.</span><span class="sxs-lookup"><span data-stu-id="aa71d-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="aa71d-106">Вы также можете создавать профили конфигурации и назначать их устройствам и группам устройств.</span><span class="sxs-lookup"><span data-stu-id="aa71d-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="aa71d-107">Какие устройства можно управлять?</span><span class="sxs-lookup"><span data-stu-id="aa71d-107">What devices can you manage?</span></span>
<span data-ttu-id="aa71d-108">Вы можете управлять любым устройством, которое сертифицировано и зарегистрировано в Teams.</span><span class="sxs-lookup"><span data-stu-id="aa71d-108">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="aa71d-109">Устройство автоматически регистрируется при первом входе пользователя в Teams на устройстве.</span><span class="sxs-lookup"><span data-stu-id="aa71d-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="aa71d-110">Список сертифицированных устройств, которыми можно управлять, вы найдете в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="aa71d-110">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="aa71d-111">Телефонная конференция</span><span class="sxs-lookup"><span data-stu-id="aa71d-111">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [<span data-ttu-id="aa71d-112">Стационарные телефоны</span><span class="sxs-lookup"><span data-stu-id="aa71d-112">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- <span data-ttu-id="aa71d-113">Панели совместной работы</span><span class="sxs-lookup"><span data-stu-id="aa71d-113">Collaboration bars</span></span>

<span data-ttu-id="aa71d-114">Управление устройствами осуществляется в [центре администрирования Microsoft Teams](https://admin.teams.microsoft.com) в разделе **устройства** на панели навигации слева.</span><span class="sxs-lookup"><span data-stu-id="aa71d-114">Devices are managed in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** in the left navigation.</span></span>

> [!NOTE]
> <span data-ttu-id="aa71d-115">Если у вас есть Microsoft Intune, устройства автоматически регистрируются в Intune.</span><span class="sxs-lookup"><span data-stu-id="aa71d-115">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="aa71d-116">После регистрации устройства считается, что соответствие устройства подтверждено и политики условного доступа применяются к устройству.</span><span class="sxs-lookup"><span data-stu-id="aa71d-116">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="aa71d-117">Управление панелью "телефоны и совместная работа" в Teams</span><span class="sxs-lookup"><span data-stu-id="aa71d-117">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="aa71d-118">Несмотря на то, что мобильные телефоны и панели совместной работы управляются в центре администрирования Microsoft Teams, у них есть соответствующие разделы на панели навигации слева в разделе **устройства**.</span><span class="sxs-lookup"><span data-stu-id="aa71d-118">Even though phones and collaboration bars are managed the same in the Microsoft Teams admin center, they have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="aa71d-119">Это позволяет управлять каждым типом устройства отдельно.</span><span class="sxs-lookup"><span data-stu-id="aa71d-119">This lets you manage each type of device separately.</span></span>

<span data-ttu-id="aa71d-120">Здесь вы можете просматривать телефоны и панели совместной работы, зарегистрированные в Teams в Организации, и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="aa71d-120">From here, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="aa71d-121">Сведения, которые вы увидите для каждого устройства, включают имя устройства, изготовителя, модель, пользователя, состояние, действие, время последнего просмотра и историю.</span><span class="sxs-lookup"><span data-stu-id="aa71d-121">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="aa71d-122">Вы можете настроить представление таким образом, чтобы в нем отображались нужные сведения.</span><span class="sxs-lookup"><span data-stu-id="aa71d-122">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="aa71d-123">Вот несколько примеров того, как управлять устройствами групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="aa71d-123">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="aa71d-124">Для этого выполните указанные ниже действия...</span><span class="sxs-lookup"><span data-stu-id="aa71d-124">To do this...</span></span>  |<span data-ttu-id="aa71d-125">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="aa71d-125">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="aa71d-126">Изменение сведений об устройствах</span><span class="sxs-lookup"><span data-stu-id="aa71d-126">Change device information</span></span>   | <span data-ttu-id="aa71d-127">Выберите устройство, > **изменить**.</span><span class="sxs-lookup"><span data-stu-id="aa71d-127">Select a device > **Edit**.</span></span> <span data-ttu-id="aa71d-128">Вы можете изменять такие сведения, как имя устройства, тег актива и добавлять заметки.</span><span class="sxs-lookup"><span data-stu-id="aa71d-128">You can edit details such as device name, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="aa71d-129">Управление обновлениями программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="aa71d-129">Manage software updates</span></span>   |<span data-ttu-id="aa71d-130">Выберите устройство, > **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="aa71d-130">Select a device > **Update**.</span></span> <span data-ttu-id="aa71d-131">Вы можете просмотреть список обновлений программного обеспечения и микропрограмм, доступных для устройства, и выбрать обновления для установки.</span><span class="sxs-lookup"><span data-stu-id="aa71d-131">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="aa71d-132">Перезагрузка устройства</span><span class="sxs-lookup"><span data-stu-id="aa71d-132">Restart a device</span></span>   |<span data-ttu-id="aa71d-133">Выберите устройство, > **перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="aa71d-133">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="aa71d-134">Просмотр журнала устройства</span><span class="sxs-lookup"><span data-stu-id="aa71d-134">View device history</span></span>  | <span data-ttu-id="aa71d-135">Выберите > **Журнал**на устройстве.</span><span class="sxs-lookup"><span data-stu-id="aa71d-135">Select a device > **History**.</span></span> <span data-ttu-id="aa71d-136">Вы можете просмотреть историю обновлений для устройства.</span><span class="sxs-lookup"><span data-stu-id="aa71d-136">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="aa71d-137">Просмотреть диагностику</span><span class="sxs-lookup"><span data-stu-id="aa71d-137">View diagnostics</span></span>  | <span data-ttu-id="aa71d-138">Выберите устройство, > **Диагностика**.</span><span class="sxs-lookup"><span data-stu-id="aa71d-138">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="aa71d-139">Использование профилей конфигурации в Teams</span><span class="sxs-lookup"><span data-stu-id="aa71d-139">Use configuration profiles in Teams</span></span>

<span data-ttu-id="aa71d-140">Используйте профили конфигурации для управления параметрами и функциями для устройств с рабочими группами в Организации.</span><span class="sxs-lookup"><span data-stu-id="aa71d-140">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="aa71d-141">Вы можете создать или добавить профили конфигурации, чтобы включить или отключить параметры и функции, а затем назначить профиль устройству или группам устройств.</span><span class="sxs-lookup"><span data-stu-id="aa71d-141">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="aa71d-142">Создание профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="aa71d-142">Create a configuration profile</span></span>

1. <span data-ttu-id="aa71d-143">На панели навигации слева перейдите в раздел **Devices**  >  **Профили конфигураций**устройств.</span><span class="sxs-lookup"><span data-stu-id="aa71d-143">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="aa71d-144">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="aa71d-144">Click **Add**.</span></span>
3. <span data-ttu-id="aa71d-145">Введите имя профиля и при желании добавьте понятное описание.</span><span class="sxs-lookup"><span data-stu-id="aa71d-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="aa71d-146">Задайте нужные параметры профиля и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aa71d-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="aa71d-147">Назначение профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="aa71d-147">Assign a configuration profile</span></span>

1. <span data-ttu-id="aa71d-148">На панели навигации слева перейдите в раздел **Devices**  >  **Профили конфигураций**устройств.</span><span class="sxs-lookup"><span data-stu-id="aa71d-148">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="aa71d-149">Выберите **профиль конфигурации** , который вы хотите назначить, а затем нажмите кнопку **назначить устройству**.</span><span class="sxs-lookup"><span data-stu-id="aa71d-149">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="aa71d-150">В области **назначить устройства для профиля конфигурации** найдите и выберите устройства, которые вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="aa71d-150">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="aa71d-151">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aa71d-151">Click **Save**.</span></span>
