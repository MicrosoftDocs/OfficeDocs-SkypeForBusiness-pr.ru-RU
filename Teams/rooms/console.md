---
title: Настройка консоли Microsoft Teams
ms.author: v-lanac
author: lanachin
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
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: В этой статье описано, как настроить консоль Microsoft Teams и ее периферийные устройства.
ms.openlocfilehash: c91c570cd83cc07f1f15823623f2b02a2ebcddf4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826097"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="ca11a-103">Настройка консоли Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca11a-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="ca11a-104">В этой статье описано, как настроить консоль Microsoft Teams и ее периферийные устройства.</span><span class="sxs-lookup"><span data-stu-id="ca11a-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="ca11a-105">Эти действия необходимо выполнить, только если на компьютере уже созданы и протестированы учетные записи Microsoft Teams и Skype для бизнеса и Exchange, описанные в разделе [развертывание комнат Microsoft Teams](rooms-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="ca11a-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="ca11a-106">Вам потребуются оборудование и программное обеспечение, описанные в [требованиях к комнатам Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca11a-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="ca11a-107">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="ca11a-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="ca11a-108">Подготовка установочного носителя</span><span class="sxs-lookup"><span data-stu-id="ca11a-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="ca11a-109">Установка закрытого сертификата ЦС на консоли</span><span class="sxs-lookup"><span data-stu-id="ca11a-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="ca11a-110">Установка Windows 10 и консольного приложения комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca11a-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="ca11a-111">Начальная настройка консоли</span><span class="sxs-lookup"><span data-stu-id="ca11a-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="ca11a-112">Контрольный список для развертывания комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca11a-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="ca11a-113">Комнаты Microsoft Teams будут работать только в правильно настроенной среде Microsoft Teams или Skype для бизнеса, в которой учетные записи устройств настроены правильно, как описано в разделе [развертывание комнат Microsoft Teams](rooms-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="ca11a-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="ca11a-114">Подготовка установочного носителя</span><span class="sxs-lookup"><span data-stu-id="ca11a-114">Prepare the installation media</span></span>
<span data-ttu-id="ca11a-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="ca11a-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="ca11a-116">Для установки консольного приложения "комнаты Microsoft Teams" требуется USB-устройство хранения данных с емкостью не менее 32 ГБ.</span><span class="sxs-lookup"><span data-stu-id="ca11a-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="ca11a-117">На устройстве не должно быть других файлов; все существующие файлы в хранилище USB будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="ca11a-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca11a-118">Не удается создать установочный носитель Microsoft Teams в помещениях в соответствии с приведенными ниже инструкциями, что может привести к неожиданному поведению.</span><span class="sxs-lookup"><span data-stu-id="ca11a-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="ca11a-119">Ниже описана процедура создания установочного носителя для новых устройств с помощью Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca11a-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="ca11a-120">Существующие устройства по умолчанию обновляются автоматически с помощью центра обновления Windows и магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="ca11a-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca11a-121">Компьютер с Windows 10, который использовался для создания установочного носителя Microsoft Teams, должен находиться в той же или более поздней версии Windows, что и целевой установочный носитель.</span><span class="sxs-lookup"><span data-stu-id="ca11a-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="ca11a-122">Скачайте [сценарий креатесрсмедиа. ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="ca11a-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="ca11a-123">Запустите сценарий CreateSrsMedia.ps1 из командной строки с повышенными привилегиями на компьютере с ОС Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ca11a-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="ca11a-124">Следуйте инструкциям по созданию сценария для создания установочного диска USB на устройстве Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca11a-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="ca11a-125">Каждый раз, когда запускается сценарий Креатесрсмедиа. ps1, выводимый на экран текст будет включать в себя имя файла журнала или транскрипции для сеанса.</span><span class="sxs-lookup"><span data-stu-id="ca11a-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="ca11a-126">Если у вас возникли проблемы с запуском сценария, убедитесь, что у вас есть копия этой записи, которая доступна при запросе поддержки.</span><span class="sxs-lookup"><span data-stu-id="ca11a-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="ca11a-127">В сценарии Креатесрсмедиа. ps1 автоматизируются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="ca11a-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="ca11a-128">Скачайте последнюю версию MSI-установщика для комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca11a-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="ca11a-129">Определите, какая сборка Windows должна быть предоставлена пользователю.</span><span class="sxs-lookup"><span data-stu-id="ca11a-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="ca11a-130">Последние версии могут быть не протестированы и не поддерживаются для использования с устройствами в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca11a-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="ca11a-131">Загрузите необходимые вспомогательные компоненты.</span><span class="sxs-lookup"><span data-stu-id="ca11a-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="ca11a-132">Соберите необходимые компоненты на установочном носителе.</span><span class="sxs-lookup"><span data-stu-id="ca11a-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="ca11a-133">Требуется определенная версия Windows 10, а эта версия доступна только пользователям с корпоративной лицензией.</span><span class="sxs-lookup"><span data-stu-id="ca11a-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="ca11a-134">Вы можете получить копию в [центре обслуживания для корпоративного лицензирования](https://www.microsoft.com/Licensing/servicecenter/).</span><span class="sxs-lookup"><span data-stu-id="ca11a-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="ca11a-135">После этого выньте USB-диск с компьютера и продолжайте [устанавливать Windows 10 и консольное приложение комнат Microsoft Teams](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="ca11a-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="ca11a-136">Установка Windows 10 и консольного приложения комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca11a-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="ca11a-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="ca11a-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="ca11a-138">Теперь необходимо применить созданный установочный носитель.</span><span class="sxs-lookup"><span data-stu-id="ca11a-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="ca11a-139">Целевое устройство будет запущено как управляющее устройство, и для него по умолчанию будет выполняться только консольное приложение комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca11a-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="ca11a-140">Если целевое устройство будет установлено на Dock (например, Surface Pro), отключите его от Dock.</span><span class="sxs-lookup"><span data-stu-id="ca11a-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="ca11a-141">Убедитесь, что оконечное устройство не подключено к сети.</span><span class="sxs-lookup"><span data-stu-id="ca11a-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="ca11a-142">Убедитесь, что оконечное устройство подключено к сети переменного тока.</span><span class="sxs-lookup"><span data-stu-id="ca11a-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="ca11a-143">Подключите установочный диск USB к целевому устройству.</span><span class="sxs-lookup"><span data-stu-id="ca11a-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="ca11a-144">Загрузитесь с установочного диска USB.</span><span class="sxs-lookup"><span data-stu-id="ca11a-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="ca11a-145">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="ca11a-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="ca11a-146">Если оконечное устройство является Pro Surface, выполните указанные ниже действия, чтобы загрузить установочный диск USB.</span><span class="sxs-lookup"><span data-stu-id="ca11a-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="ca11a-147">a)</span><span class="sxs-lookup"><span data-stu-id="ca11a-147">a.</span></span> <span data-ttu-id="ca11a-148">Нажмите и продолжайте удерживать нажатой кнопку "Громкость" (-).</span><span class="sxs-lookup"><span data-stu-id="ca11a-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="ca11a-149">б)</span><span class="sxs-lookup"><span data-stu-id="ca11a-149">b.</span></span> <span data-ttu-id="ca11a-150">Нажмите и отпустите кнопку Power.</span><span class="sxs-lookup"><span data-stu-id="ca11a-150">Press and release the power button.</span></span>

    <span data-ttu-id="ca11a-151">в.</span><span class="sxs-lookup"><span data-stu-id="ca11a-151">c.</span></span> <span data-ttu-id="ca11a-152">После загрузки установки Windows отпустите кнопку уменьшения громкости (–).</span><span class="sxs-lookup"><span data-stu-id="ca11a-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="ca11a-153">Система завершит работу после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="ca11a-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="ca11a-154">После того как система завершит работу, вы можете удалить установочный диск USB.</span><span class="sxs-lookup"><span data-stu-id="ca11a-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="ca11a-155">На этом этапе вы можете поместить целевое устройство в Dock (если используется стыковочный продукт), подключить периферийные устройства, необходимые для помещения в собрание, и подключиться к сети.</span><span class="sxs-lookup"><span data-stu-id="ca11a-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="ca11a-156">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="ca11a-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="ca11a-157">Обновления программного обеспечения для комнат Microsoft Teams автоматически загружаются из Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ca11a-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="ca11a-158">Ознакомьтесь с [требованиями для Microsoft Store для бизнеса и образовательных учреждений](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) , чтобы убедиться в том, что консоль комнаты сможет получить доступ к магазину и ее обновлению самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="ca11a-158">See [Prerequisites for Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="ca11a-159">Выбор языка</span><span class="sxs-lookup"><span data-stu-id="ca11a-159">Selecting a language</span></span> 

<span data-ttu-id="ca11a-160">В обновлении создателя вам потребуется использовать сценарий Аппликуррентрегионандлангуаже. ps1 в сценариях, где неявный выбор языка не дает пользователю фактического языка приложения (например, нужно, чтобы приложение консоли выводилось на французском языке), но она будет на английском языке).</span><span class="sxs-lookup"><span data-stu-id="ca11a-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca11a-161">Приведенные ниже инструкции применимы только для консолей, созданных с помощью центра обновления Windows Creator.</span><span class="sxs-lookup"><span data-stu-id="ca11a-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="ca11a-162">Устаревшие и печатные системы, которые не настроены на использование мультимедиа с помощью новой системы подготовки, не смогут использовать эти инструкции, но должны также отличаться от первоначальной проблемы, для которой требуется ручное вмешательство (годовщина работы с приложением в процессе настройки).</span><span class="sxs-lookup"><span data-stu-id="ca11a-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="ca11a-163">Применение необходимого языка</span><span class="sxs-lookup"><span data-stu-id="ca11a-163">To apply your desired language</span></span>

