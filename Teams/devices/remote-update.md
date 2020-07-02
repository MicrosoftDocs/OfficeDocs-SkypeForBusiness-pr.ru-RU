---
title: Удаленное обновление устройств с Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Удаленное обновление панелей Microsoft Teams для телефонов и совместной работы с помощью центра администрирования Teams
ms.openlocfilehash: 7e47c9394eddfa73b8b55279b68ae59ff7b6de3d
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944137"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="26481-103">Удаленное обновление устройств с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="26481-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="26481-104">Используя центр администрирования Microsoft Teams, вы можете обновлять свои устройства Teams, такие как телефоны и панели совместной работы, удаленно, и вы можете выбрать поведение автоматического обновления встроенного по устройства.</span><span class="sxs-lookup"><span data-stu-id="26481-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as phones and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="26481-105">Вы можете обновить следующие устройства с помощью центра администрирования teams:</span><span class="sxs-lookup"><span data-stu-id="26481-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="26481-106">Агент администрирования приложения Teams и Teams</span><span class="sxs-lookup"><span data-stu-id="26481-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="26481-107">Приложение корпоративного портала</span><span class="sxs-lookup"><span data-stu-id="26481-107">Company portal app</span></span>
- <span data-ttu-id="26481-108">Приложение агента для ПВТ</span><span class="sxs-lookup"><span data-stu-id="26481-108">OEM agent app</span></span>
- <span data-ttu-id="26481-109">Встроенное по устройства</span><span class="sxs-lookup"><span data-stu-id="26481-109">Device firmware</span></span>

<span data-ttu-id="26481-110">Обновления встроенного по устройства можно применять автоматически или по расписанию в будущем и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="26481-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="26481-111">Другие доступные обновления устройства не применяются автоматически, но их можно применять вручную или по расписанию в будущем и последующих Дата и время.</span><span class="sxs-lookup"><span data-stu-id="26481-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="26481-112">Несмотря на то, что обновление встроенного по может быть запланировано, если запланированная дата и время попадают за установленный максимум в 30 или 90 день, при достижении максимальной задержки будет применяться обновление встроенного по.</span><span class="sxs-lookup"><span data-stu-id="26481-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="26481-113">Запланированные Дата и время игнорируются.</span><span class="sxs-lookup"><span data-stu-id="26481-113">The scheduled date and time are ignored.</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="26481-114">Выбор поведения обновления встроенного по для автоматического устройства</span><span class="sxs-lookup"><span data-stu-id="26481-114">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="26481-115">Обновления встроенного по устройства применяются автоматически.</span><span class="sxs-lookup"><span data-stu-id="26481-115">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="26481-116">Вы можете решить, нужно ли применять обновления сразу после выпуска обновления, или 30 или 90 дней.</span><span class="sxs-lookup"><span data-stu-id="26481-116">You can decide whether to apply updates as soon as one is released, or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="26481-117">По умолчанию обновления встроенного по устройства применяются к одному выпущенному 30 суток.</span><span class="sxs-lookup"><span data-stu-id="26481-117">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26481-118">Последний выпуск обновления встроенного по не применяется на устройстве с Teams.</span><span class="sxs-lookup"><span data-stu-id="26481-118">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="26481-119">Вместо этого обновление, автоматически применяемое на вашем устройстве, задерживается одной версией.</span><span class="sxs-lookup"><span data-stu-id="26481-119">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="26481-120">Например, предположим, что на вашем устройстве применена версия 10, а версия "11" выпускается.</span><span class="sxs-lookup"><span data-stu-id="26481-120">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="26481-121">Версия "11" пока не будет применена.</span><span class="sxs-lookup"><span data-stu-id="26481-121">Version "11" won't be applied yet.</span></span> <span data-ttu-id="26481-122">Вместо этого ваше устройство будет обновлено до версии 11 после выпуска версии "12".</span><span class="sxs-lookup"><span data-stu-id="26481-122">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

