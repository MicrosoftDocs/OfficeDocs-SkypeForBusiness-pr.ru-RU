---
title: Настройка консоли Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: В этой статье описано, как настроить консоль Microsoft Teams и ее периферийные устройства.
ms.openlocfilehash: c2513bbd86e2754c2e1008195ca1cc050a118882
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306536"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="d6998-103">Настройка консоли Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6998-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="d6998-104">В этой статье описано, как настроить консоль Microsoft Teams и ее периферийные устройства.</span><span class="sxs-lookup"><span data-stu-id="d6998-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="d6998-105">Эти действия необходимо выполнить, только если на компьютере уже созданы и протестированы учетные записи Microsoft Teams и Skype для бизнеса и Exchange, описанные в разделе [развертывание комнат Microsoft Teams](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="d6998-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="d6998-106">Вам потребуются оборудование и программное обеспечение, описанные в [требованиях к комнатам Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6998-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="d6998-107">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="d6998-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="d6998-108">Подготовка установочного носителя</span><span class="sxs-lookup"><span data-stu-id="d6998-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="d6998-109">Установка закрытого сертификата ЦС на консоли</span><span class="sxs-lookup"><span data-stu-id="d6998-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="d6998-110">Установка Windows 10 и консольного приложения комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6998-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="d6998-111">Начальная настройка консоли</span><span class="sxs-lookup"><span data-stu-id="d6998-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="d6998-112">Контрольный список для развертывания комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6998-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="d6998-113">Комнаты Microsoft Teams будут работать только в правильно настроенной среде Microsoft Teams или Skype для бизнеса, в которой учетные записи устройств настроены правильно, как описано в разделе [развертывание комнат Microsoft Teams](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="d6998-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="d6998-114">Подготовка установочного носителя</span><span class="sxs-lookup"><span data-stu-id="d6998-114">Prepare the installation media</span></span>
<span data-ttu-id="d6998-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="d6998-115"></span></span>

<span data-ttu-id="d6998-116">Для установки консольного приложения "комнаты Microsoft Teams" требуется USB-устройство хранения данных с емкостью не менее 32 ГБ.</span><span class="sxs-lookup"><span data-stu-id="d6998-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="d6998-117">На устройстве не должно быть других файлов; все существующие файлы в хранилище USB будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="d6998-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6998-118">Не удается создать установочный носитель Microsoft Teams в помещениях в соответствии с приведенными ниже инструкциями, что может привести к неожиданному поведению.</span><span class="sxs-lookup"><span data-stu-id="d6998-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="d6998-119">Ниже описана процедура создания установочного носителя для новых устройств с помощью Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6998-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="d6998-120">Существующие устройства по умолчанию обновляются автоматически с помощью центра обновления Windows и магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="d6998-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="d6998-121">Скачайте [сценарий креатесрсмедиа. ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="d6998-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="d6998-122">Запустите сценарий CreateSrsMedia.ps1 из командной строки с повышенными привилегиями на компьютере с ОС Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d6998-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="d6998-123">Следуйте инструкциям по созданию сценария для создания установочного диска USB на устройстве Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6998-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="d6998-124">Каждый раз, когда запускается сценарий Креатесрсмедиа. ps1, выводимый на экран текст будет включать в себя имя файла журнала или транскрипции для сеанса.</span><span class="sxs-lookup"><span data-stu-id="d6998-124">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="d6998-125">Если у вас возникли проблемы с запуском сценария, убедитесь, что у вас есть копия этой записи, которая доступна при запросе поддержки.</span><span class="sxs-lookup"><span data-stu-id="d6998-125">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="d6998-126">В сценарии Креатесрсмедиа. ps1 автоматизируются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d6998-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="d6998-127">Скачайте последнюю версию MSI-установщика для комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6998-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="d6998-128">Определите, какая сборка Windows должна быть предоставлена пользователю.</span><span class="sxs-lookup"><span data-stu-id="d6998-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="d6998-129">Последние версии могут быть не протестированы и не поддерживаются для использования с устройствами в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6998-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="d6998-130">Загрузите необходимые вспомогательные компоненты.</span><span class="sxs-lookup"><span data-stu-id="d6998-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="d6998-131">Соберите необходимые компоненты на установочном носителе.</span><span class="sxs-lookup"><span data-stu-id="d6998-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="d6998-132">Требуется определенная версия Windows 10, а эта версия доступна только пользователям с корпоративной лицензией.</span><span class="sxs-lookup"><span data-stu-id="d6998-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="d6998-133">Вы можете получить копию в [центре обслуживания для корпоративного лицензирования](https://www.microsoft.com/Licensing/servicecenter/).</span><span class="sxs-lookup"><span data-stu-id="d6998-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="d6998-134">После этого выньте USB-диск с компьютера и продолжайте [устанавливать Windows 10 и консольное приложение комнат Microsoft Teams](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="d6998-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="d6998-135">Установка Windows 10 и консольного приложения комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6998-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="d6998-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="d6998-136"></span></span>

<span data-ttu-id="d6998-137">Теперь необходимо применить созданный установочный носитель.</span><span class="sxs-lookup"><span data-stu-id="d6998-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="d6998-138">Целевое устройство будет запущено как управляющее устройство, и для него по умолчанию будет выполняться только консольное приложение комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6998-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="d6998-139">Если целевое устройство будет установлено на Dock (например, Surface Pro), отключите его от Dock.</span><span class="sxs-lookup"><span data-stu-id="d6998-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="d6998-140">Убедитесь, что оконечное устройство не подключено к сети.</span><span class="sxs-lookup"><span data-stu-id="d6998-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="d6998-141">Убедитесь, что оконечное устройство подключено к сети переменного тока.</span><span class="sxs-lookup"><span data-stu-id="d6998-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="d6998-142">Подключите установочный диск USB к целевому устройству.</span><span class="sxs-lookup"><span data-stu-id="d6998-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="d6998-143">Загрузитесь с установочного диска USB.</span><span class="sxs-lookup"><span data-stu-id="d6998-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="d6998-144">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="d6998-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="d6998-145">Если оконечное устройство является Pro Surface, выполните указанные ниже действия, чтобы загрузить установочный диск USB.</span><span class="sxs-lookup"><span data-stu-id="d6998-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="d6998-146">a)</span><span class="sxs-lookup"><span data-stu-id="d6998-146">a.</span></span> <span data-ttu-id="d6998-147">Нажмите и продолжайте удерживать нажатой кнопку "Громкость" (-).</span><span class="sxs-lookup"><span data-stu-id="d6998-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="d6998-148">б)</span><span class="sxs-lookup"><span data-stu-id="d6998-148">b.</span></span> <span data-ttu-id="d6998-149">Нажмите и отпустите кнопку Power.</span><span class="sxs-lookup"><span data-stu-id="d6998-149">Press and release the power button.</span></span>

    <span data-ttu-id="d6998-150">в.</span><span class="sxs-lookup"><span data-stu-id="d6998-150">c.</span></span> <span data-ttu-id="d6998-151">После загрузки установки Windows отпустите кнопку уменьшения громкости (–).</span><span class="sxs-lookup"><span data-stu-id="d6998-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="d6998-152">Система завершит работу после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="d6998-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="d6998-153">После того как система завершит работу, вы можете удалить установочный диск USB.</span><span class="sxs-lookup"><span data-stu-id="d6998-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="d6998-154">На этом этапе вы можете поместить целевое устройство в Dock (если используется стыковочный продукт), подключить периферийные устройства, необходимые для помещения в собрание, и подключиться к сети.</span><span class="sxs-lookup"><span data-stu-id="d6998-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="d6998-155">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="d6998-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="d6998-156">Выбор языка</span><span class="sxs-lookup"><span data-stu-id="d6998-156">Selecting a language</span></span> 

<span data-ttu-id="d6998-157">В обновлении создателя вам потребуется использовать сценарий Аппликуррентрегионандлангуаже. ps1 в сценариях, где неявный выбор языка не дает пользователю фактического языка приложения (например, нужно, чтобы приложение консоли выводилось на французском языке), но она будет на английском языке).</span><span class="sxs-lookup"><span data-stu-id="d6998-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6998-158">Приведенные ниже инструкции применимы только для консолей, созданных с помощью центра обновления Windows Creator.</span><span class="sxs-lookup"><span data-stu-id="d6998-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="d6998-159">Устаревшие и печатные системы, которые не настроены на использование мультимедиа с помощью новой системы подготовки, не смогут использовать эти инструкции, но это также не повлияет на первоначальную ошибку, для которой требуется ручное вмешательство (версия годовщины позволяет вам выбрать в процессе настройки язык приложения явно указан.</span><span class="sxs-lookup"><span data-stu-id="d6998-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="d6998-160">Применение необходимого языка</span><span class="sxs-lookup"><span data-stu-id="d6998-160">To apply your desired language</span></span>

