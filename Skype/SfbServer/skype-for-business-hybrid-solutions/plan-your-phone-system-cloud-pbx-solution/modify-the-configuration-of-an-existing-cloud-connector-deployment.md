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
description: Выполните действия, описанные в этом разделе, чтобы изменить конфигурацию существующего развертывания Skype для бизнеса Cloud Connector Edition 1.4.1 или более поздней версии.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359115"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="82653-103">Изменение конфигурации существующего развертывания Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="82653-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="82653-104">Cloud Connector Edition выйдет 31 июля 2021 вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="82653-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="82653-105">После обновления вашей организации до Teams Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="82653-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="82653-106">Выполните действия, описанные в этом разделе, чтобы изменить конфигурацию существующего развертывания Skype для бизнеса Cloud Connector Edition 1.4.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="82653-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="82653-107">Изменение конфигурации отдельного сайта</span><span class="sxs-lookup"><span data-stu-id="82653-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="82653-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="82653-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="82653-109">Если на сайте имеется только одно устройство, то при необходимости изменить параметры конфигурации после развертывания устройства можно изменить файл CloudConnector.ini и снова запустить развертывание.</span><span class="sxs-lookup"><span data-stu-id="82653-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="82653-110">Выполните следующий командлет, чтобы удалить все существующие виртуальные машины на сервере узла:</span><span class="sxs-lookup"><span data-stu-id="82653-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="82653-111">Выполните следующий командлет, чтобы отменить регистрацию устройства:</span><span class="sxs-lookup"><span data-stu-id="82653-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="82653-112">Обновите файл CloudConnector.ini в каталоге устройств.</span><span class="sxs-lookup"><span data-stu-id="82653-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="82653-113">Выполните следующий командлет, чтобы обновить конфигурацию: (этот шаг применим только для версии 2; для предыдущих версий перейдите к следующему шагу).</span><span class="sxs-lookup"><span data-stu-id="82653-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="82653-114">Выполните следующий командлет, чтобы снова зарегистрировать устройство:</span><span class="sxs-lookup"><span data-stu-id="82653-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="82653-115">Выполните следующий командлет, чтобы установить Skype для бизнеса Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="82653-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="82653-116">Если на сайте несколько устройств, необходимо выполнить следующие действия, изменить файл CloudConnector.ini и повторно развернуть устройства по одному.</span><span class="sxs-lookup"><span data-stu-id="82653-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="82653-117">Выполните следующий командлет, чтобы удалить все существующие виртуальные машины на текущем устройстве:</span><span class="sxs-lookup"><span data-stu-id="82653-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="82653-118">Выполните следующий командлет, чтобы отменить регистрацию устройства:</span><span class="sxs-lookup"><span data-stu-id="82653-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="82653-119">Обновите файл CloudConnector.ini в каталоге устройств.</span><span class="sxs-lookup"><span data-stu-id="82653-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="82653-120">Выполните следующий командлет, чтобы обновить конфигурацию: (этот шаг применим только для версии 2; для предыдущих версий перейдите к следующему шагу).</span><span class="sxs-lookup"><span data-stu-id="82653-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="82653-121">Выполните следующий командлет, чтобы снова зарегистрировать устройство:</span><span class="sxs-lookup"><span data-stu-id="82653-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="82653-122">Выполните следующий командлет на всех остальных устройствах сайта, чтобы выбрать последнюю конфигурацию:</span><span class="sxs-lookup"><span data-stu-id="82653-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="82653-123">Выполните следующий командлет, чтобы повторно развернуть Cloud Connector на текущем устройстве:</span><span class="sxs-lookup"><span data-stu-id="82653-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="82653-124">Изменение конфигурации нескольких сайтов</span><span class="sxs-lookup"><span data-stu-id="82653-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="82653-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="82653-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="82653-126">Чтобы изменить конфигурацию нескольких сайтов в развертывании, выполните действия для отдельного сайта, обновив по одному сайту за раз.</span><span class="sxs-lookup"><span data-stu-id="82653-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="82653-127">Изменение конфигурации организации Microsoft 365 или Office 365 для включения автоматических обновлений</span><span class="sxs-lookup"><span data-stu-id="82653-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="82653-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="82653-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="82653-129">Чтобы включить автоматическое обновление операционной системы и автоматическое обновление службы BITS, необходимо использовать учетную запись администратора клиента Skype для бизнеса для управления через Интернет и использовать удаленную оболочку PowerShell для клиента, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="82653-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="82653-130">Если вы отключили автоматические обновления операционной системы или автоматические обновления BITS, ваш узел и виртуальная машина могут пропустить важные обновления Windows, а Cloud Connector не будет автоматически обновляться до новой версии.</span><span class="sxs-lookup"><span data-stu-id="82653-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="82653-131">Настоятельно рекомендуется включить автоматическое обновление.</span><span class="sxs-lookup"><span data-stu-id="82653-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="82653-132">Свойству EnableAutoUpdate сайта необходимо присвоить значение true (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="82653-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="82653-133">Выполните следующий командлет, чтобы убедиться, что для EnableAutoUpdate установлено значение true:</span><span class="sxs-lookup"><span data-stu-id="82653-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="82653-134">Создайте период автоматического обновления для клиента.</span><span class="sxs-lookup"><span data-stu-id="82653-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="82653-135">Окно времени может быть ежедневно, еженедельно и ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="82653-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="82653-136">Все время, в течение которого Windows требует времени начала и длительности.</span><span class="sxs-lookup"><span data-stu-id="82653-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="82653-137">Для ежедневного периода времени требуются только время начала и длительность.</span><span class="sxs-lookup"><span data-stu-id="82653-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="82653-138">Для еженедельного периода времени необходимо указать дни недели, которые могут быть представлены в течение одного дня или нескольких дней.</span><span class="sxs-lookup"><span data-stu-id="82653-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="82653-139">Для ежемесячного окна можно указать два типа.</span><span class="sxs-lookup"><span data-stu-id="82653-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="82653-140">Первый тип — указать день месяца, который может быть одним днем.</span><span class="sxs-lookup"><span data-stu-id="82653-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="82653-141">Второй тип — указать недели месяца, а также дни недели, которые могут быть одним элементом или несколькими элементами.</span><span class="sxs-lookup"><span data-stu-id="82653-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="82653-142">Для каждого клиента можно задать 20 окон времени.</span><span class="sxs-lookup"><span data-stu-id="82653-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="82653-143">Окно времени по умолчанию будет создано для нового клиента в качестве стандартного периода обновления операционной системы и обновления BITS.</span><span class="sxs-lookup"><span data-stu-id="82653-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="82653-144">Выполните следующие командлеты, чтобы установить ежедневный, еженедельный или ежемесячный период времени:</span><span class="sxs-lookup"><span data-stu-id="82653-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="82653-145">Назначьте сайт времени обновления сайту.</span><span class="sxs-lookup"><span data-stu-id="82653-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="82653-146">Окна "время обновления BITS" и "время обновления ОС" настраиваются отдельно.</span><span class="sxs-lookup"><span data-stu-id="82653-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="82653-147">Обоим пользователям можно назначить один или несколько окон.</span><span class="sxs-lookup"><span data-stu-id="82653-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="82653-148">Каждое временное окно может быть назначено разным сайтам и различное назначение (обновление BITS и обновление ОС).</span><span class="sxs-lookup"><span data-stu-id="82653-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="82653-149">Выполните следующий командлет, чтобы задать временное окно для сайта:</span><span class="sxs-lookup"><span data-stu-id="82653-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="82653-150">Обновление выделенных учетных данных администратора клиента</span><span class="sxs-lookup"><span data-stu-id="82653-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="82653-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="82653-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="82653-152">Административные изменения в организации Microsoft 365 или Office 365 для Cloud Connector выполняются из учетной записи с необходимыми разрешениями.</span><span class="sxs-lookup"><span data-stu-id="82653-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="82653-153">В версиях Cloud Connector до 2,0 эта учетная запись является выделенной учетной записью глобального администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="82653-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="82653-154">В Cloud Connector версии 2,0 и более поздней эта учетная запись может быть учетной записью Microsoft 365 или Office 365 с правами администратора Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="82653-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="82653-155">Если учетные данные учетной записи администратора меняются в Microsoft 365 или Office 365, также необходимо обновить локально кэшированные учетные данные в Cloud Connector, выполнив следующую команду администратора PowerShell на каждом развертываемом устройстве Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="82653-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="82653-156">Обновление пароля для сервера узла</span><span class="sxs-lookup"><span data-stu-id="82653-156">Update the password for the host server</span></span>
<span data-ttu-id="82653-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="82653-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="82653-158">Этот раздел относится к Cloud Connector версии 2,0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="82653-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="82653-159">Все учетные данные Cloud Connector хранятся в следующем файле: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="82653-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="82653-160">При изменении пароля на сервере узла необходимо обновить локально хранимые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="82653-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="82653-161">Чтобы обновить локально хранимые учетные данные на устройстве Cloud Connector, используйте командлеты [Get – CcCredential](get-cccredential.md) и [Set – CcCredential](set-cccredential.md) , а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="82653-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="82653-162">Выполните следующие команды, чтобы получить пароли, которые вам понадобятся позже:</span><span class="sxs-lookup"><span data-stu-id="82653-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="82653-163">Get – CcCredential — AccountType DomainAdmin — Дисплайпассворд</span><span class="sxs-lookup"><span data-stu-id="82653-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="82653-164">Get – CcCredential — AccountType VMAdmin — Дисплайпассворд</span><span class="sxs-lookup"><span data-stu-id="82653-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="82653-165">Get – CcCredential — AccountType CceService — Дисплайпассворд</span><span class="sxs-lookup"><span data-stu-id="82653-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="82653-166">Измените пароль учетной записи на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="82653-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="82653-167">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="82653-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="82653-168">Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="82653-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="82653-169">Запустите консоль PowerShell от имени администратора, а затем выполните команду "Register – CcAppliance — Local", чтобы повторно ввести пароли, указанные в описании.</span><span class="sxs-lookup"><span data-stu-id="82653-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="82653-170">Убедитесь, что вы ввели тот же пароль, который вы ввели перед развертыванием Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="82653-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="82653-171">По умолчанию для VmAdmin и DomainAdmin используется тот же пароль, что и в CceService.</span><span class="sxs-lookup"><span data-stu-id="82653-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="82653-172">Если пароли DomainAdmin, VMAdmin и CceService, возвращаемые на шаге 1, отличаются, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="82653-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="82653-173">Выполните командлет Set – CcCredential – AccountType DomainAdmin, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="82653-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="82653-174">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="82653-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="82653-175">При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="82653-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="82653-176">Выполните командлет Set – CcCredential – AccountType VmAdmin, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="82653-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="82653-177">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="82653-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="82653-178">При запросе учетных данных новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="82653-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="82653-179">Обновление пароля учетной записи CceService</span><span class="sxs-lookup"><span data-stu-id="82653-179">Update the password for the CceService account</span></span>
<span data-ttu-id="82653-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="82653-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="82653-181">Этот раздел относится к Cloud Connector версии 2.0.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="82653-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="82653-182">Служба Cloud Connector выполняет службу управления Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="82653-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="82653-183">Учетная запись CceService создается во время развертывания Cloud Connector Edition и хранится в следующих файлах: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML "и"% SystemDrive% \Programdata\Cloudconnector\credentials..CceService.xml ".</span><span class="sxs-lookup"><span data-stu-id="82653-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="82653-184">Чтобы все устройства могли получать доступ к общему ресурсу каталога сайтов, пароль для учетной записи CceService должен быть одинаковым на всех устройствах, развернутых на сайте.</span><span class="sxs-lookup"><span data-stu-id="82653-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="82653-185">Учитывайте следующее:</span><span class="sxs-lookup"><span data-stu-id="82653-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="82653-186">По умолчанию учетная запись CceService настроена как "срок действия пароля не ограничен".</span><span class="sxs-lookup"><span data-stu-id="82653-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="82653-187">При обновлении пароля Корпорация Майкрософт рекомендует оставить эту конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="82653-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="82653-188">Вы должны обновить пароль во время непиковых периодов использования и из окон автоматических периодов обновления для BITS или обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="82653-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="82653-189">При обновлении пароля необходимо выполнить сток и перезапустить устройство, что занимает некоторое время.</span><span class="sxs-lookup"><span data-stu-id="82653-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="82653-190">Перезапуск устройства приведет к прерыванию операций автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="82653-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="82653-191">При изменении пароля учетной записи CceService необходимо указать все учетные данные и обновить их в локально сохраненном файле.</span><span class="sxs-lookup"><span data-stu-id="82653-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="82653-192">Для каждого устройства, входящего в один сайт PSTN, необходимо указать следующее:</span><span class="sxs-lookup"><span data-stu-id="82653-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="82653-193">Чтобы получить имена и пароли учетных записей, которые будут использоваться позже, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="82653-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="82653-194">Выполните командлет Enter – CcUpdate, чтобы очистить устройство и переместить его в режим ручного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="82653-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="82653-195">Обновите пароль учетной записи CceService на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="82653-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="82653-196">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="82653-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="82653-197">Запустите командлет Restore – Кккредентиалс, чтобы повторно ввести пароли, следуя описанию.</span><span class="sxs-lookup"><span data-stu-id="82653-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="82653-198">Убедитесь, что вы ввели тот же пароль, который вы ввели перед развертыванием Cloud Connector, кроме учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="82653-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="82653-199">В поле Учетная запись CceService введите новый пароль.</span><span class="sxs-lookup"><span data-stu-id="82653-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="82653-200">Убедитесь, что новый пароль для учетной записи CceService одинаков для всех устройств на сайте PSTN.</span><span class="sxs-lookup"><span data-stu-id="82653-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="82653-201">По умолчанию для VmAdmin и DomainAdmin используется тот же пароль, что и в CceService.</span><span class="sxs-lookup"><span data-stu-id="82653-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="82653-202">Если пароли DomainAdmin, VMAdmin и CceService, возвращаемые на шаге 1, отличаются, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="82653-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="82653-203">Выполните командлет Set – CcCredential – AccountType DomainAdmin, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="82653-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="82653-204">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="82653-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="82653-205">При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="82653-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="82653-206">Выполните командлет Set – CcCredential – AccountType VmAdmin, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="82653-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="82653-207">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="82653-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="82653-208">При запросе учетных данных новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="82653-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="82653-209">Выполните командлет Exit – CcUpdate, чтобы переместить устройство из режима ручного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="82653-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="82653-210">После выполнения этих действий для всех устройств на одном сайте PSTN удалите следующие файлы в корневом каталоге сайта:</span><span class="sxs-lookup"><span data-stu-id="82653-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="82653-211">кклоккфиле</span><span class="sxs-lookup"><span data-stu-id="82653-211">CcLockFile</span></span>
    
    - <span data-ttu-id="82653-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="82653-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="82653-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="82653-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="82653-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="82653-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="82653-215">Добавление нового домена SIP</span><span class="sxs-lookup"><span data-stu-id="82653-215">Add a new SIP domain</span></span>
