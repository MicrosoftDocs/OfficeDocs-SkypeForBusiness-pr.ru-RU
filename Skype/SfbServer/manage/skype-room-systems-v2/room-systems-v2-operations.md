---
title: Обслуживание версии 2 Скайп комнаты систем и операции
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Прочитайте сведения об управлении v2 Скайп комнаты систем следующего поколения Скайп комнаты систем.
ms.openlocfilehash: 4c94ffbcb83e5e208e5cd7278af54e157b9f478c
ms.sourcegitcommit: ff100b32fa92fc878f1404dace266d956262c24d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2019
ms.locfileid: "30720426"
---
# <a name="skype-room-systems-v2-maintenance-and-operations"></a><span data-ttu-id="85f17-103">Обслуживание версии 2 Скайп комнаты систем и операции</span><span class="sxs-lookup"><span data-stu-id="85f17-103">Skype Room Systems v2 maintenance and operations</span></span> 
 
<span data-ttu-id="85f17-104">Прочитайте сведения об управлении v2 Скайп комнаты систем следующего поколения Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="85f17-104">Read this topic to learn about management of Skype Room Systems v2, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="85f17-105">Систем комнаты Скайп версии 2 — корпорации Майкрософт предназначена для преобразования комнате для собраний в подробные, совместной работы Скайп для бизнеса программой последние решение конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="85f17-105">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="85f17-106">Обычные пользователи оценят хорошо знакомый интерфейс Skype для бизнеса, тогда как ИТ-администраторы смогут с легкостью развернуть приложение для собраний Skype для Windows 10 и управлять им.</span><span class="sxs-lookup"><span data-stu-id="85f17-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="85f17-107">Версии 2 Скайп комнаты систем предназначен для использования существующего оборудования как Жидкокристаллических панелей для упрощения установки для переноса Скайп для бизнеса в комнате для собраний.</span><span class="sxs-lookup"><span data-stu-id="85f17-107">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="85f17-108">С помощью дополнительной настройки удаленного управления возможно с помощью пакетов управления Microsoft операции (OMS), как описано в [планирование систем комнаты Скайп v2 управлении с OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [Развертывание системы комнаты Скайп версии 2 с OMS](../../deploy/deploy-clients/with-oms.md)и [Управление Устройства системы комнаты Скайп версии 2 с OMS](oms.md).</span><span class="sxs-lookup"><span data-stu-id="85f17-108">With additional configuration, remote management is possible using Microsoft Operations Management Suite (OMS) as described in [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [Deploy Skype Room Systems v2 management with OMS](../../deploy/deploy-clients/with-oms.md), and [Manage Skype Room Systems v2 devices with OMS](oms.md).</span></span> <span data-ttu-id="85f17-109">Кроме того, поддерживается [Manage a Skype Room Systems v2 console settings remotely with an XML configuration file](xml-config-file.md), в том числе применение настраиваемых экранных тем.</span><span class="sxs-lookup"><span data-stu-id="85f17-109">You may also [Manage a Skype Room Systems v2 console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a><span data-ttu-id="85f17-110">Сбор журналов в Системах комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="85f17-110">Collecting logs on Skype Room Systems v2</span></span>
<span data-ttu-id="85f17-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="85f17-111"></span></span>

<span data-ttu-id="85f17-112">Собирать, необходимо вызвать скрипт коллекции журнала, которое поставляется с приложением версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="85f17-112">To collect logs, you must invoke the log collection script that ships with the Skype Room Systems v2 app.</span></span> <span data-ttu-id="85f17-113">В режиме администрирования запустите командную строку с повышенными привилегиями и выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="85f17-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="85f17-114">Журналы будут записываться в ZIP-файле в каталоге c:\rigel.</span><span class="sxs-lookup"><span data-stu-id="85f17-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="85f17-115">Параметры центрального дисплея</span><span class="sxs-lookup"><span data-stu-id="85f17-115">Front of Room Display Settings</span></span>
<span data-ttu-id="85f17-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="85f17-116"></span></span>

