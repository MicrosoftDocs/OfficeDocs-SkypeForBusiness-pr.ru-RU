---
title: Обновление устройства комнат Microsoft Teams вручную
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Узнайте, как вручную обновить устройство комнат Microsoft Teams до определенной версии.
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117517"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="ca4b3-103">Обновление устройства комнат Microsoft Teams вручную</span><span class="sxs-lookup"><span data-stu-id="ca4b3-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="ca4b3-104">Приложение "Комнаты Microsoft Teams" распространяется по Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="ca4b3-105">Обновления для приложения устанавливаются из Microsoft Store автоматически во время ночного обслуживания; это рекомендуемый способ получения обновлений.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="ca4b3-106">Однако в некоторых случаях устройство с комнатами Teams не может получать обновления из Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="ca4b3-107">Например, политики безопасности могут не позволять устройствам подключаться к Интернету или разрешая скачивание приложений из Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="ca4b3-108">Кроме того, может потребоваться обновить устройство перед выполнением настройки, во время которого магазин Microsoft Store не доступен.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="ca4b3-109">Если вы не можете получить обновления из Microsoft Store, вы можете использовать сценарий powerShell для автономного обновления приложения PowerShell, чтобы вручную обновить устройства комнат Teams до более новой версии приложения "Комнаты Teams".</span><span class="sxs-lookup"><span data-stu-id="ca4b3-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="ca4b3-110">Выполните действия, инструкции из этой статьи, чтобы вручную обновить устройства комнат Teams.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="ca4b3-111">Этот процесс позволяет обновить только устройство комнат Teams с уже установленным приложением "Комнаты Teams".</span><span class="sxs-lookup"><span data-stu-id="ca4b3-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="ca4b3-112">Его нельзя использовать для выполнения новой установки.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="ca4b3-113">Его также нельзя использовать для перенаградить приложение на более старую версию.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="ca4b3-114">Чтобы выполнить новую установку приложения "Комнаты Teams", обратитесь к производителю устройства, чтобы получить только его мультимедиа, или см. в этой ссылке: "Подготовка [установимого носитителя".](console.md#prepare-the-installation-media)</span><span class="sxs-lookup"><span data-stu-id="ca4b3-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="ca4b3-115">Шаг 1. Скачивание сценария обновления автономного приложения</span><span class="sxs-lookup"><span data-stu-id="ca4b3-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="ca4b3-116">Сначала скачайте последнюю версию сценария обновления автономного приложения.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="ca4b3-117">Чтобы скачать сценарий, нажмите <https://go.microsoft.com/fwlink/?linkid=2151817> кнопку .</span><span class="sxs-lookup"><span data-stu-id="ca4b3-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="ca4b3-118">Сценарий будет загружен в папку загрузок по умолчанию на вашем устройстве.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="ca4b3-119">Загруженные файлы могут быть помечены Windows как заблокированные.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="ca4b3-120">Если вам нужно запустить сценарий, не влияя на него, потребуется разблокировать его.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="ca4b3-121">Чтобы разблокировать сценарий, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ca4b3-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="ca4b3-122">Щелкните файл правой кнопкой мыши в проводнике</span><span class="sxs-lookup"><span data-stu-id="ca4b3-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="ca4b3-123">Нажмите **кнопку "Свойства"**</span><span class="sxs-lookup"><span data-stu-id="ca4b3-123">Click **Properties**</span></span>
3. <span data-ttu-id="ca4b3-124">Выберите **"Разблокировать"**</span><span class="sxs-lookup"><span data-stu-id="ca4b3-124">Select **Unblock**</span></span>
4. <span data-ttu-id="ca4b3-125">Нажмите **кнопку "ОК"**</span><span class="sxs-lookup"><span data-stu-id="ca4b3-125">Click **OK**</span></span>

<span data-ttu-id="ca4b3-126">Чтобы разблокировать сценарий с помощью PowerShell, [см. пункт "Разблокировать файл".](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)</span><span class="sxs-lookup"><span data-stu-id="ca4b3-126">To unblock the script using PowerShell, see [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="ca4b3-127">После скачивания сценария автономного обновления приложения передайте файл на устройство комнат Teams.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="ca4b3-128">Вы можете передать файл на устройство с помощью USB-накопителя или доступа к файлу из сетевой папки в режиме администрирования на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="ca4b3-129">Не забудьте учтите, где вы сохраняете файл на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="ca4b3-130">Шаг 2. Запуск сценария для обновления приложения "Комнаты Teams"</span><span class="sxs-lookup"><span data-stu-id="ca4b3-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="ca4b3-131">Сценарий обновления автономного приложения необходимо запускать из командной команды с повышенными уровнями, пока пользователь Skype (пользователь, на котором работает приложение) еще выполняется.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="ca4b3-132">Дополнительные сведения о том, как войти в учетную запись администратора для использования командной подсказки с повышенными уровнями во время входа пользователя Skype, см. в переключении в режим администрирования и обратно при запуске приложения ["Комнаты Microsoft Teams".](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)</span><span class="sxs-lookup"><span data-stu-id="ca4b3-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="ca4b3-133">Чтобы запустить сценарий из командной подсказки с повышенными уровнями, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ca4b3-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="ca4b3-134">Переключение в режим администрирования</span><span class="sxs-lookup"><span data-stu-id="ca4b3-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="ca4b3-135">Щелкните значок "Начните", введите **"Командная подсказка"** и выберите команду **"Запуск от администратора"**</span><span class="sxs-lookup"><span data-stu-id="ca4b3-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="ca4b3-136">Чтобы получить полный путь к сценарию и имя файла сценария, запустите следующую `<path to script>` команду:</span><span class="sxs-lookup"><span data-stu-id="ca4b3-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="ca4b3-137">Например, если файл сценария находится в папке и его имя `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` имеет имя, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ca4b3-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="ca4b3-138">Разрешить запуск сценария.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-138">Allow the script to run.</span></span> <span data-ttu-id="ca4b3-139">Когда все будет готово, сценарий перезагружает устройство комнат Teams.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="ca4b3-140">Сценарий также можно запустить с помощью удаленной powerShell.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="ca4b3-141">Дополнительные сведения об использовании удаленного powerShell с устройствами комнат Teams см. в руководстве по удаленному управлению [с помощью PowerShell.](rooms-operations.md#remote-management-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="ca4b3-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="ca4b3-142">Шаг 3. Проверка успешного обновления приложения</span><span class="sxs-lookup"><span data-stu-id="ca4b3-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="ca4b3-143">Если сценарий выполняется успешно, устройство перезагружается в приложение "Комнаты Teams".</span><span class="sxs-lookup"><span data-stu-id="ca4b3-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="ca4b3-144">Если сценарий столкнется с проблемой, он указывает, в чем заключается проблема в командной строке, и записыв его выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="ca4b3-145">Следуйте инструкциям сценария.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="ca4b3-146">Если вам нужно обратиться в службу поддержки Майкрософт, не забудьте включить файл журнала вместе с запросом на поддержку.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="ca4b3-147">Сценарий предоставит путь к файлу журнала.</span><span class="sxs-lookup"><span data-stu-id="ca4b3-147">The script will provide you with the path to the log file.</span></span>