1. <span data-ttu-id="ca11a-164">Переключитесь в режим администрирования.</span><span class="sxs-lookup"><span data-stu-id="ca11a-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="ca11a-165">Откройте меню "Пуск".</span><span class="sxs-lookup"><span data-stu-id="ca11a-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="ca11a-166">Щелкните значок шестеренки, чтобы запустить приложение **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="ca11a-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="ca11a-167">Выберите **язык &amp; времени**.</span><span class="sxs-lookup"><span data-stu-id="ca11a-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="ca11a-168">Выберите **язык &amp; региона**.</span><span class="sxs-lookup"><span data-stu-id="ca11a-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="ca11a-169">Выберите **Добавить язык**.</span><span class="sxs-lookup"><span data-stu-id="ca11a-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="ca11a-170">Выберите язык, который требуется добавить.</span><span class="sxs-lookup"><span data-stu-id="ca11a-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="ca11a-171">Выберите язык, который вы только что добавили в список "языки".</span><span class="sxs-lookup"><span data-stu-id="ca11a-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="ca11a-172">Выберите **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="ca11a-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="ca11a-173">Удаление языков</span><span class="sxs-lookup"><span data-stu-id="ca11a-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="ca11a-p115">а. Выберите язык, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="ca11a-p115">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="ca11a-176">б.</span><span class="sxs-lookup"><span data-stu-id="ca11a-176">b.</span></span> <span data-ttu-id="ca11a-177">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ca11a-177">Select **Remove**.</span></span>
    