<span data-ttu-id="85f17-117">Настройте расширенный режим для центрального дисплея.</span><span class="sxs-lookup"><span data-stu-id="85f17-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="85f17-118">При этом будет убедитесь, что пользовательский Интерфейс не дублируются на, отображаемых при переходе power на экране консоли.</span><span class="sxs-lookup"><span data-stu-id="85f17-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85f17-p105">Бытовой телевизор, используемый в качестве центрального дисплея, должен поддерживать функцию управления бытовой электронной техникой (CEC) стандарта HDMI для автоматического переключения на активный источник видеосигнала из режима ожидания. Эту функцию поддерживают не все телевизоры.</span><span class="sxs-lookup"><span data-stu-id="85f17-p105">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode. This feature is not supported on all TVs.</span></span> 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a><span data-ttu-id="85f17-121">Сброс Систем комнат Skype версии 2 (восстановление заводских настроек)</span><span class="sxs-lookup"><span data-stu-id="85f17-121">Skype Room Systems v2 Reset (Factory Restore)</span></span>
<span data-ttu-id="85f17-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="85f17-122"></span></span>

<span data-ttu-id="85f17-123">Если также не запущен систем комнаты Скайп версии 2, для выполнения сброса фабрики может помочь.</span><span class="sxs-lookup"><span data-stu-id="85f17-123">If Skype Room Systems v2 isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="85f17-124">Это можно сделать в приложении параметров на вкладке **восстановления** под **Сброс этого компьютера**, выберите **приступить к работе**, а затем **удалите все содержимое**.</span><span class="sxs-lookup"><span data-stu-id="85f17-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="85f17-125">Следуйте подсказкам, оставшихся сброс устройства.</span><span class="sxs-lookup"><span data-stu-id="85f17-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85f17-126">Существует известная проблема, где v2 Скайп комнаты системы может стать невозможным, если выбран параметр **Хранение файлов - удаляет приложений и настроек, но все личные файлы** , во время сброса Windows.</span><span class="sxs-lookup"><span data-stu-id="85f17-126">There is a known issue where the Skype Room Systems v2 can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="85f17-127">Выполните _не_ использовать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="85f17-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="85f17-128">Поддерживаемые параметры удаленной работы</span><span class="sxs-lookup"><span data-stu-id="85f17-128">Supported Remote Options</span></span>
<span data-ttu-id="85f17-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="85f17-129"></span></span>

<span data-ttu-id="85f17-130">В таблице ниже приводится сводка возможных удаленных операций и методов их выполнения.</span><span class="sxs-lookup"><span data-stu-id="85f17-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="85f17-131">\*\*Рабочая группа \*\*</span><span class="sxs-lookup"><span data-stu-id="85f17-131">**Workgroup**</span></span>|<span data-ttu-id="85f17-132">**Без присоединения к домену**</span><span class="sxs-lookup"><span data-stu-id="85f17-132">**Not domain joined**</span></span>|<span data-ttu-id="85f17-133">**Присоединение к домену**</span><span class="sxs-lookup"><span data-stu-id="85f17-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85f17-134">Перезапуск</span><span class="sxs-lookup"><span data-stu-id="85f17-134">Restart</span></span>  <br/> |<span data-ttu-id="85f17-135">Удаленный рабочий стол</span><span class="sxs-lookup"><span data-stu-id="85f17-135">Remote desktop</span></span>  <br/> <span data-ttu-id="85f17-136">Удаленная среда PowerShell</span><span class="sxs-lookup"><span data-stu-id="85f17-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="85f17-137">Удаленных рабочих столов (требуется дополнительная настройка)</span><span class="sxs-lookup"><span data-stu-id="85f17-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="85f17-138">Удаленная оболочка Powershell (требуется дополнительная настройка)</span><span class="sxs-lookup"><span data-stu-id="85f17-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="85f17-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="85f17-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="85f17-140">Обновление ОС</span><span class="sxs-lookup"><span data-stu-id="85f17-140">Update OS</span></span>  <br/> |<span data-ttu-id="85f17-141">Обновление Windows</span><span class="sxs-lookup"><span data-stu-id="85f17-141">Windows Update</span></span>  <br/> |<span data-ttu-id="85f17-142">Обновление Windows</span><span class="sxs-lookup"><span data-stu-id="85f17-142">Windows Update</span></span>  <br/> <span data-ttu-id="85f17-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="85f17-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="85f17-144">Обновление приложения</span><span class="sxs-lookup"><span data-stu-id="85f17-144">App update</span></span>  <br/> |<span data-ttu-id="85f17-145">	Магазин Windows</span><span class="sxs-lookup"><span data-stu-id="85f17-145">Windows Store</span></span>  <br/> |<span data-ttu-id="85f17-146">Магазин Windows</span><span class="sxs-lookup"><span data-stu-id="85f17-146">Windows Store</span></span>  <br/> <span data-ttu-id="85f17-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="85f17-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="85f17-148">Настройка учетной записи Skype</span><span class="sxs-lookup"><span data-stu-id="85f17-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="85f17-149">В настоящее время не поддерживается</span><span class="sxs-lookup"><span data-stu-id="85f17-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="85f17-150">	В настоящее время не поддерживается</span><span class="sxs-lookup"><span data-stu-id="85f17-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="85f17-151">Журналы доступа</span><span class="sxs-lookup"><span data-stu-id="85f17-151">Access logs</span></span>  <br/> |<span data-ttu-id="85f17-152">	В настоящее время не поддерживается</span><span class="sxs-lookup"><span data-stu-id="85f17-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="85f17-153">	В настоящее время не поддерживается</span><span class="sxs-lookup"><span data-stu-id="85f17-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a><span data-ttu-id="85f17-154">Настройка групповой политики для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="85f17-154">Configuring Group Policy for Skype Room Systems v2</span></span>
<span data-ttu-id="85f17-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="85f17-155"></span></span>

