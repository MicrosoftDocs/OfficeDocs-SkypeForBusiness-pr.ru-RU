---
title: Обслуживание и эксплуатация комнат Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: В этой статье рассказывается о том, как управлять комнатами Microsoft Teams, а также нового поколения систем комнат Skype.
ms.openlocfilehash: 14f4fb23868cc3e4247c700d15851511310db471
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775234"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="09dd6-103">Обслуживание и эксплуатация комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09dd6-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="09dd6-104">В этой статье рассказывается о том, как управлять комнатами Microsoft Teams, а также нового поколения систем комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="09dd6-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="09dd6-105">Комнаты Microsoft Teams — это новейшее решение для конференц-связи Майкрософт, разработанное для преобразования помещения для собраний в богатые и совместные работы.</span><span class="sxs-lookup"><span data-stu-id="09dd6-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="09dd6-106">Пользователи смогут пользоваться привычным интерфейсом Microsoft Teams или Skype для бизнеса, и ИТ-администраторы будут рады легкому развертыванию и управляемому приложению "собрание Skype" в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="09dd6-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="09dd6-107">Комнаты Microsoft Teams разработаны для работы с существующим оборудованием (например, ЖК-панелью) для упрощения установки, чтобы перевести Microsoft Teams или Skype для бизнеса в комнату для собраний.</span><span class="sxs-lookup"><span data-stu-id="09dd6-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="09dd6-108">С дополнительным конфигурированием можно использовать монитор Microsoft Azure, как описано в разделе [Планирование управления комнатами в Microsoft Teams с помощью монитора Azure](azure-monitor-plan.md), [развертывание службы Microsoft Teams с помощью монитора](azure-monitor-deploy.md)Azure, [Управление Microsoft Teams — это устройства с монитором Azure](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="09dd6-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="09dd6-109">Кроме того, вы можете [удаленно управлять параметрами консоли Microsoft Teams с помощью XML-файла конфигурации](xml-config-file.md), который включает в себя применение настраиваемой темы отображения.</span><span class="sxs-lookup"><span data-stu-id="09dd6-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="09dd6-110">Сбор журналов в комнатах Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09dd6-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="09dd6-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="09dd6-111"></span></span>

<span data-ttu-id="09dd6-112">Для сбора журналов необходимо вызвать сценарий сбора журналов, который поставляется с приложением Microsoft Teams комнаты.</span><span class="sxs-lookup"><span data-stu-id="09dd6-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="09dd6-113">В режиме администрирования запустите командную строку с повышенными привилегиями и выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="09dd6-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="09dd6-114">Журналы будут записываться в ZIP-файле в каталоге c:\rigel.</span><span class="sxs-lookup"><span data-stu-id="09dd6-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="09dd6-115">Параметры центрального дисплея</span><span class="sxs-lookup"><span data-stu-id="09dd6-115">Front of Room Display Settings</span></span>
<span data-ttu-id="09dd6-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="09dd6-116"></span></span>

<span data-ttu-id="09dd6-117">Настройте расширенный режим для центрального дисплея.</span><span class="sxs-lookup"><span data-stu-id="09dd6-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="09dd6-118">Это гарантирует, что пользовательский интерфейс консоли не будет дублироваться на этом дисплее при цикле включения на экране.</span><span class="sxs-lookup"><span data-stu-id="09dd6-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09dd6-p105">Бытовой телевизор, используемый в качестве центрального дисплея, должен поддерживать функцию управления бытовой электронной техникой (CEC) стандарта HDMI для автоматического переключения на активный источник видеосигнала из режима ожидания. Эту функцию поддерживают не все телевизоры.</span><span class="sxs-lookup"><span data-stu-id="09dd6-p105">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode. This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="09dd6-121">Сброс комнат Microsoft Teams (Восстановление заводских настроек)</span><span class="sxs-lookup"><span data-stu-id="09dd6-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="09dd6-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="09dd6-122"></span></span>

