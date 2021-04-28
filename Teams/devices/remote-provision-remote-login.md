---
title: Удаленная подготовка и вход для устройств с Android в Teams
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
description: Узнайте, как удаленно подготовка и вход в Teams для устройств с Android
ms.openlocfilehash: f39b93a048cee84cf6890d063e272edbef5edb4e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059193"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="c56fa-103">Удаленная подготовка и вход для устройств с Android в Teams</span><span class="sxs-lookup"><span data-stu-id="c56fa-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="c56fa-104">ИТ-администраторы могут удаленно подавка и вход на устройство с Android в Teams.</span><span class="sxs-lookup"><span data-stu-id="c56fa-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="c56fa-105">Чтобы подготовка устройства была удаленной, администратор должен отправить их коды MAC и создать код проверки.</span><span class="sxs-lookup"><span data-stu-id="c56fa-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="c56fa-106">Весь процесс можно завершить удаленно из Центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="c56fa-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="c56fa-107">Просмотр поддерживаемых устройств</span><span class="sxs-lookup"><span data-stu-id="c56fa-107">Review the supported devices</span></span>

<span data-ttu-id="c56fa-108">В следующем списке показаны требования к устройству с Android.</span><span class="sxs-lookup"><span data-stu-id="c56fa-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="c56fa-109">Категория устройств</span><span class="sxs-lookup"><span data-stu-id="c56fa-109">Device category</span></span>|<span data-ttu-id="c56fa-110">Модель устройства</span><span class="sxs-lookup"><span data-stu-id="c56fa-110">Device model</span></span>|<span data-ttu-id="c56fa-111">Версия с программным пошивом</span><span class="sxs-lookup"><span data-stu-id="c56fa-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="c56fa-112">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="c56fa-112">Teams phones</span></span>|<span data-ttu-id="c56fa-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="c56fa-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="c56fa-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="c56fa-114">58.15.0.124</span></span>|
|<span data-ttu-id="c56fa-115">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="c56fa-115">Teams phones</span></span>|<span data-ttu-id="c56fa-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="c56fa-116">Yealink VP59</span></span>|<span data-ttu-id="c56fa-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="c56fa-117">91.15.0.58</span></span>|
|<span data-ttu-id="c56fa-118">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="c56fa-118">Teams phones</span></span>|<span data-ttu-id="c56fa-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="c56fa-119">Yealink CP960</span></span>|<span data-ttu-id="c56fa-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="c56fa-120">73.15.0.117</span></span>|
|<span data-ttu-id="c56fa-121">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="c56fa-121">Teams phones</span></span>|<span data-ttu-id="c56fa-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="c56fa-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="c56fa-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="c56fa-123">122.15.0.36</span></span>|
|<span data-ttu-id="c56fa-124">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="c56fa-124">Teams phones</span></span>|<span data-ttu-id="c56fa-125">Воронова UC-2</span><span class="sxs-lookup"><span data-stu-id="c56fa-125">Crestron UC-2</span></span>|<span data-ttu-id="c56fa-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="c56fa-126">1.0.3.52</span></span>|
|<span data-ttu-id="c56fa-127">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="c56fa-127">Teams phones</span></span>|  <span data-ttu-id="c56fa-128">Poly Trio C60</span><span class="sxs-lookup"><span data-stu-id="c56fa-128">Poly Trio C60</span></span>|  <span data-ttu-id="c56fa-129">7.0.2.1071</span><span class="sxs-lookup"><span data-stu-id="c56fa-129">7.0.2.1071</span></span>|
|<span data-ttu-id="c56fa-130">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="c56fa-130">Teams phones</span></span>|  <span data-ttu-id="c56fa-131">CCX400/CCX500/CCX600</span><span class="sxs-lookup"><span data-stu-id="c56fa-131">CCX400/CCX500/CCX600</span></span>    |<span data-ttu-id="c56fa-132">7.0.2.1072</span><span class="sxs-lookup"><span data-stu-id="c56fa-132">7.0.2.1072</span></span>|
|<span data-ttu-id="c56fa-133">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="c56fa-133">Teams phones</span></span>|  <span data-ttu-id="c56fa-134">Audio Codes C448HD/C450HD/C470HD</span><span class="sxs-lookup"><span data-stu-id="c56fa-134">Audio Codes C448HD/C450HD/C470HD</span></span>|   <span data-ttu-id="c56fa-135">1.10.120</span><span class="sxs-lookup"><span data-stu-id="c56fa-135">1.10.120</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="c56fa-136">Добавление адреса MAC устройства</span><span class="sxs-lookup"><span data-stu-id="c56fa-136">Add a device MAC address</span></span>

<span data-ttu-id="c56fa-137">Выполните следующие действия, чтобы подвести новое устройство.</span><span class="sxs-lookup"><span data-stu-id="c56fa-137">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="c56fa-138">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="c56fa-138">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="c56fa-139">Развернуть **устройства**.</span><span class="sxs-lookup"><span data-stu-id="c56fa-139">Expand **Devices**.</span></span>
3. <span data-ttu-id="c56fa-140">На **вкладке Действия выберите** Подготовка **нового** устройства.</span><span class="sxs-lookup"><span data-stu-id="c56fa-140">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="c56fa-141">В **окне Подготовка новых устройств** можно добавить адрес MAC вручную или отправить файл.</span><span class="sxs-lookup"><span data-stu-id="c56fa-141">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="c56fa-142">Добавление адреса MAC устройства вручную</span><span class="sxs-lookup"><span data-stu-id="c56fa-142">Manually add a device MAC address</span></span>

