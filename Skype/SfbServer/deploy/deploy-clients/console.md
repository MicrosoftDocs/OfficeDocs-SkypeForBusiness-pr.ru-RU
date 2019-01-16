---
title: Настройка консоли для Систем комнат Skype версии 2
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: В этой статье описывается настройка консоли версии 2 Скайп комнаты систем и его периферийных устройств.
ms.openlocfilehash: fab2854406e22b156c8fcca76e6701214199f62c
ms.sourcegitcommit: d3708702393ac434344c758959109a3be2b3bfa4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "28324936"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="c507c-103">Настройка консоли для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c507c-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="c507c-104">В этой статье описывается настройка консоли версии 2 Скайп комнаты систем и его периферийных устройств.</span><span class="sxs-lookup"><span data-stu-id="c507c-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="c507c-105">Эти действия следует выполнять только в том случае, при необходимости Скайп для учетных записей Exchange и бизнес-уже создан и проверен, как описано в [Развертывание системы комнаты Скайп версии 2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c507c-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="c507c-106">Необходимо будет требованиях к оборудованию и программному обеспечению, описанные в [системах комнаты Скайп требования к версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c507c-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="c507c-107">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="c507c-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="c507c-108">Подготовка установочного носителя</span><span class="sxs-lookup"><span data-stu-id="c507c-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="c507c-109">Установка закрытого сертификата ЦС в консоли</span><span class="sxs-lookup"><span data-stu-id="c507c-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="c507c-110">Установка Windows 10 и консольного приложения Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c507c-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="c507c-111">Начальный набор копирование консоли</span><span class="sxs-lookup"><span data-stu-id="c507c-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="c507c-112">Контрольный список развертывания систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="c507c-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="c507c-113">Версии 2 систем комнаты Скайп вариант возможен только в правильно настроенных Скайп для бизнес-среде, где учетные записи устройства правильно настроены как описано в [Развертывание системы комнаты Скайп версии 2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c507c-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="c507c-114">Подготовка установочного носителя</span><span class="sxs-lookup"><span data-stu-id="c507c-114">Prepare the installation media</span></span>
<span data-ttu-id="c507c-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="c507c-115"></span></span>

<span data-ttu-id="c507c-116">Установка приложения консоли систем комнаты Скайп v2 требуется USB-накопитель с по крайней мере 32 ГБ.</span><span class="sxs-lookup"><span data-stu-id="c507c-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="c507c-117">Должно быть не файлы на устройстве; все существующие файлы на хранение USB будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="c507c-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c507c-118">Сбой для создания систем комнаты Скайп v2 установочного носителя в соответствии с этим инструкциям, могут измениться в непредвиденных последствий.</span><span class="sxs-lookup"><span data-stu-id="c507c-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="c507c-119">Для создания установочного носителя изображения устройствам системы комнаты Скайп версии 2 — приведенной ниже процедуре.</span><span class="sxs-lookup"><span data-stu-id="c507c-119">The process below is for creating installation media to image new Skype Room System v2 devices.</span></span> <span data-ttu-id="c507c-120">Существующего устройства по умолчанию, автоматического обновления из центра обновления Windows и магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="c507c-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="c507c-121">Скачайте [сценарий CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842). </span><span class="sxs-lookup"><span data-stu-id="c507c-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="c507c-122">Запустите сценарий CreateSrsMedia.ps1 из командной строки с повышенными привилегиями на компьютере с ОС Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c507c-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="c507c-123">Следуйте инструкциям, сценарий для создания диска настройки систем комнаты Скайп USB версии 2.</span><span class="sxs-lookup"><span data-stu-id="c507c-123">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span>

<span data-ttu-id="c507c-124">После завершения удаления USB-диска со своего компьютера и перейдите к [10 Установка Windows и систем комнаты Скайп v2 консольное приложение](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="c507c-124">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="c507c-125">Установка Windows 10 и консольного приложения Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c507c-125">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="c507c-126"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="c507c-126"></span></span>

<span data-ttu-id="c507c-127">Теперь необходимо применить установочном носителе, созданные пользователем.</span><span class="sxs-lookup"><span data-stu-id="c507c-127">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="c507c-128">Устройство будет работать как устройства и пользователей по умолчанию присваивается значение только запуска приложения консоли систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="c507c-128">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="c507c-129">Если устройство будет установлен в приемки (например, Surface Pro), отключите его из приемки.</span><span class="sxs-lookup"><span data-stu-id="c507c-129">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="c507c-130">Убедитесь, что носитель не подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="c507c-130">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="c507c-131">Убедитесь, что устройство конечного подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="c507c-131">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="c507c-132">Подключите на диске установки USB целевого устройства.</span><span class="sxs-lookup"><span data-stu-id="c507c-132">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="c507c-133">Загрузите установочный диск USB.</span><span class="sxs-lookup"><span data-stu-id="c507c-133">Boot to the USB setup disk.</span></span> <span data-ttu-id="c507c-134">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="c507c-134">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="c507c-135">Если ваше устройство Surface Pro, выполните следующие действия для загрузки на диске установки USB:</span><span class="sxs-lookup"><span data-stu-id="c507c-135">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    1. <span data-ttu-id="c507c-136">Нажмите клавишу, удерживая тома нажатой кнопку (-).</span><span class="sxs-lookup"><span data-stu-id="c507c-136">Press and continue to hold the volume down (-) button.</span></span>

    2. <span data-ttu-id="c507c-137">Нажмите клавишу и кнопку питания.</span><span class="sxs-lookup"><span data-stu-id="c507c-137">Press and release the power button.</span></span>

    3. <span data-ttu-id="c507c-138">После загрузки установки Windows отпустите кнопку уменьшения громкости (–).</span><span class="sxs-lookup"><span data-stu-id="c507c-138">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="c507c-139">Система завершит работу после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="c507c-139">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="c507c-140">После выпуска системы завершил работу, сообщением о возможности удаления установочный диск USB.</span><span class="sxs-lookup"><span data-stu-id="c507c-140">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="c507c-141">На этом этапе можно поместить целевого устройства в его приемки (при использовании продуктов на основе закрепления), периферийных устройств, необходимые для вашего комнату переговоров с подключением и подключиться к сети.</span><span class="sxs-lookup"><span data-stu-id="c507c-141">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="c507c-142">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="c507c-142">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="c507c-143">Выбор языка</span><span class="sxs-lookup"><span data-stu-id="c507c-143">Selecting a language</span></span> 

<span data-ttu-id="c507c-144">В обновлении создателя, необходимо использовать сценарий ApplyCurrentRegionAndLanguage.ps1 в сценариях, где неявных язык не обеспечивает пользователя с языка приложения, они должны (например, они должны консольное приложение, чтобы отображалось на французском языке, но оно будет на английском языке).</span><span class="sxs-lookup"><span data-stu-id="c507c-144">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c507c-145">Следующие инструкции работает только для консоли, созданные с помощью центра обновления Windows создателя.</span><span class="sxs-lookup"><span data-stu-id="c507c-145">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="c507c-146">Устаревшие/в рынка систем, которые не были настроены с помощью мультимедиа с новой подготовки системы не сможет использовать эти инструкции, но должны также могут испытывать из начального проблеме, которую нужно этот вмешательства (Годовщина Edition позволяет выбрать вашей язык приложения явно как часть процесса установки).</span><span class="sxs-lookup"><span data-stu-id="c507c-146">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="c507c-147">Применение необходимого языка</span><span class="sxs-lookup"><span data-stu-id="c507c-147">To apply your desired language</span></span>

1. <span data-ttu-id="c507c-148">Переключитесь в режим администрирования.</span><span class="sxs-lookup"><span data-stu-id="c507c-148">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="c507c-149">Откройте меню "Пуск".</span><span class="sxs-lookup"><span data-stu-id="c507c-149">Select the Start menu.</span></span>
    
3. <span data-ttu-id="c507c-150">Щелкните значок шестеренки, чтобы запустить приложение **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="c507c-150">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="c507c-151">Выберите **время &amp; языка**.</span><span class="sxs-lookup"><span data-stu-id="c507c-151">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="c507c-152">Выберите **области &amp; языка**.</span><span class="sxs-lookup"><span data-stu-id="c507c-152">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="c507c-153">Выберите **Добавить язык**.</span><span class="sxs-lookup"><span data-stu-id="c507c-153">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="c507c-154">Выберите язык, который требуется добавить.</span><span class="sxs-lookup"><span data-stu-id="c507c-154">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="c507c-155">Выберите язык, который вы только что добавили в список «Языки».</span><span class="sxs-lookup"><span data-stu-id="c507c-155">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="c507c-156">Выберите **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="c507c-156">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="c507c-157">Удаление языков</span><span class="sxs-lookup"><span data-stu-id="c507c-157">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="c507c-p108">а. Выберите язык, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c507c-p108">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="c507c-p109">б. Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c507c-p109">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="c507c-162">Запустите командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="c507c-162">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="c507c-163">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="c507c-163">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="c507c-164">Перезапустите систему.</span><span class="sxs-lookup"><span data-stu-id="c507c-164">Restart the system.</span></span>
    
<span data-ttu-id="c507c-165">Язык теперь применяется к консоли систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="c507c-165">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="c507c-166">Начальный набор копирование консоли</span><span class="sxs-lookup"><span data-stu-id="c507c-166">Initial set up of the console</span></span>
<span data-ttu-id="c507c-167"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="c507c-167"></span></span>

<span data-ttu-id="c507c-168">После установки Windows при следующем запуске или, если выбран параметр/reboot консольное приложение версии 2 Скайп комнаты систем перейдет в его начальной установки и настройки устройств.</span><span class="sxs-lookup"><span data-stu-id="c507c-168">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="c507c-169">Появится экран "Учетная запись пользователя".</span><span class="sxs-lookup"><span data-stu-id="c507c-169">The User Account screen appears.</span></span> <span data-ttu-id="c507c-170">Введите Скайп адрес для входа (в формате user@domain) комнаты учетной записи для использования с помощью консоли.</span><span class="sxs-lookup"><span data-stu-id="c507c-170">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="c507c-171">Введите пароль для учетной записи комнаты и подтвердите его.</span><span class="sxs-lookup"><span data-stu-id="c507c-171">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="c507c-172">В разделе «Настройка домена» задайте полное доменное имя для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="c507c-172">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="c507c-173">Если Скайп для бизнеса SIP-домена отличается от домена Exchange пользователя, введите домен Exchange в этом поле.</span><span class="sxs-lookup"><span data-stu-id="c507c-173">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="c507c-174">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c507c-174">Click **Next**.</span></span>
    
5. <span data-ttu-id="c507c-175">Выберите указанный устройства, на экране компонентов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c507c-175">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="c507c-176">По умолчанию автоматическая демонстрация экрана включена, а скрытие имен во время собрания отключено.</span><span class="sxs-lookup"><span data-stu-id="c507c-176">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="c507c-177">Для выбора доступны следующие устройства:</span><span class="sxs-lookup"><span data-stu-id="c507c-177">The devices to select are:</span></span>
    
   - <span data-ttu-id="c507c-178">Микрофон для конференций. Микрофон, который используется по умолчанию в этом конференц-зале.</span><span class="sxs-lookup"><span data-stu-id="c507c-178">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="c507c-179">Динамик для конференций. Динамик, который используется по умолчанию для проведения конференций. </span><span class="sxs-lookup"><span data-stu-id="c507c-179">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="c507c-180">Динамик по умолчанию. Динамик, который используется для воспроизведения звука со входа HDMI.</span><span class="sxs-lookup"><span data-stu-id="c507c-180">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="c507c-p113">Параметры каждого элемента можно настроить в соответствующем раскрывающемся списке. Необходимо сделать выбор для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="c507c-p113">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="c507c-183">Нажмите кнопку \*\*Готово \*\*.</span><span class="sxs-lookup"><span data-stu-id="c507c-183">Click **Finish**.</span></span>
    
<span data-ttu-id="c507c-184">Приложение консоли версии 2 Скайп комнаты систем сразу же будет запускаться вход с использованием Скайп для Business Server с использованием учетных данных, указанном выше и также должна начинать синхронизацию его календаря с сервером Exchange, используя те же учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c507c-184">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="c507c-185">Для получения дополнительных сведений об использовании консольное приложение обратитесь к [Скайп комнаты систем версии 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="c507c-185">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c507c-186">Версии 2 Скайп комнаты систем полагается на наличие сертифицированного консоли оборудования.</span><span class="sxs-lookup"><span data-stu-id="c507c-186">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="c507c-187">Даже правильно созданное изображение, содержащее ваше приложение консоли систем комнаты Скайп версии 2 не загружается после начального этапа процедуры Если обнаружена консоли оборудования.</span><span class="sxs-lookup"><span data-stu-id="c507c-187">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="c507c-188">Для Surface Pro на основе решений Surface Pro должен быть подключен к его сопутствующий закрепления оборудования для передачи этой проверки.</span><span class="sxs-lookup"><span data-stu-id="c507c-188">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c507c-189">Некоторые пользователи не английский язык может потребоваться физической клавиатуры, подключенной к консоли во время начальной установки, в том случае, если символы не поддерживаются в сенсорной клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="c507c-189">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="c507c-190">Установка закрытого сертификата ЦС в консоли</span><span class="sxs-lookup"><span data-stu-id="c507c-190">Install a private CA certificate on the console</span></span>
<span data-ttu-id="c507c-191"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c507c-191"></span></span>

<span data-ttu-id="c507c-192">Также необходимо доверия сертификатов, используемых с Скайп для бизнеса и Exchange серверы, к которому подключен к консоли систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="c507c-192">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="c507c-193">В O365 это реализуется автоматически, так как соответствующие серверы используют общедоступные центры сертификации, по умолчанию являющиеся доверенными в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c507c-193">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="c507c-194">В случае где сертификации — это частный, например локальное развертывание с помощью Active Directory и сертификации Windows, можно добавить сертификат на консоль систем комнаты Скайп версии 2 в несколько способов:</span><span class="sxs-lookup"><span data-stu-id="c507c-194">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="c507c-195">Присоединение к консоли в Active Directory и, автоматически добавляет требуемые сертификаты, присвоенное сертификации будет опубликована в Active Directory (обычное развертывание вариант).</span><span class="sxs-lookup"><span data-stu-id="c507c-195">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="c507c-196">Сертификат можно установить вручную после завершения создания образа.</span><span class="sxs-lookup"><span data-stu-id="c507c-196">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="c507c-197">Перед этим следует выполнить [Начальная настройка консоли](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="c507c-197">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="c507c-198">Установка сертификата вручную </span><span class="sxs-lookup"><span data-stu-id="c507c-198">To manually install the certificate</span></span>

1. <span data-ttu-id="c507c-199">Скачайте сертификат ЦС на компьютер и сохраните его в папке C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer.</span><span class="sxs-lookup"><span data-stu-id="c507c-199">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="c507c-200">Установите консоль в режиме admin ( [администратор режим и устройства управления](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)см).</span><span class="sxs-lookup"><span data-stu-id="c507c-200">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="c507c-201">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="c507c-201">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="c507c-202">Присоединение к домену Active Directory (необязательно)</span><span class="sxs-lookup"><span data-stu-id="c507c-202">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="c507c-203"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c507c-203"></span></span>

<span data-ttu-id="c507c-204">Скайп помещения систем версии 2 консоли можно объединить с вашего домена.</span><span class="sxs-lookup"><span data-stu-id="c507c-204">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="c507c-205">Систем комнаты Скайп версии 2 консоли должны находиться в отдельные Подразделения из рабочих станциях ПК, так как количество политик рабочей станции не совместимы с системами комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="c507c-205">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="c507c-206">Распространенные пример, принудительное применение политики паролей, которые не позволит систем комнаты Скайп v2 автоматический запуск.</span><span class="sxs-lookup"><span data-stu-id="c507c-206">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="c507c-207">Информацию об управлении параметрами GPO см. в статье [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c507c-207">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="c507c-208">Присоединение Систем комнат Skype версии 2 к домену</span><span class="sxs-lookup"><span data-stu-id="c507c-208">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="c507c-209">Войти в консоль администрирования с учетной записью ( [режим и устройства управления Admin](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)см).</span><span class="sxs-lookup"><span data-stu-id="c507c-209">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="c507c-210">Запустите командную строку Powershell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="c507c-210">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="c507c-211">Введите следующую команду в Powershell:</span><span class="sxs-lookup"><span data-stu-id="c507c-211">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="c507c-212">Например, если redmond.corp.microsoft.com — это полное доменное, и вы хотите вашей консоли систем комнаты Скайп версии 2 в «v2 систем комнаты Скайп» Подразделения, являющийся дочерним элементом «ресурсы» Подразделение, команда будет:</span><span class="sxs-lookup"><span data-stu-id="c507c-212">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="c507c-213">Если вы хотите переименовать компьютер при присоединении к домену, используйте флаг - NewName, а затем новое имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="c507c-213">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="c507c-214">Контрольный список развертывания систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="c507c-214">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="c507c-215"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c507c-215"></span></span>

<span data-ttu-id="c507c-216">Используйте следующий контрольный список во время выполнения действий полностью настроить консоль и всех периферийных устройств:</span><span class="sxs-lookup"><span data-stu-id="c507c-216">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="c507c-217">**Параметры приложения**</span><span class="sxs-lookup"><span data-stu-id="c507c-217">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c507c-218">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-218">☐</span></span>  <br/> |<span data-ttu-id="c507c-219">В верхнем правом углу экрана консоли правильно отображаются название учетной записи комнаты и номер телефона (если доступна ТСОП).</span><span class="sxs-lookup"><span data-stu-id="c507c-219">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="c507c-220">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-220">☐</span></span>  <br/> |<span data-ttu-id="c507c-221">Правильно задано имя компьютера Windows (для удаленного администрирования)</span><span class="sxs-lookup"><span data-stu-id="c507c-221">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="c507c-222">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-222">☐</span></span>  <br/> |<span data-ttu-id="c507c-223">Задан и подтвержден пароль учетной записи администратора</span><span class="sxs-lookup"><span data-stu-id="c507c-223">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="c507c-224">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-224">☐</span></span>  <br/> |<span data-ttu-id="c507c-225">Были применены все обновления встроенного по</span><span class="sxs-lookup"><span data-stu-id="c507c-225">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="c507c-226">**Периферийных аудио и видео**</span><span class="sxs-lookup"><span data-stu-id="c507c-226">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c507c-227">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-227">☐</span></span>  <br/> |<span data-ttu-id="c507c-228">Указана правильная версия встроенного ПО периферийной камеры (если применимо)</span><span class="sxs-lookup"><span data-stu-id="c507c-228">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c507c-229">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-229">☐</span></span>  <br/> |<span data-ttu-id="c507c-230">Камера работоспособно и оптимально расположенных</span><span class="sxs-lookup"><span data-stu-id="c507c-230">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="c507c-231">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-231">☐</span></span>  <br/> |<span data-ttu-id="c507c-232">В качестве используемого по умолчанию устройства воспроизведения и устройства связи для воспроизведения задано нужное периферийное звуковое устройство</span><span class="sxs-lookup"><span data-stu-id="c507c-232">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c507c-233">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-233">☐</span></span>  <br/> |<span data-ttu-id="c507c-234">В качестве используемого по умолчанию устройства связи для записи задано нужное периферийное звуковое устройство</span><span class="sxs-lookup"><span data-stu-id="c507c-234">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c507c-235">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-235">☐</span></span>  <br/> |<span data-ttu-id="c507c-236">Указана правильная версия встроенного ПО периферийного звукового устройства (если применимо)</span><span class="sxs-lookup"><span data-stu-id="c507c-236">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c507c-237">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-237">☐</span></span>  <br/> |<span data-ttu-id="c507c-238">Входное звуковое устройство работает и правильно расположено</span><span class="sxs-lookup"><span data-stu-id="c507c-238">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="c507c-239">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-239">☐</span></span>  <br/> |<span data-ttu-id="c507c-240">Выходное звуковое устройство работает и правильно расположено</span><span class="sxs-lookup"><span data-stu-id="c507c-240">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="c507c-241">**Док-станция**</span><span class="sxs-lookup"><span data-stu-id="c507c-241">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c507c-242">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-242">☐</span></span>  <br/> |<span data-ttu-id="c507c-243">Все кабели закреплены и не пережаты</span><span class="sxs-lookup"><span data-stu-id="c507c-243">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="c507c-244">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-244">☐</span></span>  <br/> |<span data-ttu-id="c507c-245">Работает прием звукового сигнала через HDMI</span><span class="sxs-lookup"><span data-stu-id="c507c-245">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c507c-246">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-246">☐</span></span>  <br/> |<span data-ttu-id="c507c-247">Работает прием видеосигнала через HDMI</span><span class="sxs-lookup"><span data-stu-id="c507c-247">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c507c-248">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-248">☐</span></span>  <br/> |<span data-ttu-id="c507c-249">Док-станция свободно вращается</span><span class="sxs-lookup"><span data-stu-id="c507c-249">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="c507c-250">☐</span><span class="sxs-lookup"><span data-stu-id="c507c-250">☐</span></span>  <br/> |<span data-ttu-id="c507c-251">Яркость экрана соответствует обстановке</span><span class="sxs-lookup"><span data-stu-id="c507c-251">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c507c-252">Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.</span><span class="sxs-lookup"><span data-stu-id="c507c-252">See also</span></span>
<span data-ttu-id="c507c-253"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c507c-253"></span></span>

[<span data-ttu-id="c507c-254">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="c507c-254">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="c507c-255">Развертывание Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c507c-255">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="c507c-256">Настройка консоли для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c507c-256">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="c507c-257">Управление Системами комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c507c-257">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)