<span data-ttu-id="09dd6-123">Если комнаты Microsoft Teams не работают, может помочь выполнение заводского сброса.</span><span class="sxs-lookup"><span data-stu-id="09dd6-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="09dd6-124">Это можно сделать в приложении "Параметры" на вкладке " **Восстановление** ". в разделе **Восстановление компьютера**нажмите кнопку Начало **работы**, а затем **удалите все**.</span><span class="sxs-lookup"><span data-stu-id="09dd6-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="09dd6-125">Для сброса устройства следуйте дальнейшим инструкциям.</span><span class="sxs-lookup"><span data-stu-id="09dd6-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09dd6-126">Существует известная неполадка, из-за которой комнаты Microsoft Teams могут стать недоступными, если в процессе сброса Windows будет выбран параметр **хранить мои файлы, удаляя приложения и параметры, но при этом сохраняются настройки личных файлов** .</span><span class="sxs-lookup"><span data-stu-id="09dd6-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="09dd6-127">_Не_ используйте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="09dd6-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="09dd6-128">Поддерживаемые параметры удаленной работы</span><span class="sxs-lookup"><span data-stu-id="09dd6-128">Supported Remote Options</span></span>
<span data-ttu-id="09dd6-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="09dd6-129"></span></span>

<span data-ttu-id="09dd6-130">В таблице ниже приводится сводка возможных удаленных операций и методов их выполнения.</span><span class="sxs-lookup"><span data-stu-id="09dd6-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="09dd6-131">\*\*Рабочая группа \*\*</span><span class="sxs-lookup"><span data-stu-id="09dd6-131">**Workgroup**</span></span>|<span data-ttu-id="09dd6-132">**Без присоединения к домену**</span><span class="sxs-lookup"><span data-stu-id="09dd6-132">**Not domain joined**</span></span>|<span data-ttu-id="09dd6-133">**Присоединение к домену**</span><span class="sxs-lookup"><span data-stu-id="09dd6-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="09dd6-134">Перезапуск</span><span class="sxs-lookup"><span data-stu-id="09dd6-134">Restart</span></span>  <br/> |<span data-ttu-id="09dd6-135">Удаленный рабочий стол</span><span class="sxs-lookup"><span data-stu-id="09dd6-135">Remote desktop</span></span>  <br/> <span data-ttu-id="09dd6-136">Удаленная среда PowerShell</span><span class="sxs-lookup"><span data-stu-id="09dd6-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="09dd6-137">Дистанционное управление рабочим столом (требуется дополнительная настройка)</span><span class="sxs-lookup"><span data-stu-id="09dd6-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="09dd6-138">Удаленная оболочка PowerShell (требуется дополнительная настройка)</span><span class="sxs-lookup"><span data-stu-id="09dd6-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="09dd6-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="09dd6-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="09dd6-140">Обновление ОС</span><span class="sxs-lookup"><span data-stu-id="09dd6-140">Update OS</span></span>  <br/> |<span data-ttu-id="09dd6-141">Обновление Windows</span><span class="sxs-lookup"><span data-stu-id="09dd6-141">Windows Update</span></span>  <br/> |<span data-ttu-id="09dd6-142">Обновление Windows</span><span class="sxs-lookup"><span data-stu-id="09dd6-142">Windows Update</span></span>  <br/> <span data-ttu-id="09dd6-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="09dd6-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="09dd6-144">Обновление приложения</span><span class="sxs-lookup"><span data-stu-id="09dd6-144">App update</span></span>  <br/> |<span data-ttu-id="09dd6-145">	Магазин Windows</span><span class="sxs-lookup"><span data-stu-id="09dd6-145">Windows Store</span></span>  <br/> |<span data-ttu-id="09dd6-146">Магазин Windows</span><span class="sxs-lookup"><span data-stu-id="09dd6-146">Windows Store</span></span>  <br/> <span data-ttu-id="09dd6-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="09dd6-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="09dd6-148">Настройка учетной записи Skype</span><span class="sxs-lookup"><span data-stu-id="09dd6-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="09dd6-149">В настоящее время не поддерживается</span><span class="sxs-lookup"><span data-stu-id="09dd6-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="09dd6-150">	В настоящее время не поддерживается</span><span class="sxs-lookup"><span data-stu-id="09dd6-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="09dd6-151">Журналы доступа</span><span class="sxs-lookup"><span data-stu-id="09dd6-151">Access logs</span></span>  <br/> |<span data-ttu-id="09dd6-152">	В настоящее время не поддерживается</span><span class="sxs-lookup"><span data-stu-id="09dd6-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="09dd6-153">	В настоящее время не поддерживается</span><span class="sxs-lookup"><span data-stu-id="09dd6-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="09dd6-154">Настройка групповой политики для комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09dd6-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="09dd6-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="09dd6-155"></span></span>

