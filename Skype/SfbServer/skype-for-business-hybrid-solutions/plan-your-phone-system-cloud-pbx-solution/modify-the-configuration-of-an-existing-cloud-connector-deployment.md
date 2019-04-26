---
title: Изменение конфигурации существующего развертывания Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Выполните действия, описанные в этом разделе, чтобы изменить конфигурацию существующего Скайп для соединителя Cloud Business Edition версии 1.4.1 или более поздняя версия развертывания.
ms.openlocfilehash: abe7d9be6ec0ae48ff8cbac09475c6a41bf2a49f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237611"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="e1326-103">Изменение конфигурации существующего развертывания Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e1326-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="e1326-104">Выполните действия, описанные в этом разделе, чтобы изменить конфигурацию существующего Скайп для соединителя Cloud Business Edition версии 1.4.1 или более поздняя версия развертывания.</span><span class="sxs-lookup"><span data-stu-id="e1326-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="e1326-105">Изменение конфигурации отдельного сайта</span><span class="sxs-lookup"><span data-stu-id="e1326-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="e1326-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="e1326-106"></span></span>

<span data-ttu-id="e1326-107">Если сайт содержит только одно устройство, при необходимости изменить параметры конфигурации после его развертывания можно внести изменения в файл CloudConnector.ini и снова запустить развертывание.</span><span class="sxs-lookup"><span data-stu-id="e1326-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="e1326-108">Выполните следующий командлет, чтобы удалить все существующие виртуальные машины на сервере узла. </span><span class="sxs-lookup"><span data-stu-id="e1326-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="e1326-109">Выполните следующий командлет, чтобы отменить регистрацию устройства:</span><span class="sxs-lookup"><span data-stu-id="e1326-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="e1326-110">Измените файл CloudConnector.ini в каталоге устройств.</span><span class="sxs-lookup"><span data-stu-id="e1326-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="e1326-111">Выполните следующий командлет, чтобы обновить конфигурацию: (этот шаг применима только для версии 2; для предыдущих версий, перейдите к следующему шагу.)</span><span class="sxs-lookup"><span data-stu-id="e1326-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="e1326-112">Выполните следующий командлет, чтобы зарегистрировать устройство снова:</span><span class="sxs-lookup"><span data-stu-id="e1326-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```
   Register-CcAppliance
   ```

