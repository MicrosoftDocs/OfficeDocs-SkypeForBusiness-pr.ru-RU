---
title: Настройка консоли комнат Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: В этой статье описано, как настроить консоль microsoft Teams Rooms и ее периферийные устройства.
ms.openlocfilehash: 4caa2677eea01ecc96e426692b536aec8563c473
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117577"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="d8ad3-103">Настройка консоли комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8ad3-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="d8ad3-104">В этой статье описано, как настроить консоль комнат Microsoft Teams и ее периферийные устройства.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="d8ad3-105">Эти действия следует выполнять только в том случае, если необходимые учетные записи Microsoft Teams, Skype для бизнеса и Exchange и Exchange уже созданы и проверены, как описано в описании развертывания [комнат Microsoft Teams.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="d8ad3-106">Вам потребуется оборудование и программное обеспечение, описанные в требованиях [к комнатам Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="d8ad3-107">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="d8ad3-108">Подготовка установного носителю</span><span class="sxs-lookup"><span data-stu-id="d8ad3-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="d8ad3-109">Установка частного сертификата ЦС на консоли</span><span class="sxs-lookup"><span data-stu-id="d8ad3-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="d8ad3-110">Установка Windows 10 и приложения консоли для комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8ad3-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="d8ad3-111">Начальная настройка консоли</span><span class="sxs-lookup"><span data-stu-id="d8ad3-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="d8ad3-112">Контрольный список развертывания комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8ad3-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="d8ad3-113">Комнаты Microsoft Teams будут работать только в правильно настроенной среде Microsoft Teams или Skype для бизнеса, где учетные записи устройств настроены правильно, как описано в описании в развертывании [комнат Microsoft Teams.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="d8ad3-114">Подготовка установного носителю</span><span class="sxs-lookup"><span data-stu-id="d8ad3-114">Prepare the installation media</span></span>
<span data-ttu-id="d8ad3-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ad3-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="d8ad3-116">Для установки консоли Microsoft Teams Rooms требуется USB-накопитель емкостью не менее 32 ГБ.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="d8ad3-117">На устройстве не должно быть других файлов; все существующие файлы в USB-накопителе будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8ad3-118">Непредвиденное поведение при установке мультимедиа в комнатах Microsoft Teams согласно этим инструкциям.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="d8ad3-119">Ниже приведен процесс создания установок мультимедиа для создания образа новых устройств комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="d8ad3-120">Существующие устройства по умолчанию автоматически обновляются из Windows Update и Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8ad3-121">Компьютер с Windows 10, используемый для создания установок Microsoft Teams Rooms, должен быть в той же или более поздней версии Windows, что и целевой установный носитчик.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="d8ad3-122">Скачайте [сценарийCreateSrsMedia.ps1.](https://go.microsoft.com/fwlink/?linkid=867842)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="d8ad3-123">Запустите сценарий CreateSrsMedia.ps1 из командной строки с повышенными привилегиями на компьютере с ОС Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="d8ad3-124">Следуйте инструкциям сценария, чтобы создать USB-диск microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="d8ad3-125">При каждом CreateSrsMedia.ps1 сценария на экране выводит имя файла журнала или запись разговоров для сеанса.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="d8ad3-126">При наличии проблем с запуском сценария убедитесь, что при запросе поддержки доступна копия этого расшифровки.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="d8ad3-127">Сценарий CreateSrsMedia.ps1 автоматизирует следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d8ad3-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="d8ad3-128">Скачайте последнюю версию установщика MSI для комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="d8ad3-129">Определите сборку Windows, которую должен предоставить пользователь.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="d8ad3-130">Последние версии могут не тестироваться и не поддерживаться для использования с устройствами комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="d8ad3-131">Скачайте необходимые вспомогательные компоненты.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="d8ad3-132">Соберите необходимые компоненты на установимом носите.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="d8ad3-133">Необходима определенная версия Windows 10, которая доступна только клиентам корпоративного лицензирования.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="d8ad3-134">Вы можете получить копию из [Volume Licensing Service Center.](https://www.microsoft.com/Licensing/servicecenter/)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="d8ad3-135">По завершению удалите USB-диск с компьютера и переперейти к установке [Windows 10 и приложения](console.md#Reimage)консоли microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="d8ad3-136">Установка Windows 10 и приложения консоли для комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8ad3-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="d8ad3-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ad3-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="d8ad3-138">Теперь нужно применить созданный установ установный носител.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="d8ad3-139">Целевое устройство будет работать как устройство, а по умолчанию будет настроено только на запуск консоли microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="d8ad3-140">Если целевое устройство будет установлено на док-станции (например, Surface Pro), отключите его от док-станции.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="d8ad3-141">Убедитесь, что целевое устройство не подключено к сети.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="d8ad3-142">Убедитесь, что целевое устройство подключено к электроу питания.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="d8ad3-143">Подключите usb-диск к целевому устройству.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="d8ad3-144">Загрузка на установочный диск USB.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="d8ad3-145">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="d8ad3-146">Если целевое устройство — Surface Pro, для загрузки usb-диска используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d8ad3-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="d8ad3-147">а)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-147">a.</span></span> <span data-ttu-id="d8ad3-148">Нажмите и удерживайте кнопку громкости (-).</span><span class="sxs-lookup"><span data-stu-id="d8ad3-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="d8ad3-149">б)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-149">b.</span></span> <span data-ttu-id="d8ad3-150">Нажмите и отпустите кнопку питания.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-150">Press and release the power button.</span></span>

    <span data-ttu-id="d8ad3-151">в.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-151">c.</span></span> <span data-ttu-id="d8ad3-152">После загрузки установки Windows отпустите кнопку уменьшения громкости (–).</span><span class="sxs-lookup"><span data-stu-id="d8ad3-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="d8ad3-153">Система закроется после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="d8ad3-154">После того как система выключится, вы можете удалить usb-накопитель установки.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="d8ad3-155">На этом этапе вы можете разместить целевое устройство на своей док-станции (при использовании док-станции), прикрепить периферийные устройства, необходимые для вашей комнаты собрания, и подключиться к сети.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="d8ad3-156">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="d8ad3-157">Обновления программного обеспечения для комнат Microsoft Teams автоматически загружаются из Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="d8ad3-158">См. [статью "Предварительные](/microsoft-store/prerequisites-microsoft-store-for-business) условия для Microsoft Store для бизнеса и образования", чтобы убедиться в том, что консоль комнаты может получить доступ к магазину и для самостоятельного обновления.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-158">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="d8ad3-159">Выбор языка</span><span class="sxs-lookup"><span data-stu-id="d8ad3-159">Selecting a language</span></span> 

<span data-ttu-id="d8ad3-160">В Обновлении для создателя необходимо использовать сценарий ApplyCurrentRegionAndLanguage.ps1 в сценариях, когда неявный выбор языка не дает пользователю нужного языка приложения (например, он хочет, чтобы приложение консоли было доступно на французском языке, но будет доступно на английском).</span><span class="sxs-lookup"><span data-stu-id="d8ad3-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8ad3-161">Эти инструкции работают только для консолей, созданных с помощью Обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="d8ad3-162">Устаревшие и рыночные системы, которые не были настроены на использование мультимедиа в новой системе предварительной установки, не смогут использовать эти инструкции, но не должны страдать от первоначальной проблемы, которая требует вмешательства вручную (Anniversary Edition позволяет выбрать язык приложения явным образом в рамках настройки).</span><span class="sxs-lookup"><span data-stu-id="d8ad3-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="d8ad3-163">Применение необходимого языка</span><span class="sxs-lookup"><span data-stu-id="d8ad3-163">To apply your desired language</span></span>

1. <span data-ttu-id="d8ad3-164">Переключитесь в режим администрирования.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="d8ad3-165">Откройте меню "Пуск".</span><span class="sxs-lookup"><span data-stu-id="d8ad3-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="d8ad3-166">Щелкните значок шестеренки, чтобы запустить приложение **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="d8ad3-167">Выберите **язык &amp; времени.**</span><span class="sxs-lookup"><span data-stu-id="d8ad3-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="d8ad3-168">Выберите **язык &amp; "Регион".**</span><span class="sxs-lookup"><span data-stu-id="d8ad3-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="d8ad3-169">Выберите **Добавить язык**.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="d8ad3-170">Выберите язык, который требуется добавить.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="d8ad3-171">Выберите язык, который вы только что добавили в список "Языки".</span><span class="sxs-lookup"><span data-stu-id="d8ad3-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="d8ad3-172">Выберите **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="d8ad3-173">Удаление языков</span><span class="sxs-lookup"><span data-stu-id="d8ad3-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="d8ad3-p115">а. Выберите язык, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-p115">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="d8ad3-176">б.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-176">b.</span></span> <span data-ttu-id="d8ad3-177">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-177">Select **Remove**.</span></span>
    
11. <span data-ttu-id="d8ad3-178">Запустите командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="d8ad3-179">Выполните следующую команду. </span><span class="sxs-lookup"><span data-stu-id="d8ad3-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="d8ad3-180">Перезапустите систему.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-180">Restart the system.</span></span>
    
<span data-ttu-id="d8ad3-181">Теперь нужное вам язык будет применено к консоли комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="d8ad3-182">Начальная настройка консоли</span><span class="sxs-lookup"><span data-stu-id="d8ad3-182">Initial set up of the console</span></span>
<span data-ttu-id="d8ad3-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ad3-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="d8ad3-184">После установки Windows консоль приложения "Комнаты Microsoft Teams" начнет перейти в процесс начальной настройки при следующем его начале или при выбранном варианте /reboot.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="d8ad3-185">Появится экран "Учетная запись пользователя".</span><span class="sxs-lookup"><span data-stu-id="d8ad3-185">The User Account screen appears.</span></span> <span data-ttu-id="d8ad3-186">Введите адрес для входа в Skype (user@domain формате) учетной записи комнаты, которая будет использоваться с консолью.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="d8ad3-187">Введите пароль для учетной записи комнаты и подтвердите его.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="d8ad3-188">В области "Настройка домена" установите FQDN для сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="d8ad3-189">Если домен SIP Skype для бизнеса отличается от домена Exchange пользователя, введите в этом поле домен Exchange.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="d8ad3-190">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="d8ad3-191">Выберите указанные устройства на экране "Возможности" и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="d8ad3-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="d8ad3-192">По умолчанию автоматическая демонстрация экрана включена, а скрытие имен во время собрания отключено.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="d8ad3-193">Для выбора доступны следующие устройства:</span><span class="sxs-lookup"><span data-stu-id="d8ad3-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="d8ad3-194">Микрофон для конференций. Микрофон, который используется по умолчанию в этом конференц-зале.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="d8ad3-195">Динамик для конференций. Динамик, который используется по умолчанию для проведения конференций. </span><span class="sxs-lookup"><span data-stu-id="d8ad3-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="d8ad3-196">Динамик по умолчанию. Динамик, который используется для воспроизведения звука со входа HDMI.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="d8ad3-197">Для каждого элемента есть меню параметров, которые можно выбрать.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-197">Each item has a drop-down menu of options to select from.</span></span> <span data-ttu-id="d8ad3-198">Необходимо выбрать его для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-198">You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="d8ad3-199">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-199">Click **Finish**.</span></span>
    
<span data-ttu-id="d8ad3-200">Приложение консоли комнат Microsoft Teams должно немедленно начать вход в Skype для бизнеса Server с учетными данными, которые введены выше, и синхронизировать календарь с Exchange с использованием этих же учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="d8ad3-201">Подробные сведения об использовании приложения консоли можно найти в справке [по комнатам Microsoft Teams.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d8ad3-202">В комнатах Microsoft Teams есть сертифицированное консольное оборудование.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="d8ad3-203">Даже правильно созданное изображение с консолью "Комнаты Microsoft Teams" не будет загрузиться после начальной процедуры настройки, если оборудование консоли не будет обнаружено.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="d8ad3-204">Для решения Surface Pro для проверки необходимо подключение Surface Pro к прилагаемой док-станции.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8ad3-205">Если на сенсорной клавиатуре не поддерживаются символы, некоторым пользователям на других языках может потребоваться физическая клавиатура, подключенная к консоли.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="d8ad3-206">Установка частного сертификата ЦС на консоли</span><span class="sxs-lookup"><span data-stu-id="d8ad3-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="d8ad3-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ad3-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="d8ad3-208">Консоли комнат Microsoft Teams необходимо доверять сертификатам, используемым серверами, к которые она подключается.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="d8ad3-209">Для O365 это происходит автоматически, так как эти серверы используют общедоступные органы сертификации, и Windows 10 автоматически доверяет их.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="d8ad3-210">Если сертификат является частным, например при локальном развертывании с Active Directory и сертификатом Windows, вы можете добавить сертификат на консоль комнат Microsoft Teams несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="d8ad3-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="d8ad3-211">Вы можете присоединиться к консоли в Active Directory, и она автоматически добавит необходимые сертификаты с учетом публикации центра сертификации в Active Directory (обычный вариант развертывания).</span><span class="sxs-lookup"><span data-stu-id="d8ad3-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="d8ad3-212">После обработки изображений сертификат можно установить вручную.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="d8ad3-213">Прежде чем это сделать, необходимо завершить начальное [настройка консоли.](console.md#Initial)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="d8ad3-214">Установка сертификата вручную</span><span class="sxs-lookup"><span data-stu-id="d8ad3-214">To manually install the certificate</span></span>

1. <span data-ttu-id="d8ad3-215">Скачайте сертификат ЦС на компьютер и сохраните его в "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="d8ad3-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="d8ad3-216">Поместите консоль в режим администрирования (см. [режим администрирования и управление устройствами).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="d8ad3-217">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="d8ad3-218">Присоединиться к домену Active Directory (необязательно)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="d8ad3-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ad3-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="d8ad3-220">Вы можете присоединиться к консолям комнат Microsoft Teams в вашем домене.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="d8ad3-221">Консоли комнат Microsoft Teams следует размещать в отдельном обл. и на рабочих станциях компьютера, так как многие политики рабочих станции несовместимы с комнатами Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="d8ad3-222">Распространенным примером являются политики обеспечения паролей, которые предотвращают автоматический запуск комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="d8ad3-223">Сведения об управлении настройками GPO можно найти в сведениях об управлении комнатами [Microsoft Teams.](rooms-operations.md)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="d8ad3-224">Чтобы присоединиться к комнатам Microsoft Teams в домене</span><span class="sxs-lookup"><span data-stu-id="d8ad3-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="d8ad3-225">Во войти в консоль можно из учетной записи администратора (см. [режим администрирования и управление устройствами).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="d8ad3-226">Запустите командную подсказку Powershell с повышенными уровнями.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="d8ad3-227">Введите следующую команду в Powershell:</span><span class="sxs-lookup"><span data-stu-id="d8ad3-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="d8ad3-228">Например, если ваш полное доменное имя redmond.corp.microsoft.com и вы хотите, чтобы консоли комнат Microsoft Teams были в "комнатах Microsoft Teams", который является частью "ресурсов" OU, будет реализована команда:</span><span class="sxs-lookup"><span data-stu-id="d8ad3-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="d8ad3-229">Если вы хотите переименовать компьютер при присоединении к домену, используйте флаг -NewName и новое имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="d8ad3-230">Контрольный список развертывания комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8ad3-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="d8ad3-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ad3-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="d8ad3-232">При окончательной проверке полной настройки консоли и всех ее периферийных устройств используйте следующий контрольный список:</span><span class="sxs-lookup"><span data-stu-id="d8ad3-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="d8ad3-233">**Параметры приложения**</span><span class="sxs-lookup"><span data-stu-id="d8ad3-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d8ad3-234">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-234">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-235">Имя учетной записи комнаты и номер телефона (если она включена) правильно отображаются в правом верхнем верхнем экране консоли</span><span class="sxs-lookup"><span data-stu-id="d8ad3-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="d8ad3-236">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-236">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-237">Имя компьютера с Windows настроено правильно (полезно для удаленного администрирования)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="d8ad3-238">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-238">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-239">Настройка и проверка пароля для учетной записи администратора</span><span class="sxs-lookup"><span data-stu-id="d8ad3-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="d8ad3-240">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-240">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-241">Все обновления программного обеспечения были применены</span><span class="sxs-lookup"><span data-stu-id="d8ad3-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="d8ad3-242">**Периферийные устройства для звука и видео**</span><span class="sxs-lookup"><span data-stu-id="d8ad3-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d8ad3-243">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-243">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-244">Версия периферийного ПО для камеры правильная (если применимо)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="d8ad3-245">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-245">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-246">Оптимальный функциональный и оптимальный расположение камеры</span><span class="sxs-lookup"><span data-stu-id="d8ad3-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="d8ad3-247">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-247">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-248">Параметры устройства воспроизведения по умолчанию и устройства связи воспроизведения по умолчанию настроены на предполагаемую периферийную ось звука</span><span class="sxs-lookup"><span data-stu-id="d8ad3-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="d8ad3-249">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-249">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-250">Параметры для записи устройства связи по умолчанию, установленного на предполагаемую периферийную устройства</span><span class="sxs-lookup"><span data-stu-id="d8ad3-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="d8ad3-251">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-251">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-252">Правильная версия звукового периферийного ПО (если применимо)</span><span class="sxs-lookup"><span data-stu-id="d8ad3-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="d8ad3-253">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-253">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-254">Звуковое устройство работает и находится в оптимальном положении</span><span class="sxs-lookup"><span data-stu-id="d8ad3-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="d8ad3-255">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-255">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-256">Звуковое устройство работает и находится в оптимальном положении</span><span class="sxs-lookup"><span data-stu-id="d8ad3-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="d8ad3-257">**Dock**</span><span class="sxs-lookup"><span data-stu-id="d8ad3-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d8ad3-258">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-258">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-259">Кабели безопасны и не сжимаются</span><span class="sxs-lookup"><span data-stu-id="d8ad3-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="d8ad3-260">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-260">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-261">Audio ingest over HDMI is functional</span><span class="sxs-lookup"><span data-stu-id="d8ad3-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="d8ad3-262">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-262">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-263">Работает видео при наихыве на HDMI</span><span class="sxs-lookup"><span data-stu-id="d8ad3-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="d8ad3-264">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-264">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-265">Закрепление может свободно протасковываться</span><span class="sxs-lookup"><span data-stu-id="d8ad3-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="d8ad3-266">☐</span><span class="sxs-lookup"><span data-stu-id="d8ad3-266">☐</span></span>  <br/> |<span data-ttu-id="d8ad3-267">Яркость дисплея приемлема для среды</span><span class="sxs-lookup"><span data-stu-id="d8ad3-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d8ad3-268">См. также</span><span class="sxs-lookup"><span data-stu-id="d8ad3-268">See also</span></span>
<span data-ttu-id="d8ad3-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ad3-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="d8ad3-270">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8ad3-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="d8ad3-271">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8ad3-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="d8ad3-272">Настройка консоли комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8ad3-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="d8ad3-273">Управление комнатами Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8ad3-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)