1. <span data-ttu-id="d6998-161">Переключитесь в режим администрирования.</span><span class="sxs-lookup"><span data-stu-id="d6998-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="d6998-162">Откройте меню "Пуск".</span><span class="sxs-lookup"><span data-stu-id="d6998-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="d6998-163">Щелкните значок шестеренки, чтобы запустить приложение **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="d6998-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="d6998-164">Выберите **язык &amp; времени**.</span><span class="sxs-lookup"><span data-stu-id="d6998-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="d6998-165">Выберите **язык &amp; региона**.</span><span class="sxs-lookup"><span data-stu-id="d6998-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="d6998-166">Выберите **Добавить язык**.</span><span class="sxs-lookup"><span data-stu-id="d6998-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="d6998-167">Выберите язык, который требуется добавить.</span><span class="sxs-lookup"><span data-stu-id="d6998-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="d6998-168">Выберите язык, который вы только что добавили в список "языки".</span><span class="sxs-lookup"><span data-stu-id="d6998-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="d6998-169">Выберите **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="d6998-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="d6998-170">Удаление языков</span><span class="sxs-lookup"><span data-stu-id="d6998-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="d6998-p114">а. Выберите язык, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="d6998-p114">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="d6998-173">б.</span><span class="sxs-lookup"><span data-stu-id="d6998-173">b.</span></span> <span data-ttu-id="d6998-174">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d6998-174">Select **Remove**.</span></span>
    