6. <span data-ttu-id="e1326-113">Выполните следующий командлет, чтобы установить Skype для бизнеса Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="e1326-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```
   Install-CcAppliance
   ```

<span data-ttu-id="e1326-114">При наличии нескольких устройств на сайте необходимо выполнить эти шаги, изменить файл CloudConnector.ini и последовательно развернуть все устройства снова.</span><span class="sxs-lookup"><span data-stu-id="e1326-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="e1326-115">Выполните следующий командлет, чтобы удалить все существующие виртуальные машины на текущем устройстве. </span><span class="sxs-lookup"><span data-stu-id="e1326-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="e1326-116">Выполните следующий командлет, чтобы отменить регистрацию устройства:</span><span class="sxs-lookup"><span data-stu-id="e1326-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="e1326-117">Измените файл CloudConnector.ini в каталоге устройств.</span><span class="sxs-lookup"><span data-stu-id="e1326-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="e1326-118">Выполните следующий командлет, чтобы обновить конфигурацию: (этот шаг применима только для версии 2; для предыдущих версий, перейдите к следующему шагу.)</span><span class="sxs-lookup"><span data-stu-id="e1326-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="e1326-119">Выполните следующий командлет, чтобы зарегистрировать устройство снова:</span><span class="sxs-lookup"><span data-stu-id="e1326-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```
   Register-CcAppliance
   ```

6. <span data-ttu-id="e1326-120">Выполните следующий командлет на всех остальных устройствах сайта, чтобы получить последнюю конфигурацию:</span><span class="sxs-lookup"><span data-stu-id="e1326-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```
   Publish-CcAppliance
   ```

7. <span data-ttu-id="e1326-121">Выполните следующий командлет, чтобы снова развернуть соединитель облака на текущем устройстве:</span><span class="sxs-lookup"><span data-stu-id="e1326-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="e1326-122">Изменение конфигурации нескольких сайтов</span><span class="sxs-lookup"><span data-stu-id="e1326-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="e1326-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e1326-123"></span></span>

<span data-ttu-id="e1326-124">Для изменения конфигурации для нескольких сайтов в развертывании, выполните шаги для одного сайта, обновление одного сайта за раз.</span><span class="sxs-lookup"><span data-stu-id="e1326-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="e1326-125">Включите автоматические обновления в конфигурации своего клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="e1326-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="e1326-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e1326-126"></span></span>

<span data-ttu-id="e1326-127">Чтобы включить автоматическое обновление операционной системы и биты автоматических обновлений, необходимо использовать Скайп для учетной записи администратора клиента Business для управления и использования клиентов удаленной оболочки PowerShell следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e1326-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="e1326-128">Если вы отключили автоматические обновления операционной системы или бит автоматических обновлений, узла и виртуальной машиной пропустить важные обновления Windows и соединитель облака не обновления до новой версии автоматически.</span><span class="sxs-lookup"><span data-stu-id="e1326-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="e1326-129">Настоятельно рекомендуется включить автоматическое обновление.</span><span class="sxs-lookup"><span data-stu-id="e1326-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="e1326-130">Свойство EnableAutoUpdate сайта должен иметь значение true (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e1326-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="e1326-131">Выполните следующий командлет, чтобы убедиться, что свойство EnableAutoUpdate имеет значение true:</span><span class="sxs-lookup"><span data-stu-id="e1326-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="e1326-132">Создайте период автоматического обновления для клиента.</span><span class="sxs-lookup"><span data-stu-id="e1326-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="e1326-p103">Автоматическое обновление может выполняться ежедневно, еженедельно и ежемесячно. Для каждого периода необходимо задать дату начала и продолжительность.</span><span class="sxs-lookup"><span data-stu-id="e1326-p103">The time window can be daily, weekly and monthly. All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="e1326-135">Для ежедневного обновления требуется указать только время начала и продолжительность. </span><span class="sxs-lookup"><span data-stu-id="e1326-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="e1326-136">Для еженедельного обновления необходимо указать один или несколько дней недели.</span><span class="sxs-lookup"><span data-stu-id="e1326-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="e1326-p104">Ежемесячное обновление может выполняться двумя разными способами. В первом случае указывается день месяца. Во втором задаются недели и дни недели (допускается выбор нескольких элементов).</span><span class="sxs-lookup"><span data-stu-id="e1326-p104">For a monthly time window, there can be two types. The first type is to specify the day of the month, which can be a single day. The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="e1326-p105">Для каждого клиента можно определить 20 периодов времени. По умолчанию для нового клиента устанавливается период, соответствующий периоду обновления операционной системы и компонентов. Чтобы настроить ежедневное, еженедельное или ежемесячное обновление, выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="e1326-p105">Each tenant can have 20 time windows defined. The default time window will be created for a new tenant as the default time window for operating system update and Bits update. Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="e1326-143">Задайте интервал времени обновления для сайта. </span><span class="sxs-lookup"><span data-stu-id="e1326-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="e1326-p106">Интервалы времени обновления BITS-файлов и операционной системы задаются отдельно. В обоих случаях можно настроить один или несколько интервалов времени. Каждый интервал времени может быть назначен разным сайтам для разных целей (обновление BITS-файлов или операционной системы). Выполните следующий командлет, чтобы установить интервал времени для сайта: </span><span class="sxs-lookup"><span data-stu-id="e1326-p106">The Bits update time and OS update time windows are configured separately. Both of them can be assigned single or multiple time windows. Each time window can be assigned to different sites and different purpose (Bits update and OS update). Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="e1326-148">Обновите выделенные учетные данные администратора клиента. </span><span class="sxs-lookup"><span data-stu-id="e1326-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="e1326-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e1326-149"></span></span>

<span data-ttu-id="e1326-150">Из учетной записи с необходимых разрешениях выполняются административные изменения в клиента Office 365 для соединителя облака.</span><span class="sxs-lookup"><span data-stu-id="e1326-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="e1326-151">В облаке соединителя версиях до 2.0 этой учетной записи — это учетная запись администратора выделенного глобального клиента.</span><span class="sxs-lookup"><span data-stu-id="e1326-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="e1326-152">В облаке соединителя версии 2.0 и более поздних версий этой учетной записи может быть учетную запись Office 365 с помощью Скайп для права администратора предприятия.</span><span class="sxs-lookup"><span data-stu-id="e1326-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="e1326-153">Если изменить свои учетные данные учетной записи администратора в Office 365, также потребуется обновить локально кэшированные учетные данные в облаке соединителя, выполнив следующую команду PowerShell администратора на каждом устройстве соединителя облачных развернутого:</span><span class="sxs-lookup"><span data-stu-id="e1326-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="e1326-154">Обновите пароль для сервера узла. </span><span class="sxs-lookup"><span data-stu-id="e1326-154">Update the password for the host server</span></span>
<span data-ttu-id="e1326-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e1326-155"></span></span>

> [!NOTE]
> <span data-ttu-id="e1326-156">Это раздел применяется только к Cloud Connector версии 2.0 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="e1326-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="e1326-157">Все облака соединителя учетные данные хранятся в следующий файл: «% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml».</span><span class="sxs-lookup"><span data-stu-id="e1326-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="e1326-158">При изменении пароля на сервере узла необходимо обновить учетные данные, сохраненные локально.</span><span class="sxs-lookup"><span data-stu-id="e1326-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="e1326-159">Чтобы обновить локально сохраненных учетных данных на устройстве соединителя облаке, используйте командлеты [Get-CcCredential](get-cccredential.md) и [Set-CcCredential](set-cccredential.md) и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e1326-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="e1326-160">Выполните следующие команды, чтобы получить пароли, которые вам понадобятся в дальнейшем. </span><span class="sxs-lookup"><span data-stu-id="e1326-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="e1326-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e1326-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="e1326-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e1326-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="e1326-163">Get-CcCredential -AccountType CceService -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e1326-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="e1326-164">Измените пароль учетной записи на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="e1326-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="e1326-165">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="e1326-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="e1326-166">Удалите следующий файл: «% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml».</span><span class="sxs-lookup"><span data-stu-id="e1326-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="e1326-167">Запуск консоли PowerShell от имени администратора и запустите «Register CcAppliance-локальный» повторного ввода после описания службы и паролей.</span><span class="sxs-lookup"><span data-stu-id="e1326-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="e1326-168">Необходимо ввести тот же пароль, который был указан ранее для развертывания Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e1326-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="e1326-p110">По умолчанию для учетных записей VmAdmin и DomainAdmin используется тот же пароль, что и для CceService. Если пароли для учетных записей DomainAdmin, VMAdmin и CceService, возвращаемые на шаге 1, различаются между собой, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e1326-p110">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="e1326-171">Запустите командлет Set-CcCredential -AccountType DomainAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="e1326-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="e1326-172">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="e1326-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="e1326-173">При запросе учетных данных новой учетной записи введите пароль для учетной записи DomainAdmin, возвращенный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="e1326-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="e1326-174">Запустите командлет Set-CcCredential -AccountType VmAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="e1326-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="e1326-175">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="e1326-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="e1326-176">При запросе учетных данных новой учетной записи введите пароль для учетной записи VmAdmin, возвращенный на шаге 1. </span><span class="sxs-lookup"><span data-stu-id="e1326-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="e1326-177">Обновление пароля для учетной записи CceService</span><span class="sxs-lookup"><span data-stu-id="e1326-177">Update the password for the CceService account</span></span>
<span data-ttu-id="e1326-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e1326-178"></span></span>

> [!NOTE]
> <span data-ttu-id="e1326-179">В этом разделе, применимы к версии облачных соединителя 2.0.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="e1326-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="e1326-180">Служба управления соединителя облачных запущена служба соединителя облака.</span><span class="sxs-lookup"><span data-stu-id="e1326-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="e1326-181">Учетная запись CceService создан во время развертывания облака соединителя Edition и сохраняются в следующие файлы: «% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml» и «% SystemDrive%\Programdata\Cloudconnector\credentials... CceService.xml».</span><span class="sxs-lookup"><span data-stu-id="e1326-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="e1326-182">Чтобы убедиться, что все устройства можно получить доступ к общий каталог сайтов, пароль для учетной записи CceService должны быть одинаковыми на всех устройствах, развернут на сайте.</span><span class="sxs-lookup"><span data-stu-id="e1326-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="e1326-183">Учитывайте следующее.</span><span class="sxs-lookup"><span data-stu-id="e1326-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="e1326-184">По умолчанию учетная запись CceService настроен как «Срок действия пароля не ограничен».</span><span class="sxs-lookup"><span data-stu-id="e1326-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="e1326-185">При обновлении пароля, корпорация Майкрософт рекомендует поддержание этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e1326-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="e1326-186">Необходимо обновить пароль во время использования наименьшей и за ее пределами windows время автоматического обновления для битов или обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="e1326-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="e1326-187">При обновлении пароля, устройства должны быть извлекаются и перезапущена, который принимает некоторое время.</span><span class="sxs-lookup"><span data-stu-id="e1326-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="e1326-188">Перезапуск устройства будут прерывания операции автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="e1326-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="e1326-189">При изменении пароля учетной записи CceService, необходимо указать все учетные данные и обновлять их в локально сохраненных файлов.</span><span class="sxs-lookup"><span data-stu-id="e1326-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="e1326-190">Для каждого устройства, к которой принадлежит на одном сайте PSTN необходимо указать следующее:</span><span class="sxs-lookup"><span data-stu-id="e1326-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="e1326-191">Выполните следующие команды, чтобы получить имена учетных записей и пароли, которые будут использовать более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e1326-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```
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

