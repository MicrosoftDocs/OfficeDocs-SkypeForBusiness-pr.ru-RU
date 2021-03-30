---
title: Удаленная подготовка и вход в Teams для устройств с Android
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как дистанционно подавь и войти в Teams на устройствах Android
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410383"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="06a89-103">Удаленная подготовка и вход в Teams для устройств с Android</span><span class="sxs-lookup"><span data-stu-id="06a89-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="06a89-104">ИТ-администраторы могут удаленно подаять и войти в Teams на устройстве с Android.</span><span class="sxs-lookup"><span data-stu-id="06a89-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="06a89-105">Чтобы можно было создавать устройства удаленно, администратор должен отправить их коды MAC и создать код проверки.</span><span class="sxs-lookup"><span data-stu-id="06a89-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="06a89-106">Весь процесс можно завершить удаленно из Центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="06a89-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="06a89-107">Просмотр поддерживаемых устройств</span><span class="sxs-lookup"><span data-stu-id="06a89-107">Review the supported devices</span></span>

<span data-ttu-id="06a89-108">В следующем списке показаны требования к устройству с Android.</span><span class="sxs-lookup"><span data-stu-id="06a89-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="06a89-109">Категория устройства</span><span class="sxs-lookup"><span data-stu-id="06a89-109">Device category</span></span>|<span data-ttu-id="06a89-110">Модель устройства</span><span class="sxs-lookup"><span data-stu-id="06a89-110">Device model</span></span>|<span data-ttu-id="06a89-111">Версия по пошива</span><span class="sxs-lookup"><span data-stu-id="06a89-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="06a89-112">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="06a89-112">Teams phones</span></span>|<span data-ttu-id="06a89-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="06a89-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="06a89-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="06a89-114">58.15.0.124</span></span>|
|<span data-ttu-id="06a89-115">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="06a89-115">Teams phones</span></span>|<span data-ttu-id="06a89-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="06a89-116">Yealink VP59</span></span>|<span data-ttu-id="06a89-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="06a89-117">91.15.0.58</span></span>|
|<span data-ttu-id="06a89-118">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="06a89-118">Teams phones</span></span>|<span data-ttu-id="06a89-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="06a89-119">Yealink CP960</span></span>|<span data-ttu-id="06a89-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="06a89-120">73.15.0.117</span></span>|
|<span data-ttu-id="06a89-121">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="06a89-121">Teams phones</span></span>|<span data-ttu-id="06a89-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="06a89-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="06a89-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="06a89-123">122.15.0.36</span></span>|
|<span data-ttu-id="06a89-124">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="06a89-124">Teams phones</span></span>|<span data-ttu-id="06a89-125">Окаймл UC-2</span><span class="sxs-lookup"><span data-stu-id="06a89-125">Crestron UC-2</span></span>|<span data-ttu-id="06a89-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="06a89-126">1.0.3.52</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="06a89-127">Добавление адреса MAC устройства</span><span class="sxs-lookup"><span data-stu-id="06a89-127">Add a device MAC address</span></span>

<span data-ttu-id="06a89-128">Выполните следующие действия, чтобы подготовка нового устройства.</span><span class="sxs-lookup"><span data-stu-id="06a89-128">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="06a89-129">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="06a89-129">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="06a89-130">"Развернуть **устройства".**</span><span class="sxs-lookup"><span data-stu-id="06a89-130">Expand **Devices**.</span></span>
3. <span data-ttu-id="06a89-131">Выберите **"Подготовка нового устройства" на** вкладке **"Действия".**</span><span class="sxs-lookup"><span data-stu-id="06a89-131">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="06a89-132">В **окне "Подготовка** новых устройств" можно добавить адрес MAC вручную или отправить файл.</span><span class="sxs-lookup"><span data-stu-id="06a89-132">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="06a89-133">Добавление адреса MAC устройства вручную</span><span class="sxs-lookup"><span data-stu-id="06a89-133">Manually add a device MAC address</span></span>

1. <span data-ttu-id="06a89-134">На вкладке **"Ожидание активации"** выберите **"Добавить ИД MAC".**</span><span class="sxs-lookup"><span data-stu-id="06a89-134">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![добавление адреса mac устройства вручную](../media/remote-provision-6.png)

