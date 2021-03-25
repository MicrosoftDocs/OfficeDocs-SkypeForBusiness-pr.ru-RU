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
description: Выполните действия в этом разделе, чтобы изменить конфигурацию существующего облачного соединитетеля Skype для бизнеса Edition 1.4.1 или более позднего развертывания.
ms.openlocfilehash: 7fdfdd5ac5a76ebbc3ac58e12a69e2e3af1330cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109175"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="658ed-103">Изменение конфигурации существующего развертывания Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="658ed-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="658ed-104">Cloud Connector Edition завершит карьеру 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="658ed-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="658ed-105">После обновления организации до Teams узнайте, как подключить сеть локальной телефонии к Teams с помощью прямой [маршрутизации.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="658ed-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="658ed-106">Выполните действия в этом разделе, чтобы изменить конфигурацию существующего облачного соединитетеля Skype для бизнеса Edition 1.4.1 или более позднего развертывания.</span><span class="sxs-lookup"><span data-stu-id="658ed-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="658ed-107">Изменение конфигурации одного сайта</span><span class="sxs-lookup"><span data-stu-id="658ed-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="658ed-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="658ed-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="658ed-109">Если на сайте есть только один прибор, при изменении параметров конфигурации после развертывания можно изменить файл CloudConnector.ini и запустить развертывание снова.</span><span class="sxs-lookup"><span data-stu-id="658ed-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="658ed-110">Запустите следующий cmdlet, чтобы удалить все существующие виртуальные машины на сервере хост-сервера:</span><span class="sxs-lookup"><span data-stu-id="658ed-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="658ed-111">Запустите следующий cmdlet, чтобы оторегистрить устройство:</span><span class="sxs-lookup"><span data-stu-id="658ed-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="658ed-112">Обновление файла CloudConnector.ini в Каталоге приборов.</span><span class="sxs-lookup"><span data-stu-id="658ed-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="658ed-113">Запустите следующий комдлет для обновления конфигурации: (Этот шаг применим только для версии 2; для предыдущих версий пропустите следующий шаг.)</span><span class="sxs-lookup"><span data-stu-id="658ed-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="658ed-114">Запустите следующий cmdlet, чтобы зарегистрировать устройство снова:</span><span class="sxs-lookup"><span data-stu-id="658ed-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="658ed-115">Запустите следующий cmdlet, чтобы установить Skype для бизнеса Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="658ed-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="658ed-116">Если на сайте имеется несколько устройств, необходимо следовать этим шагам, изменять файл CloudConnector.ini и передиплоять устройства по одному.</span><span class="sxs-lookup"><span data-stu-id="658ed-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="658ed-117">Запустите следующий cmdlet, чтобы удалить все существующие виртуальные машины на текущем устройстве:</span><span class="sxs-lookup"><span data-stu-id="658ed-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="658ed-118">Запустите следующий cmdlet, чтобы оторегистрить устройство:</span><span class="sxs-lookup"><span data-stu-id="658ed-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="658ed-119">Обновление файла CloudConnector.ini в Каталоге приборов.</span><span class="sxs-lookup"><span data-stu-id="658ed-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="658ed-120">Запустите следующий комдлет для обновления конфигурации: (Этот шаг применим только для версии 2; для предыдущих версий пропустите следующий шаг.)</span><span class="sxs-lookup"><span data-stu-id="658ed-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="658ed-121">Запустите следующий cmdlet, чтобы зарегистрировать устройство снова:</span><span class="sxs-lookup"><span data-stu-id="658ed-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="658ed-122">Запустите следующий cmdlet на всех других устройствах на сайте, чтобы выбрать последнюю конфигурацию:</span><span class="sxs-lookup"><span data-stu-id="658ed-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="658ed-123">Запустите следующий cmdlet для передиплойки облачного соединителя на текущем устройстве:</span><span class="sxs-lookup"><span data-stu-id="658ed-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="658ed-124">Изменение конфигурации нескольких сайтов</span><span class="sxs-lookup"><span data-stu-id="658ed-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="658ed-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="658ed-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="658ed-126">Чтобы изменить конфигурацию для нескольких сайтов в развертывании, выполните действия для одного сайта, обновляя по одному сайту одновременно.</span><span class="sxs-lookup"><span data-stu-id="658ed-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="658ed-127">Измените конфигурацию организации Microsoft 365 или Office 365, чтобы включить автоматические обновления</span><span class="sxs-lookup"><span data-stu-id="658ed-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="658ed-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="658ed-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="658ed-129">Чтобы включить автоматические обновления операционной системы и автоматические обновления Bits, необходимо использовать учетную запись администратора клиента Skype для бизнеса для управления интернетом и использовать удаленный powerShell клиента следующим образом.</span><span class="sxs-lookup"><span data-stu-id="658ed-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="658ed-130">Если вы отключили автоматические обновления операционной системы или автоматические обновления Bits, ваш хост и виртуальная машина могут пропустить важные обновления Windows, и облачный соединителю не будет автоматически обновляться до новой версии.</span><span class="sxs-lookup"><span data-stu-id="658ed-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="658ed-131">Рекомендуется включить автоматические обновления.</span><span class="sxs-lookup"><span data-stu-id="658ed-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="658ed-132">Свойство EnableAutoUpdate сайта необходимо задать значение true (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="658ed-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="658ed-133">Запустите следующий cmdlet, чтобы убедиться, что EnableAutoUpdate задавалось верно:</span><span class="sxs-lookup"><span data-stu-id="658ed-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="658ed-134">Создайте окно времени автоматического обновления для клиента.</span><span class="sxs-lookup"><span data-stu-id="658ed-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="658ed-135">Окно времени может быть ежедневным, еженедельным и ежемесячным.</span><span class="sxs-lookup"><span data-stu-id="658ed-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="658ed-136">Все окна времени требуют времени начала и продолжительности.</span><span class="sxs-lookup"><span data-stu-id="658ed-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="658ed-137">Для ежедневного окне времени требуется только время начала и продолжительность.</span><span class="sxs-lookup"><span data-stu-id="658ed-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="658ed-138">Для еженедельного окна времени необходимы дни недели, которые могут быть одним днем или несколькими днями.</span><span class="sxs-lookup"><span data-stu-id="658ed-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="658ed-139">Для ежемесячного окне времени может быть два типа.</span><span class="sxs-lookup"><span data-stu-id="658ed-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="658ed-140">Первый тип — указать день месяца, который может быть одним днем.</span><span class="sxs-lookup"><span data-stu-id="658ed-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="658ed-141">Второй тип — указать недели месяца, а также дни недели, которые могут быть как одним элементом, так и несколькими элементами.</span><span class="sxs-lookup"><span data-stu-id="658ed-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="658ed-142">Каждый клиент может иметь 20 окон времени.</span><span class="sxs-lookup"><span data-stu-id="658ed-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="658ed-143">Окно времени по умолчанию будет создано для нового клиента в качестве окна времени по умолчанию для обновления операционной системы и обновления битов.</span><span class="sxs-lookup"><span data-stu-id="658ed-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="658ed-144">Запустите следующий cmdlet(s), чтобы установить дневное, еженедельное или ежемесячное окно времени:</span><span class="sxs-lookup"><span data-stu-id="658ed-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="658ed-145">Назначьте на сайт окна времени обновления.</span><span class="sxs-lookup"><span data-stu-id="658ed-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="658ed-146">Время обновления битов и окна времени обновления ОС настраиваются отдельно.</span><span class="sxs-lookup"><span data-stu-id="658ed-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="658ed-147">Оба из них могут быть назначены одним или несколькими окнами времени.</span><span class="sxs-lookup"><span data-stu-id="658ed-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="658ed-148">Каждое окно времени может быть назначено различным сайтам и различным целям (обновление битов и обновление ОС).</span><span class="sxs-lookup"><span data-stu-id="658ed-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="658ed-149">Запустите следующий cmdlet, чтобы установить окно времени для сайта:</span><span class="sxs-lookup"><span data-stu-id="658ed-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="658ed-150">Обновление учетных данных администратора клиента</span><span class="sxs-lookup"><span data-stu-id="658ed-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="658ed-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="658ed-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="658ed-152">Административные изменения в организации Microsoft 365 или Office 365 для облачного соединитетеля внесения из учетной записи с необходимыми разрешениями.</span><span class="sxs-lookup"><span data-stu-id="658ed-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="658ed-153">В версиях Cloud Connector до 2.0 эта учетная запись является выделенной глобальной учетной записью администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="658ed-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="658ed-154">В версиях Cloud Connector 2.0 и более поздней версии эта учетная запись может быть учетной записью Microsoft 365 или Office 365 с правами Администратора Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="658ed-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="658ed-155">Если учетные данные учетных данных учетных записей администратора изменяются в Microsoft 365 или Office 365, необходимо также обновить локализованные кэшные учетные данные в облачном соединителе, выведя следующую команду администратора PowerShell на каждом развернутом устройстве cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="658ed-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="658ed-156">Обновление пароля для хост-сервера</span><span class="sxs-lookup"><span data-stu-id="658ed-156">Update the password for the host server</span></span>
<span data-ttu-id="658ed-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="658ed-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="658ed-158">Этот раздел применим к версии Cloud Connector 2.0 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="658ed-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="658ed-159">Все учетные данные cloud Connector хранятся в следующем файле: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="658ed-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="658ed-160">Когда пароль на сервере хост-сервера изменится, вам потребуется обновить учетные данные, хранимые на локальном уровне.</span><span class="sxs-lookup"><span data-stu-id="658ed-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="658ed-161">Чтобы обновить локально хранимые учетные данные в устройстве Облачного соединителя, используйте [cmdlets Get-CcCredential](get-cccredential.md) и [Set-CcCredential](set-cccredential.md) и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="658ed-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="658ed-162">Запустите следующие команды, чтобы получить необходимые пароли позже:</span><span class="sxs-lookup"><span data-stu-id="658ed-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="658ed-163">Get-CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="658ed-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="658ed-164">Get-CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="658ed-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="658ed-165">Get-CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="658ed-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="658ed-166">Измените пароль учетной записи на сервере хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="658ed-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="658ed-167">Перезапустите хост-сервер.</span><span class="sxs-lookup"><span data-stu-id="658ed-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="658ed-168">Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="658ed-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="658ed-169">Запустите консоль PowerShell в качестве администратора, а затем запустите "Register-CcAppliance-Local", чтобы повторно ввести пароли, следующие описанию.</span><span class="sxs-lookup"><span data-stu-id="658ed-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="658ed-170">Убедитесь, что вы вводите тот же пароль, который был введен ранее для развертывания облачного соединитела.</span><span class="sxs-lookup"><span data-stu-id="658ed-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="658ed-171">По умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и CceService.</span><span class="sxs-lookup"><span data-stu-id="658ed-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="658ed-172">Если пароли DomainAdmin, VMAdmin и CceService, возвращенные на шаге 1, отличаются, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="658ed-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="658ed-173">Выполните Set-CcCredential-AccountType DomainAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="658ed-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="658ed-174">При запросе на старую учетную запись введите учетные данные, используемые для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="658ed-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="658ed-175">При запросе новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="658ed-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="658ed-176">Выполните Set-CcCredential-AccountType VmAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="658ed-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="658ed-177">При запросе на старую учетную запись введите учетные данные, используемые для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="658ed-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="658ed-178">При запросе новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="658ed-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="658ed-179">Обновление пароля для учетной записи CceService</span><span class="sxs-lookup"><span data-stu-id="658ed-179">Update the password for the CceService account</span></span>
<span data-ttu-id="658ed-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="658ed-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="658ed-181">Этот раздел применим к версии Cloud Connector 2.0.1 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="658ed-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="658ed-182">Служба облачного соединитела запускает службу управления облачным соединитетелем.</span><span class="sxs-lookup"><span data-stu-id="658ed-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="658ed-183">Учетная запись CceService создается во время развертывания Cloud Connector Edition и хранится в следующих файлах: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml" и "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span><span class="sxs-lookup"><span data-stu-id="658ed-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="658ed-184">Чтобы все устройства могли получить доступ к совместной службе каталогов сайтов, пароль для учетной записи CceService должен быть одинаковым для всех устройств, развернутых на сайте.</span><span class="sxs-lookup"><span data-stu-id="658ed-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="658ed-185">Учитывайте следующее:</span><span class="sxs-lookup"><span data-stu-id="658ed-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="658ed-186">По умолчанию учетная запись CceService настроена как "Пароль никогда не истекает".</span><span class="sxs-lookup"><span data-stu-id="658ed-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="658ed-187">При обновлении пароля Корпорация Майкрософт рекомендует сохранить эту конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="658ed-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="658ed-188">Необходимо обновить пароль во время периодов не пикового использования и вне автоматических окон времени обновления для битов или обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="658ed-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="658ed-189">При обновлении пароля необходимо осушить и перезапустить устройство, что занимает некоторое время.</span><span class="sxs-lookup"><span data-stu-id="658ed-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="658ed-190">Перезапуск устройства прерывает автоматические операции обновления.</span><span class="sxs-lookup"><span data-stu-id="658ed-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="658ed-191">При изменении пароля учетной записи CceService необходимо указать все учетные данные и обновить их в локальном файле.</span><span class="sxs-lookup"><span data-stu-id="658ed-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="658ed-192">Для каждого устройства, принадлежаного одному и тому же сайту PSTN, необходимо указать следующее:</span><span class="sxs-lookup"><span data-stu-id="658ed-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="658ed-193">Запустите следующие команды, чтобы получить имена и пароли учетных записей, которые будут использовать позже:</span><span class="sxs-lookup"><span data-stu-id="658ed-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="658ed-194">Запустите Enter-CcUpdate, чтобы слить устройство и переместить его в режим ручного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="658ed-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="658ed-195">Обновление пароля учетной записи CceService на хост-сервере.</span><span class="sxs-lookup"><span data-stu-id="658ed-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="658ed-196">Перезапустите хост-сервер.</span><span class="sxs-lookup"><span data-stu-id="658ed-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="658ed-197">Запустите Restore-CcCredentials для повторного ввода паролей после описания.</span><span class="sxs-lookup"><span data-stu-id="658ed-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="658ed-198">Убедитесь, что вы вводите тот же пароль, который был введен ранее для развертывания облачного соединиттеля, за исключением учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="658ed-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="658ed-199">Для учетной записи CceService введите новый пароль.</span><span class="sxs-lookup"><span data-stu-id="658ed-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="658ed-200">Убедитесь, что новый пароль для учетной записи CceService является одинаковым для всех устройств на сайте PSTN.</span><span class="sxs-lookup"><span data-stu-id="658ed-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="658ed-201">По умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и CceService.</span><span class="sxs-lookup"><span data-stu-id="658ed-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="658ed-202">Если пароли DomainAdmin, VMAdmin и CceService, возвращенные на шаге 1, отличаются, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="658ed-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="658ed-203">Выполните Set-CcCredential-AccountType DomainAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="658ed-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="658ed-204">При запросе на старую учетную запись введите учетные данные, используемые для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="658ed-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="658ed-205">При запросе новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="658ed-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="658ed-206">Выполните Set-CcCredential-AccountType VmAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="658ed-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="658ed-207">При запросе на старую учетную запись введите учетные данные, используемые для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="658ed-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="658ed-208">При запросе новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="658ed-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="658ed-209">Запустите Exit-CcUpdate, чтобы переместить устройство из режима ручного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="658ed-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="658ed-210">После выполнения этих действий на всех устройствах на одном сайте PSTN удалите следующие файлы в корневом каталоге сайта:</span><span class="sxs-lookup"><span data-stu-id="658ed-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="658ed-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="658ed-211">CcLockFile</span></span>
    
    - <span data-ttu-id="658ed-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="658ed-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="658ed-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="658ed-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="658ed-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="658ed-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="658ed-215">Добавление нового домена SIP</span><span class="sxs-lookup"><span data-stu-id="658ed-215">Add a new SIP domain</span></span>
