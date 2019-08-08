---
title: Управление устройствами в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1keywords:
- ms.teamsadmincenter.devicemanagement.overview
- ms.teamsadmincenter.managedevices.overview
description: Здесь вы узнаете, как управлять устройствами, используемыми в вашей организации с помощью Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b259b893f443a068b8156f2298613b0feb6d028
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237507"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="3602d-103">Управление устройствами в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3602d-103">Manage your devices in Microsoft Teams</span></span>

::: zone target="docs"
<span data-ttu-id="3602d-104">Администраторы могут управлять всеми устройствами, используемыми Teams в Организации, из Microsoft Teams & центре администрирования Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3602d-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="3602d-105">Вы можете просматривать и управлять инвентаризацией устройств для вашей организации, а также выполнять такие задачи, как обновление, перезапуск и мониторинг диагностики для устройств.</span><span class="sxs-lookup"><span data-stu-id="3602d-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="3602d-106">Вы также можете создавать профили конфигурации и назначать их устройствам и группам устройств.</span><span class="sxs-lookup"><span data-stu-id="3602d-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="3602d-107">Какие устройства можно управлять?</span><span class="sxs-lookup"><span data-stu-id="3602d-107">What devices can you manage?</span></span>
<span data-ttu-id="3602d-108">Устройства должны быть сертифицированы для Teams и зарегистрированы в Teams.</span><span class="sxs-lookup"><span data-stu-id="3602d-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="3602d-109">Устройство автоматически регистрируется при первом входе пользователя в Teams на устройстве.</span><span class="sxs-lookup"><span data-stu-id="3602d-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="3602d-110">Список сертифицированных для управления устройств можно найти в разделе [конференции](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) и [стационарные телефоны](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span><span class="sxs-lookup"><span data-stu-id="3602d-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span></span>

> [!NOTE]
> <span data-ttu-id="3602d-111">Если у вас есть Microsoft Intune, устройства автоматически регистрируются в Intune.</span><span class="sxs-lookup"><span data-stu-id="3602d-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="3602d-112">После регистрации устройства считается, что соответствие устройства подтверждено и политики условного доступа применяются к устройству.</span><span class="sxs-lookup"><span data-stu-id="3602d-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="3602d-113">Управление устройствами в Teams</span><span class="sxs-lookup"><span data-stu-id="3602d-113">Manage devices in Teams</span></span>

<span data-ttu-id="3602d-114">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="3602d-114">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="3602d-115">На панели навигации слева перейдите на вкладку **устройства** > **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="3602d-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="3602d-116">Выберите **все устройства**.</span><span class="sxs-lookup"><span data-stu-id="3602d-116">Select **All devices**.</span></span>  

::: zone-end

 <span data-ttu-id="3602d-117">Отсюда вы можете просматривать и управлять всеми устройствами, зарегистрированными в Teams в Организации.</span><span class="sxs-lookup"><span data-stu-id="3602d-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="3602d-118">Сведения, которые вы увидите для каждого устройства, включают имя устройства, изготовителя, модель, пользователя, состояние, действие, время последнего просмотра и историю.</span><span class="sxs-lookup"><span data-stu-id="3602d-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="3602d-119">Вы можете настроить представление таким образом, чтобы в нем отображались нужные сведения.</span><span class="sxs-lookup"><span data-stu-id="3602d-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="3602d-120">Вот несколько примеров того, как управлять устройствами групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="3602d-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="3602d-121">Для этого выполните указанные ниже действия...</span><span class="sxs-lookup"><span data-stu-id="3602d-121">To do this...</span></span>  |<span data-ttu-id="3602d-122">Действие</span><span class="sxs-lookup"><span data-stu-id="3602d-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="3602d-123">Изменение сведений об устройствах</span><span class="sxs-lookup"><span data-stu-id="3602d-123">Change device information</span></span>   | <span data-ttu-id="3602d-124">Выберите устройство, > **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3602d-124">Select a device > **Edit**.</span></span> <span data-ttu-id="3602d-125">Вы можете изменить такие сведения, как имя устройства, сведения о пользователе, тег актива и добавить заметки.</span><span class="sxs-lookup"><span data-stu-id="3602d-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="3602d-126">Управление обновлениями программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="3602d-126">Manage software updates</span></span>   |<span data-ttu-id="3602d-127">Выберите устройство, > **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="3602d-127">Select a device > **Update**.</span></span> <span data-ttu-id="3602d-128">Вы можете просмотреть список обновлений программного обеспечения и микропрограмм, доступных для устройства, и выбрать обновления для установки.</span><span class="sxs-lookup"><span data-stu-id="3602d-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="3602d-129">Перезагрузка устройства</span><span class="sxs-lookup"><span data-stu-id="3602d-129">Restart a device</span></span>   |<span data-ttu-id="3602d-130">Выберите устройство, > **перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="3602d-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="3602d-131">Просмотр журнала устройства</span><span class="sxs-lookup"><span data-stu-id="3602d-131">View device history</span></span>  | <span data-ttu-id="3602d-132">Выберите > **Журнал**на устройстве.</span><span class="sxs-lookup"><span data-stu-id="3602d-132">Select a device > **History**.</span></span> <span data-ttu-id="3602d-133">Вы можете просмотреть историю обновлений для устройства.</span><span class="sxs-lookup"><span data-stu-id="3602d-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="3602d-134">Просмотреть диагностику</span><span class="sxs-lookup"><span data-stu-id="3602d-134">View diagnostics</span></span>  | <span data-ttu-id="3602d-135">Выберите устройство, > **Диагностика**.</span><span class="sxs-lookup"><span data-stu-id="3602d-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="3602d-136">Использование профилей конфигурации в Teams</span><span class="sxs-lookup"><span data-stu-id="3602d-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="3602d-137">Используйте профили конфигурации для управления параметрами и функциями для устройств с рабочими группами в Организации.</span><span class="sxs-lookup"><span data-stu-id="3602d-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="3602d-138">Вы можете создать или добавить профили конфигурации, чтобы включить или отключить параметры и функции, а затем назначить профиль устройству или группам устройств.</span><span class="sxs-lookup"><span data-stu-id="3602d-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="3602d-139">Создание профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="3602d-139">Create a configuration profile</span></span>

::: zone target="docs"

![Значок, показывающий логотип Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="3602d-141">Использование центра администрирования Skype для бизнеса в Microsoft Teams &</span><span class="sxs-lookup"><span data-stu-id="3602d-141">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="3602d-142">На панели навигации слева перейдите на вкладку **устройства** > **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="3602d-142">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="3602d-143">Выберите пункт **профили конфигурации**и нажмите кнопку **создать профиль конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="3602d-143">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="3602d-144">Введите имя профиля и при желании добавьте понятное описание.</span><span class="sxs-lookup"><span data-stu-id="3602d-144">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="3602d-145">Задайте нужные параметры профиля и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3602d-145">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="3602d-146">Назначение профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="3602d-146">Assign a configuration profile</span></span>

::: zone target="docs"

![Значок, показывающий логотип Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="3602d-148">Использование центра администрирования Skype для бизнеса в Microsoft Teams &</span><span class="sxs-lookup"><span data-stu-id="3602d-148">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="3602d-149">На панели навигации слева перейдите на вкладку **устройства** > **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="3602d-149">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="3602d-150">Выберите **профиль конфигурации**, а затем в \*\*\*\* поле назначено в профиле, который вы хотите назначить, щелкните ссылку.</span><span class="sxs-lookup"><span data-stu-id="3602d-150">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="3602d-151">В области **назначить устройства для профиля конфигурации** найдите и выберите устройства, которые вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="3602d-151">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="3602d-152">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3602d-152">Click **Save**.</span></span>