<span data-ttu-id="85f17-156">В этом разделе описываются параметры системы, от которых зависит систем комнаты Скайп v2 для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="85f17-156">This section covers system settings that Skype Room Systems v2 depends on to function properly.</span></span> <span data-ttu-id="85f17-157">При присоединении к версии 2 Скайп комнаты систем в домен, убедитесь, что групповой политики не переопределять параметры в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="85f17-157">When joining Skype Room Systems v2 to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="85f17-158">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="85f17-158">**Setting**</span></span>|<span data-ttu-id="85f17-159">**Позволяет**</span><span class="sxs-lookup"><span data-stu-id="85f17-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85f17-160">HKLM\SOFTWARE\Microsoft\Windows программы AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="85f17-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="85f17-161">Версии 2 систем комнаты Скайп позволяет загружать</span><span class="sxs-lookup"><span data-stu-id="85f17-161">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="85f17-162">Power Management -\> от сети, отключить экран после 10 минут</span><span class="sxs-lookup"><span data-stu-id="85f17-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="85f17-163">Power Management -\> от сети, никогда не создавать системы в спящий режим</span><span class="sxs-lookup"><span data-stu-id="85f17-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="85f17-164">Позволяет v2 систем комнаты Скайп отключение вложенные отображает и спящего режима автоматически</span><span class="sxs-lookup"><span data-stu-id="85f17-164">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="85f17-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="85f17-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="85f17-166">Или эквивалентный означает, что отключения истечение срока действия пароля на локальной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="85f17-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="85f17-167">Для этого в конце концов вызывает учетной записи Скайп Сбой входа жалуется пароль с истекшим сроком действия.</span><span class="sxs-lookup"><span data-stu-id="85f17-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="85f17-168">Обратите внимание на то, что это влияет на всех локальных учетных записей на компьютере, и таким образом не удалось установить это также будет происходить учетную запись администратора на поле в конечном счете срок действия которых истекает также.</span><span class="sxs-lookup"><span data-stu-id="85f17-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="85f17-169">Позволяет учетной записи Skype всегда выполнять вход.</span><span class="sxs-lookup"><span data-stu-id="85f17-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="85f17-170">Передача файлов с помощью групповых политик рассматривается в статье [Настройка файла элемента](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="85f17-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="85f17-171">Удаленное управление с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="85f17-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="85f17-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="85f17-172"></span></span>

<span data-ttu-id="85f17-173">Можно выполнить следующие операции управления удаленно с помощью PowerShell (в приведенной ниже таблице для примеров сценариев):</span><span class="sxs-lookup"><span data-stu-id="85f17-173">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="85f17-174">Получение списка подключенных устройств</span><span class="sxs-lookup"><span data-stu-id="85f17-174">Get attached devices</span></span>
    
- <span data-ttu-id="85f17-175">Получение сведений о состоянии приложений</span><span class="sxs-lookup"><span data-stu-id="85f17-175">Get app status</span></span>
    
- <span data-ttu-id="85f17-176">Получение сведений о системе</span><span class="sxs-lookup"><span data-stu-id="85f17-176">Get system info</span></span>
    
- <span data-ttu-id="85f17-177">Перезагрузка системы</span><span class="sxs-lookup"><span data-stu-id="85f17-177">Reboot system</span></span>
    