11. <span data-ttu-id="ca11a-178">Запустите командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="ca11a-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="ca11a-179">Выполните следующую команду. </span><span class="sxs-lookup"><span data-stu-id="ca11a-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="ca11a-180">Перезапустите систему.</span><span class="sxs-lookup"><span data-stu-id="ca11a-180">Restart the system.</span></span>
    
<span data-ttu-id="ca11a-181">Выбранный язык теперь применен к консоли Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca11a-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="ca11a-182">Начальная настройка консоли</span><span class="sxs-lookup"><span data-stu-id="ca11a-182">Initial set up of the console</span></span>
<span data-ttu-id="ca11a-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="ca11a-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="ca11a-184">После установки Windows консольное приложение Microsoft Teams будет переведено в первоначальный процесс настройки при следующем запуске или если выбран параметр/ребут.</span><span class="sxs-lookup"><span data-stu-id="ca11a-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="ca11a-185">Появится экран "Учетная запись пользователя".</span><span class="sxs-lookup"><span data-stu-id="ca11a-185">The User Account screen appears.</span></span> <span data-ttu-id="ca11a-186">Введите адрес для входа в Skype (в user@domain формате) для учетной записи комнаты, которая будет использоваться на консоли.</span><span class="sxs-lookup"><span data-stu-id="ca11a-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="ca11a-187">Введите пароль для учетной записи комнаты и подтвердите его.</span><span class="sxs-lookup"><span data-stu-id="ca11a-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="ca11a-188">В разделе "Настройка домена" Задайте полное доменное имя сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ca11a-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="ca11a-189">Если домен SIP Skype для бизнеса не отличается от домена Exchange пользователя, введите в это поле Домен Exchange.</span><span class="sxs-lookup"><span data-stu-id="ca11a-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="ca11a-190">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ca11a-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="ca11a-191">На экране "возможности" выберите указанные устройства и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ca11a-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="ca11a-192">По умолчанию автоматическая демонстрация экрана включена, а скрытие имен во время собрания отключено.</span><span class="sxs-lookup"><span data-stu-id="ca11a-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="ca11a-193">Для выбора доступны следующие устройства:</span><span class="sxs-lookup"><span data-stu-id="ca11a-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="ca11a-194">Микрофон для конференций. Микрофон, который используется по умолчанию в этом конференц-зале.</span><span class="sxs-lookup"><span data-stu-id="ca11a-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="ca11a-195">Динамик для конференций. Динамик, который используется по умолчанию для проведения конференций. </span><span class="sxs-lookup"><span data-stu-id="ca11a-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="ca11a-196">Динамик по умолчанию. Динамик, который используется для воспроизведения звука со входа HDMI.</span><span class="sxs-lookup"><span data-stu-id="ca11a-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="ca11a-197">У каждого элемента есть раскрывающееся меню с параметрами выбора.</span><span class="sxs-lookup"><span data-stu-id="ca11a-197">Each item has a drop-down menu of options to select from.</span></span> <span data-ttu-id="ca11a-198">Для каждого устройства необходимо выбрать один из вариантов.</span><span class="sxs-lookup"><span data-stu-id="ca11a-198">You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="ca11a-199">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ca11a-199">Click **Finish**.</span></span>
    