11. <span data-ttu-id="d6998-175">Запустите командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d6998-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="d6998-176">Выполните следующую команду. </span><span class="sxs-lookup"><span data-stu-id="d6998-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="d6998-177">Перезапустите систему.</span><span class="sxs-lookup"><span data-stu-id="d6998-177">Restart the system.</span></span>
    
<span data-ttu-id="d6998-178">Выбранный язык теперь применен к консоли Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6998-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="d6998-179">Начальная настройка консоли</span><span class="sxs-lookup"><span data-stu-id="d6998-179">Initial set up of the console</span></span>
<span data-ttu-id="d6998-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="d6998-180"></span></span>

<span data-ttu-id="d6998-181">После установки Windows консольное приложение Microsoft Teams будет переведено в первоначальный процесс настройки при следующем запуске или если выбран параметр/ребут.</span><span class="sxs-lookup"><span data-stu-id="d6998-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="d6998-182">Появится экран "Учетная запись пользователя".</span><span class="sxs-lookup"><span data-stu-id="d6998-182">The User Account screen appears.</span></span> <span data-ttu-id="d6998-183">Введите адрес для входа в Skype (в формате пользователя @ домена) для учетной записи комнаты, которая будет использоваться с консолью.</span><span class="sxs-lookup"><span data-stu-id="d6998-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="d6998-184">Введите пароль для учетной записи комнаты и подтвердите его.</span><span class="sxs-lookup"><span data-stu-id="d6998-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="d6998-185">В разделе "Настройка домена" Задайте полное доменное имя сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d6998-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="d6998-186">Если домен SIP Skype для бизнеса не отличается от домена Exchange пользователя, введите в это поле Домен Exchange.</span><span class="sxs-lookup"><span data-stu-id="d6998-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="d6998-187">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d6998-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="d6998-188">На экране "возможности" выберите указанные устройства и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d6998-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="d6998-189">По умолчанию автоматическая демонстрация экрана включена, а скрытие имен во время собрания отключено.</span><span class="sxs-lookup"><span data-stu-id="d6998-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="d6998-190">Для выбора доступны следующие устройства:</span><span class="sxs-lookup"><span data-stu-id="d6998-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="d6998-191">Микрофон для конференций. Микрофон, который используется по умолчанию в этом конференц-зале.</span><span class="sxs-lookup"><span data-stu-id="d6998-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="d6998-192">Динамик для конференций. Динамик, который используется по умолчанию для проведения конференций. </span><span class="sxs-lookup"><span data-stu-id="d6998-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="d6998-193">Динамик по умолчанию. Динамик, который используется для воспроизведения звука со входа HDMI.</span><span class="sxs-lookup"><span data-stu-id="d6998-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="d6998-194">У каждого элемента есть раскрывающееся меню с параметрами выбора.</span><span class="sxs-lookup"><span data-stu-id="d6998-194">Each item has a drop-down menu of options to select from.</span></span> <span data-ttu-id="d6998-195">Для каждого устройства необходимо выбрать один из вариантов.</span><span class="sxs-lookup"><span data-stu-id="d6998-195">You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="d6998-196">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d6998-196">Click **Finish**.</span></span>
    
