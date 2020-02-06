---
title: Изменение конфигурации существующего развертывания Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Выполните действия, описанные в этой статье, чтобы изменить конфигурацию существующего выпуска Skype для бизнеса Cloud Connector 1.4.1 или более поздней версии.
ms.openlocfilehash: 32a231ed85b94c09591adfcc6299cba704be267f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799439"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="e124d-103">Изменение конфигурации существующего развертывания Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e124d-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="e124d-104">Выполните действия, описанные в этой статье, чтобы изменить конфигурацию существующего выпуска Skype для бизнеса Cloud Connector 1.4.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e124d-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="e124d-105">Изменение конфигурации отдельного сайта</span><span class="sxs-lookup"><span data-stu-id="e124d-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="e124d-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="e124d-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="e124d-107">Если сайт содержит только одно устройство, при необходимости изменить параметры конфигурации после его развертывания можно внести изменения в файл CloudConnector.ini и снова запустить развертывание.</span><span class="sxs-lookup"><span data-stu-id="e124d-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="e124d-108">Выполните следующий командлет, чтобы удалить все существующие виртуальные машины на сервере узла. </span><span class="sxs-lookup"><span data-stu-id="e124d-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="e124d-109">Выполните следующий командлет, чтобы отменить регистрацию устройства:</span><span class="sxs-lookup"><span data-stu-id="e124d-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="e124d-110">Измените файл CloudConnector.ini в каталоге устройств.</span><span class="sxs-lookup"><span data-stu-id="e124d-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="e124d-111">Чтобы обновить конфигурацию, запустите следующий командлет: (этот шаг применим только для версии 2, для предыдущих версий — переход к следующему шагу).</span><span class="sxs-lookup"><span data-stu-id="e124d-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="e124d-112">Выполните следующий командлет, чтобы зарегистрировать устройство снова:</span><span class="sxs-lookup"><span data-stu-id="e124d-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="e124d-113">Выполните следующий командлет, чтобы установить Skype для бизнеса Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="e124d-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="e124d-114">При наличии нескольких устройств на сайте необходимо выполнить эти шаги, изменить файл CloudConnector.ini и последовательно развернуть все устройства снова.</span><span class="sxs-lookup"><span data-stu-id="e124d-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="e124d-115">Выполните следующий командлет, чтобы удалить все существующие виртуальные машины на текущем устройстве. </span><span class="sxs-lookup"><span data-stu-id="e124d-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="e124d-116">Выполните следующий командлет, чтобы отменить регистрацию устройства:</span><span class="sxs-lookup"><span data-stu-id="e124d-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="e124d-117">Измените файл CloudConnector.ini в каталоге устройств.</span><span class="sxs-lookup"><span data-stu-id="e124d-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="e124d-118">Чтобы обновить конфигурацию, запустите следующий командлет: (этот шаг применим только для версии 2, для предыдущих версий — переход к следующему шагу).</span><span class="sxs-lookup"><span data-stu-id="e124d-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="e124d-119">Выполните следующий командлет, чтобы зарегистрировать устройство снова:</span><span class="sxs-lookup"><span data-stu-id="e124d-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="e124d-120">Выполните следующий командлет на всех остальных устройствах сайта, чтобы получить последнюю конфигурацию:</span><span class="sxs-lookup"><span data-stu-id="e124d-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="e124d-121">Запустите следующий командлет для повторного развертывания облачного соединителя на текущем устройстве:</span><span class="sxs-lookup"><span data-stu-id="e124d-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="e124d-122">Изменение конфигурации нескольких сайтов</span><span class="sxs-lookup"><span data-stu-id="e124d-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="e124d-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e124d-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="e124d-124">Чтобы изменить конфигурацию нескольких сайтов в развертывании, выполните указанные ниже действия для одного сайта, обновив один сайт по очереди.</span><span class="sxs-lookup"><span data-stu-id="e124d-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="e124d-125">Включите автоматические обновления в конфигурации своего клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="e124d-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="e124d-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e124d-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="e124d-127">Чтобы включить автоматическое обновление операционной системы и автоматическое обновление службы BITS, вы должны использовать учетную запись администратора клиента Skype для бизнеса для управления Интернетом и использовать удаленную оболочку PowerShell для клиента, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="e124d-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="e124d-128">Если вы отключили автоматическое обновление операционной системы или автоматическое обновление службы BITS, узел и виртуальный компьютер могут пропустить важные обновления Windows, а облачный соединитель не будет обновляться до новой версии автоматически.</span><span class="sxs-lookup"><span data-stu-id="e124d-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="e124d-129">Настоятельно рекомендуется включить автоматическое обновление.</span><span class="sxs-lookup"><span data-stu-id="e124d-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="e124d-130">Свойству Енаблеаутаупдате сайта должно быть задано значение true (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e124d-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="e124d-131">Выполните следующий командлет, чтобы убедиться, что свойство EnableAutoUpdate имеет значение true:</span><span class="sxs-lookup"><span data-stu-id="e124d-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="e124d-132">Создайте период автоматического обновления для клиента.</span><span class="sxs-lookup"><span data-stu-id="e124d-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="e124d-p103">Автоматическое обновление может выполняться ежедневно, еженедельно и ежемесячно. Для каждого периода необходимо задать дату начала и продолжительность.</span><span class="sxs-lookup"><span data-stu-id="e124d-p103">The time window can be daily, weekly and monthly. All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="e124d-135">Для ежедневного обновления требуется указать только время начала и продолжительность. </span><span class="sxs-lookup"><span data-stu-id="e124d-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="e124d-136">Для еженедельного обновления необходимо указать один или несколько дней недели.</span><span class="sxs-lookup"><span data-stu-id="e124d-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="e124d-p104">Ежемесячное обновление может выполняться двумя разными способами. В первом случае указывается день месяца. Во втором задаются недели и дни недели (допускается выбор нескольких элементов).</span><span class="sxs-lookup"><span data-stu-id="e124d-p104">For a monthly time window, there can be two types. The first type is to specify the day of the month, which can be a single day. The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="e124d-p105">Для каждого клиента можно определить 20 периодов времени. По умолчанию для нового клиента устанавливается период, соответствующий периоду обновления операционной системы и компонентов. Чтобы настроить ежедневное, еженедельное или ежемесячное обновление, выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="e124d-p105">Each tenant can have 20 time windows defined. The default time window will be created for a new tenant as the default time window for operating system update and Bits update. Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="e124d-143">Задайте интервал времени обновления для сайта. </span><span class="sxs-lookup"><span data-stu-id="e124d-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="e124d-p106">Интервалы времени обновления BITS-файлов и операционной системы задаются отдельно. В обоих случаях можно настроить один или несколько интервалов времени. Каждый интервал времени может быть назначен разным сайтам для разных целей (обновление BITS-файлов или операционной системы). Выполните следующий командлет, чтобы установить интервал времени для сайта: </span><span class="sxs-lookup"><span data-stu-id="e124d-p106">The Bits update time and OS update time windows are configured separately. Both of them can be assigned single or multiple time windows. Each time window can be assigned to different sites and different purpose (Bits update and OS update). Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="e124d-148">Обновите выделенные учетные данные администратора клиента. </span><span class="sxs-lookup"><span data-stu-id="e124d-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="e124d-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e124d-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="e124d-150">Административные изменения в клиенте Office 365 для облачного соединителя выполняются из учетной записи с необходимыми разрешениями.</span><span class="sxs-lookup"><span data-stu-id="e124d-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="e124d-151">В версиях облачных соединителей, предшествующих 2,0, эта учетная запись является выделенной учетной записью администратора глобального клиента.</span><span class="sxs-lookup"><span data-stu-id="e124d-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="e124d-152">В облачных соединителях версии 2,0 и более поздних эта учетная запись может быть учетной записью Office 365 с правами администратора Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e124d-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="e124d-153">Если учетные данные учетной записи администратора изменяются в Office 365, вам также нужно обновить локально кэшированные учетные данные в облачном соединителе, выполнив следующую команду администратора PowerShell на каждом устройстве облачного соединителя, которое вы развернули:</span><span class="sxs-lookup"><span data-stu-id="e124d-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="e124d-154">Обновите пароль для сервера узла. </span><span class="sxs-lookup"><span data-stu-id="e124d-154">Update the password for the host server</span></span>
<span data-ttu-id="e124d-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e124d-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="e124d-156">Это раздел применяется только к Cloud Connector версии 2.0 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="e124d-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="e124d-157">Все учетные данные облачного соединителя хранятся в следующем файле: "%Системдриве%\програмдата\клаудконнектор\кредентиалс. \<CurrentUser\>. XML ".</span><span class="sxs-lookup"><span data-stu-id="e124d-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="e124d-158">При изменении пароля на сервере узла необходимо обновить учетные данные, сохраненные локально.</span><span class="sxs-lookup"><span data-stu-id="e124d-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="e124d-159">Чтобы обновить локально хранящиеся учетные данные на устройстве облачного соединителя, используйте командлеты [Get-кккредентиал](get-cccredential.md) и [Set-кккредентиал](set-cccredential.md) , а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e124d-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="e124d-160">Выполните следующие команды, чтобы получить пароли, которые вам понадобятся в дальнейшем. </span><span class="sxs-lookup"><span data-stu-id="e124d-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="e124d-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e124d-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="e124d-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e124d-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="e124d-163">Get-CcCredential -AccountType CceService -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e124d-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="e124d-164">Измените пароль учетной записи на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="e124d-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="e124d-165">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="e124d-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="e124d-166">Удалите следующий файл: "%Системдриве%\програмдата\клаудконнектор\кредентиалс. \<CurrentUser\>. XML ".</span><span class="sxs-lookup"><span data-stu-id="e124d-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="e124d-167">Запустите консоль PowerShell с правами администратора, а затем выполните команду "Register-Ккапплианце-Local", чтобы повторно ввести пароли после описания.</span><span class="sxs-lookup"><span data-stu-id="e124d-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="e124d-168">Необходимо ввести тот же пароль, который был указан ранее для развертывания Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e124d-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="e124d-p110">По умолчанию для учетных записей VmAdmin и DomainAdmin используется тот же пароль, что и для CceService. Если пароли для учетных записей DomainAdmin, VMAdmin и CceService, возвращаемые на шаге 1, различаются между собой, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e124d-p110">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="e124d-171">Запустите командлет Set-CcCredential -AccountType DomainAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="e124d-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="e124d-172">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="e124d-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="e124d-173">При запросе учетных данных новой учетной записи введите пароль для учетной записи DomainAdmin, возвращенный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="e124d-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="e124d-174">Запустите командлет Set-CcCredential -AccountType VmAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="e124d-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="e124d-175">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="e124d-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="e124d-176">При запросе учетных данных новой учетной записи введите пароль для учетной записи VmAdmin, возвращенный на шаге 1. </span><span class="sxs-lookup"><span data-stu-id="e124d-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="e124d-177">Обновление пароля для учетной записи Кцесервице</span><span class="sxs-lookup"><span data-stu-id="e124d-177">Update the password for the CceService account</span></span>
<span data-ttu-id="e124d-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e124d-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="e124d-179">Этот раздел подходит для облачного соединителя версии 2.0.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="e124d-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="e124d-180">Служба облачного соединителя запускает службу управления облачным соединителем.</span><span class="sxs-lookup"><span data-stu-id="e124d-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="e124d-181">Учетная запись Кцесервице создается при развертывании Cloud Connector Edition и хранится в следующих файлах: "%Системдриве%\програмдата\клаудконнектор\кредентиалс. \<CurrentUser\>. XML "и"%системдриве%\програмдата\клаудконнектор\кредентиалс.. Кцесервице. XML ".</span><span class="sxs-lookup"><span data-stu-id="e124d-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="e124d-182">Чтобы убедиться в том, что все устройства могут получать доступ к общему каталогу сайта, пароль учетной записи Кцесервице на всех устройствах, развернутых на сайте, должен быть одинаковым.</span><span class="sxs-lookup"><span data-stu-id="e124d-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="e124d-183">Учитывайте следующее.</span><span class="sxs-lookup"><span data-stu-id="e124d-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="e124d-184">По умолчанию для учетной записи Кцесервице задано значение "пароль не просрочен".</span><span class="sxs-lookup"><span data-stu-id="e124d-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="e124d-185">Если вы обновите пароль, корпорация Майкрософт рекомендует сохранить эти настройки.</span><span class="sxs-lookup"><span data-stu-id="e124d-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="e124d-186">Вы должны обновить пароль в течение непиковых периодов использования, а также за пределами периодов автоматического обновления в Windows для BITS или обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="e124d-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="e124d-187">Когда вы обновляете пароль, устройство должно быть стоко и перезапускаться, что займет некоторое время.</span><span class="sxs-lookup"><span data-stu-id="e124d-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="e124d-188">Перезапуск устройства приведет к прерыванию операций автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="e124d-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="e124d-189">Когда вы измените пароль учетной записи Кцесервице, вам нужно будет указать все учетные данные и обновить их в файле, сохраненном на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e124d-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="e124d-190">Для каждого устройства, принадлежащего к одному и тому же сайту PSTN, необходимо указать следующее:</span><span class="sxs-lookup"><span data-stu-id="e124d-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="e124d-191">Чтобы получить имена учетных записей и пароли, которые будут использоваться позже, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="e124d-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. <span data-ttu-id="e124d-192">Запустите командлет Enter-Ккупдате, чтобы очистить устройство и переместить его в режим ручного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e124d-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="e124d-193">Обновите пароль учетной записи Кцесервице на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="e124d-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="e124d-194">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="e124d-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="e124d-195">Запустите командлет Restore-Кккредентиалс, чтобы повторно ввести пароль, следуя описанию.</span><span class="sxs-lookup"><span data-stu-id="e124d-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="e124d-196">Убедитесь, что вы ввели тот же пароль, который вы указали перед развертыванием облачного соединителя, кроме учетной записи Кцесервице.</span><span class="sxs-lookup"><span data-stu-id="e124d-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="e124d-197">Введите новый пароль для учетной записи Кцесервице.</span><span class="sxs-lookup"><span data-stu-id="e124d-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="e124d-198">Убедитесь, что новый пароль для учетной записи Кцесервице одинаков для всех устройств на сайте КТСОП.</span><span class="sxs-lookup"><span data-stu-id="e124d-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="e124d-p116">По умолчанию для учетных записей VmAdmin и DomainAdmin используется тот же пароль, что и для CceService. Если пароли для учетных записей DomainAdmin, VMAdmin и CceService, возвращаемые на шаге 1, различаются между собой, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e124d-p116">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="e124d-201">Запустите командлет Set-CcCredential -AccountType DomainAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="e124d-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="e124d-202">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="e124d-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="e124d-203">При запросе учетных данных новой учетной записи введите пароль для учетной записи DomainAdmin, возвращенный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="e124d-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="e124d-204">Запустите командлет Set-CcCredential -AccountType VmAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="e124d-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="e124d-205">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="e124d-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="e124d-206">При запросе учетных данных новой учетной записи введите пароль для учетной записи VmAdmin, возвращенный на шаге 1. </span><span class="sxs-lookup"><span data-stu-id="e124d-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="e124d-207">Запустите командлет Exit-Ккупдате, чтобы переместить устройство из режима ручного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e124d-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="e124d-208">После выполнения этих действий на всех устройствах на одном сайте КТСОП удалите следующие файлы в корневом каталоге сайта.</span><span class="sxs-lookup"><span data-stu-id="e124d-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="e124d-209">кклоккфиле</span><span class="sxs-lookup"><span data-stu-id="e124d-209">CcLockFile</span></span>
    
    - <span data-ttu-id="e124d-210">Полное\<доменное имя пула внешних SIP Site_ Edge\></span><span class="sxs-lookup"><span data-stu-id="e124d-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="e124d-211">Полное\<доменное имя пула внешних SIP Tenant_ Edge\></span><span class="sxs-lookup"><span data-stu-id="e124d-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="e124d-212">Полное\<доменное имя пула внешних SIP TenantConfigLock_ Edge\></span><span class="sxs-lookup"><span data-stu-id="e124d-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="e124d-213">Добавьте новый домен SIP. </span><span class="sxs-lookup"><span data-stu-id="e124d-213">Add a new SIP domain</span></span>