<span data-ttu-id="ca11a-200">Консольное приложение Microsoft Teams может сразу же приступить к входу в Skype для бизнеса Server с помощью указанных выше учетных данных, а также начинать синхронизацию своего календаря с Exchange с использованием тех же учетных данных.</span><span class="sxs-lookup"><span data-stu-id="ca11a-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="ca11a-201">Подробнее об использовании консольного приложения можно найти в справке по [комнатам Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="ca11a-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ca11a-202">Комнаты Microsoft Teams основываются на присутствии сертифицированного оборудования консоли.</span><span class="sxs-lookup"><span data-stu-id="ca11a-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="ca11a-203">Даже правильно созданное изображение, содержащее консольных комнат Microsoft Teams, не загрузится после начальной процедуры установки, если не будет обнаружено оборудование консоли.</span><span class="sxs-lookup"><span data-stu-id="ca11a-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="ca11a-204">Для решений на базе Surface Pro Surface Pro должны быть подключены к соответствующему оборудованию Dock для прохождения этой проверки.</span><span class="sxs-lookup"><span data-stu-id="ca11a-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca11a-205">Для некоторых пользователей, не являющихся английским языком, во время начальной настройки может потребоваться физическая клавиатура, подключенная к консоли, в том случае, если символы не поддерживаются сенсорной клавиатурой.</span><span class="sxs-lookup"><span data-stu-id="ca11a-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="ca11a-206">Установка закрытого сертификата ЦС на консоли</span><span class="sxs-lookup"><span data-stu-id="ca11a-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="ca11a-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="ca11a-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="ca11a-208">Консоли Microsoft Teams необходимо доверять сертификатам, используемым серверами, к которым он подключен.</span><span class="sxs-lookup"><span data-stu-id="ca11a-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="ca11a-209">Для O365 это выполняется автоматически, так как на этих серверах используются общедоступные центры сертификации, и они автоматически доверяются Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ca11a-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="ca11a-210">В случае, если центр сертификации является частным, для локального развертывания с помощью службы каталогов Active Directory и центра сертификации Windows вы можете добавить сертификат в консоль Microsoft Teams в несколько способов.</span><span class="sxs-lookup"><span data-stu-id="ca11a-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="ca11a-211">Вы можете присоединиться к консоли в Active Directory и автоматически добавить требуемые сертификаты, предоставленные центром сертификации, опубликованные в Active Directory (параметр развертывания в обычном режиме).</span><span class="sxs-lookup"><span data-stu-id="ca11a-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="ca11a-212">Вы можете установить сертификат вручную после процесса обработки изображений.</span><span class="sxs-lookup"><span data-stu-id="ca11a-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="ca11a-213">Перед тем как это сделать, вы должны выполнить [начальную настройку консоли](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="ca11a-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="ca11a-214">Установка сертификата вручную</span><span class="sxs-lookup"><span data-stu-id="ca11a-214">To manually install the certificate</span></span>

