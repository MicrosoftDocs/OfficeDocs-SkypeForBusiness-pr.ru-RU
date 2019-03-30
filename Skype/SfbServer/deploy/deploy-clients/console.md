---
title: Настройка консоли комнат группами Майкрософт
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: В этой статье описывается настройка консоли комнат группами Майкрософт и ее периферийных устройств.
ms.openlocfilehash: fc1d50ffe6dd7415848e02571eab1484bd3dfe22
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012615"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="da184-103">Настройка консоли комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="da184-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="da184-104">В этой статье описывается настройка консоли комнат группами Майкрософт и ее периферийных устройств.</span><span class="sxs-lookup"><span data-stu-id="da184-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="da184-105">Эти действия следует выполнять только в том случае, при необходимости Скайп для учетных записей Exchange и бизнес-уже создан и проверен, как описано в [Развертывание комнат группами Майкрософт](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="da184-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="da184-106">Необходимо будет требованиях к оборудованию и программному обеспечению, описанным в статье [requirements комнат группами Майкрософт](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da184-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="da184-107">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="da184-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="da184-108">Подготовка установочного носителя</span><span class="sxs-lookup"><span data-stu-id="da184-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="da184-109">Установка закрытого сертификата ЦС в консоли</span><span class="sxs-lookup"><span data-stu-id="da184-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="da184-110">Установка Windows 10 и консольное приложение Microsoft группами комнат</span><span class="sxs-lookup"><span data-stu-id="da184-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="da184-111">Начальный набор копирование консоли</span><span class="sxs-lookup"><span data-stu-id="da184-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="da184-112">Контрольный список развертывания Microsoft группами комнат</span><span class="sxs-lookup"><span data-stu-id="da184-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="da184-113">Комнат группами Майкрософт вариант возможен только в правильно настроенных Скайп для бизнес-среде, где учетные записи устройства правильно настроены как описано в [Развертывание комнат группами Майкрософт](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="da184-113">Microsoft Teams Rooms will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="da184-114">Подготовка установочного носителя</span><span class="sxs-lookup"><span data-stu-id="da184-114">Prepare the installation media</span></span>
<span data-ttu-id="da184-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="da184-115"></span></span>

<span data-ttu-id="da184-116">Установка приложения консоли комнат группами Майкрософт требуется USB-накопитель с по крайней мере 32 ГБ.</span><span class="sxs-lookup"><span data-stu-id="da184-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="da184-117">Должно быть не файлы на устройстве; все существующие файлы на хранение USB будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="da184-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da184-118">Не удалось создать установочным носителем комнат группами Майкрософт в соответствии с этим инструкциям, могут измениться в непредвиденных последствий.</span><span class="sxs-lookup"><span data-stu-id="da184-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="da184-119">Для создания установочного носителя для изображения новых устройств комнат группами Майкрософт — приведенной ниже процедуре.</span><span class="sxs-lookup"><span data-stu-id="da184-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="da184-120">Существующего устройства по умолчанию, автоматического обновления из центра обновления Windows и магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="da184-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="da184-121">Загрузите [сценарий CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="da184-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="da184-122">Запустите сценарий CreateSrsMedia.ps1 из командной строки с повышенными привилегиями на компьютере с ОС Windows 10.</span><span class="sxs-lookup"><span data-stu-id="da184-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="da184-123">Следуйте инструкциям, сценарий для создания диска настройки USB комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="da184-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>

> [!CAUTION]
> <span data-ttu-id="da184-124">Имя папки, на котором запущен мультимедиа сценария создания из не может содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="da184-124">The name of the folder that you run the media creation script from can not contain a space.</span></span> <span data-ttu-id="da184-125">Если места в имени папки, скрипт завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="da184-125">If there is a space in to folder name, the script will fail.</span></span>

<span data-ttu-id="da184-126">Сценарий CreateSrsMedia.ps1 автоматизирует следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="da184-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="da184-127">Загрузите последние установщик MSI для комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="da184-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="da184-128">Определение построения Windows, необходимо задать пользователя.</span><span class="sxs-lookup"><span data-stu-id="da184-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="da184-129">Недавно выпущенных версий может или может не быть проверен и поддерживается для использования с устройствами комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="da184-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="da184-130">Загрузите необходимые вспомогательные компоненты.</span><span class="sxs-lookup"><span data-stu-id="da184-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="da184-131">Сборка необходимые компоненты на установочном носителе.</span><span class="sxs-lookup"><span data-stu-id="da184-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="da184-132">Определенной версии Windows 10 является обязательным, и эта версия доступна только для пользователей корпоративных лицензий.</span><span class="sxs-lookup"><span data-stu-id="da184-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="da184-133">Вы можете получить копию на [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span><span class="sxs-lookup"><span data-stu-id="da184-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="da184-134">После завершения удаления USB-диска со своего компьютера и перейдите к [Установка Windows 10 и комнат группами Майкрософт консольного приложения](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="da184-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="da184-135">Установка Windows 10 и консольное приложение Microsoft группами комнат</span><span class="sxs-lookup"><span data-stu-id="da184-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="da184-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="da184-136"></span></span>

<span data-ttu-id="da184-137">Теперь необходимо применить установочном носителе, созданные пользователем.</span><span class="sxs-lookup"><span data-stu-id="da184-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="da184-138">Устройство будет работать как устройства и пользователей по умолчанию присваивается значение только запуска приложения консоли комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="da184-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="da184-139">Если устройство будет установлен в приемки (например, Surface Pro), отключите его из приемки.</span><span class="sxs-lookup"><span data-stu-id="da184-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="da184-140">Убедитесь, что носитель не подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="da184-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="da184-141">Убедитесь, что устройство конечного подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="da184-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="da184-142">Подключите на диске установки USB целевого устройства.</span><span class="sxs-lookup"><span data-stu-id="da184-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="da184-143">Загрузите установочный диск USB.</span><span class="sxs-lookup"><span data-stu-id="da184-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="da184-144">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="da184-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="da184-145">Если ваше устройство Surface Pro, выполните следующие действия для загрузки на диске установки USB:</span><span class="sxs-lookup"><span data-stu-id="da184-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="da184-146">а.</span><span class="sxs-lookup"><span data-stu-id="da184-146">a.</span></span> <span data-ttu-id="da184-147">Нажмите клавишу, удерживая тома нажатой кнопку (-).</span><span class="sxs-lookup"><span data-stu-id="da184-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="da184-148">б.</span><span class="sxs-lookup"><span data-stu-id="da184-148">b.</span></span> <span data-ttu-id="da184-149">Нажмите клавишу и кнопку питания.</span><span class="sxs-lookup"><span data-stu-id="da184-149">Press and release the power button.</span></span>

    <span data-ttu-id="da184-150">в.</span><span class="sxs-lookup"><span data-stu-id="da184-150">c.</span></span> <span data-ttu-id="da184-151">После загрузки установки Windows отпустите кнопку уменьшения громкости (–).</span><span class="sxs-lookup"><span data-stu-id="da184-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="da184-152">Система завершит работу после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="da184-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="da184-153">После выпуска системы завершил работу, сообщением о возможности удаления установочный диск USB.</span><span class="sxs-lookup"><span data-stu-id="da184-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="da184-154">На этом этапе можно поместить целевого устройства в его приемки (при использовании продуктов на основе закрепления), периферийных устройств, необходимые для вашего комнату переговоров с подключением и подключиться к сети.</span><span class="sxs-lookup"><span data-stu-id="da184-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="da184-155">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="da184-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="da184-156">Выбор языка</span><span class="sxs-lookup"><span data-stu-id="da184-156">Selecting a language</span></span> 

<span data-ttu-id="da184-157">В обновлении создателя, необходимо использовать сценарий ApplyCurrentRegionAndLanguage.ps1 в сценариях, где неявных язык не обеспечивает пользователя с языка приложения, они должны (например, они должны консольное приложение, чтобы отображалось на французском языке, но оно будет на английском языке).</span><span class="sxs-lookup"><span data-stu-id="da184-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="da184-158">Следующие инструкции работает только для консоли, созданные с помощью центра обновления Windows создателя.</span><span class="sxs-lookup"><span data-stu-id="da184-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="da184-159">Устаревшие/в рынка систем, которые не были настроены с помощью мультимедиа с новой подготовки системы не сможет использовать эти инструкции, но должны также могут испытывать из начального проблеме, которую нужно этот вмешательства (Годовщина Edition позволяет выбрать вашей язык приложения явно как часть процесса установки).</span><span class="sxs-lookup"><span data-stu-id="da184-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="da184-160">Применение необходимого языка</span><span class="sxs-lookup"><span data-stu-id="da184-160">To apply your desired language</span></span>

1. <span data-ttu-id="da184-161">Переключитесь в режим администрирования.</span><span class="sxs-lookup"><span data-stu-id="da184-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="da184-162">Откройте меню "Пуск".</span><span class="sxs-lookup"><span data-stu-id="da184-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="da184-163">Щелкните значок шестеренки, чтобы запустить приложение **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="da184-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="da184-164">Выберите **время &amp; языка**.</span><span class="sxs-lookup"><span data-stu-id="da184-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="da184-165">Выберите **области &amp; языка**.</span><span class="sxs-lookup"><span data-stu-id="da184-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="da184-166">Выберите **Добавить язык**.</span><span class="sxs-lookup"><span data-stu-id="da184-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="da184-167">Выберите язык, который требуется добавить.</span><span class="sxs-lookup"><span data-stu-id="da184-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="da184-168">Выберите язык, который вы только что добавили в список «Языки».</span><span class="sxs-lookup"><span data-stu-id="da184-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="da184-169">Выберите **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="da184-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="da184-170">Удаление языков</span><span class="sxs-lookup"><span data-stu-id="da184-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="da184-p114">а. Выберите язык, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="da184-p114">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="da184-173">б.</span><span class="sxs-lookup"><span data-stu-id="da184-173">b.</span></span> <span data-ttu-id="da184-174">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="da184-174">Select **Remove**.</span></span>
    
11. <span data-ttu-id="da184-175">Запустите командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="da184-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="da184-176">Выполните следующую команду. </span><span class="sxs-lookup"><span data-stu-id="da184-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="da184-177">Перезапустите систему.</span><span class="sxs-lookup"><span data-stu-id="da184-177">Restart the system.</span></span>
    
<span data-ttu-id="da184-178">Язык теперь применяется к консоли комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="da184-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="da184-179">Начальный набор копирование консоли</span><span class="sxs-lookup"><span data-stu-id="da184-179">Initial set up of the console</span></span>
<span data-ttu-id="da184-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="da184-180"></span></span>

<span data-ttu-id="da184-181">После установки Windows при следующем запуске или, если выбран параметр/reboot консольное приложение Microsoft группами комнат перейдет в его начальной установки и настройки устройств.</span><span class="sxs-lookup"><span data-stu-id="da184-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="da184-182">Появится экран "Учетная запись пользователя".</span><span class="sxs-lookup"><span data-stu-id="da184-182">The User Account screen appears.</span></span> <span data-ttu-id="da184-183">Введите Скайп адрес для входа (в формате user@domain) комнаты учетной записи для использования с помощью консоли.</span><span class="sxs-lookup"><span data-stu-id="da184-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="da184-184">Введите пароль для учетной записи комнаты и подтвердите его.</span><span class="sxs-lookup"><span data-stu-id="da184-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="da184-185">В разделе «Настройка домена» задайте полное доменное имя для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="da184-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="da184-186">Если Скайп для бизнеса SIP-домена отличается от домена Exchange пользователя, введите домен Exchange в этом поле.</span><span class="sxs-lookup"><span data-stu-id="da184-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="da184-187">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da184-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="da184-188">Выберите указанный устройства, на экране компонентов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da184-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="da184-189">По умолчанию автоматическая демонстрация экрана включена, а скрытие имен во время собрания отключено.</span><span class="sxs-lookup"><span data-stu-id="da184-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="da184-190">Для выбора доступны следующие устройства:</span><span class="sxs-lookup"><span data-stu-id="da184-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="da184-191">Микрофон для конференций. Микрофон, который используется по умолчанию в этом конференц-зале.</span><span class="sxs-lookup"><span data-stu-id="da184-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="da184-192">Динамик для конференций. Динамик, который используется по умолчанию для проведения конференций. </span><span class="sxs-lookup"><span data-stu-id="da184-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="da184-193">Динамик по умолчанию. Динамик, который используется для воспроизведения звука со входа HDMI.</span><span class="sxs-lookup"><span data-stu-id="da184-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="da184-194">У каждого элемента раскрывающегося меню параметров для выбора.</span><span class="sxs-lookup"><span data-stu-id="da184-194">Each item has a drop-down menu of options to select from.</span></span> <span data-ttu-id="da184-195">Необходимо выбрать значение для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="da184-195">You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="da184-196">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="da184-196">Click **Finish**.</span></span>
    
<span data-ttu-id="da184-197">Приложение консоли комнат группы Microsoft сразу же будет запускаться вход с использованием Скайп для Business Server с использованием учетных данных, указанном выше и также должна начинать синхронизацию с сервером Exchange, используя те же учетные данные его календаря.</span><span class="sxs-lookup"><span data-stu-id="da184-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="da184-198">Для получения дополнительных сведений об использовании консольное приложение обратитесь к [помочь комнат группами Майкрософт](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="da184-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="da184-199">Комнат группами Майкрософт полагается на наличие сертифицированного консоли оборудования.</span><span class="sxs-lookup"><span data-stu-id="da184-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="da184-200">Даже правильно созданное изображение, содержащее ваше приложение консоли комнат группами Майкрософт не загружается после начального этапа процедуры Если обнаружена консоли оборудования.</span><span class="sxs-lookup"><span data-stu-id="da184-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="da184-201">Для Surface Pro на основе решений Surface Pro должен быть подключен к его сопутствующий закрепления оборудования для передачи этой проверки.</span><span class="sxs-lookup"><span data-stu-id="da184-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da184-202">Некоторые пользователи не английский язык может потребоваться физической клавиатуры, подключенной к консоли во время начальной установки, в том случае, если символы не поддерживаются в сенсорной клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="da184-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="da184-203">Установка закрытого сертификата ЦС в консоли</span><span class="sxs-lookup"><span data-stu-id="da184-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="da184-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="da184-204"></span></span>

<span data-ttu-id="da184-205">Также необходимо доверия сертификатов, используемых с Скайп для бизнеса и Exchange серверы, к которому подключен к консоли комнат группы Microsoft.</span><span class="sxs-lookup"><span data-stu-id="da184-205">The Microsoft Teams Rooms console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="da184-206">Для O365 это выполняется автоматически, поскольку этих серверов используется общедоступный центрам сертификации и они автоматически доверяет Windows 10.</span><span class="sxs-lookup"><span data-stu-id="da184-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="da184-207">В случае где сертификации — это частный, например локальное развертывание с помощью Active Directory и сертификации Windows, можно добавить сертификат в консоль комнат группами Майкрософт в несколько способов:</span><span class="sxs-lookup"><span data-stu-id="da184-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="da184-208">Присоединение к консоли в Active Directory и, автоматически добавляет требуемые сертификаты, присвоенное сертификации будет опубликована в Active Directory (обычное развертывание вариант).</span><span class="sxs-lookup"><span data-stu-id="da184-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="da184-209">Сертификат можно установить вручную после процесс обработки изображений.</span><span class="sxs-lookup"><span data-stu-id="da184-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="da184-210">Перед этим следует выполнить [Начальная настройка консоли](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="da184-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="da184-211">Чтобы вручную установить сертификат</span><span class="sxs-lookup"><span data-stu-id="da184-211">To manually install the certificate</span></span>

1. <span data-ttu-id="da184-212">Загрузка сертификата ЦС на свой компьютер и сохраните его «Systems\x64\Scripts\Provisioning\CAcertificate.cer C:\Skype комнаты».</span><span class="sxs-lookup"><span data-stu-id="da184-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="da184-213">Установите консоль в режиме admin ( [администратор режим и устройства управления](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)см).</span><span class="sxs-lookup"><span data-stu-id="da184-213">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="da184-214">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="da184-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="da184-215">Присоединение к домену Active Directory (необязательно)</span><span class="sxs-lookup"><span data-stu-id="da184-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="da184-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="da184-216"></span></span>

<span data-ttu-id="da184-217">Комнат группами Майкрософт консоли можно объединить с вашего домена.</span><span class="sxs-lookup"><span data-stu-id="da184-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="da184-218">Консоли комнат группы Microsoft должны находиться в отдельные Подразделения из рабочих станциях ПК, так как количество политик рабочей станции не совместимы с группами комнат Microsoft.</span><span class="sxs-lookup"><span data-stu-id="da184-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="da184-219">Распространенные пример, принудительное применение политики паролей, которые не позволит комнат группами Майкрософт автоматический запуск.</span><span class="sxs-lookup"><span data-stu-id="da184-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="da184-220">Сведения об управлении параметры объектов групповой Политики можно найти [Управление группами комнат Microsoft](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="da184-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="da184-221">Чтобы присоединиться к комнат группами Майкрософт в домен</span><span class="sxs-lookup"><span data-stu-id="da184-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="da184-222">Войти в консоль администрирования с учетной записью ( [режим и устройства управления Admin](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)см).</span><span class="sxs-lookup"><span data-stu-id="da184-222">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="da184-223">Запуск командной строки с повышенными привилегиями Powershell.</span><span class="sxs-lookup"><span data-stu-id="da184-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="da184-224">В Powershell введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="da184-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="da184-225">Например если redmond.corp.microsoft.com — это полное доменное и требуется вашей консоли комнат группами Майкрософт в Подразделении «Microsoft групп-залы», являющийся дочерним элементом «ресурсы» OU, команда будет:</span><span class="sxs-lookup"><span data-stu-id="da184-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="da184-226">Если вы хотите переименовать компьютер при присоединении к домену, используйте флаг - NewName, а затем новое имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="da184-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="da184-227">Контрольный список развертывания Microsoft группами комнат</span><span class="sxs-lookup"><span data-stu-id="da184-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="da184-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="da184-228"></span></span>

<span data-ttu-id="da184-229">Используйте следующий контрольный список во время выполнения действий полностью настроить консоль и всех периферийных устройств:</span><span class="sxs-lookup"><span data-stu-id="da184-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="da184-230">**Параметры приложения**</span><span class="sxs-lookup"><span data-stu-id="da184-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="da184-231">☐</span><span class="sxs-lookup"><span data-stu-id="da184-231">☐</span></span>  <br/> |<span data-ttu-id="da184-232">Аудитория имя учетной записи и телефон # (если включены PSTN) правильно отображаются в верхней правой части экрана консоли</span><span class="sxs-lookup"><span data-stu-id="da184-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="da184-233">☐</span><span class="sxs-lookup"><span data-stu-id="da184-233">☐</span></span>  <br/> |<span data-ttu-id="da184-234">Имя компьютера Windows установлен правильно (полезно для удаленного администрирования)</span><span class="sxs-lookup"><span data-stu-id="da184-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="da184-235">☐</span><span class="sxs-lookup"><span data-stu-id="da184-235">☐</span></span>  <br/> |<span data-ttu-id="da184-236">Установка пароля учетной записи администратора и проверки</span><span class="sxs-lookup"><span data-stu-id="da184-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="da184-237">☐</span><span class="sxs-lookup"><span data-stu-id="da184-237">☐</span></span>  <br/> |<span data-ttu-id="da184-238">Были применены все обновления встроенного по</span><span class="sxs-lookup"><span data-stu-id="da184-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="da184-239">**Периферийных аудио и видео**</span><span class="sxs-lookup"><span data-stu-id="da184-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="da184-240">☐</span><span class="sxs-lookup"><span data-stu-id="da184-240">☐</span></span>  <br/> |<span data-ttu-id="da184-241">Версия микропрограммы периферийных камеры правильный (если применимо)</span><span class="sxs-lookup"><span data-stu-id="da184-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="da184-242">☐</span><span class="sxs-lookup"><span data-stu-id="da184-242">☐</span></span>  <br/> |<span data-ttu-id="da184-243">Камера работоспособно и оптимально расположенных</span><span class="sxs-lookup"><span data-stu-id="da184-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="da184-244">☐</span><span class="sxs-lookup"><span data-stu-id="da184-244">☐</span></span>  <br/> |<span data-ttu-id="da184-245">Для воспроизведения устройства по умолчанию и воспроизведения устройства связи по умолчанию установлен предполагаемая аудио периферийный</span><span class="sxs-lookup"><span data-stu-id="da184-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="da184-246">☐</span><span class="sxs-lookup"><span data-stu-id="da184-246">☐</span></span>  <br/> |<span data-ttu-id="da184-247">Параметры для устройства записи по умолчанию связи равной периферийный предполагаемая звука</span><span class="sxs-lookup"><span data-stu-id="da184-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="da184-248">☐</span><span class="sxs-lookup"><span data-stu-id="da184-248">☐</span></span>  <br/> |<span data-ttu-id="da184-249">Версия микропрограммы звука периферийный правильный (если применимо)</span><span class="sxs-lookup"><span data-stu-id="da184-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="da184-250">☐</span><span class="sxs-lookup"><span data-stu-id="da184-250">☐</span></span>  <br/> |<span data-ttu-id="da184-251">Звуковое устройство ввода работоспособно и оптимально расположенных</span><span class="sxs-lookup"><span data-stu-id="da184-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="da184-252">☐</span><span class="sxs-lookup"><span data-stu-id="da184-252">☐</span></span>  <br/> |<span data-ttu-id="da184-253">Функциональные и оптимально находится устройстве аудиовыхода</span><span class="sxs-lookup"><span data-stu-id="da184-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="da184-254">**Закрепление**</span><span class="sxs-lookup"><span data-stu-id="da184-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="da184-255">☐</span><span class="sxs-lookup"><span data-stu-id="da184-255">☐</span></span>  <br/> |<span data-ttu-id="da184-256">Кабели безопасной и не pinched</span><span class="sxs-lookup"><span data-stu-id="da184-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="da184-257">☐</span><span class="sxs-lookup"><span data-stu-id="da184-257">☐</span></span>  <br/> |<span data-ttu-id="da184-258">Звук потребления по функциональным HDMI</span><span class="sxs-lookup"><span data-stu-id="da184-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="da184-259">☐</span><span class="sxs-lookup"><span data-stu-id="da184-259">☐</span></span>  <br/> |<span data-ttu-id="da184-260">Видео потребления по функциональным HDMI</span><span class="sxs-lookup"><span data-stu-id="da184-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="da184-261">☐</span><span class="sxs-lookup"><span data-stu-id="da184-261">☐</span></span>  <br/> |<span data-ttu-id="da184-262">Закрепление могут свободно Скольжение</span><span class="sxs-lookup"><span data-stu-id="da184-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="da184-263">☐</span><span class="sxs-lookup"><span data-stu-id="da184-263">☐</span></span>  <br/> |<span data-ttu-id="da184-264">Яркости экрана является приемлемым для среды</span><span class="sxs-lookup"><span data-stu-id="da184-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="da184-265">См. также</span><span class="sxs-lookup"><span data-stu-id="da184-265">See also</span></span>
<span data-ttu-id="da184-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="da184-266"></span></span>

[<span data-ttu-id="da184-267">Планирование для групп Майкрософт комнат</span><span class="sxs-lookup"><span data-stu-id="da184-267">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="da184-268">Развертывание групп Майкрософт комнат</span><span class="sxs-lookup"><span data-stu-id="da184-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="da184-269">Настройка консоли комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="da184-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="da184-270">Управление группами Майкрософт комнат</span><span class="sxs-lookup"><span data-stu-id="da184-270">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)