1. <span data-ttu-id="c56fa-143">На **вкладке Ожидание активации** выберите **Добавить mac ID**.</span><span class="sxs-lookup"><span data-stu-id="c56fa-143">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![добавление адреса mac устройства вручную](../media/remote-provision-6.png)

1. <span data-ttu-id="c56fa-145">Введите mac ID.</span><span class="sxs-lookup"><span data-stu-id="c56fa-145">Enter the MAC ID.</span></span>
1. <span data-ttu-id="c56fa-146">Введите расположение, которое поможет техническим специалистам определить, где установить устройства.</span><span class="sxs-lookup"><span data-stu-id="c56fa-146">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="c56fa-147">По **завершению** выберите Применить.</span><span class="sxs-lookup"><span data-stu-id="c56fa-147">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="c56fa-148">Добавление файла для добавления адреса MAC устройства</span><span class="sxs-lookup"><span data-stu-id="c56fa-148">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="c56fa-149">На **вкладке Ожидание активации** выберите **Отправить mac IDs**.</span><span class="sxs-lookup"><span data-stu-id="c56fa-149">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="c56fa-150">Скачайте шаблон файла.</span><span class="sxs-lookup"><span data-stu-id="c56fa-150">Download the file template.</span></span>
3. <span data-ttu-id="c56fa-151">Введите mac ID и расположение, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="c56fa-151">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="c56fa-152">**Выберите файл** и выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="c56fa-152">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="c56fa-153">Создание проверочных кодов</span><span class="sxs-lookup"><span data-stu-id="c56fa-153">Generate a verification code</span></span>

<span data-ttu-id="c56fa-154">Вам потребуется код проверки для устройств.</span><span class="sxs-lookup"><span data-stu-id="c56fa-154">You need a verification code for the devices.</span></span> <span data-ttu-id="c56fa-155">Код проверки создается массово или на уровне устройства и действителен в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="c56fa-155">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="c56fa-156">На **вкладке Ожидание активации** выберите существующий ИД MAC.</span><span class="sxs-lookup"><span data-stu-id="c56fa-156">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="c56fa-157">Пароль создается для адреса MAC и отображается в столбце **Код проверки.**</span><span class="sxs-lookup"><span data-stu-id="c56fa-157">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="c56fa-158">Предофератирует технических специалистов по полю список кодов MAC и кодов проверки.</span><span class="sxs-lookup"><span data-stu-id="c56fa-158">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="c56fa-159">Вы можете экспортировать подробности непосредственно в файл и поделиться им с техническим специалистом, который фактически работает над установкой.</span><span class="sxs-lookup"><span data-stu-id="c56fa-159">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="c56fa-160">Подготовка устройства</span><span class="sxs-lookup"><span data-stu-id="c56fa-160">Provision the device</span></span>

<span data-ttu-id="c56fa-161">Когда устройство подключено и подключено к сети, специалист под его подготовка.</span><span class="sxs-lookup"><span data-stu-id="c56fa-161">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="c56fa-162">Эти действия будут выполнены на устройстве Teams.</span><span class="sxs-lookup"><span data-stu-id="c56fa-162">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="c56fa-163">Специалист выбирает устройство **подготовка в** **параметрах**.</span><span class="sxs-lookup"><span data-stu-id="c56fa-163">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![Параметр "Подготовка нового устройства" на вкладке "Действия"](../media/provision-device1.png)
  
2. <span data-ttu-id="c56fa-165">Специалист вводит код проверки для конкретного устройства в предоставленное поле ввода.</span><span class="sxs-lookup"><span data-stu-id="c56fa-165">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![Подготовка проверки нового устройства](../media/provision-device-verification1.png)

   <span data-ttu-id="c56fa-167">После успешной подготовка устройства на странице для регистрации появится имя клиента.</span><span class="sxs-lookup"><span data-stu-id="c56fa-167">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![Имя клиента на странице регистрации](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="c56fa-169">Удаленный вход</span><span class="sxs-lookup"><span data-stu-id="c56fa-169">Sign in remotely</span></span>

<span data-ttu-id="c56fa-170">Устройство появится на вкладке **Ожидается** вход. Начните удаленный вход, выбрав отдельное устройство.</span><span class="sxs-lookup"><span data-stu-id="c56fa-170">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="c56fa-171">Выберите устройство на вкладке **Ожидается** вход.</span><span class="sxs-lookup"><span data-stu-id="c56fa-171">Select a device from the **Awaiting sign in** tab.</span></span>

   ![Окно со списком устройств, готовых к входу.](../media/remote-device1.png)

2. <span data-ttu-id="c56fa-173">Следуйте инструкциям в **оке Вход пользователя**, а затем выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c56fa-173">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![Окно "Вход в окно пользователя" для отдельного устройства](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="c56fa-175">Связанная статья</span><span class="sxs-lookup"><span data-stu-id="c56fa-175">Related article</span></span>

- [<span data-ttu-id="c56fa-176">Управление устройствами в Teams</span><span class="sxs-lookup"><span data-stu-id="c56fa-176">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="c56fa-177">Удаленное обновление устройств Teams</span><span class="sxs-lookup"><span data-stu-id="c56fa-177">Update Teams devices remotely</span></span>](remote-update.md)