<span data-ttu-id="09dd6-156">В этом разделе описаны системные параметры, от которых зависит правильность работы комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="09dd6-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="09dd6-157">При присоединении к домену комнат Microsoft Teams убедитесь, что групповая политика не переопределяет параметры, указанные в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="09dd6-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="09dd6-158">**Параметрами**</span><span class="sxs-lookup"><span data-stu-id="09dd6-158">**Setting**</span></span>|<span data-ttu-id="09dd6-159">**Можете**</span><span class="sxs-lookup"><span data-stu-id="09dd6-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="09dd6-160">HKLM\SOFTWARE\Microsoft\Windows Нт\куррентверсион\винлогон Аутоадминлогон = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="09dd6-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="09dd6-161">Включает комнаты Microsoft Teams для загрузки</span><span class="sxs-lookup"><span data-stu-id="09dd6-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="09dd6-162">Управление питанием\> в сети переменного тока, отключение экрана через 10 минут</span><span class="sxs-lookup"><span data-stu-id="09dd6-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="09dd6-163">Управление питанием\> — вкл., не переводит систему в спящий режим</span><span class="sxs-lookup"><span data-stu-id="09dd6-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="09dd6-164">Позволяет комнатам Microsoft Teams отключить подключенные дисплеи и автоматически выключаться из спящего режима</span><span class="sxs-lookup"><span data-stu-id="09dd6-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="09dd6-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="09dd6-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="09dd6-166">Или аналогичный способ отключения срока действия пароля в локальной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="09dd6-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="09dd6-167">Невыполнение этого действия приводит к тому, что учетной записи Skype не удается войти в систему с нарушением пароля.</span><span class="sxs-lookup"><span data-stu-id="09dd6-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="09dd6-168">Обратите внимание, что это влияет на все локальные учетные записи на компьютере, поэтому при установке этого флажка также может возникнуть срок действия административной учетной записи в поле.</span><span class="sxs-lookup"><span data-stu-id="09dd6-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="09dd6-169">Позволяет учетной записи Skype всегда выполнять вход.</span><span class="sxs-lookup"><span data-stu-id="09dd6-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="09dd6-170">Передача файлов с помощью групповых политик рассматривается в разделе [Настройка элемента файла](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="09dd6-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="09dd6-171">Если приложение Microsoft Teams для комнат совместимо со следующей версией операционной системы Windows 10, устройство автоматически обновляется до следующей версии с помощью центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="09dd6-171">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="09dd6-172">Приложение Microsoft Teams не следует обновлять до следующего выпуска Windows 10 вручную или с помощью групповой политики "включение Windows Update для бизнеса (ВУФБ)" выберите уровень готовности Windows для обновлений, которые вы хотите получать "и" выберите при предварительных сборках и Обновления компонентов получены с помощью GPO.</span><span class="sxs-lookup"><span data-stu-id="09dd6-172">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="09dd6-173">Устройство, для которого включены эти групповые политики, известно о проблемах, возникающих при обновлении операционной системы Windows 10 с помощью приложения Microsoft Teams помещений.</span><span class="sxs-lookup"><span data-stu-id="09dd6-173">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="09dd6-174">Удаленное управление с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="09dd6-174">Remote Management using PowerShell</span></span>
<span data-ttu-id="09dd6-175"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="09dd6-175"></span></span>

<span data-ttu-id="09dd6-176">С помощью PowerShell можно удаленно выполнять следующие операции управления (в приведенной ниже таблице приведены примеры сценария).</span><span class="sxs-lookup"><span data-stu-id="09dd6-176">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="09dd6-177">Получение списка подключенных устройств</span><span class="sxs-lookup"><span data-stu-id="09dd6-177">Get attached devices</span></span>
    
- <span data-ttu-id="09dd6-178">Получение сведений о состоянии приложений</span><span class="sxs-lookup"><span data-stu-id="09dd6-178">Get app status</span></span>
    
- <span data-ttu-id="09dd6-179">Получение сведений о системе</span><span class="sxs-lookup"><span data-stu-id="09dd6-179">Get system info</span></span>
    
- <span data-ttu-id="09dd6-180">Перезагрузка системы</span><span class="sxs-lookup"><span data-stu-id="09dd6-180">Reboot system</span></span>
    
- <span data-ttu-id="09dd6-181">Получение журналов</span><span class="sxs-lookup"><span data-stu-id="09dd6-181">Retrieve logs</span></span>
    
- <span data-ttu-id="09dd6-182">Передача файлов (требуется присоединение к домену из комнаты Microsoft Teams)</span><span class="sxs-lookup"><span data-stu-id="09dd6-182">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="09dd6-183">По умолчанию эта возможность выключена.</span><span class="sxs-lookup"><span data-stu-id="09dd6-183">This functionality is off by default.</span></span> <span data-ttu-id="09dd6-184">Для выполнения операций ниже необходимо включить удаленную оболочку PowerShell для вашей среды в системе комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="09dd6-184">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="09dd6-185">Сведения о том, как включить удаленную оболочку PowerShell, можно найти в документации по **[Enable-псремотинг](https://technet.microsoft.com/library/hh849694.aspx)** .</span><span class="sxs-lookup"><span data-stu-id="09dd6-185">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="09dd6-186">Например, чтобы включить удаленную оболочку PowerShell, можно выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="09dd6-186">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="09dd6-187">Войдите в систему как администратор на устройстве с комнатой Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="09dd6-187">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="09dd6-188">Откройте командную в командной строке PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="09dd6-188">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="09dd6-189">Введите следующую команду: Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="09dd6-189">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="09dd6-190">Чтобы совершить операцию по управлению, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="09dd6-190">To perform a management operation:</span></span>
  
1. <span data-ttu-id="09dd6-191">Войдите на компьютер с учетными данными учетной записи, у которых есть разрешение на запуск команд PowerShell на устройстве с комнатой Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="09dd6-191">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="09dd6-192">Откройте на компьютере стандартную командную кнопку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09dd6-192">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="09dd6-193">Скопируйте текст команды из приведенной ниже таблицы и вставьте ее в строке запроса.</span><span class="sxs-lookup"><span data-stu-id="09dd6-193">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="09dd6-194">Замените `<Device fqdn>` поля значениями полного доменного имени, соответствующими вашей среде.</span><span class="sxs-lookup"><span data-stu-id="09dd6-194">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="09dd6-195">Замените \* \<путь\> \* именем файла и локальным путем к главному файлу конфигурации скипесеттингс. XML (или рисунку темы).</span><span class="sxs-lookup"><span data-stu-id="09dd6-195">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="09dd6-196">Получение подключенных устройств</span><span class="sxs-lookup"><span data-stu-id="09dd6-196">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="09dd6-197">получение состояния приложений;</span><span class="sxs-lookup"><span data-stu-id="09dd6-197">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="09dd6-198">получение сведений о системе;</span><span class="sxs-lookup"><span data-stu-id="09dd6-198">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="09dd6-199">перезагрузка системы;</span><span class="sxs-lookup"><span data-stu-id="09dd6-199">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="09dd6-200">получение журналов.</span><span class="sxs-lookup"><span data-stu-id="09dd6-200">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="09dd6-201">Отправка XML-файла конфигурации (или рисунка темы)</span><span class="sxs-lookup"><span data-stu-id="09dd6-201">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="09dd6-202">Обновления программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="09dd6-202">Software updates</span></span>
<span data-ttu-id="09dd6-203"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="09dd6-203"></span></span>

<span data-ttu-id="09dd6-204">По умолчанию комнаты Microsoft Teams пытаются подключиться к Магазину Windows для получения последней версии Microsoft Teams, поэтому для работы устройства потребуется обычный доступ к Интернету.</span><span class="sxs-lookup"><span data-stu-id="09dd6-204">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="09dd6-205">Перед обращением в корпорацию Майкрософт по вопросам поддержки, убедитесь в том, что на устройстве Microsoft Teams загружена новейшая версия приложения.</span><span class="sxs-lookup"><span data-stu-id="09dd6-205">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="09dd6-206">По умолчанию комнаты Microsoft Teams подключаются к центру обновления Windows для получения обновлений операционной системы и USB-устройств, а затем устанавливаются за пределами настроенного рабочего времени.</span><span class="sxs-lookup"><span data-stu-id="09dd6-206">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="09dd6-207">Чтобы указать часы работы, войдите в учетную запись администратора и запустите приложение "Параметры".</span><span class="sxs-lookup"><span data-stu-id="09dd6-207">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="09dd6-208">Если вы хотите управлять обновлениями вручную и не можете подписаться на стандартную процедуру [Microsoft Store для бизнеса](https://businessstore.microsoft.com/store) для [распространения автономных приложений](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), вы можете получить соответствующий APPX-файл и зависимости из [комплекта средств для развертывания](https://go.microsoft.com/fwlink/?linkid=851168) (от инструкции по [настройке консоли Microsoft Teams](console.md), которые можно использовать с SCCM.</span><span class="sxs-lookup"><span data-stu-id="09dd6-208">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="09dd6-209">Выпуск комплекта развертывания отключается за выпуском в магазине, поэтому он может не всегда совпадать с последней доступной сборкой.</span><span class="sxs-lookup"><span data-stu-id="09dd6-209">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="09dd6-210">Обновление с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="09dd6-210">To update using Powershell</span></span>

1. <span data-ttu-id="09dd6-211">Извлеките пакет из [MSI](https://go.microsoft.com/fwlink/?linkid=851168) -файла установки в папку, к которой можно получить доступ на устройстве.</span><span class="sxs-lookup"><span data-stu-id="09dd6-211">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="09dd6-212">Запустите следующий сценарий, нацеленный на устройства Microsoft Teams комнаты, \<и\> измените его на общий доступ к устройствам.</span><span class="sxs-lookup"><span data-stu-id="09dd6-212">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="09dd6-213">Режим администрирования и управление устройствами</span><span class="sxs-lookup"><span data-stu-id="09dd6-213">Admin mode and device management</span></span>
<span data-ttu-id="09dd6-214"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="09dd6-214"></span></span>

<span data-ttu-id="09dd6-215">Некоторые функции управления, например ручная установка закрытого сертификата ЦС, требуют помещения устройства Surface Pro в режим администратора.</span><span class="sxs-lookup"><span data-stu-id="09dd6-215">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="09dd6-216">Переключение в режим администратора и обратно при запущенном приложении "комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="09dd6-216">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="09dd6-217">Повесьте все текущие звонки и вернитесь на начальный экран.</span><span class="sxs-lookup"><span data-stu-id="09dd6-217">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="09dd6-218">Щелкните значок шестеренки и выбери меню (параметры: **Параметры**, **Специальные возможности**и **Перезагрузка устройства** ).</span><span class="sxs-lookup"><span data-stu-id="09dd6-218">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="09dd6-219">Выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="09dd6-219">Select **Settings**.</span></span>
    
4. <span data-ttu-id="09dd6-220">Введите пароль администратора.</span><span class="sxs-lookup"><span data-stu-id="09dd6-220">Enter the Administrator Password.</span></span> <span data-ttu-id="09dd6-221">Откроется экран настройки.</span><span class="sxs-lookup"><span data-stu-id="09dd6-221">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09dd6-222">Если устройство не подключено к домену, по умолчанию будет использоваться локальная учетная запись администратора (username "Администратор").</span><span class="sxs-lookup"><span data-stu-id="09dd6-222">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="09dd6-223">Паролем по умолчанию для этой учетной записи является "sfb", но по соображениям безопасности его рекомендуется как можно быстрее изменить.</span><span class="sxs-lookup"><span data-stu-id="09dd6-223">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="09dd6-224">Если компьютер присоединен к домену, вы можете войти в систему с помощью соответствующей учетной записи домена с правами доступа.</span><span class="sxs-lookup"><span data-stu-id="09dd6-224">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="09dd6-225">В левом столбце выберите **Параметры Windows** .</span><span class="sxs-lookup"><span data-stu-id="09dd6-225">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="09dd6-226">Выберите **Go to Admin Sign-in** (Перейти на страницу входа администратора).</span><span class="sxs-lookup"><span data-stu-id="09dd6-226">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="09dd6-227">Введите пароль администратора.</span><span class="sxs-lookup"><span data-stu-id="09dd6-227">Enter the Administrator Password.</span></span> <span data-ttu-id="09dd6-228">Будет выполнен выход из приложения, а затем откроется экран входа Windows.</span><span class="sxs-lookup"><span data-stu-id="09dd6-228">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="09dd6-229">Выполните вход в систему с использованием учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="09dd6-229">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="09dd6-230">У вас есть необходимые разрешения на управление устройством.</span><span class="sxs-lookup"><span data-stu-id="09dd6-230">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="09dd6-231">Выполните необходимые административные задачи.</span><span class="sxs-lookup"><span data-stu-id="09dd6-231">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="09dd6-232">Выйдите из учетной записи с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="09dd6-232">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="09dd6-233">Вернитесь в комнаты Microsoft Teams, щелкнув значок учетной записи пользователя в дальней левой части экрана, а затем выбрав **Skype**.</span><span class="sxs-lookup"><span data-stu-id="09dd6-233">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="09dd6-234">Если пользователя **Skype** нет в списке, может потребоваться выбрать **другого пользователя** и ввести **.\скипе** в качестве имени пользователя и войти в службу.</span><span class="sxs-lookup"><span data-stu-id="09dd6-234">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="09dd6-235">Консоль будет восстановлена в обычном режиме работы. Для следующей процедуры требуется, чтобы на устройстве была присоединена клавиатура, если она еще не подключена.</span><span class="sxs-lookup"><span data-stu-id="09dd6-235">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="09dd6-236">Переключение в режим администратора и обратно при сбое приложения Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09dd6-236">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="09dd6-237">Быстро нажмите клавишу Windows пять раз подряд.</span><span class="sxs-lookup"><span data-stu-id="09dd6-237">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="09dd6-238">Откроется экран входа Windows.</span><span class="sxs-lookup"><span data-stu-id="09dd6-238">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="09dd6-239">Выполните вход в систему с использованием учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="09dd6-239">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09dd6-240">Этот метод не регистрирует пользователя Skype в автономном режиме или некорректно завершает работу приложения, но его можно использовать, если приложение не отвечает, а другой метод недоступен.</span><span class="sxs-lookup"><span data-stu-id="09dd6-240">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="09dd6-241">Выполните необходимые административные задачи.</span><span class="sxs-lookup"><span data-stu-id="09dd6-241">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="09dd6-242">Когда вы закончите, перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="09dd6-242">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="09dd6-243">Консоль перезапускается в нормальном режиме работы, в котором запускается приложение Microsoft Teams комнаты.</span><span class="sxs-lookup"><span data-stu-id="09dd6-243">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="09dd6-244">Вы можете удалить раскладку клавиатуры, если она была подключена, чтобы выполнить эту процедуру.</span><span class="sxs-lookup"><span data-stu-id="09dd6-244">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="09dd6-245">Советы по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="09dd6-245">Troubleshooting tips</span></span>
   <span data-ttu-id="09dd6-246"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="09dd6-246"></span></span>

- <span data-ttu-id="09dd6-247">Приглашения на собрания могут не отображаться при отправке через границы домена (например, между двумя компаниями).</span><span class="sxs-lookup"><span data-stu-id="09dd6-247">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="09dd6-248">В таких случаях ИТ-администраторы должны решить, следует ли разрешать внешним пользователям планировать собрания.</span><span class="sxs-lookup"><span data-stu-id="09dd6-248">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="09dd6-249">Комнаты Microsoft Teams не поддерживают перенаправления автообнаружения Exchange через Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="09dd6-249">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="09dd6-250">Как правило, для ИТ-администраторов рекомендуется отключить любые конечные точки звука, которые они не планирует использовать.</span><span class="sxs-lookup"><span data-stu-id="09dd6-250">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="09dd6-251">Если в режиме предварительного просмотра комнаты выводится зеркальное отражение, ИТ-администратор может устранить эту проблему, выключив и снова включив питание камеры или настроив зеркальное отражение изображения с помощью пульта дистанционного управления камерой.</span><span class="sxs-lookup"><span data-stu-id="09dd6-251">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="09dd6-252">Известны случаи утери доступа к сенсорному экрану консоли.</span><span class="sxs-lookup"><span data-stu-id="09dd6-252">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="09dd6-253">В таких случаях проблему иногда можно решить, перезапуская систему комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="09dd6-253">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="09dd6-254">Известны случаи исчезновения локального звукового сигнала при подключении компьютера к консоли с помощью кабеля.</span><span class="sxs-lookup"><span data-stu-id="09dd6-254">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="09dd6-255">Эту проблему можно устранить путем перезагрузки компьютера.</span><span class="sxs-lookup"><span data-stu-id="09dd6-255">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