2. <span data-ttu-id="e1326-192">Выполните командлет CcUpdate ввод для извлечения устройства и перетащить его в режим обслуживания вручную.</span><span class="sxs-lookup"><span data-stu-id="e1326-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="e1326-193">Обновление пароля учетной записи CceService на хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="e1326-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="e1326-194">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="e1326-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="e1326-195">Выполните командлет Restore-CcCredentials повторного ввода после описания службы и паролей.</span><span class="sxs-lookup"><span data-stu-id="e1326-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="e1326-196">Убедитесь, что укажите тот же пароль, введенные до развертывания облака соединителя за исключением учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="e1326-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="e1326-197">Для учетной записи CceService введите новый пароль.</span><span class="sxs-lookup"><span data-stu-id="e1326-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="e1326-198">Убедитесь, что новый пароль для учетной записи CceService является общим для всех устройств на сайте PSTN.</span><span class="sxs-lookup"><span data-stu-id="e1326-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="e1326-p116">По умолчанию для учетных записей VmAdmin и DomainAdmin используется тот же пароль, что и для CceService. Если пароли для учетных записей DomainAdmin, VMAdmin и CceService, возвращаемые на шаге 1, различаются между собой, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e1326-p116">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="e1326-201">Запустите командлет Set-CcCredential -AccountType DomainAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="e1326-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="e1326-202">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="e1326-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="e1326-203">При запросе учетных данных новой учетной записи введите пароль для учетной записи DomainAdmin, возвращенный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="e1326-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="e1326-204">Запустите командлет Set-CcCredential -AccountType VmAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="e1326-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="e1326-205">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="e1326-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="e1326-206">При запросе учетных данных новой учетной записи введите пароль для учетной записи VmAdmin, возвращенный на шаге 1. </span><span class="sxs-lookup"><span data-stu-id="e1326-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="e1326-207">Выполните командлет CcUpdate выхода для перемещения устройства из режима обслуживания вручную.</span><span class="sxs-lookup"><span data-stu-id="e1326-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="e1326-208">После выполнения этих действий на всех устройствах на том же сайте PSTN, удалите следующие файлы в корневой папке сайта:</span><span class="sxs-lookup"><span data-stu-id="e1326-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="e1326-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="e1326-209">CcLockFile</span></span>
    
    - <span data-ttu-id="e1326-210">Site_\<полное доменное имя пограничного пула внешнего Sip\></span><span class="sxs-lookup"><span data-stu-id="e1326-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="e1326-211">Tenant_\<полное доменное имя пограничного пула внешнего Sip\></span><span class="sxs-lookup"><span data-stu-id="e1326-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="e1326-212">TenantConfigLock_\<полное доменное имя пограничного пула внешнего Sip\></span><span class="sxs-lookup"><span data-stu-id="e1326-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="e1326-213">Добавьте новый домен SIP. </span><span class="sxs-lookup"><span data-stu-id="e1326-213">Add a new SIP domain</span></span>