<span data-ttu-id="26481-123">Чтобы выбрать режим автоматического обновления для устройств, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="26481-123">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="26481-124">Войдите в центр администрирования Microsoft Teams, посетивhttps://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="26481-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="26481-125">Навигация по **устройствам**на  >  **телефоне** или на **панели совместной работы**</span><span class="sxs-lookup"><span data-stu-id="26481-125">Navigate **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="26481-126">Выберите одно или несколько устройств и нажмите кнопку **Обновить** .</span><span class="sxs-lookup"><span data-stu-id="26481-126">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="26481-127">В разделе **Автоматическое обновление микропрограммы**выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="26481-127">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="26481-128">**Как можно скорее** Второе-новейшее обновление встроенного по для устройства, как можно скорее, будет применено после выпуска последнего обновления.</span><span class="sxs-lookup"><span data-stu-id="26481-128">**As soon as available** Second-newest device firmware update is applied as soon as possible after the latest update is released.</span></span>
    - <span data-ttu-id="26481-129">**Задерживает 30 дней** Второе-новейшее обновление встроенного по устройства в течение 30 дней после выпуска последнего обновления.</span><span class="sxs-lookup"><span data-stu-id="26481-129">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="26481-130">**Отложить 90 дней** Второе обновление встроенного по для устройства в 90 дней после выпуска последнего обновления.</span><span class="sxs-lookup"><span data-stu-id="26481-130">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="26481-131">Нажмите кнопку " **Обновить** "</span><span class="sxs-lookup"><span data-stu-id="26481-131">Select **Update**</span></span>

<span data-ttu-id="26481-132">Если по какой-либо причине вам нужно вернуться к обновлению встроенного по устройства, необходимо восстановить заводские настройки устройства.</span><span class="sxs-lookup"><span data-stu-id="26481-132">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="26481-133">Восстановите свое устройство с помощью инструкций, предоставленных производителем.</span><span class="sxs-lookup"><span data-stu-id="26481-133">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="26481-134">Обновление удаленных устройств вручную</span><span class="sxs-lookup"><span data-stu-id="26481-134">Manually update remote devices</span></span>

<span data-ttu-id="26481-135">Когда вы обновляете одно или несколько устройств с помощью центра администрирования, вы можете решить, следует ли немедленно обновлять эти устройства или запланировать обновление в течение следующего периода.</span><span class="sxs-lookup"><span data-stu-id="26481-135">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="26481-136">Чтобы вручную обновить удаленные устройства, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="26481-136">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="26481-137">Войдите в центр администрирования Microsoft Teams, посетивhttps://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="26481-137">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="26481-138">Навигация по **устройствам**на  >  **телефоне** или на **панели совместной работы**</span><span class="sxs-lookup"><span data-stu-id="26481-138">Navigate  **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="26481-139">Выберите одно или несколько устройств и нажмите кнопку **Обновить** .</span><span class="sxs-lookup"><span data-stu-id="26481-139">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="26481-140">В разделе **обновления вручную**выберите **Расписание** , если вы хотите запланировать обновление в будущем и более поздней дате.</span><span class="sxs-lookup"><span data-stu-id="26481-140">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="26481-141">Обновления применяются к дате и времени на часовом поясе, выбранном в **часовом поясе**.</span><span class="sxs-lookup"><span data-stu-id="26481-141">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="26481-142">Сведения о том, что вы видите, зависят от того, выбраны ли вы один или несколько устройств.</span><span class="sxs-lookup"><span data-stu-id="26481-142">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="26481-143">На рисунке ниже показано, как выделено несколько устройств, а на изображении справа — одно выбранное устройство.</span><span class="sxs-lookup"><span data-stu-id="26481-143">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="Одно и несколько представлений устройства в области состояния обновления устройства":::

<span data-ttu-id="26481-145">Выбрав несколько устройств, вы можете выбрать типы обновлений, которые будут применяться ко всем выбранным устройствам.</span><span class="sxs-lookup"><span data-stu-id="26481-145">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="26481-146">Выберите типы обновлений, которые вы хотите применить, и нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="26481-146">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="26481-147">При выборе одного устройства отображаются обновления, доступные для устройства.</span><span class="sxs-lookup"><span data-stu-id="26481-147">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="26481-148">Если для устройства доступно несколько типов обновлений, выберите тип каждого из них для применения.</span><span class="sxs-lookup"><span data-stu-id="26481-148">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="26481-149">Вы можете просмотреть **текущую версию** , примененную на устройстве, и **новую версию** , которая будет применена.</span><span class="sxs-lookup"><span data-stu-id="26481-149">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="26481-150">Выберите обновления, которые вы хотите применить, и нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="26481-150">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="26481-151">После выбора **обновления**к вашим устройствам применяются обновленные Дата и время, указанные при планировании обновления.</span><span class="sxs-lookup"><span data-stu-id="26481-151">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="26481-152">Если вы не выбрали дату и время в будущем, то обновления будут применены к вашим устройствам в течение нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="26481-152">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