<span data-ttu-id="e124d-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e124d-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="e124d-215">Чтобы добавить новый домен SIP (или несколько доменов SIP) в существующее развертывание облачного соединителя, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e124d-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="e124d-216">Вам потребуется выполнить процедуру по изменению домена в Office 365 и убедиться, что вы можете добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="e124d-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="e124d-217">Дополнительные сведения о настройке домена в Office 365 можно найти в разделе [Добавление домена в office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="e124d-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="e124d-218">Обновите файл конфигурации облачного соединителя с помощью нового домена или доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="e124d-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="e124d-219">Запрос нового внешнего сертификата пограничного сервера с дополнительными именами SAN для SIP. Domain для каждого домена SIP, определенного в конфигурации облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="e124d-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="e124d-220">Задайте путь к новому внешнему сертификату пограничного компонента в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="e124d-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="e124d-221">Следуйте инструкциям, приведенным в статьях [Изменение конфигурации отдельного сайта](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) или [Изменение конфигурации нескольких сайтов](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="e124d-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="e124d-222">Измените основной домен SIP.</span><span class="sxs-lookup"><span data-stu-id="e124d-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="e124d-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e124d-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="e124d-224">Если вам нужно изменить основной домен SIP в развертывании облачного соединителя, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e124d-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="e124d-225">Вам потребуется выполнить процедуру по изменению домена в Office 365 и убедиться, что вы можете добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="e124d-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="e124d-226">Дополнительные сведения о настройке домена в Office 365 можно найти в разделе [Добавление домена в office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="e124d-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="e124d-227">Обновите файл конфигурации облачного соединителя с новым доменом SIP.</span><span class="sxs-lookup"><span data-stu-id="e124d-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="e124d-228">Запрос нового внешнего сертификата пограничного сервера с дополнительными именами SAN для SIP. Domain для каждого домена SIP, определенного в конфигурации облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="e124d-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="e124d-229">Задайте путь к новому внешнему сертификату пограничного компонента в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="e124d-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="e124d-230">Удалите регистрацию клиента для каждого устройства на сайте, выполнив следующий командлет из оболочки администратора PowerShell для облачного соединителя:</span><span class="sxs-lookup"><span data-stu-id="e124d-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="e124d-231">Удалите регистрацию клиента для каждого устройства на сайте, выполнив следующий командлет в консоли PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e124d-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="e124d-232">Удалите каждое устройство, выполнив следующий командлет в PowerShell администратора для облачного соединителя:</span><span class="sxs-lookup"><span data-stu-id="e124d-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="e124d-233">Зарегистрируйте каждое устройство, выполнив следующий командлет в PowerShell администратора в облачном соединителе:</span><span class="sxs-lookup"><span data-stu-id="e124d-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="e124d-234">Установите каждое устройство по одному, выполнив следующий командлет в PowerShell администратора в облачном соединителе:</span><span class="sxs-lookup"><span data-stu-id="e124d-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="e124d-235">Замена внешнего сертификата пограничного сервера новым сертификатом</span><span class="sxs-lookup"><span data-stu-id="e124d-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="e124d-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e124d-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="e124d-237">Если вам потребуется заменить внешний сертификат EDGE на устройствах облачного соединителя, вам потребуется получить новый пограничный сертификат, подготовить PFX-файл с закрытым ключом и цепочкой полного сертификата, а затем выполнить указанные ниже действия для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="e124d-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="e124d-238">Переведите устройство в режим обслуживания с помощью командлета Enter-Ккупдате.</span><span class="sxs-lookup"><span data-stu-id="e124d-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="e124d-239">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e124d-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="e124d-240">Если пароль нового сертификата совпадает со старым, импорт будет выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e124d-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="e124d-241">Если пароль не изменится, появится сообщение о том, что пароль неверен, и вам потребуется сбросить пароль, запустив командлет Register-Ккапплианце с параметром-Local, а затем повторив шаг 2.</span><span class="sxs-lookup"><span data-stu-id="e124d-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="e124d-242">Извлеките устройство из режима обслуживания с помощью командлета Exit-Ккупдате.</span><span class="sxs-lookup"><span data-stu-id="e124d-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