<span data-ttu-id="e1326-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e1326-214"></span></span>

<span data-ttu-id="e1326-215">Чтобы добавить новый домен SIP (или несколько доменов SIP) существующего развертывания облака соединителя, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e1326-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="e1326-216">Вам потребуется выполнить процедуру по изменению домена в Office 365 и убедиться, что вы можете добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="e1326-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="e1326-217">Дополнительные сведения о том, как настроить свой домен в Office 365 можно [Добавить домен в Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="e1326-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="e1326-218">Обновления файла конфигурации соединителя облаке новый домен SIP или доменов.</span><span class="sxs-lookup"><span data-stu-id="e1326-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="e1326-219">Запросите новый внешний сертификат пограничного сервера с помощью дополнительных имен SAN для sip.domain для каждого домена SIP, определенных в конфигурацию соединителя облака.</span><span class="sxs-lookup"><span data-stu-id="e1326-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="e1326-220">Задайте путь к новому внешнему сертификату пограничного компонента в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="e1326-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="e1326-221">Следуйте инструкциям, приведенным в статьях [Изменение конфигурации отдельного сайта](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) или [Изменение конфигурации нескольких сайтов](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="e1326-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="e1326-222">Измените основной домен SIP.</span><span class="sxs-lookup"><span data-stu-id="e1326-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="e1326-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e1326-223"></span></span>

