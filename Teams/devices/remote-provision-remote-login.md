---
title: Удаленная подготовка и вход для Teams устройств с Android
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
description: Узнайте, как дистанционно подавь и войти в Teams устройствах с Android
ms.openlocfilehash: f39b93a048cee84cf6890d063e272edbef5edb4e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059193"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="5fd4c-103">Удаленная подготовка и вход для Teams устройств с Android</span><span class="sxs-lookup"><span data-stu-id="5fd4c-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="5fd4c-104">ИТ-администраторы могут удаленно подавлю и войти на устройство Teams Android.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="5fd4c-105">Чтобы подготовка устройства была удаленной, администратор должен отправить их коды MAC и создать код проверки.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="5fd4c-106">Весь процесс можно завершить удаленно из центра Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="5fd4c-107">Просмотр поддерживаемых устройств</span><span class="sxs-lookup"><span data-stu-id="5fd4c-107">Review the supported devices</span></span>

<span data-ttu-id="5fd4c-108">В следующем списке показаны требования к устройству с Android.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="5fd4c-109">Категория устройств</span><span class="sxs-lookup"><span data-stu-id="5fd4c-109">Device category</span></span>|<span data-ttu-id="5fd4c-110">Модель устройства</span><span class="sxs-lookup"><span data-stu-id="5fd4c-110">Device model</span></span>|<span data-ttu-id="5fd4c-111">Версия с программным пошивом</span><span class="sxs-lookup"><span data-stu-id="5fd4c-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="5fd4c-112">Teams телефонов</span><span class="sxs-lookup"><span data-stu-id="5fd4c-112">Teams phones</span></span>|<span data-ttu-id="5fd4c-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="5fd4c-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="5fd4c-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="5fd4c-114">58.15.0.124</span></span>|
|<span data-ttu-id="5fd4c-115">Teams телефонов</span><span class="sxs-lookup"><span data-stu-id="5fd4c-115">Teams phones</span></span>|<span data-ttu-id="5fd4c-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="5fd4c-116">Yealink VP59</span></span>|<span data-ttu-id="5fd4c-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="5fd4c-117">91.15.0.58</span></span>|
|<span data-ttu-id="5fd4c-118">Teams телефонов</span><span class="sxs-lookup"><span data-stu-id="5fd4c-118">Teams phones</span></span>|<span data-ttu-id="5fd4c-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="5fd4c-119">Yealink CP960</span></span>|<span data-ttu-id="5fd4c-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="5fd4c-120">73.15.0.117</span></span>|
|<span data-ttu-id="5fd4c-121">Teams телефонов</span><span class="sxs-lookup"><span data-stu-id="5fd4c-121">Teams phones</span></span>|<span data-ttu-id="5fd4c-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="5fd4c-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="5fd4c-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="5fd4c-123">122.15.0.36</span></span>|
|<span data-ttu-id="5fd4c-124">Teams телефонов</span><span class="sxs-lookup"><span data-stu-id="5fd4c-124">Teams phones</span></span>|<span data-ttu-id="5fd4c-125">Воронова UC-2</span><span class="sxs-lookup"><span data-stu-id="5fd4c-125">Crestron UC-2</span></span>|<span data-ttu-id="5fd4c-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="5fd4c-126">1.0.3.52</span></span>|
|<span data-ttu-id="5fd4c-127">Teams телефонов</span><span class="sxs-lookup"><span data-stu-id="5fd4c-127">Teams phones</span></span>|  <span data-ttu-id="5fd4c-128">Poly Trio C60</span><span class="sxs-lookup"><span data-stu-id="5fd4c-128">Poly Trio C60</span></span>|  <span data-ttu-id="5fd4c-129">7.0.2.1071</span><span class="sxs-lookup"><span data-stu-id="5fd4c-129">7.0.2.1071</span></span>|
|<span data-ttu-id="5fd4c-130">Teams телефонов</span><span class="sxs-lookup"><span data-stu-id="5fd4c-130">Teams phones</span></span>|  <span data-ttu-id="5fd4c-131">CCX400/CCX500/CCX600</span><span class="sxs-lookup"><span data-stu-id="5fd4c-131">CCX400/CCX500/CCX600</span></span>    |<span data-ttu-id="5fd4c-132">7.0.2.1072</span><span class="sxs-lookup"><span data-stu-id="5fd4c-132">7.0.2.1072</span></span>|
|<span data-ttu-id="5fd4c-133">Teams телефонов</span><span class="sxs-lookup"><span data-stu-id="5fd4c-133">Teams phones</span></span>|  <span data-ttu-id="5fd4c-134">Audio Codes C448HD/C450HD/C470HD</span><span class="sxs-lookup"><span data-stu-id="5fd4c-134">Audio Codes C448HD/C450HD/C470HD</span></span>|   <span data-ttu-id="5fd4c-135">1.10.120</span><span class="sxs-lookup"><span data-stu-id="5fd4c-135">1.10.120</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="5fd4c-136">Добавление адреса MAC устройства</span><span class="sxs-lookup"><span data-stu-id="5fd4c-136">Add a device MAC address</span></span>