<span data-ttu-id="d6998-197">Консольное приложение Microsoft Teams может сразу же приступить к входу в Skype для бизнеса Server с помощью указанных выше учетных данных, а также начинать синхронизацию своего календаря с Exchange с использованием тех же учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d6998-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="d6998-198">Подробнее об использовании консольного приложения можно найти в справке по [комнатам Microsoft Teams](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="d6998-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d6998-199">Комнаты Microsoft Teams основываются на присутствии сертифицированного оборудования консоли.</span><span class="sxs-lookup"><span data-stu-id="d6998-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="d6998-200">Даже правильно созданное изображение, содержащее консольных комнат Microsoft Teams, не загрузится после начальной процедуры установки, если не будет обнаружено оборудование консоли.</span><span class="sxs-lookup"><span data-stu-id="d6998-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="d6998-201">Для решений на базе Surface Pro Surface Pro должны быть подключены к соответствующему оборудованию Dock для прохождения этой проверки.</span><span class="sxs-lookup"><span data-stu-id="d6998-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6998-202">Для некоторых пользователей, не являющихся английским языком, во время начальной настройки может потребоваться физическая клавиатура, подключенная к консоли, в том случае, если символы не поддерживаются сенсорной клавиатурой.</span><span class="sxs-lookup"><span data-stu-id="d6998-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="d6998-203">Установка закрытого сертификата ЦС на консоли</span><span class="sxs-lookup"><span data-stu-id="d6998-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="d6998-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="d6998-204"></span></span>

<span data-ttu-id="d6998-205">Консоли Microsoft Teams необходимо доверять сертификатам, используемым серверами, к которым он подключен.</span><span class="sxs-lookup"><span data-stu-id="d6998-205">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="d6998-206">Для O365 это выполняется автоматически, так как на этих серверах используются общедоступные центры сертификации, и они автоматически доверяются Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d6998-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="d6998-207">В случае, если центр сертификации является частным, для локального развертывания с помощью службы каталогов Active Directory и центра сертификации Windows вы можете добавить сертификат в консоль Microsoft Teams в несколько способов.</span><span class="sxs-lookup"><span data-stu-id="d6998-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="d6998-208">Вы можете присоединиться к консоли в Active Directory и автоматически добавить требуемые сертификаты, предоставленные центром сертификации, опубликованные в Active Directory (параметр развертывания в обычном режиме).</span><span class="sxs-lookup"><span data-stu-id="d6998-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="d6998-209">Вы можете установить сертификат вручную после процесса обработки изображений.</span><span class="sxs-lookup"><span data-stu-id="d6998-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="d6998-210">Перед тем как это сделать, вы должны выполнить [начальную настройку консоли](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="d6998-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="d6998-211">Установка сертификата вручную</span><span class="sxs-lookup"><span data-stu-id="d6998-211">To manually install the certificate</span></span>

1. <span data-ttu-id="d6998-212">Скачайте сертификат ЦС на свой компьютер и сохраните его в "К:\скипе Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="d6998-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="d6998-213">Расположите консоль в режиме администратора (см. [режим администрирования и управление устройствами](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="d6998-213">Place the console in admin mode (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="d6998-214">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="d6998-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="d6998-215">Присоединение к домену Active Directory (необязательно)</span><span class="sxs-lookup"><span data-stu-id="d6998-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="d6998-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="d6998-216"></span></span>

<span data-ttu-id="d6998-217">Вы можете присоединиться к консоли Microsoft Teams в вашем домене.</span><span class="sxs-lookup"><span data-stu-id="d6998-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="d6998-218">Консоли Microsoft Teams должны размещаться в отдельном подразделении на рабочих станциях компьютера, так как многие политики рабочих станций несовместимы с комнатами Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6998-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="d6998-219">Распространенный пример — это политики принудительного применения паролей, которые не позволят автоматически запускать комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6998-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="d6998-220">Сведения об управлении параметрами GPO можно найти в статье [Управление комнатами Microsoft Teams](room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="d6998-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="d6998-221">Присоединение к домену комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6998-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="d6998-222">Войдите в консоль из учетной записи администратора (см. [режим администратора и управление устройствами](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="d6998-222">Sign into the console from the admin account (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="d6998-223">Запустите командную окно PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d6998-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="d6998-224">Введите следующую команду в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d6998-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="d6998-225">Например, если полное доменное имя — redmond.corp.microsoft.com и вы хотите, чтобы консоли Microsoft Teams могли находиться в подразделении "ресурсы Microsoft Teams", который является дочерним элементом для OU "Resources", команда будет:</span><span class="sxs-lookup"><span data-stu-id="d6998-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="d6998-226">Если вы хотите переименовать компьютер при присоединении к домену, используйте флаг-NewName, а затем — новое имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="d6998-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="d6998-227">Контрольный список для развертывания комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6998-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="d6998-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="d6998-228"></span></span>

<span data-ttu-id="d6998-229">Используйте следующий контрольный список при выполнении последней проверки правильности настройки консоли и всех ее периферийных устройств.</span><span class="sxs-lookup"><span data-stu-id="d6998-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="d6998-230">**Параметры приложения**</span><span class="sxs-lookup"><span data-stu-id="d6998-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d6998-231">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-231">☐</span></span>  <br/> |<span data-ttu-id="d6998-232">Имя учетной записи комнаты и номер телефона (если ТЕЛЕФОНная сеть включена) правильно отображаются в правом верхнем углу экрана консоли</span><span class="sxs-lookup"><span data-stu-id="d6998-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="d6998-233">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-233">☐</span></span>  <br/> |<span data-ttu-id="d6998-234">Имя компьютера Windows задано правильно (полезно для удаленного администрирования)</span><span class="sxs-lookup"><span data-stu-id="d6998-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="d6998-235">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-235">☐</span></span>  <br/> |<span data-ttu-id="d6998-236">Пароль учетной записи администратора установлен и проверен.</span><span class="sxs-lookup"><span data-stu-id="d6998-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="d6998-237">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-237">☐</span></span>  <br/> |<span data-ttu-id="d6998-238">Все обновления микропрограмм применены</span><span class="sxs-lookup"><span data-stu-id="d6998-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="d6998-239">**Аудио-и видеопериферийные устройства**</span><span class="sxs-lookup"><span data-stu-id="d6998-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d6998-240">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-240">☐</span></span>  <br/> |<span data-ttu-id="d6998-241">Версия встроенного по камеры Камера верна (если применимо)</span><span class="sxs-lookup"><span data-stu-id="d6998-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="d6998-242">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-242">☐</span></span>  <br/> |<span data-ttu-id="d6998-243">Работа с камерой и расстановка оптимальной работы</span><span class="sxs-lookup"><span data-stu-id="d6998-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="d6998-244">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-244">☐</span></span>  <br/> |<span data-ttu-id="d6998-245">Параметры воспроизведения для устройства по умолчанию и устройства связи по умолчанию, настроенные на назначенное звуковое подключение</span><span class="sxs-lookup"><span data-stu-id="d6998-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="d6998-246">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-246">☐</span></span>  <br/> |<span data-ttu-id="d6998-247">Параметры записи устройства связи по умолчанию, установленного на звуковом периферийном устройстве</span><span class="sxs-lookup"><span data-stu-id="d6998-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="d6998-248">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-248">☐</span></span>  <br/> |<span data-ttu-id="d6998-249">Версия встроенного по звукового устройства (если применимо)</span><span class="sxs-lookup"><span data-stu-id="d6998-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="d6998-250">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-250">☐</span></span>  <br/> |<span data-ttu-id="d6998-251">Звуковое устройство ввода и оптимальное расположение</span><span class="sxs-lookup"><span data-stu-id="d6998-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="d6998-252">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-252">☐</span></span>  <br/> |<span data-ttu-id="d6998-253">Звуковое устройство звукового вывода и оптимальное расположение</span><span class="sxs-lookup"><span data-stu-id="d6998-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="d6998-254">**Перенос**</span><span class="sxs-lookup"><span data-stu-id="d6998-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d6998-255">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-255">☐</span></span>  <br/> |<span data-ttu-id="d6998-256">Кабели защищены и не сжаты</span><span class="sxs-lookup"><span data-stu-id="d6998-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="d6998-257">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-257">☐</span></span>  <br/> |<span data-ttu-id="d6998-258">Голосовые функции, принимающие по HDMI, работают</span><span class="sxs-lookup"><span data-stu-id="d6998-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="d6998-259">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-259">☐</span></span>  <br/> |<span data-ttu-id="d6998-260">Видео, принимающее функции HDMI, работает</span><span class="sxs-lookup"><span data-stu-id="d6998-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="d6998-261">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-261">☐</span></span>  <br/> |<span data-ttu-id="d6998-262">Закрепление может свободно поворачивается</span><span class="sxs-lookup"><span data-stu-id="d6998-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="d6998-263">☐</span><span class="sxs-lookup"><span data-stu-id="d6998-263">☐</span></span>  <br/> |<span data-ttu-id="d6998-264">Яркость экрана приемлема для среды</span><span class="sxs-lookup"><span data-stu-id="d6998-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d6998-265">См. также</span><span class="sxs-lookup"><span data-stu-id="d6998-265">See also</span></span>
<span data-ttu-id="d6998-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="d6998-266"></span></span>

[<span data-ttu-id="d6998-267">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6998-267">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="d6998-268">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6998-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="d6998-269">Настройка консоли Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6998-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="d6998-270">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="d6998-270">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