<span data-ttu-id="e1326-224">Если необходимо изменить основной домен SIP в развертывании облачных соединителя, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e1326-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="e1326-225">Вам потребуется выполнить процедуру по изменению домена в Office 365 и убедиться, что вы можете добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="e1326-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="e1326-226">Дополнительные сведения о том, как настроить свой домен в Office 365 можно [Добавить домен в Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="e1326-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="e1326-227">Обновите файл конфигурации соединителя облако с новый домен SIP.</span><span class="sxs-lookup"><span data-stu-id="e1326-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="e1326-228">Запросите новый внешний сертификат пограничного сервера с помощью дополнительных имен SAN для sip.domain для каждого домена SIP, определенных в конфигурацию соединителя облака.</span><span class="sxs-lookup"><span data-stu-id="e1326-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="e1326-229">Задайте путь к новому внешнему сертификату пограничного компонента в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="e1326-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="e1326-230">Удалите регистрацию клиента для каждого устройства на сайте, выполнив следующий командлет в администратор PowerShell на соединителе облаке:</span><span class="sxs-lookup"><span data-stu-id="e1326-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="e1326-231">Удалите регистрацию клиента для каждого устройства на сайте, выполнив следующий командлет в консоли PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e1326-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="e1326-232">Удалите каждого устройства, выполнив следующий командлет в администратор PowerShell на соединителе облачных:</span><span class="sxs-lookup"><span data-stu-id="e1326-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="e1326-233">Регистрация каждого устройства, выполнив следующий командлет в администратор PowerShell на соединителе облаке:</span><span class="sxs-lookup"><span data-stu-id="e1326-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="e1326-234">Установка каждого устройства по одному, выполнив следующий командлет в администратор PowerShell на соединителе облаке:</span><span class="sxs-lookup"><span data-stu-id="e1326-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="e1326-235">Замените сертификат внешней границы нового сертификата</span><span class="sxs-lookup"><span data-stu-id="e1326-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="e1326-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e1326-236"></span></span>

<span data-ttu-id="e1326-237">Если вам необходимо заменить сертификат внешней границы на устройствах вашей облачной соединителя, необходимо получить новый сертификат для пограничного сервера, Подготовка PFX-файл, содержащий закрытый ключ и цепочки сертификатов, а затем выполните следующие действия на каждом устройстве:</span><span class="sxs-lookup"><span data-stu-id="e1326-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="e1326-238">Поместите устройства для обеспечения связи в режиме обслуживания с помощью командлета CcUpdate ввод.</span><span class="sxs-lookup"><span data-stu-id="e1326-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="e1326-239">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e1326-239">Run the following command:</span></span> 
    
   ```
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="e1326-240">Если пароль нового сертификата — это то же, что старый, импорт будет успешной.</span><span class="sxs-lookup"><span data-stu-id="e1326-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="e1326-241">Если пароль не совпадают, появится сообщение об ошибке пароль не так, что требуется сбросить пароль, выполнив командлет Register-CcAppliance с - параметр Local, и затем повторяющихся шаг 2.</span><span class="sxs-lookup"><span data-stu-id="e1326-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="e1326-242">Воспользуйтесь устройства из режима обслуживания с помощью командлета Exit - CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="e1326-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