1. <span data-ttu-id="06a89-136">Введите mac ID.</span><span class="sxs-lookup"><span data-stu-id="06a89-136">Enter the MAC ID.</span></span>
1. <span data-ttu-id="06a89-137">Введите расположение, которое помогает техническим специалистам определить, где установить устройства.</span><span class="sxs-lookup"><span data-stu-id="06a89-137">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="06a89-138">Выберите **"Применить** по завершению".</span><span class="sxs-lookup"><span data-stu-id="06a89-138">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="06a89-139">Отправка файла для добавления адреса MAC устройства</span><span class="sxs-lookup"><span data-stu-id="06a89-139">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="06a89-140">На вкладке **"Ожидание активации"** выберите **"Отправить ИД MAC".**</span><span class="sxs-lookup"><span data-stu-id="06a89-140">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="06a89-141">Скачайте шаблон файла.</span><span class="sxs-lookup"><span data-stu-id="06a89-141">Download the file template.</span></span>
3. <span data-ttu-id="06a89-142">Введите ИД MAC и его расположение, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="06a89-142">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="06a89-143">**Выберите файл,** а затем выберите **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="06a89-143">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="06a89-144">Создание проверочных кодов</span><span class="sxs-lookup"><span data-stu-id="06a89-144">Generate a verification code</span></span>

<span data-ttu-id="06a89-145">Вам потребуется провероный код для устройств.</span><span class="sxs-lookup"><span data-stu-id="06a89-145">You need a verification code for the devices.</span></span> <span data-ttu-id="06a89-146">Код проверки создается массово или на уровне устройства и действителен в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="06a89-146">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="06a89-147">На **вкладке "Ожидание активации"** выберите существующий ИД MAC.</span><span class="sxs-lookup"><span data-stu-id="06a89-147">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="06a89-148">Пароль создается для адреса MAC и отображается в столбце **"Код проверки".**</span><span class="sxs-lookup"><span data-stu-id="06a89-148">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="06a89-149">Предоставить список кодов MAC и кодов проверки техническим специалистам по полям.</span><span class="sxs-lookup"><span data-stu-id="06a89-149">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="06a89-150">Вы можете экспортировать информацию непосредственно в файл и поделиться файлом с техническим специалистом, который фактически работает над установкой.</span><span class="sxs-lookup"><span data-stu-id="06a89-150">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="06a89-151">Подготовка устройства</span><span class="sxs-lookup"><span data-stu-id="06a89-151">Provision the device</span></span>

<span data-ttu-id="06a89-152">Когда устройство работает и подключено к сети, технические специалисты его подавют.</span><span class="sxs-lookup"><span data-stu-id="06a89-152">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="06a89-153">Эти действия выполнены на устройстве Teams.</span><span class="sxs-lookup"><span data-stu-id="06a89-153">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="06a89-154">Специалист выбирает устройство **в** **параметрах.**</span><span class="sxs-lookup"><span data-stu-id="06a89-154">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![Параметр "Подготовка нового устройства" на вкладке "Действия"](../media/provision-device1.png)
  
2. <span data-ttu-id="06a89-156">Специалист вводит код проверки для конкретного устройства в предоставленное поле ввода.</span><span class="sxs-lookup"><span data-stu-id="06a89-156">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![Подготовка проверки нового устройства](../media/provision-device-verification1.png)

   <span data-ttu-id="06a89-158">После успешной подготовка устройства на странице регистрации появится имя клиента.</span><span class="sxs-lookup"><span data-stu-id="06a89-158">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![Tenant name on sign-in page](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="06a89-160">Удаленный вход</span><span class="sxs-lookup"><span data-stu-id="06a89-160">Sign in remotely</span></span>

<span data-ttu-id="06a89-161">Это устройство появится на вкладке **"Ожидание".** Начните удаленный вход, выбрав отдельное устройство.</span><span class="sxs-lookup"><span data-stu-id="06a89-161">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="06a89-162">Выберите устройство на вкладке **"Ожидание".**</span><span class="sxs-lookup"><span data-stu-id="06a89-162">Select a device from the **Awaiting sign in** tab.</span></span>

   ![Окно со списком устройств, готовых к входу.](../media/remote-device1.png)

2. <span data-ttu-id="06a89-164">Следуйте инструкциям при входе **пользователя, а** затем выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="06a89-164">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![Окно "Войти в окно пользователя" для отдельного устройства](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="06a89-166">Связанная статья</span><span class="sxs-lookup"><span data-stu-id="06a89-166">Related article</span></span>

- [<span data-ttu-id="06a89-167">Управление устройствами в Teams</span><span class="sxs-lookup"><span data-stu-id="06a89-167">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="06a89-168">Удаленное обновление устройств Teams</span><span class="sxs-lookup"><span data-stu-id="06a89-168">Update Teams devices remotely</span></span>](remote-update.md)