<span data-ttu-id="5fd4c-137">Выполните следующие действия, чтобы подвести новое устройство.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-137">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="5fd4c-138">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-138">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="5fd4c-139">Развернуть **устройства**.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-139">Expand **Devices**.</span></span>
3. <span data-ttu-id="5fd4c-140">На **вкладке Действия выберите** Подготовка **нового** устройства.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-140">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="5fd4c-141">В **окне Подготовка новых устройств** можно добавить адрес MAC вручную или отправить файл.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-141">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="5fd4c-142">Добавление адреса MAC устройства вручную</span><span class="sxs-lookup"><span data-stu-id="5fd4c-142">Manually add a device MAC address</span></span>

1. <span data-ttu-id="5fd4c-143">На **вкладке Ожидание активации** выберите **Добавить mac ID**.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-143">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![добавление адреса mac устройства вручную](../media/remote-provision-6.png)

1. <span data-ttu-id="5fd4c-145">Введите mac ID.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-145">Enter the MAC ID.</span></span>
1. <span data-ttu-id="5fd4c-146">Введите расположение, которое поможет техническим специалистам определить, где установить устройства.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-146">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="5fd4c-147">По **завершению** выберите Применить.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-147">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="5fd4c-148">Upload файл, чтобы добавить адрес mac устройства</span><span class="sxs-lookup"><span data-stu-id="5fd4c-148">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="5fd4c-149">На **вкладке Ожидание активации** выберите Upload **mac IDs**.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-149">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="5fd4c-150">Скачайте шаблон файла.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-150">Download the file template.</span></span>
3. <span data-ttu-id="5fd4c-151">Введите mac ID и расположение, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-151">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="5fd4c-152">**Выберите файл**, а затем **выберите** Upload .</span><span class="sxs-lookup"><span data-stu-id="5fd4c-152">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="5fd4c-153">Создание проверочных кодов</span><span class="sxs-lookup"><span data-stu-id="5fd4c-153">Generate a verification code</span></span>

<span data-ttu-id="5fd4c-154">Вам потребуется код проверки для устройств.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-154">You need a verification code for the devices.</span></span> <span data-ttu-id="5fd4c-155">Код проверки создается массово или на уровне устройства и действителен в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-155">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="5fd4c-156">На **вкладке Ожидание активации** выберите существующий ИД MAC.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-156">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="5fd4c-157">Пароль создается для адреса MAC и отображается в столбце **Код проверки.**</span><span class="sxs-lookup"><span data-stu-id="5fd4c-157">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="5fd4c-158">Предофератирует технических специалистов по полю список кодов MAC и кодов проверки.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-158">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="5fd4c-159">Вы можете экспортировать подробности непосредственно в файл и поделиться им с техническим специалистом, который фактически работает над установкой.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-159">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="5fd4c-160">Подготовка устройства</span><span class="sxs-lookup"><span data-stu-id="5fd4c-160">Provision the device</span></span>

<span data-ttu-id="5fd4c-161">Когда устройство подключено и подключено к сети, специалист под его подготовка.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-161">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="5fd4c-162">Эти действия будут выполнены на Teams устройстве.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-162">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="5fd4c-163">Специалист выбирает устройство **подготовка** в **Параметры.**</span><span class="sxs-lookup"><span data-stu-id="5fd4c-163">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![Параметр "Подготовка нового устройства" на вкладке "Действия"](../media/provision-device1.png)
  
2. <span data-ttu-id="5fd4c-165">Специалист вводит код проверки для конкретного устройства в предоставленное поле ввода.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-165">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![Подготовка новой проверки устройства](../media/provision-device-verification1.png)

   <span data-ttu-id="5fd4c-167">После успешной подготовка устройства на странице для регистрации появится имя клиента.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-167">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![Имя клиента на странице регистрации](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="5fd4c-169">Удаленный вход</span><span class="sxs-lookup"><span data-stu-id="5fd4c-169">Sign in remotely</span></span>

<span data-ttu-id="5fd4c-170">Устройство появится на вкладке **Ожидается** вход. Начните удаленный вход, выбрав отдельное устройство.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-170">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="5fd4c-171">Выберите устройство на вкладке **Ожидается** вход.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-171">Select a device from the **Awaiting sign in** tab.</span></span>

   ![Окно со списком устройств, готовых к входу.](../media/remote-device1.png)

2. <span data-ttu-id="5fd4c-173">Следуйте инструкциям в **оке Вход пользователя**, а затем выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="5fd4c-173">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![Окно "Вход в окно пользователя" для отдельного устройства](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="5fd4c-175">Связанная статья</span><span class="sxs-lookup"><span data-stu-id="5fd4c-175">Related article</span></span>

- [<span data-ttu-id="5fd4c-176">Управление устройствами в Teams</span><span class="sxs-lookup"><span data-stu-id="5fd4c-176">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="5fd4c-177">Удаленное обновление Teams устройств</span><span class="sxs-lookup"><span data-stu-id="5fd4c-177">Update Teams devices remotely</span></span>](remote-update.md)
