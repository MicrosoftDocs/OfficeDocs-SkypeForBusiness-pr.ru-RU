---
title: Настройка консоли для Систем комнат Skype версии 2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: В этой статье описывается настройка консольного устройства и его периферийных устройств для Систем комнат Skype версии 2.
ms.openlocfilehash: 6ca029fa7f5560dfdfebd789938d9b53ff2e9abc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="c39ab-103">Настройка консоли для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c39ab-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="c39ab-104">В этой статье описывается настройка консольного устройства и его периферийных устройств для Систем комнат Skype версии 2.</span><span class="sxs-lookup"><span data-stu-id="c39ab-104">This article describes how to set up the Skype Room Systems v2 console device and its peripherals.</span></span>
  
<span data-ttu-id="c39ab-105">Эти действия следует выполнять только в том случае, при необходимости Скайп для учетных записей Exchange и бизнес-уже создан и проверен, как описано в [Развертывание системы комнаты Скайп версии 2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c39ab-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="c39ab-106">Необходимо будет требованиях к оборудованию и программному обеспечению, описанные в [системах комнаты Скайп требования к версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c39ab-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="c39ab-107">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="c39ab-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="c39ab-108">Подготовка образа установки</span><span class="sxs-lookup"><span data-stu-id="c39ab-108">Prepare the installation image</span></span>](console.md#Prep_Image)
    
- [<span data-ttu-id="c39ab-109">Установка на планшете закрытого сертификата ЦС</span><span class="sxs-lookup"><span data-stu-id="c39ab-109">Install a private CA certificate on the tablet device</span></span>](console.md#Certs)
    
- [<span data-ttu-id="c39ab-110">Установка Windows 10 и консольное приложение систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="c39ab-110">Install Windows 10 and the Skype Room Systems v2 console app </span></span>](console.md#Reimage)
   
- [<span data-ttu-id="c39ab-111">Начальный набор копирование консоли</span><span class="sxs-lookup"><span data-stu-id="c39ab-111">Initial set up of the Console </span></span>](console.md#Initial)
    
- [<span data-ttu-id="c39ab-112">Контрольный список развертывания комнаты Скайп систем версии 2</span><span class="sxs-lookup"><span data-stu-id="c39ab-112">Skype Room Systems v2 Deployment Checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="c39ab-113">Версии 2 систем комнаты Скайп вариант возможен только в правильно настроенных Скайп для бизнес-среде, где учетные записи устройства правильно настроены как описано в [Развертывание системы комнаты Скайп версии 2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c39ab-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-image"></a><span data-ttu-id="c39ab-114">Подготовка образа установки</span><span class="sxs-lookup"><span data-stu-id="c39ab-114">Prepare the installation image</span></span>
<span data-ttu-id="c39ab-115"><a name="Prep_Image"> </a></span><span class="sxs-lookup"><span data-stu-id="c39ab-115"></span></span>

<span data-ttu-id="c39ab-116">Установка приложения v2 Скайп комнаты систем на 4 Surface Pro или Surface Pro требуется USB-накопитель с по крайней мере 32 ГБ оперативной памяти, отформатированные в FAT32 диска.</span><span class="sxs-lookup"><span data-stu-id="c39ab-116">Installing the Skype Room Systems v2 app on a Surface Pro 4 or Surface Pro requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="c39ab-117">Должно быть не файлы на устройстве, будут потеряны все существующие файлы на хранение USB.</span><span class="sxs-lookup"><span data-stu-id="c39ab-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c39ab-118">Если вам не удастся создать образ консоли согласно этим инструкциям, результат может быть непредвиденным.</span><span class="sxs-lookup"><span data-stu-id="c39ab-118">Failure to create your console image according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="c39ab-119">Годовщина Enterprise 10 Windows Update (версия 1607) больше не поддерживается для создания образа систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="c39ab-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 image creation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c39ab-120">Существующей версии 2 Скайп комнаты систем с 10 Enterprise Годовщина центра обновления Windows переход к версии 2 систем комнаты Скайп обновление 3 путем получения магазина Windows будет работать, но необходимо провести новую установку, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="c39ab-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="c39ab-121">Загрузите [MSU для KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span><span class="sxs-lookup"><span data-stu-id="c39ab-121">Download the [MSU for KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span></span>
2. <span data-ttu-id="c39ab-122">Загрузите [сценарий CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="c39ab-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
3. <span data-ttu-id="c39ab-123">Размещение MSU для KB4056892 в том же каталоге как сценарий CreateSrsMedia.ps1.</span><span class="sxs-lookup"><span data-stu-id="c39ab-123">Place the MSU for KB4056892 in the same directory as the CreateSrsMedia.ps1 script.</span></span>
4. <span data-ttu-id="c39ab-124">Запустите сценарий CreateSrsMedia.ps1 из командной строки с повышенными привилегиями на компьютере Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c39ab-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="c39ab-125">Следуйте инструкциям, сценарий для создания диска настройки систем комнаты Скайп USB версии 2.</span><span class="sxs-lookup"><span data-stu-id="c39ab-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="c39ab-126">После завершения удаления USB-диска со своего компьютера и перейдите к [10 Установка Windows и систем комнаты Скайп v2 консольное приложение ](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="c39ab-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app ](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="c39ab-127">Установка Windows 10 и консольного приложения Систем комнат Skype версии 2 </span><span class="sxs-lookup"><span data-stu-id="c39ab-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="c39ab-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="c39ab-128"></span></span>

<span data-ttu-id="c39ab-129">Далее необходимо применить созданный образ.</span><span class="sxs-lookup"><span data-stu-id="c39ab-129">You now need to apply the image you've created.</span></span> <span data-ttu-id="c39ab-130">Планшета будет выполняться как устройства и пользователей по умолчанию присваивается значение только запустите приложение Скайп комнаты систем, версии 2.</span><span class="sxs-lookup"><span data-stu-id="c39ab-130">The tablet will run as an appliance and the default user will be set to only run the Skype Room Systems v2 app.</span></span> 
  
1. <span data-ttu-id="c39ab-131">Планшет должен быть подключен к источнику питания.</span><span class="sxs-lookup"><span data-stu-id="c39ab-131">The tablet should be connected to a power source.</span></span> <span data-ttu-id="c39ab-132">Перед началом процедуры выключите питание.</span><span class="sxs-lookup"><span data-stu-id="c39ab-132">Start from a completely powered-off state.</span></span> <span data-ttu-id="c39ab-133">При необходимости нажмите и удерживайте нажатой кнопку питания до тех пор, пока планшет не отключится.</span><span class="sxs-lookup"><span data-stu-id="c39ab-133">If necessary, press and keep pressing the Power button until the tablet switches off.</span></span>
    
2. <span data-ttu-id="c39ab-134">Подключите установочный USB-диск к планшету.</span><span class="sxs-lookup"><span data-stu-id="c39ab-134">Plug your USB Setup disk into the tablet.</span></span>
    
3. <span data-ttu-id="c39ab-135">Нажмите и удерживайте кнопку уменьшения громкости (–) на планшете.</span><span class="sxs-lookup"><span data-stu-id="c39ab-135">Press and continue to hold the volume down (-) button on the tablet.</span></span> 
    
4. <span data-ttu-id="c39ab-136">Нажмите и отпустите кнопку питания на планшете.</span><span class="sxs-lookup"><span data-stu-id="c39ab-136">Press and release the power button on the tablet.</span></span>
    
5. <span data-ttu-id="c39ab-137">После загрузки установки Windows отпустите кнопку уменьшения громкости (–).</span><span class="sxs-lookup"><span data-stu-id="c39ab-137">Once Windows setup is booted, release the volume down (-) button.</span></span>
    
6. <span data-ttu-id="c39ab-138">При запуске устройства версии 2 Скайп комнаты систем в первый раз, его поведение будет зависеть от версии Sysprep.exe используется в файле AutoUnattend.xml (см. шаг 7 [подготовить образ установки](console.md#Prep_Image)):</span><span class="sxs-lookup"><span data-stu-id="c39ab-138">When the Skype Room Systems v2 device starts for the first time, its behavior will depend on which version of Sysprep.exe is used in the AutoUnattend.xml file (see step 7 of [Prepare the installation image](console.md#Prep_Image)):</span></span>
    
   - <span data-ttu-id="c39ab-p107">Если была активирована версия команды с параметром /shutdown, система продолжит установку, а затем завершит работу. После завершения работы вы можете выполнить загрузку с внешнего носителя, содержащего среду Windows PE, и использовать систему DISM для установки языковых пакетов, применения образов, записи эталонного образа компьютера или выполнения других действий.</span><span class="sxs-lookup"><span data-stu-id="c39ab-p107">If the /shutdown version of the command was enabled, the system will proceed with installation and eventually shut down. Once it is shut down, you may boot to external media containing Windows PE and use DISM to install language packs, apply images, capture your reference image from the machine, or perform other actions.</span></span>
    
   - <span data-ttu-id="c39ab-141">Если было включено/reboot версию команды, система продолжить установку и в конечном счете попросите пользователя выберите свои параметры языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="c39ab-141">If the /reboot version of the command was enabled, the system will proceed with installation, and eventually ask the user to select their locale settings.</span></span> <span data-ttu-id="c39ab-142">После этого выбора устройства v2 систем комнаты Скайп загрузится в его запуска процесса.</span><span class="sxs-lookup"><span data-stu-id="c39ab-142">After making this selection, the Skype Room Systems v2 device will boot into its initial startup process.</span></span> <span data-ttu-id="c39ab-143">Просмотреть [Начальная настройка консоли](console.md#Initial)</span><span class="sxs-lookup"><span data-stu-id="c39ab-143">See [Initial set up of the Console ](console.md#Initial)</span></span>
    
<span data-ttu-id="c39ab-144">После выключения или перезагрузки системы можно извлечь установочный USB-диск.</span><span class="sxs-lookup"><span data-stu-id="c39ab-144">After the system has shut down or rebooted, it is safe to remove the USB Setup Disk.</span></span> <span data-ttu-id="c39ab-145">На данном этапе можно установить планшет в док-станцию и подключить к нему все необходимые в комнате для собраний периферийные устройства.</span><span class="sxs-lookup"><span data-stu-id="c39ab-145">At this point, you can place the tablet in the dock and attach the peripherals needed for your meeting room.</span></span> <span data-ttu-id="c39ab-146">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="c39ab-146">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="c39ab-147">Выбор языка в обновлении для дизайнеров</span><span class="sxs-lookup"><span data-stu-id="c39ab-147">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="c39ab-148">В обновлении создателя, необходимо использовать сценарий ApplyCurrentRegionAndLanguage.ps1 в сценариях, где неявных язык не обеспечивает пользователя с языка приложения, они должны (например, они приложение на разработку на французском языке, но это готовится к на английском языке).</span><span class="sxs-lookup"><span data-stu-id="c39ab-148">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c39ab-149">Приведенные ниже инструкции относятся только к устройствам, созданным с использованием обновления Windows для дизайнеров.</span><span class="sxs-lookup"><span data-stu-id="c39ab-149">The following instructions work only for devices created using Windows Creator's Update.</span></span> <span data-ttu-id="c39ab-150">Эти инструкции не применяются к устаревшим и представленным на рынке системам, для которых не были созданы соответствующие образы для новой системы подготовки. Тем не менее, на них не должна распространяться первичная проблема, требующая ручного вмешательства (в рамках установки юбилейного выпуска можно явно задать язык приложения).</span><span class="sxs-lookup"><span data-stu-id="c39ab-150">Legacy/in-market systems that have not been re-imaged properly to the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span> 
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="c39ab-151">Применение необходимого языка</span><span class="sxs-lookup"><span data-stu-id="c39ab-151">To apply your desired language</span></span>

1. <span data-ttu-id="c39ab-152">Переключитесь в режим администрирования.</span><span class="sxs-lookup"><span data-stu-id="c39ab-152">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="c39ab-153">Откройте меню "Пуск".</span><span class="sxs-lookup"><span data-stu-id="c39ab-153">Select the Start menu.</span></span>
    
3. <span data-ttu-id="c39ab-154">Щелкните значок шестеренки, чтобы запустить приложение **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="c39ab-154">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="c39ab-155">Выберите **время &amp; языка**.</span><span class="sxs-lookup"><span data-stu-id="c39ab-155">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="c39ab-156">Выберите **области &amp; языка**.</span><span class="sxs-lookup"><span data-stu-id="c39ab-156">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="c39ab-157">Выберите **Добавить язык**.</span><span class="sxs-lookup"><span data-stu-id="c39ab-157">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="c39ab-158">Выберите язык, который требуется добавить.</span><span class="sxs-lookup"><span data-stu-id="c39ab-158">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="c39ab-159">Выберите язык, который вы только что добавили в список «Языки».</span><span class="sxs-lookup"><span data-stu-id="c39ab-159">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="c39ab-160">Выберите **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="c39ab-160">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="c39ab-161">Удаление языков</span><span class="sxs-lookup"><span data-stu-id="c39ab-161">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="c39ab-162">а.</span><span class="sxs-lookup"><span data-stu-id="c39ab-162">a.</span></span> <span data-ttu-id="c39ab-163">Выберите язык, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c39ab-163">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="c39ab-164">б.</span><span class="sxs-lookup"><span data-stu-id="c39ab-164">b.</span></span> <span data-ttu-id="c39ab-165">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c39ab-165">Select **Remove**.</span></span>
    
11. <span data-ttu-id="c39ab-166">Запустите командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="c39ab-166">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="c39ab-167">Выполните следующую команду. </span><span class="sxs-lookup"><span data-stu-id="c39ab-167">Run the following command:</span></span> 
    
    <span data-ttu-id="c39ab-168">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="c39ab-168">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="c39ab-169">Перезапустите систему.</span><span class="sxs-lookup"><span data-stu-id="c39ab-169">Restart the system.</span></span>
    
<span data-ttu-id="c39ab-170">Язык теперь применяется к устройства версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="c39ab-170">Your desired language is now applied to the Skype Room Systems v2 device.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="c39ab-171">Начальная настройка консоли </span><span class="sxs-lookup"><span data-stu-id="c39ab-171">Initial set up of the Console</span></span>
<span data-ttu-id="c39ab-172"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="c39ab-172"></span></span>

<span data-ttu-id="c39ab-173">После установки Windows при следующем запуске или, если выбран параметр/reboot приложения v2 систем комнаты Скайп перейдет в его начальной установки и настройки устройств.</span><span class="sxs-lookup"><span data-stu-id="c39ab-173">After Windows is installed, the Skype Room Systems v2 app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="c39ab-p113">Появится экран "Учетная запись пользователя". Введите адрес для входа Skype в формате пользователь@домен для учетной записи комнаты, которая будет использоваться на этом устройстве.</span><span class="sxs-lookup"><span data-stu-id="c39ab-p113">The User Account screen appears. Enter the Skype sign-in address (in user@domain format) of the room account to be used with the device.</span></span>
    
2. <span data-ttu-id="c39ab-176">Введите пароль для учетной записи комнаты и подтвердите его.</span><span class="sxs-lookup"><span data-stu-id="c39ab-176">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="c39ab-177">В разделе «Настройка домена» задайте полное доменное имя для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="c39ab-177">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="c39ab-178">Если Скайп для бизнеса SIP-домена отличается от домена Exchange пользователя, введите домен Exchange в этом поле.</span><span class="sxs-lookup"><span data-stu-id="c39ab-178">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="c39ab-179">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c39ab-179">Click **Next**.</span></span>
    
5. <span data-ttu-id="c39ab-180">Выберите указанный устройства, на экране компонентов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c39ab-180">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="c39ab-181">По умолчанию автоматическая демонстрация экрана включена, а скрытие имен во время собрания отключено.</span><span class="sxs-lookup"><span data-stu-id="c39ab-181">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="c39ab-182">Для выбора доступны следующие устройства:</span><span class="sxs-lookup"><span data-stu-id="c39ab-182">The devices to select are:</span></span>
    
   - <span data-ttu-id="c39ab-183">Микрофон для конференций. Микрофон, который используется по умолчанию в этом конференц-зале.</span><span class="sxs-lookup"><span data-stu-id="c39ab-183">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="c39ab-184">Динамик для конференций. Динамик, который используется по умолчанию для проведения конференций. </span><span class="sxs-lookup"><span data-stu-id="c39ab-184">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="c39ab-185">Динамик по умолчанию. Динамик, который используется для воспроизведения звука со входа HDMI.</span><span class="sxs-lookup"><span data-stu-id="c39ab-185">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
    <span data-ttu-id="c39ab-p116">Параметры каждого элемента можно настроить в соответствующем раскрывающемся списке. Необходимо сделать выбор для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="c39ab-p116">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="c39ab-188">Нажмите кнопку **Готово **.</span><span class="sxs-lookup"><span data-stu-id="c39ab-188">Click **Finish**.</span></span>
    
<span data-ttu-id="c39ab-189">Приложение сразу же будет запускаться вход с использованием Скайп для Business Server 2015 с использованием учетных данных, введенных ранее, а также также начать синхронизацию его календаря с сервером Exchange, используя те же учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c39ab-189">The app should immediately start signing in to Skype for Business Server 2015 with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="c39ab-190">Для получения дополнительных сведений об использовании приложения обратитесь к [Скайп комнаты систем версии 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="c39ab-190">For details on using the app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c39ab-191">Версии 2 Скайп комнаты систем полагается на наличие сертифицированного консоли оборудования (Logitech SmartDock).</span><span class="sxs-lookup"><span data-stu-id="c39ab-191">Skype Room Systems v2 relies on the presence of certified console hardware (the Logitech SmartDock).</span></span> <span data-ttu-id="c39ab-192">Если обнаружена оборудования консоли даже правильно созданное изображение, содержащее ваше приложение версии 2 Скайп комнаты систем, загруженных в 4 Surface Pro или Surface Pro не загружается после начального этапа процедуры.</span><span class="sxs-lookup"><span data-stu-id="c39ab-192">Even a correctly created image containing the Skype Room Systems v2 app loaded on a Surface Pro 4 or Surface Pro will not boot past the initial setup procedure unless the console hardware is detected.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c39ab-193">При начальной настройке некоторым пользователям, не владеющим английским языком, потребуется подключить физическую клавиатуру к консоли, если сенсорная клавиатура не поддерживает символы.</span><span class="sxs-lookup"><span data-stu-id="c39ab-193">Some non-English language users may need a physical keyboard connected to the Console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span> 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a><span data-ttu-id="c39ab-194">Установка сертификата закрытого ЦС на планшет</span><span class="sxs-lookup"><span data-stu-id="c39ab-194">Install a private CA certificate on the tablet device</span></span>
<span data-ttu-id="c39ab-195"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c39ab-195"></span></span>

<span data-ttu-id="c39ab-196">Устройства версии 2 Скайп комнаты систем требуется доверие к сертификатам, используемые Скайп для бизнеса и Exchange серверы, к которому подключен к.</span><span class="sxs-lookup"><span data-stu-id="c39ab-196">The Skype Room Systems v2 device needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="c39ab-197">В O365 это реализуется автоматически, так как соответствующие серверы используют общедоступные центры сертификации, по умолчанию являющиеся доверенными в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c39ab-197">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="c39ab-198">В случае где сертификации — это частный, например локальное развертывание с помощью Active Directory и сертификации Windows, можно добавить сертификат на устройство систем комнаты Скайп версии 2 в несколько способов:</span><span class="sxs-lookup"><span data-stu-id="c39ab-198">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 device in a couple of ways:</span></span>
  
- <span data-ttu-id="c39ab-199">Можно присоединить устройство к Active Directory, в результате чего необходимые сертификаты будут добавлены автоматически при условии, что центр сертификации опубликован в Active Directory (стандартный вариант развертывания).</span><span class="sxs-lookup"><span data-stu-id="c39ab-199">You can join the device to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="c39ab-p120">Сертификат можно установить вручную после завершения создания образа. Прежде чем сделать это, необходимо выполнить [начальную настройку консоли](console.md#Initial). </span><span class="sxs-lookup"><span data-stu-id="c39ab-p120">You can install the certificate manually after the imaging process. Before you do this, you must complete [Initial set up of the Console ](console.md#Initial).</span></span> 
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="c39ab-202">Установка сертификата вручную </span><span class="sxs-lookup"><span data-stu-id="c39ab-202">To manually install the certificate</span></span>

1. <span data-ttu-id="c39ab-203">Скачайте сертификат ЦС на компьютер и сохраните его в папке C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer.</span><span class="sxs-lookup"><span data-stu-id="c39ab-203">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="c39ab-204">Поместите 4 поверхности в режиме администратором ( [Admin режим и устройства управления](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)см).</span><span class="sxs-lookup"><span data-stu-id="c39ab-204">Place the Surface 4 in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="c39ab-205">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="c39ab-205">Run the following command:</span></span>
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="c39ab-206">Присоединение к домену Active Directory (необязательно)</span><span class="sxs-lookup"><span data-stu-id="c39ab-206">Join an Active Directory Domain (Optional)</span></span>
<span data-ttu-id="c39ab-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c39ab-207"></span></span>

<span data-ttu-id="c39ab-208">Скайп комнаты систем v2 устройств можно объединить с вашего домена.</span><span class="sxs-lookup"><span data-stu-id="c39ab-208">You can join Skype Room Systems v2 devices to your domain.</span></span> <span data-ttu-id="c39ab-209">Систем комнаты Скайп v2 устройств должны находиться в отдельные Подразделения из рабочих станциях ПК, так как количество политик рабочей станции не совместимы с системами комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="c39ab-209">Skype Room Systems v2 devices should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="c39ab-210">Распространенные пример, принудительное применение политики паролей, которые не позволит систем комнаты Скайп v2 автоматический запуск.</span><span class="sxs-lookup"><span data-stu-id="c39ab-210">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="c39ab-211">Сведения об управлении параметры объектов групповой Политики можно найти [Управление системами комнаты Скайп версии 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c39ab-211">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span> 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="c39ab-212">Присоединение Систем комнат Skype версии 2 к домену</span><span class="sxs-lookup"><span data-stu-id="c39ab-212">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="c39ab-213">Войти в консоль администрирования с учетной записью ( [режим и устройства управления Admin](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)см).</span><span class="sxs-lookup"><span data-stu-id="c39ab-213">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="c39ab-214">Запустите командную строку Powershell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="c39ab-214">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="c39ab-215">Введите следующую команду в Powershell:</span><span class="sxs-lookup"><span data-stu-id="c39ab-215">Enter the following command in Powershell:</span></span>
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

<span data-ttu-id="c39ab-216">Например, если redmond.corp.microsoft.com — это полное доменное, и вы хотите устройство систем комнаты Скайп версии 2 в «v2 систем комнаты Скайп» Подразделения, являющийся дочерним элементом «ресурсы» Подразделение, команда будет:</span><span class="sxs-lookup"><span data-stu-id="c39ab-216">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 devices to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="c39ab-217">Если вы хотите переименовать компьютер при присоединении к домену, используйте флаг - NewName, а затем новое имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="c39ab-217">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="c39ab-218">Контрольный список для развертывания Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c39ab-218">Skype Room Systems v2 Deployment Checklist</span></span>
<span data-ttu-id="c39ab-219"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c39ab-219"></span></span>

<span data-ttu-id="c39ab-220">Для окончательной проверки настройки консольного устройства и всех периферийных устройств следуйте приведенному ниже контрольному списку.</span><span class="sxs-lookup"><span data-stu-id="c39ab-220">Use the following checklist while doing a final verification that the console device and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="c39ab-221">**Параметры приложения**</span><span class="sxs-lookup"><span data-stu-id="c39ab-221">**Application Settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c39ab-222">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-222">☐</span></span>  <br/> |<span data-ttu-id="c39ab-223">В верхнем правом углу экрана консоли правильно отображаются название учетной записи комнаты и номер телефона (если доступна ТСОП).</span><span class="sxs-lookup"><span data-stu-id="c39ab-223">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="c39ab-224">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-224">☐</span></span>  <br/> |<span data-ttu-id="c39ab-225">Правильно задано имя компьютера Windows (для удаленного администрирования)</span><span class="sxs-lookup"><span data-stu-id="c39ab-225">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="c39ab-226">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-226">☐</span></span>  <br/> |<span data-ttu-id="c39ab-227">Задан и подтвержден пароль учетной записи администратора</span><span class="sxs-lookup"><span data-stu-id="c39ab-227">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="c39ab-228">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-228">☐</span></span>  <br/> |<span data-ttu-id="c39ab-229">Установлены все системные обновления для устройств Surface Pro 4 или Surface Pro</span><span class="sxs-lookup"><span data-stu-id="c39ab-229">All Surface Pro 4 or Surface Pro System Updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="c39ab-230">**Периферийных аудио и видео**</span><span class="sxs-lookup"><span data-stu-id="c39ab-230">**Audio/Video Peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c39ab-231">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-231">☐</span></span>  <br/> |<span data-ttu-id="c39ab-232">Указана правильная версия встроенного ПО периферийной камеры (если применимо)</span><span class="sxs-lookup"><span data-stu-id="c39ab-232">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c39ab-233">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-233">☐</span></span>  <br/> |<span data-ttu-id="c39ab-234">Камера работоспособно и оптимально расположенных</span><span class="sxs-lookup"><span data-stu-id="c39ab-234">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="c39ab-235">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-235">☐</span></span>  <br/> |<span data-ttu-id="c39ab-236">В качестве используемых по умолчанию устройства воспроизведения и устройства связи для воспроизведения задано нужное периферийное звуковое устройство</span><span class="sxs-lookup"><span data-stu-id="c39ab-236">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c39ab-237">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-237">☐</span></span>  <br/> |<span data-ttu-id="c39ab-238">В качестве используемого по умолчанию устройства связи для записи задано нужное периферийное звуковое устройство</span><span class="sxs-lookup"><span data-stu-id="c39ab-238">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c39ab-239">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-239">☐</span></span>  <br/> |<span data-ttu-id="c39ab-240">Указана правильная версия встроенного ПО периферийного звукового устройства (если применимо)</span><span class="sxs-lookup"><span data-stu-id="c39ab-240">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c39ab-241">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-241">☐</span></span>  <br/> |<span data-ttu-id="c39ab-242">Входное звуковое устройство работает и правильно расположено</span><span class="sxs-lookup"><span data-stu-id="c39ab-242">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="c39ab-243">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-243">☐</span></span>  <br/> |<span data-ttu-id="c39ab-244">Выходное звуковое устройство работает и правильно расположено</span><span class="sxs-lookup"><span data-stu-id="c39ab-244">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="c39ab-245">**Закрепление**</span><span class="sxs-lookup"><span data-stu-id="c39ab-245">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c39ab-246">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-246">☐</span></span>  <br/> |<span data-ttu-id="c39ab-247">Все кабели закреплены и не пережаты</span><span class="sxs-lookup"><span data-stu-id="c39ab-247">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="c39ab-248">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-248">☐</span></span>  <br/> |<span data-ttu-id="c39ab-249">Работает прием звукового сигнала через HDMI</span><span class="sxs-lookup"><span data-stu-id="c39ab-249">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c39ab-250">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-250">☐</span></span>  <br/> |<span data-ttu-id="c39ab-251">Работает прием видеосигнала через HDMI</span><span class="sxs-lookup"><span data-stu-id="c39ab-251">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c39ab-252">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-252">☐</span></span>  <br/> |<span data-ttu-id="c39ab-253">Док-станция свободно вращается</span><span class="sxs-lookup"><span data-stu-id="c39ab-253">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="c39ab-254">☐</span><span class="sxs-lookup"><span data-stu-id="c39ab-254">☐</span></span>  <br/> |<span data-ttu-id="c39ab-255">Яркость экрана соответствует обстановке</span><span class="sxs-lookup"><span data-stu-id="c39ab-255">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c39ab-256">Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.</span><span class="sxs-lookup"><span data-stu-id="c39ab-256">See also</span></span>
<span data-ttu-id="c39ab-257"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c39ab-257"></span></span>

#### 

[<span data-ttu-id="c39ab-258">Планирование для помещения Скайп систем версии 2</span><span class="sxs-lookup"><span data-stu-id="c39ab-258">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="c39ab-259">Развертывание Скайп комнаты систем версии 2</span><span class="sxs-lookup"><span data-stu-id="c39ab-259">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="c39ab-260">Настройка консоли систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="c39ab-260">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="c39ab-261">Управление Скайп комнаты систем версии 2</span><span class="sxs-lookup"><span data-stu-id="c39ab-261">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