- <span data-ttu-id="85f17-178">Получение журналов</span><span class="sxs-lookup"><span data-stu-id="85f17-178">Retrieve logs</span></span>
    
- <span data-ttu-id="85f17-179">Передавать файлы (требуется версии системы комнаты Скайп 2 присоединенный к домену)</span><span class="sxs-lookup"><span data-stu-id="85f17-179">Transfer files (requires a domain-joined Skype Room Systems v2)</span></span>
    
> [!NOTE]
> <span data-ttu-id="85f17-180">По умолчанию эта возможность выключена.</span><span class="sxs-lookup"><span data-stu-id="85f17-180">This functionality is off by default.</span></span> <span data-ttu-id="85f17-181">Необходимо включить удаленной оболочки PowerShell для вашей среды в системе версии 2 Скайп комнаты системы для выполнения операций ниже.</span><span class="sxs-lookup"><span data-stu-id="85f17-181">You need to enable remote PowerShell for your environment on the Skype Room Systems v2 system to perform the operations below.</span></span> <span data-ttu-id="85f17-182">Обратитесь к документации на **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** сведения о том, как включить удаленной оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85f17-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="85f17-183">Например, чтобы включить удаленную оболочку PowerShell, можно выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="85f17-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="85f17-184">Войдите в качестве администратора на устройстве систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="85f17-184">Sign in as Admin on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="85f17-185">Откройте командную строку с повышенными привилегиями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85f17-185">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="85f17-186">Введите следующую команду: Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="85f17-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="85f17-187">Чтобы совершить операцию по управлению, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="85f17-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="85f17-188">Вход в систему с использованием учетных данных учетной записи, которые имеют разрешение на выполнение команд PowerShell на устройстве систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="85f17-188">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="85f17-189">Откройте командную строку регулярных PowerShell на персональном Компьютере.</span><span class="sxs-lookup"><span data-stu-id="85f17-189">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="85f17-190">Скопируйте текст команды из в приведенной ниже таблице и вставьте его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="85f17-190">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="85f17-191">Замените `<Device fqdn>` значениями полное доменное имя поля, допустимые для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="85f17-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="85f17-192">Замените \* \<путь\> \* с именем файла и локальный путь основной файл конфигурации SkypeSettings.xml (или темы изображение).</span><span class="sxs-lookup"><span data-stu-id="85f17-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="85f17-193">Чтобы получить подключенные устройства</span><span class="sxs-lookup"><span data-stu-id="85f17-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="85f17-194">получение состояния приложений;</span><span class="sxs-lookup"><span data-stu-id="85f17-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="85f17-195">получение сведений о системе;</span><span class="sxs-lookup"><span data-stu-id="85f17-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="85f17-196">перезагрузка системы;</span><span class="sxs-lookup"><span data-stu-id="85f17-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="85f17-197">получение журналов.</span><span class="sxs-lookup"><span data-stu-id="85f17-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="85f17-198">Push-XML-файла конфигурации (или рисунки темы)</span><span class="sxs-lookup"><span data-stu-id="85f17-198">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="85f17-199">Обновления программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="85f17-199">Software updates</span></span>
<span data-ttu-id="85f17-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="85f17-200"></span></span>

<span data-ttu-id="85f17-201">По умолчанию версии 2 систем комнаты Скайп пытается подключиться для магазина Windows для получения последней версии программного обеспечения систем комнаты Скайп версии 2, поэтому устройство потребует регулярных доступ к Интернету.</span><span class="sxs-lookup"><span data-stu-id="85f17-201">By default, Skype Room Systems v2 attempts to connect to the Windows Store to get the latest version of Skype Room Systems v2 software, so the device will require regular internet access.</span></span> <span data-ttu-id="85f17-202">Перед обращением с поддержки корпорации Майкрософт, убедитесь, что устройства v2 систем комнаты Скайп загружается с последней версией приложения.</span><span class="sxs-lookup"><span data-stu-id="85f17-202">Before contacting Microsoft with support issues, be sure the Skype Room Systems v2 device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="85f17-203">По умолчанию версии 2 Скайп комнаты систем подключается к Windows Update для получения операционной системы и обновления встроенного периферийный устройства USB и устанавливает их за пределами настроенных рабочих часов.</span><span class="sxs-lookup"><span data-stu-id="85f17-203">By default, Skype Room Systems v2 connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="85f17-204">Чтобы указать часы работы, войдите в учетную запись администратора и запустите приложение "Параметры".</span><span class="sxs-lookup"><span data-stu-id="85f17-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="85f17-205">Если нужно вручную управление обновлениями и не смогут выполните процедуру в разделе обычных для [Хранилища Майкрософт для бизнеса](https://businessstore.microsoft.com/store) для [автономных приложений, использующих распределить](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), можно получить в зависимостей из [набора развертывания](https://go.microsoft.com/fwlink/?linkid=851168) (от и APPX файлов инструкции для [настройки консоли версии 2 Скайп комнаты систем](../../deploy/deploy-clients/console.md)), который можно использовать с SCCM.</span><span class="sxs-lookup"><span data-stu-id="85f17-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="85f17-206">Выпуск пакета развертывания меньше, чем выпуска хранилища, поэтому он может не всегда соответствовать последняя построения.</span><span class="sxs-lookup"><span data-stu-id="85f17-206">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="85f17-207">Чтобы обновить с помощью Powershell</span><span class="sxs-lookup"><span data-stu-id="85f17-207">To update using Powershell</span></span>