<span data-ttu-id="82653-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="82653-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="82653-217">Чтобы добавить новый домен SIP (или несколько доменов SIP) к существующему развертыванию Cloud Connector, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="82653-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="82653-218">Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365, а также можете добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="82653-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="82653-219">Для получения дополнительных сведений о настройке домена в Microsoft 365 или Office 365, ознакомьтесь со статьей [Добавление домена в microsoft 365 или office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="82653-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="82653-220">Обновите файл конфигурации Cloud Connector с помощью нового домена SIP или доменов.</span><span class="sxs-lookup"><span data-stu-id="82653-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="82653-221">Запросите новый внешний сертификат пограничного сервера с дополнительными именами SAN для каждого домена SIP, определенного в конфигурации Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="82653-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="82653-222">Задайте путь к новому внешнему сертификату пограничного сервера следующим образом:</span><span class="sxs-lookup"><span data-stu-id="82653-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="82653-223">Следуйте инструкциям, чтобы [изменить конфигурацию отдельного сайта](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) или [изменить конфигурацию нескольких сайтов](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="82653-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="82653-224">Изменение основного домена SIP</span><span class="sxs-lookup"><span data-stu-id="82653-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="82653-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="82653-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="82653-226">Если необходимо изменить основной домен SIP в развертывании Cloud Connector, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="82653-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="82653-227">Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365, а также можете добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="82653-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="82653-228">Для получения дополнительных сведений о настройке домена в Microsoft 365 или Office 365, ознакомьтесь со статьей [Добавление домена в microsoft 365 или office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="82653-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="82653-229">Обновите файл конфигурации Cloud Connector с помощью нового домена SIP.</span><span class="sxs-lookup"><span data-stu-id="82653-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="82653-230">Запросите новый внешний сертификат пограничного сервера с дополнительными именами SAN для каждого домена SIP, определенного в конфигурации Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="82653-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="82653-231">Задайте путь к новому внешнему сертификату пограничного сервера следующим образом:</span><span class="sxs-lookup"><span data-stu-id="82653-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="82653-232">Удалите регистрацию клиента для каждого устройства на сайте, выполнив следующий командлет в оболочке PowerShell в Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="82653-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="82653-233">Удалите регистрацию сайта для каждого сайта, выполнив следующий командлет в Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82653-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="82653-234">Удалите каждое устройство, выполнив следующий командлет в консоли администрирования PowerShell на облачном соединителе:</span><span class="sxs-lookup"><span data-stu-id="82653-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="82653-235">Зарегистрируйте каждое устройство, выполнив следующий командлет в консоли PowerShell администратора Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="82653-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="82653-236">Установите каждое устройство по одному, выполнив следующий командлет в оболочке PowerShell в Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="82653-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="82653-237">Замена внешнего сертификата пограничного сервера на новый</span><span class="sxs-lookup"><span data-stu-id="82653-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="82653-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="82653-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="82653-239">Когда вам потребуется заменить внешний пограничный сертификат на устройствах Cloud Connector, необходимо получить новый пограничный сертификат, подготовить PFX-файл, содержащий закрытый ключ и цепочку сертификатов, а затем выполнить следующие действия на каждом устройстве:</span><span class="sxs-lookup"><span data-stu-id="82653-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="82653-240">Перевести устройство в режим обслуживания с помощью командлета Enter – CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="82653-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="82653-241">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="82653-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="82653-242">Если пароль нового сертификата совпадает со старым, импорт будет успешным.</span><span class="sxs-lookup"><span data-stu-id="82653-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="82653-243">Если пароль отличается, появится сообщение о том, что пароль неверный, а пароль необходимо сбросить, запустив командлет Register-CcAppliance с параметром-Local, а затем повторив шаг 2.</span><span class="sxs-lookup"><span data-stu-id="82653-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="82653-244">Переведите устройство из режима обслуживания с помощью командлета Exit – CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="82653-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