1. <span data-ttu-id="ca11a-215">Скачайте сертификат ЦС на свой компьютер и сохраните его в "К:\скипе Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="ca11a-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="ca11a-216">Расположите консоль в режиме администратора (см. [режим администрирования и управление устройствами](rooms-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="ca11a-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="ca11a-217">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ca11a-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="ca11a-218">Присоединение к домену Active Directory (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ca11a-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="ca11a-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="ca11a-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="ca11a-220">Вы можете присоединиться к консоли Microsoft Teams в вашем домене.</span><span class="sxs-lookup"><span data-stu-id="ca11a-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="ca11a-221">Консоли Microsoft Teams должны размещаться в отдельном подразделении на рабочих станциях компьютера, так как многие политики рабочих станций несовместимы с комнатами Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca11a-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="ca11a-222">Распространенный пример — это политики принудительного применения паролей, которые не позволят автоматически запускать комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca11a-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="ca11a-223">Сведения об управлении параметрами GPO можно найти в статье [Управление комнатами Microsoft Teams](rooms-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ca11a-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="ca11a-224">Присоединение к домену комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca11a-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="ca11a-225">Войдите в консоль из учетной записи администратора (см. [режим администратора и управление устройствами](rooms-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="ca11a-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="ca11a-226">Запустите командную окно PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="ca11a-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="ca11a-227">Введите следующую команду в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ca11a-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="ca11a-228">Например, если полное доменное имя — redmond.corp.microsoft.com и вы хотите, чтобы консоли Microsoft Teams могли находиться в подразделении "ресурсы Microsoft Teams", который является дочерним элементом для OU "Resources", команда будет:</span><span class="sxs-lookup"><span data-stu-id="ca11a-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="ca11a-229">Если вы хотите переименовать компьютер при присоединении к домену, используйте флаг-NewName, а затем — новое имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="ca11a-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="ca11a-230">Контрольный список для развертывания комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca11a-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="ca11a-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="ca11a-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="ca11a-232">Используйте следующий контрольный список при выполнении последней проверки правильности настройки консоли и всех ее периферийных устройств.</span><span class="sxs-lookup"><span data-stu-id="ca11a-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="ca11a-233">**Параметры приложения**</span><span class="sxs-lookup"><span data-stu-id="ca11a-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ca11a-234">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-234">☐</span></span>  <br/> |<span data-ttu-id="ca11a-235">Имя учетной записи комнаты и номер телефона (если ТЕЛЕФОНная сеть включена) правильно отображаются в правом верхнем углу экрана консоли</span><span class="sxs-lookup"><span data-stu-id="ca11a-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="ca11a-236">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-236">☐</span></span>  <br/> |<span data-ttu-id="ca11a-237">Имя компьютера Windows задано правильно (полезно для удаленного администрирования)</span><span class="sxs-lookup"><span data-stu-id="ca11a-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="ca11a-238">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-238">☐</span></span>  <br/> |<span data-ttu-id="ca11a-239">Пароль учетной записи администратора установлен и проверен.</span><span class="sxs-lookup"><span data-stu-id="ca11a-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="ca11a-240">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-240">☐</span></span>  <br/> |<span data-ttu-id="ca11a-241">Все обновления микропрограмм применены</span><span class="sxs-lookup"><span data-stu-id="ca11a-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="ca11a-242">**Аудио-и видеопериферийные устройства**</span><span class="sxs-lookup"><span data-stu-id="ca11a-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ca11a-243">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-243">☐</span></span>  <br/> |<span data-ttu-id="ca11a-244">Версия встроенного по камеры Камера верна (если применимо)</span><span class="sxs-lookup"><span data-stu-id="ca11a-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="ca11a-245">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-245">☐</span></span>  <br/> |<span data-ttu-id="ca11a-246">Работа с камерой и расстановка оптимальной работы</span><span class="sxs-lookup"><span data-stu-id="ca11a-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="ca11a-247">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-247">☐</span></span>  <br/> |<span data-ttu-id="ca11a-248">Параметры воспроизведения для устройства по умолчанию и устройства связи по умолчанию, настроенные на назначенное звуковое подключение</span><span class="sxs-lookup"><span data-stu-id="ca11a-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="ca11a-249">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-249">☐</span></span>  <br/> |<span data-ttu-id="ca11a-250">Параметры записи устройства связи по умолчанию, установленного на звуковом периферийном устройстве</span><span class="sxs-lookup"><span data-stu-id="ca11a-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="ca11a-251">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-251">☐</span></span>  <br/> |<span data-ttu-id="ca11a-252">Версия встроенного по звукового устройства (если применимо)</span><span class="sxs-lookup"><span data-stu-id="ca11a-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="ca11a-253">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-253">☐</span></span>  <br/> |<span data-ttu-id="ca11a-254">Звуковое устройство ввода и оптимальное расположение</span><span class="sxs-lookup"><span data-stu-id="ca11a-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="ca11a-255">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-255">☐</span></span>  <br/> |<span data-ttu-id="ca11a-256">Звуковое устройство звукового вывода и оптимальное расположение</span><span class="sxs-lookup"><span data-stu-id="ca11a-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="ca11a-257">**Перенос**</span><span class="sxs-lookup"><span data-stu-id="ca11a-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ca11a-258">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-258">☐</span></span>  <br/> |<span data-ttu-id="ca11a-259">Кабели защищены и не сжаты</span><span class="sxs-lookup"><span data-stu-id="ca11a-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="ca11a-260">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-260">☐</span></span>  <br/> |<span data-ttu-id="ca11a-261">Голосовые функции, принимающие по HDMI, работают</span><span class="sxs-lookup"><span data-stu-id="ca11a-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="ca11a-262">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-262">☐</span></span>  <br/> |<span data-ttu-id="ca11a-263">Видео, принимающее функции HDMI, работает</span><span class="sxs-lookup"><span data-stu-id="ca11a-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="ca11a-264">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-264">☐</span></span>  <br/> |<span data-ttu-id="ca11a-265">Закрепление может свободно поворачивается</span><span class="sxs-lookup"><span data-stu-id="ca11a-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="ca11a-266">☐</span><span class="sxs-lookup"><span data-stu-id="ca11a-266">☐</span></span>  <br/> |<span data-ttu-id="ca11a-267">Яркость экрана приемлема для среды</span><span class="sxs-lookup"><span data-stu-id="ca11a-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ca11a-268">См. также</span><span class="sxs-lookup"><span data-stu-id="ca11a-268">See also</span></span>
<span data-ttu-id="ca11a-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="ca11a-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="ca11a-270">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca11a-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="ca11a-271">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca11a-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="ca11a-272">Настройка консоли Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca11a-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="ca11a-273">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="ca11a-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