1. <span data-ttu-id="85f17-208">Извлеките из установки [MSI](https://go.microsoft.com/fwlink/?linkid=851168) в ресурсе устройства имеет доступ.</span><span class="sxs-lookup"><span data-stu-id="85f17-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="85f17-209">Выполните следующий скрипт, предназначенные для устройств версии 2 Скайп комнаты системы, изменение \<общий доступ к\> на устройство общий доступ к соответствующим образом:</span><span class="sxs-lookup"><span data-stu-id="85f17-209">Run the following script targeting the Skype Room Systems v2 devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="85f17-210">Режим администрирования и управление устройствами</span><span class="sxs-lookup"><span data-stu-id="85f17-210">Admin mode and device management</span></span>
<span data-ttu-id="85f17-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="85f17-211"></span></span>

<span data-ttu-id="85f17-212">Некоторые функции управления, как вручную Установка закрытого сертификата ЦС, требуются Surface Pro устройства в режиме администратором.</span><span class="sxs-lookup"><span data-stu-id="85f17-212">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a><span data-ttu-id="85f17-213">Переключение в режим администрирования и обратно в том случае, если запущены приложения систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="85f17-213">Switching to Admin Mode and back when the Skype Room Systems v2 app is running</span></span>

1. <span data-ttu-id="85f17-214">Разорвите все текущие вызовы и вернуться на главном экране.</span><span class="sxs-lookup"><span data-stu-id="85f17-214">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="85f17-215">Выберите значок шестеренки и вызова меню (параметры являются **Параметры**, **Специальные возможности**и **Перезапустите устройства** ).</span><span class="sxs-lookup"><span data-stu-id="85f17-215">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="85f17-216">Выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="85f17-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="85f17-217">Введите пароль администратора.</span><span class="sxs-lookup"><span data-stu-id="85f17-217">Enter the Administrator Password.</span></span> <span data-ttu-id="85f17-218">Откроется экран настройки.</span><span class="sxs-lookup"><span data-stu-id="85f17-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="85f17-219">Если устройство не присоединенный к домену, по умолчанию будет использоваться локальный учетную запись администратора (имя пользователя «Admin»).</span><span class="sxs-lookup"><span data-stu-id="85f17-219">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="85f17-220">Паролем по умолчанию для этой учетной записи является "sfb", но по соображениям безопасности его рекомендуется как можно быстрее изменить.</span><span class="sxs-lookup"><span data-stu-id="85f17-220">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="85f17-221">Если компьютер, присоединенный к домену, могут выполнить вход с соответствующим образом привилегированной домен учетной записи.</span><span class="sxs-lookup"><span data-stu-id="85f17-221">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="85f17-222">В левом столбце выберите **Параметры Windows** .</span><span class="sxs-lookup"><span data-stu-id="85f17-222">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="85f17-223">Выберите **Go to Admin Sign-in** (Перейти на страницу входа администратора).</span><span class="sxs-lookup"><span data-stu-id="85f17-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="85f17-224">Введите пароль администратора.</span><span class="sxs-lookup"><span data-stu-id="85f17-224">Enter the Administrator Password.</span></span> <span data-ttu-id="85f17-225">Будет выполнен выход из приложения, а затем откроется экран входа Windows.</span><span class="sxs-lookup"><span data-stu-id="85f17-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="85f17-226">Выполните вход в систему с использованием учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="85f17-226">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="85f17-227">Вам придется необходимые привилегии управлять устройством.</span><span class="sxs-lookup"><span data-stu-id="85f17-227">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="85f17-228">Выполните необходимые административные задачи.</span><span class="sxs-lookup"><span data-stu-id="85f17-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="85f17-229">Выйдите из учетной записи с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="85f17-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="85f17-230">Вернуться к версии 2 Скайп комнаты систем, выбрав значок учетной записи пользователя в левой части экрана и затем выбрав **Скайп**.</span><span class="sxs-lookup"><span data-stu-id="85f17-230">Return to Skype Room Systems v2 by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="85f17-231">Если пользователь **Скайп** не указан, может потребоваться выберите **других пользователей** и введите **. \skype** как имя пользователя и войти.</span><span class="sxs-lookup"><span data-stu-id="85f17-231">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="85f17-232">Консоль является теперь обратно в обычном режиме. Следующая процедура запрашивает присоединение клавиатуры на устройство, если один еще не подключена.</span><span class="sxs-lookup"><span data-stu-id="85f17-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a><span data-ttu-id="85f17-233">Переключение в режим администрирования и обратно в том случае, если сбой приложения систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="85f17-233">Switching to Admin Mode and back when the Skype Room Systems v2 app crashes</span></span>

1. <span data-ttu-id="85f17-234">Быстро нажмите клавишу Windows пять раз подряд.</span><span class="sxs-lookup"><span data-stu-id="85f17-234">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="85f17-235">Откроется экран входа Windows.</span><span class="sxs-lookup"><span data-stu-id="85f17-235">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="85f17-236">Выполните вход в систему с использованием учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="85f17-236">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="85f17-237">Этот метод не выход пользователя Скайп или корректного завершения приложения, но можно использовать его, если приложения не был отвечать на запросы и другой метод были недоступны.</span><span class="sxs-lookup"><span data-stu-id="85f17-237">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="85f17-238">Выполните необходимые административные задачи.</span><span class="sxs-lookup"><span data-stu-id="85f17-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="85f17-239">Перезагрузите компьютер после завершения работы.</span><span class="sxs-lookup"><span data-stu-id="85f17-239">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="85f17-240">Консоль перезапускает в его обычной работе режима, работа приложения v2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="85f17-240">The console restarts into its normal operation mode, running the Skype Room Systems v2 app.</span></span> <span data-ttu-id="85f17-241">Можно удалить клавиатуры, если он был подключен к для выполнения этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="85f17-241">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="85f17-242">Советы по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="85f17-242">Troubleshooting tips</span></span>
   <span data-ttu-id="85f17-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="85f17-243"></span></span>

- <span data-ttu-id="85f17-244">Приглашения на собрания может не отображаться при отправке за пределами домена (например, между двумя компаниями).</span><span class="sxs-lookup"><span data-stu-id="85f17-244">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="85f17-245">В таких случаях ИТ-администраторов. следует решить, следует ли разрешить внешним пользователям планировать собрания.</span><span class="sxs-lookup"><span data-stu-id="85f17-245">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="85f17-246">Версии 2 Скайп комнаты систем не поддерживает перенаправления автообнаружения Exchange с помощью Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="85f17-246">Skype Room Systems v2 doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="85f17-247">В общем случае рекомендуется для ИТ-администраторов для отключения любого звука конечных точек, они не требуется использовать.</span><span class="sxs-lookup"><span data-stu-id="85f17-247">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="85f17-248">Если в режиме предварительного просмотра комнаты выводится зеркальное отражение, ИТ-администратор может устранить эту проблему, выключив и снова включив питание камеры или настроив зеркальное отражение изображения с помощью пульта дистанционного управления камерой.</span><span class="sxs-lookup"><span data-stu-id="85f17-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="85f17-249">Известны случаи утери доступа к сенсорному экрану консоли.</span><span class="sxs-lookup"><span data-stu-id="85f17-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="85f17-250">В таких случаях в некоторых случаях неполадки посредством перезагрузки системы систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="85f17-250">In such cases, the issue is sometimes resolved by restarting the Skype Room Systems v2 system.</span></span>
    
- <span data-ttu-id="85f17-251">Известны случаи исчезновения локального звукового сигнала при подключении компьютера к консоли с помощью кабеля.</span><span class="sxs-lookup"><span data-stu-id="85f17-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="85f17-252">Эту проблему можно устранить путем перезагрузки компьютера.</span><span class="sxs-lookup"><span data-stu-id="85f17-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
