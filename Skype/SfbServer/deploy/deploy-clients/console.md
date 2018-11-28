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
ms.openlocfilehash: 4218365e7cb4b396d3e93d3fa969546138ace33d
ms.sourcegitcommit: 336a9c95602d58ff069e4990b340e376a2d0d809
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26716376"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="c9139-103">Настройка консоли для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c9139-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="c9139-104">В этой статье описывается настройка консоли версии 2 Скайп комнаты систем и его периферийных устройств.</span><span class="sxs-lookup"><span data-stu-id="c9139-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="c9139-105">Эти действия следует выполнять только в том случае, при необходимости Скайп для учетных записей Exchange и бизнес-уже создан и проверен, как описано в [Развертывание системы комнаты Скайп версии 2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c9139-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="c9139-106">Необходимо будет требованиях к оборудованию и программному обеспечению, описанные в [системах комнаты Скайп требования к версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9139-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="c9139-107">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="c9139-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="c9139-108">Подготовка установочного носителя</span><span class="sxs-lookup"><span data-stu-id="c9139-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="c9139-109">Установка закрытого сертификата ЦС в консоли</span><span class="sxs-lookup"><span data-stu-id="c9139-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="c9139-110">Установка Windows 10 и консольного приложения Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c9139-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="c9139-111">Начальный набор копирование консоли</span><span class="sxs-lookup"><span data-stu-id="c9139-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="c9139-112">Контрольный список развертывания систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="c9139-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="c9139-113">Версии 2 систем комнаты Скайп вариант возможен только в правильно настроенных Скайп для бизнес-среде, где учетные записи устройства правильно настроены как описано в [Развертывание системы комнаты Скайп версии 2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c9139-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="c9139-114">Подготовка установочного носителя</span><span class="sxs-lookup"><span data-stu-id="c9139-114">Prepare the installation media</span></span>
<span data-ttu-id="c9139-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="c9139-115"></span></span>

<span data-ttu-id="c9139-116">Установка приложения консоли систем комнаты Скайп v2 требуется USB-накопитель с по крайней мере 32 ГБ оперативной памяти, отформатированные в FAT32 диска.</span><span class="sxs-lookup"><span data-stu-id="c9139-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="c9139-117">На устройстве USB не должно быть других файлов, иначе они будут удалены.</span><span class="sxs-lookup"><span data-stu-id="c9139-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9139-118">Сбой для создания систем комнаты Скайп v2 установочного носителя в соответствии с этим инструкциям, могут измениться в непредвиденных последствий.</span><span class="sxs-lookup"><span data-stu-id="c9139-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="c9139-119">Годовщина Enterprise 10 Windows Update (версия 1607) больше не поддерживается для создания носителя установки систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="c9139-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 installation media creation.</span></span>

> [!NOTE]
> <span data-ttu-id="c9139-120">Существующей версии 2 Скайп комнаты систем с помощью Windows 10 Enterprise переход к версии 2 систем комнаты Скайп обновление 3 путем получения магазина Windows будет работать, но необходимо провести новую установку, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="c9139-120">An existing Skype Room Systems v2 with Windows 10 Enterprise moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span>
  
1. <span data-ttu-id="c9139-121">Скачайте [сценарий CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842). </span><span class="sxs-lookup"><span data-stu-id="c9139-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="c9139-122">(Необязательно) Загрузите и установите любой язык пакета CAB-файлов в одном каталоге с скрипта.</span><span class="sxs-lookup"><span data-stu-id="c9139-122">(Optional) Download and place any desired language pack CAB files in the same directory as the script.</span></span> <span data-ttu-id="c9139-123">Скрипт будет указывать, где можно загрузить файлы языкового пакета, соответствующий тип носителя, который вы создаете, если вы не уверены в том where для получения языковые пакеты из.</span><span class="sxs-lookup"><span data-stu-id="c9139-123">The script will indicate where you can download language pack files appropriate for the type of media you are creating, if you're unsure where to acquire the language packs from.</span></span>
3. <span data-ttu-id="c9139-124">Запустите сценарий CreateSrsMedia.ps1 из командной строки с повышенными привилегиями на компьютере с ОС Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c9139-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>

<span data-ttu-id="c9139-125">Следуйте инструкциям, сценарий для создания диска настройки систем комнаты Скайп USB версии 2.</span><span class="sxs-lookup"><span data-stu-id="c9139-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="c9139-126">После завершения удаления USB-диска со своего компьютера и перейдите к [10 Установка Windows и систем комнаты Скайп v2 консольное приложение](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="c9139-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>

> [!TIP]
> <span data-ttu-id="c9139-127">Вы могли заметить, что мы больше не ответный звонок определенных версий драйверов, клиентских систем комнаты Скайп версии 2 или Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c9139-127">You might have noticed that we no longer call out specific versions of the drivers, Skype Room Systems v2 client, or Windows 10 Enterprise.</span></span> <span data-ttu-id="c9139-128">Это можно опустить, мы хотим скрипта для сопоставления и проверки совместимости для всех программ установки.</span><span class="sxs-lookup"><span data-stu-id="c9139-128">This is deliberate, we want the script to match and verify compatibility for all installers.</span></span> <span data-ttu-id="c9139-129">Скрипт автоматически поиск и получение необходимых для поддерживаемых конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c9139-129">The script will automatically find and get what it needs for a supported configuration.</span></span>  
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="c9139-130">Установка Windows 10 и консольного приложения Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c9139-130">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="c9139-131"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="c9139-131"></span></span>

<span data-ttu-id="c9139-132">Теперь необходимо применить установочном носителе, созданные пользователем.</span><span class="sxs-lookup"><span data-stu-id="c9139-132">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="c9139-133">Устройство будет работать как устройства и пользователей по умолчанию присваивается значение только запуска приложения консоли систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="c9139-133">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="c9139-134">Если устройство будет установлен в приемки (например, Surface Pro), отключите его из приемки.</span><span class="sxs-lookup"><span data-stu-id="c9139-134">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="c9139-135">Убедитесь, что носитель не подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="c9139-135">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="c9139-136">Убедитесь, что устройство конечного подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="c9139-136">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="c9139-137">Подключите на диске установки USB целевого устройства.</span><span class="sxs-lookup"><span data-stu-id="c9139-137">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="c9139-138">Загрузите установочный диск USB.</span><span class="sxs-lookup"><span data-stu-id="c9139-138">Boot to the USB setup disk.</span></span> <span data-ttu-id="c9139-139">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="c9139-139">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="c9139-140">Если ваше устройство Surface Pro, выполните следующие действия для загрузки на диске установки USB:</span><span class="sxs-lookup"><span data-stu-id="c9139-140">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    1. <span data-ttu-id="c9139-141">Нажмите клавишу, удерживая тома нажатой кнопку (-).</span><span class="sxs-lookup"><span data-stu-id="c9139-141">Press and continue to hold the volume down (-) button.</span></span>

    2. <span data-ttu-id="c9139-142">Нажмите клавишу и кнопку питания.</span><span class="sxs-lookup"><span data-stu-id="c9139-142">Press and release the power button.</span></span>

    3. <span data-ttu-id="c9139-143">После загрузки установки Windows отпустите кнопку уменьшения громкости (–).</span><span class="sxs-lookup"><span data-stu-id="c9139-143">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="c9139-144">Система завершит работу после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="c9139-144">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="c9139-145">После выпуска системы завершил работу, сообщением о возможности удаления установочный диск USB.</span><span class="sxs-lookup"><span data-stu-id="c9139-145">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="c9139-146">На этом этапе можно поместить целевого устройства в его приемки (при использовании продуктов на основе закрепления), периферийных устройств, необходимые для вашего комнату переговоров с подключением и подключиться к сети.</span><span class="sxs-lookup"><span data-stu-id="c9139-146">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="c9139-147">Следуйте инструкциям производителя.</span><span class="sxs-lookup"><span data-stu-id="c9139-147">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="c9139-148">Выбор языка</span><span class="sxs-lookup"><span data-stu-id="c9139-148">Selecting a language</span></span> 

<span data-ttu-id="c9139-149">В обновлении создателя, необходимо использовать сценарий ApplyCurrentRegionAndLanguage.ps1 в сценариях, где неявных язык не обеспечивает пользователя с языка приложения, они должны (например, они должны консольное приложение, чтобы отображалось на французском языке, но оно будет на английском языке).</span><span class="sxs-lookup"><span data-stu-id="c9139-149">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9139-150">Следующие инструкции работает только для консоли, созданные с помощью центра обновления Windows создателя.</span><span class="sxs-lookup"><span data-stu-id="c9139-150">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="c9139-151">Устаревшие/в рынка систем, которые не были настроены с помощью мультимедиа с новой подготовки системы не сможет использовать эти инструкции, но должны также могут испытывать из начального проблеме, которую нужно этот вмешательства (Годовщина Edition позволяет выбрать вашей язык приложения явно как часть процесса установки).</span><span class="sxs-lookup"><span data-stu-id="c9139-151">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="c9139-152">Применение необходимого языка</span><span class="sxs-lookup"><span data-stu-id="c9139-152">To apply your desired language</span></span>

1. <span data-ttu-id="c9139-153">Переключитесь в режим администрирования.</span><span class="sxs-lookup"><span data-stu-id="c9139-153">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="c9139-154">Откройте меню "Пуск".</span><span class="sxs-lookup"><span data-stu-id="c9139-154">Select the Start menu.</span></span>
    
3. <span data-ttu-id="c9139-155">Щелкните значок шестеренки, чтобы запустить приложение **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="c9139-155">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="c9139-156">Выберите **время &amp; языка**.</span><span class="sxs-lookup"><span data-stu-id="c9139-156">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="c9139-157">Выберите **области &amp; языка**.</span><span class="sxs-lookup"><span data-stu-id="c9139-157">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="c9139-158">Выберите **Добавить язык**.</span><span class="sxs-lookup"><span data-stu-id="c9139-158">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="c9139-159">Выберите язык, который требуется добавить.</span><span class="sxs-lookup"><span data-stu-id="c9139-159">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="c9139-160">Выберите язык, который вы только что добавили в список «Языки».</span><span class="sxs-lookup"><span data-stu-id="c9139-160">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="c9139-161">Выберите **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="c9139-161">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="c9139-162">Удаление языков</span><span class="sxs-lookup"><span data-stu-id="c9139-162">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="c9139-p111">а. Выберите язык, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c9139-p111">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="c9139-p112">б. Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c9139-p112">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="c9139-167">Запустите командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="c9139-167">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="c9139-168">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="c9139-168">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="c9139-169">Перезапустите систему.</span><span class="sxs-lookup"><span data-stu-id="c9139-169">Restart the system.</span></span>
    
<span data-ttu-id="c9139-170">Язык теперь применяется к консоли систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="c9139-170">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="c9139-171">Начальный набор копирование консоли</span><span class="sxs-lookup"><span data-stu-id="c9139-171">Initial set up of the console</span></span>
<span data-ttu-id="c9139-172"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="c9139-172"></span></span>

<span data-ttu-id="c9139-173">После установки Windows при следующем запуске или, если выбран параметр/reboot консольное приложение версии 2 Скайп комнаты систем перейдет в его начальной установки и настройки устройств.</span><span class="sxs-lookup"><span data-stu-id="c9139-173">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="c9139-174">Появится экран "Учетная запись пользователя".</span><span class="sxs-lookup"><span data-stu-id="c9139-174">The User Account screen appears.</span></span> <span data-ttu-id="c9139-175">Введите Скайп адрес для входа (в формате user@domain) комнаты учетной записи для использования с помощью консоли.</span><span class="sxs-lookup"><span data-stu-id="c9139-175">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="c9139-176">Введите пароль для учетной записи комнаты и подтвердите его.</span><span class="sxs-lookup"><span data-stu-id="c9139-176">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="c9139-177">В разделе «Настройка домена» задайте полное доменное имя для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9139-177">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="c9139-178">Если Скайп для бизнеса SIP-домена отличается от домена Exchange пользователя, введите домен Exchange в этом поле.</span><span class="sxs-lookup"><span data-stu-id="c9139-178">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="c9139-179">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c9139-179">Click **Next**.</span></span>
    
5. <span data-ttu-id="c9139-180">Выберите указанный устройства, на экране компонентов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c9139-180">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="c9139-181">По умолчанию автоматическая демонстрация экрана включена, а скрытие имен во время собрания отключено.</span><span class="sxs-lookup"><span data-stu-id="c9139-181">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="c9139-182">Для выбора доступны следующие устройства:</span><span class="sxs-lookup"><span data-stu-id="c9139-182">The devices to select are:</span></span>
    
   - <span data-ttu-id="c9139-183">Микрофон для конференций. Микрофон, который используется по умолчанию в этом конференц-зале.</span><span class="sxs-lookup"><span data-stu-id="c9139-183">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="c9139-184">Динамик для конференций. Динамик, который используется по умолчанию для проведения конференций. </span><span class="sxs-lookup"><span data-stu-id="c9139-184">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="c9139-185">Динамик по умолчанию. Динамик, который используется для воспроизведения звука со входа HDMI.</span><span class="sxs-lookup"><span data-stu-id="c9139-185">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="c9139-p116">Параметры каждого элемента можно настроить в соответствующем раскрывающемся списке. Необходимо сделать выбор для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="c9139-p116">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="c9139-188">Нажмите кнопку \*\*Готово \*\*.</span><span class="sxs-lookup"><span data-stu-id="c9139-188">Click **Finish**.</span></span>
    
<span data-ttu-id="c9139-189">Приложение консоли версии 2 Скайп комнаты систем сразу же будет запускаться вход с использованием Скайп для Business Server с использованием учетных данных, указанном выше и также должна начинать синхронизацию его календаря с сервером Exchange, используя те же учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c9139-189">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="c9139-190">Для получения дополнительных сведений об использовании консольное приложение обратитесь к [Скайп комнаты систем версии 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="c9139-190">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c9139-191">Версии 2 Скайп комнаты систем полагается на наличие сертифицированного консоли оборудования.</span><span class="sxs-lookup"><span data-stu-id="c9139-191">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="c9139-192">Даже правильно созданное изображение, содержащее ваше приложение консоли систем комнаты Скайп версии 2 не загружается после начального этапа процедуры Если обнаружена консоли оборудования.</span><span class="sxs-lookup"><span data-stu-id="c9139-192">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="c9139-193">Для Surface Pro на основе решений Surface Pro должен быть подключен к его сопутствующий закрепления оборудования для передачи этой проверки.</span><span class="sxs-lookup"><span data-stu-id="c9139-193">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9139-194">Некоторые пользователи не английский язык может потребоваться физической клавиатуры, подключенной к консоли во время начальной установки, в том случае, если символы не поддерживаются в сенсорной клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="c9139-194">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="c9139-195">Установка закрытого сертификата ЦС в консоли</span><span class="sxs-lookup"><span data-stu-id="c9139-195">Install a private CA certificate on the console</span></span>
<span data-ttu-id="c9139-196"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c9139-196"></span></span>

<span data-ttu-id="c9139-197">Также необходимо доверия сертификатов, используемых с Скайп для бизнеса и Exchange серверы, к которому подключен к консоли систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="c9139-197">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="c9139-198">В O365 это реализуется автоматически, так как соответствующие серверы используют общедоступные центры сертификации, по умолчанию являющиеся доверенными в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c9139-198">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="c9139-199">В случае где сертификации — это частный, например локальное развертывание с помощью Active Directory и сертификации Windows, можно добавить сертификат на консоль систем комнаты Скайп версии 2 в несколько способов:</span><span class="sxs-lookup"><span data-stu-id="c9139-199">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="c9139-200">Присоединение к консоли в Active Directory и, автоматически добавляет требуемые сертификаты, присвоенное сертификации будет опубликована в Active Directory (обычное развертывание вариант).</span><span class="sxs-lookup"><span data-stu-id="c9139-200">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="c9139-201">Сертификат можно установить вручную после завершения создания образа.</span><span class="sxs-lookup"><span data-stu-id="c9139-201">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="c9139-202">Перед этим следует выполнить [Начальная настройка консоли](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="c9139-202">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="c9139-203">Установка сертификата вручную </span><span class="sxs-lookup"><span data-stu-id="c9139-203">To manually install the certificate</span></span>

1. <span data-ttu-id="c9139-204">Скачайте сертификат ЦС на компьютер и сохраните его в папке C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer.</span><span class="sxs-lookup"><span data-stu-id="c9139-204">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="c9139-205">Установите консоль в режиме admin ( [администратор режим и устройства управления](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)см).</span><span class="sxs-lookup"><span data-stu-id="c9139-205">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="c9139-206">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="c9139-206">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="c9139-207">Присоединение к домену Active Directory (необязательно)</span><span class="sxs-lookup"><span data-stu-id="c9139-207">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="c9139-208"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c9139-208"></span></span>

<span data-ttu-id="c9139-209">Скайп помещения систем версии 2 консоли можно объединить с вашего домена.</span><span class="sxs-lookup"><span data-stu-id="c9139-209">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="c9139-210">Систем комнаты Скайп версии 2 консоли должны находиться в отдельные Подразделения из рабочих станциях ПК, так как количество политик рабочей станции не совместимы с системами комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="c9139-210">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="c9139-211">Распространенные пример, принудительное применение политики паролей, которые не позволит систем комнаты Скайп v2 автоматический запуск.</span><span class="sxs-lookup"><span data-stu-id="c9139-211">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="c9139-212">Информацию об управлении параметрами GPO см. в статье [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c9139-212">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="c9139-213">Присоединение Систем комнат Skype версии 2 к домену</span><span class="sxs-lookup"><span data-stu-id="c9139-213">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="c9139-214">Войти в консоль администрирования с учетной записью ( [режим и устройства управления Admin](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)см).</span><span class="sxs-lookup"><span data-stu-id="c9139-214">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="c9139-215">Запустите командную строку Powershell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="c9139-215">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="c9139-216">Введите следующую команду в Powershell:</span><span class="sxs-lookup"><span data-stu-id="c9139-216">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="c9139-217">Например, если redmond.corp.microsoft.com — это полное доменное, и вы хотите вашей консоли систем комнаты Скайп версии 2 в «v2 систем комнаты Скайп» Подразделения, являющийся дочерним элементом «ресурсы» Подразделение, команда будет:</span><span class="sxs-lookup"><span data-stu-id="c9139-217">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="c9139-218">Если вы хотите переименовать компьютер при присоединении к домену, используйте флаг - NewName, а затем новое имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="c9139-218">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="c9139-219">Контрольный список развертывания систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="c9139-219">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="c9139-220"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c9139-220"></span></span>

<span data-ttu-id="c9139-221">Используйте следующий контрольный список во время выполнения действий полностью настроить консоль и всех периферийных устройств:</span><span class="sxs-lookup"><span data-stu-id="c9139-221">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="c9139-222">**Параметры приложения**</span><span class="sxs-lookup"><span data-stu-id="c9139-222">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c9139-223">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-223">☐</span></span>  <br/> |<span data-ttu-id="c9139-224">В верхнем правом углу экрана консоли правильно отображаются название учетной записи комнаты и номер телефона (если доступна ТСОП).</span><span class="sxs-lookup"><span data-stu-id="c9139-224">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="c9139-225">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-225">☐</span></span>  <br/> |<span data-ttu-id="c9139-226">Правильно задано имя компьютера Windows (для удаленного администрирования)</span><span class="sxs-lookup"><span data-stu-id="c9139-226">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="c9139-227">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-227">☐</span></span>  <br/> |<span data-ttu-id="c9139-228">Задан и подтвержден пароль учетной записи администратора</span><span class="sxs-lookup"><span data-stu-id="c9139-228">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="c9139-229">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-229">☐</span></span>  <br/> |<span data-ttu-id="c9139-230">Были применены все обновления встроенного по</span><span class="sxs-lookup"><span data-stu-id="c9139-230">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="c9139-231">**Периферийных аудио и видео**</span><span class="sxs-lookup"><span data-stu-id="c9139-231">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c9139-232">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-232">☐</span></span>  <br/> |<span data-ttu-id="c9139-233">Указана правильная версия встроенного ПО периферийной камеры (если применимо)</span><span class="sxs-lookup"><span data-stu-id="c9139-233">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c9139-234">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-234">☐</span></span>  <br/> |<span data-ttu-id="c9139-235">Камера работоспособно и оптимально расположенных</span><span class="sxs-lookup"><span data-stu-id="c9139-235">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="c9139-236">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-236">☐</span></span>  <br/> |<span data-ttu-id="c9139-237">В качестве используемого по умолчанию устройства воспроизведения и устройства связи для воспроизведения задано нужное периферийное звуковое устройство</span><span class="sxs-lookup"><span data-stu-id="c9139-237">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c9139-238">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-238">☐</span></span>  <br/> |<span data-ttu-id="c9139-239">В качестве используемого по умолчанию устройства связи для записи задано нужное периферийное звуковое устройство</span><span class="sxs-lookup"><span data-stu-id="c9139-239">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c9139-240">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-240">☐</span></span>  <br/> |<span data-ttu-id="c9139-241">Указана правильная версия встроенного ПО периферийного звукового устройства (если применимо)</span><span class="sxs-lookup"><span data-stu-id="c9139-241">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c9139-242">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-242">☐</span></span>  <br/> |<span data-ttu-id="c9139-243">Входное звуковое устройство работает и правильно расположено</span><span class="sxs-lookup"><span data-stu-id="c9139-243">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="c9139-244">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-244">☐</span></span>  <br/> |<span data-ttu-id="c9139-245">Выходное звуковое устройство работает и правильно расположено</span><span class="sxs-lookup"><span data-stu-id="c9139-245">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="c9139-246">**Док-станция**</span><span class="sxs-lookup"><span data-stu-id="c9139-246">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c9139-247">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-247">☐</span></span>  <br/> |<span data-ttu-id="c9139-248">Все кабели закреплены и не пережаты</span><span class="sxs-lookup"><span data-stu-id="c9139-248">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="c9139-249">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-249">☐</span></span>  <br/> |<span data-ttu-id="c9139-250">Работает прием звукового сигнала через HDMI</span><span class="sxs-lookup"><span data-stu-id="c9139-250">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c9139-251">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-251">☐</span></span>  <br/> |<span data-ttu-id="c9139-252">Работает прием видеосигнала через HDMI</span><span class="sxs-lookup"><span data-stu-id="c9139-252">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c9139-253">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-253">☐</span></span>  <br/> |<span data-ttu-id="c9139-254">Док-станция свободно вращается</span><span class="sxs-lookup"><span data-stu-id="c9139-254">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="c9139-255">☐</span><span class="sxs-lookup"><span data-stu-id="c9139-255">☐</span></span>  <br/> |<span data-ttu-id="c9139-256">Яркость экрана соответствует обстановке</span><span class="sxs-lookup"><span data-stu-id="c9139-256">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c9139-257">Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.</span><span class="sxs-lookup"><span data-stu-id="c9139-257">See also</span></span>
<span data-ttu-id="c9139-258"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c9139-258"></span></span>

[<span data-ttu-id="c9139-259">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="c9139-259">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="c9139-260">Развертывание Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c9139-260">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="c9139-261">Настройка консоли для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c9139-261">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="c9139-262">Управление Системами комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="c9139-262">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)