<span data-ttu-id="658ed-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="658ed-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="658ed-217">Чтобы добавить новый домен SIP (или несколько SIP-доменов) в существующее развертывание облачного соединиттеля, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="658ed-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="658ed-218">Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и получили возможность добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="658ed-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="658ed-219">Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в добавлении домена в [Microsoft 365 или Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="658ed-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="658ed-220">Обновление файла конфигурации облачного соединиттеля с помощью нового домена SIP или доменов.</span><span class="sxs-lookup"><span data-stu-id="658ed-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="658ed-221">Запросите новый внешний сертификат Edge с дополнительными именами SAN для sip.domain для каждого домена SIP, определенного в конфигурации облачного соединиттеля.</span><span class="sxs-lookup"><span data-stu-id="658ed-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="658ed-222">Установите путь для нового внешнего сертификата Edge следующим образом:</span><span class="sxs-lookup"><span data-stu-id="658ed-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="658ed-223">Следуйте инструкциям по [изменению](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) конфигурации одного сайта или [изменению конфигурации нескольких сайтов.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)</span><span class="sxs-lookup"><span data-stu-id="658ed-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="658ed-224">Изменение основного домена SIP</span><span class="sxs-lookup"><span data-stu-id="658ed-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="658ed-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="658ed-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="658ed-226">Если вам необходимо изменить основной домен SIP в развертывании облачного соединитела, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="658ed-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="658ed-227">Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и получили возможность добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="658ed-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="658ed-228">Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в добавлении домена в [Microsoft 365 или Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="658ed-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="658ed-229">Обновление файла конфигурации облачного соединиттеля с помощью нового домена SIP.</span><span class="sxs-lookup"><span data-stu-id="658ed-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="658ed-230">Запросите новый внешний сертификат Edge с дополнительными именами SAN для sip.domain для каждого домена SIP, определенного в конфигурации облачного соединиттеля.</span><span class="sxs-lookup"><span data-stu-id="658ed-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="658ed-231">Установите путь для нового внешнего сертификата Edge следующим образом:</span><span class="sxs-lookup"><span data-stu-id="658ed-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="658ed-232">Удалите регистрацию клиента для каждого устройства на сайте, заняв следующие cmdlet в администраторе PowerShell в Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="658ed-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="658ed-233">Удалите регистрацию сайта для каждого сайта, заняв следующие cmdlet в Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="658ed-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="658ed-234">Удалить каждое устройство, запуская следующий комдлет в администраторе PowerShell в облачном соединителе:</span><span class="sxs-lookup"><span data-stu-id="658ed-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="658ed-235">Зарегистрируйте каждое устройство, задав следующий кодлет в администраторе PowerShell в облачном соединителе:</span><span class="sxs-lookup"><span data-stu-id="658ed-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="658ed-236">Установите каждое устройство по одному, запуская следующий комдлет в администраторе PowerShell на облачном соединителе:</span><span class="sxs-lookup"><span data-stu-id="658ed-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="658ed-237">Замените внешний сертификат Edge новым сертификатом</span><span class="sxs-lookup"><span data-stu-id="658ed-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="658ed-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="658ed-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="658ed-239">Если требуется заменить внешний сертификат Edge на устройствах облачного соединитела, вам потребуется получить новый сертификат Edge, подготовить файл PFX, содержащий закрытый ключ и цепочку полного сертификата, а затем сделать следующее на каждом устройстве:</span><span class="sxs-lookup"><span data-stu-id="658ed-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="658ed-240">Поместите устройство в режим обслуживания с помощью Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="658ed-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="658ed-241">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="658ed-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="658ed-242">Если пароль нового сертификата будет таким же, как и старый, импорт будет успешным.</span><span class="sxs-lookup"><span data-stu-id="658ed-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="658ed-243">Если пароль отличается, вы получите ошибку, что пароль неправ, и вам нужно будет сбросить пароль, запуская Register-CcAppliance с параметром -Local, а затем повторяя шаг 2.</span><span class="sxs-lookup"><span data-stu-id="658ed-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="658ed-244">Вытащайте устройство из режима обслуживания с помощью cmdlet Exit -CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="658ed-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
