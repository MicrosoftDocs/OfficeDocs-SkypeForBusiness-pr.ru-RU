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
description: Выполните действия в этом разделе, чтобы изменить конфигурацию существующего развертывания Skype для бизнеса Cloud Connector Edition 1.4.1 или более поздней версии.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359115"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="41c26-103">Изменение конфигурации существующего развертывания Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="41c26-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="41c26-104">Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="41c26-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="41c26-105">После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="41c26-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="41c26-106">Выполните действия в этом разделе, чтобы изменить конфигурацию существующего развертывания Skype для бизнеса Cloud Connector Edition 1.4.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="41c26-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="41c26-107">Изменение конфигурации одного сайта</span><span class="sxs-lookup"><span data-stu-id="41c26-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="41c26-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="41c26-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="41c26-109">Если на сайте имеется только одно устройство, то при изменении параметров конфигурации после его развертывания можно изменить файл CloudConnector.ini и снова запустить развертывание.</span><span class="sxs-lookup"><span data-stu-id="41c26-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="41c26-110">Чтобы удалить все существующие виртуальные машины на сервере хост-сервера, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="41c26-111">Чтобы отоиметь регистрацию устройства, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="41c26-112">Обновим CloudConnector.ini в каталоге устройств.</span><span class="sxs-lookup"><span data-stu-id="41c26-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="41c26-113">Чтобы обновить конфигурацию, запустите следующий cmdlet: (Этот шаг применим только для версии 2; для предыдущих версий перешаговые перейти к следующему шагу.)</span><span class="sxs-lookup"><span data-stu-id="41c26-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="41c26-114">Чтобы снова зарегистрировать устройство, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="41c26-115">Чтобы установить Skype для бизнеса Cloud Connector Edition, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="41c26-116">Если на сайте несколько устройств, вам потребуется выполнять эти действия, изменять файл CloudConnector.ini и выполнять их развявку по одному.</span><span class="sxs-lookup"><span data-stu-id="41c26-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="41c26-117">Чтобы удалить все существующие виртуальные машины на текущем устройстве, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="41c26-118">Чтобы отоиметь регистрацию устройства, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="41c26-119">Обновим CloudConnector.ini в каталоге устройств.</span><span class="sxs-lookup"><span data-stu-id="41c26-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="41c26-120">Чтобы обновить конфигурацию, запустите следующий cmdlet: (Этот шаг применим только для версии 2; для предыдущих версий перешаговые перейти к следующему шагу.)</span><span class="sxs-lookup"><span data-stu-id="41c26-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="41c26-121">Чтобы снова зарегистрировать устройство, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="41c26-122">Чтобы получить последнюю конфигурацию, запустите следующий cmdlet на всех остальных устройствах на сайте:</span><span class="sxs-lookup"><span data-stu-id="41c26-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="41c26-123">Чтобы выполнить перезапись Cloud Connector на текущем устройстве, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="41c26-124">Изменение конфигурации нескольких сайтов</span><span class="sxs-lookup"><span data-stu-id="41c26-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="41c26-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="41c26-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="41c26-126">Чтобы изменить конфигурацию для нескольких сайтов в развертывании, выполните действия для одного сайта, обновляя по одному сайту за раз.</span><span class="sxs-lookup"><span data-stu-id="41c26-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="41c26-127">Изменение конфигурации организации Microsoft 365 или Office 365 для автоматического обновления</span><span class="sxs-lookup"><span data-stu-id="41c26-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="41c26-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="41c26-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="41c26-129">Чтобы включить автоматическое обновление операционной системы и автоматическое обновление bits, необходимо использовать учетную запись администратора клиента Skype для бизнеса для управления через Интернет и использовать удаленную долю PowerShell клиента следующим образом.</span><span class="sxs-lookup"><span data-stu-id="41c26-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="41c26-130">Если вы отключили автоматическое обновление операционной системы или bits automatic updates, ваш хост и виртуальная машина могут пропустить важные обновления Windows, и Cloud Connector не будет автоматически обновляться до новой версии.</span><span class="sxs-lookup"><span data-stu-id="41c26-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="41c26-131">Настоятельно рекомендуется включить автоматические обновления.</span><span class="sxs-lookup"><span data-stu-id="41c26-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="41c26-132">Для свойства EnableAutoUpdate сайта должно быть установлено значение true (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="41c26-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="41c26-133">Чтобы убедиться, что для EnableAutoUpdate установлено true, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="41c26-134">Создание окна автоматического обновления для клиента.</span><span class="sxs-lookup"><span data-stu-id="41c26-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="41c26-135">Период времени может быть ежедневным, еженедельным и ежемесячным.</span><span class="sxs-lookup"><span data-stu-id="41c26-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="41c26-136">Все время в окнах требуется время начала и длительность.</span><span class="sxs-lookup"><span data-stu-id="41c26-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="41c26-137">Для ежедневного периода времени требуется только время начала и длительность.</span><span class="sxs-lookup"><span data-stu-id="41c26-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="41c26-138">Для еженедельного окна времени необходимы дни недели, которые могут быть одним или несколькими днями.</span><span class="sxs-lookup"><span data-stu-id="41c26-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="41c26-139">В течение ежемесячного времени может быть два типа.</span><span class="sxs-lookup"><span data-stu-id="41c26-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="41c26-140">Первый тип — указать день месяца, который может быть одним днем.</span><span class="sxs-lookup"><span data-stu-id="41c26-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="41c26-141">Второй тип — указать недели месяца вместе с днями недели, которые могут быть как одним элементом, так и несколькими элементами.</span><span class="sxs-lookup"><span data-stu-id="41c26-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="41c26-142">Для каждого клиента может быть определено 20 периодов времени.</span><span class="sxs-lookup"><span data-stu-id="41c26-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="41c26-143">По умолчанию для нового клиента будет создано окно времени по умолчанию для обновления операционной системы и bits.</span><span class="sxs-lookup"><span data-stu-id="41c26-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="41c26-144">Запустите следующие cmdlets, чтобы установить ежедневный, еженедельный или ежемесячный период времени:</span><span class="sxs-lookup"><span data-stu-id="41c26-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="41c26-145">Назначьте время обновления сайту.</span><span class="sxs-lookup"><span data-stu-id="41c26-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="41c26-146">Время обновления bits и время обновления ОС настраиваются отдельно.</span><span class="sxs-lookup"><span data-stu-id="41c26-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="41c26-147">Обоим из них можно на назначены один или несколько периодов времени.</span><span class="sxs-lookup"><span data-stu-id="41c26-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="41c26-148">Каждый период времени может быть назначен различным сайтам и их назначению (bits update and OS update).</span><span class="sxs-lookup"><span data-stu-id="41c26-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="41c26-149">Чтобы установить время для сайта, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="41c26-150">Обновление учетных данных администратора выделенного клиента</span><span class="sxs-lookup"><span data-stu-id="41c26-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="41c26-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="41c26-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="41c26-152">Административные изменения в организации Microsoft 365 или Office 365 для Cloud Connector внося из учетной записи с необходимыми разрешениями.</span><span class="sxs-lookup"><span data-stu-id="41c26-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="41c26-153">В Версиях Cloud Connector до версии 2.0 эта учетная запись является выделенной учетной записью глобального администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="41c26-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="41c26-154">В Cloud Connector версий 2.0 и более поздних версий эта учетная запись может быть учетной записью Microsoft 365 или Office 365 с правами администратора Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="41c26-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="41c26-155">Если учетные данные учетной записи администратора меняются в Microsoft 365 или Office 365, вам также потребуется обновить локально кэшные учетные данные в Cloud Connector, выведя следующую команду администратора PowerShell на каждом развернутом устройстве Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="41c26-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="41c26-156">Обновление пароля для сервера хост-сервера</span><span class="sxs-lookup"><span data-stu-id="41c26-156">Update the password for the host server</span></span>
<span data-ttu-id="41c26-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="41c26-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="41c26-158">Этот раздел применим к Cloud Connector версии 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="41c26-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="41c26-159">Все учетные данные Cloud Connector хранятся в следующем файле: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="41c26-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="41c26-160">При смене пароля на сервере на хост-сервере потребуется обновить локально сохраненные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="41c26-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="41c26-161">Чтобы обновить локально хранимые учетные данные на устройстве Cloud Connector, выполните указанные ниже действия с помощью [get-CcCredential](get-cccredential.md) и [Set-CcCredential.](set-cccredential.md)</span><span class="sxs-lookup"><span data-stu-id="41c26-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="41c26-162">Чтобы получить пароли, необходимые позже, запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="41c26-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="41c26-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="41c26-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="41c26-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="41c26-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="41c26-165">Get-CcCredential -AccountType CceService -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="41c26-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="41c26-166">Измените пароль учетной записи на сервере.</span><span class="sxs-lookup"><span data-stu-id="41c26-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="41c26-167">Перезапустите сервер хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="41c26-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="41c26-168">Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".</span><span class="sxs-lookup"><span data-stu-id="41c26-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="41c26-169">Запустите консоль PowerShell от учетной записи администратора, а затем запустите "Register-CcAppliance -Local", чтобы повторно ввести пароли, следуя описанию.</span><span class="sxs-lookup"><span data-stu-id="41c26-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="41c26-170">Обязательно введите тот же пароль, который был введен ранее для развертывания Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="41c26-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="41c26-171">По умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и CceService.</span><span class="sxs-lookup"><span data-stu-id="41c26-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="41c26-172">Если пароли DomainAdmin, VMAdmin и CceService, возвращенные на шаге 1, отличаются, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="41c26-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="41c26-173">Выполните Set-CcCredential -AccountType DomainAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41c26-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="41c26-174">При запросе учетных данных старой учетной записи введите учетные данные, использованные для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="41c26-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="41c26-175">При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="41c26-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="41c26-176">Выполните Set-CcCredential -AccountType VmAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41c26-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="41c26-177">При запросе учетных данных старой учетной записи введите учетные данные, использованные для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="41c26-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="41c26-178">При запросе учетных данных новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="41c26-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="41c26-179">Обновление пароля учетной записи CceService</span><span class="sxs-lookup"><span data-stu-id="41c26-179">Update the password for the CceService account</span></span>
<span data-ttu-id="41c26-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="41c26-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="41c26-181">Этот раздел применим к Cloud Connector версии 2.0.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="41c26-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="41c26-182">Служба Cloud Connector запускает службу управления Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="41c26-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="41c26-183">Учетная запись CceService создается во время развертывания Cloud Connector Edition и сохраняется в следующих файлах: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" и "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span><span class="sxs-lookup"><span data-stu-id="41c26-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="41c26-184">Чтобы обеспечить доступ всех устройств к совместному доступу к каталогу сайта, пароль для учетной записи CceService должен быть одинаковым на всех устройствах, развернутых на сайте.</span><span class="sxs-lookup"><span data-stu-id="41c26-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="41c26-185">Учитывайте следующее:</span><span class="sxs-lookup"><span data-stu-id="41c26-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="41c26-186">По умолчанию учетная запись CceService настроена как "Срок действия пароля не истекает".</span><span class="sxs-lookup"><span data-stu-id="41c26-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="41c26-187">При обновлении пароля Корпорация Майкрософт рекомендует сохранить эту конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="41c26-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="41c26-188">Пароль следует обновлять в периоды не пиковой нагрузки и вне периода автоматического обновления для битов или обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="41c26-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="41c26-189">При обновлении пароля необходимо опустить и перезапустить устройство, что занимает некоторое время.</span><span class="sxs-lookup"><span data-stu-id="41c26-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="41c26-190">Перезапуск устройства прерывает операции автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="41c26-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="41c26-191">При изменении пароля учетной записи CceService необходимо указать все учетные данные и обновить их в локально сохраненном файле.</span><span class="sxs-lookup"><span data-stu-id="41c26-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="41c26-192">Для каждого устройства, которое принадлежит к одному сайту STN, необходимо указать следующее:</span><span class="sxs-lookup"><span data-stu-id="41c26-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="41c26-193">Чтобы получить имена и пароли учетных записей, которые будут использовать позже, запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="41c26-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="41c26-194">Запустите Enter-CcUpdate для истощать устройство и переходить в режим обслуживания вручную.</span><span class="sxs-lookup"><span data-stu-id="41c26-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="41c26-195">Обновите пароль учетной записи CceService на сервере.</span><span class="sxs-lookup"><span data-stu-id="41c26-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="41c26-196">Перезапустите сервер хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="41c26-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="41c26-197">Запустите Restore-CcCredentials, чтобы повторно ввести пароли, следуя описанию.</span><span class="sxs-lookup"><span data-stu-id="41c26-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="41c26-198">Обязательно введите тот же пароль, который был введен ранее для развертывания Cloud Connector, за исключением учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="41c26-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="41c26-199">Для учетной записи CceService введите новый пароль.</span><span class="sxs-lookup"><span data-stu-id="41c26-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="41c26-200">Убедитесь, что новый пароль для учетной записи CceService одинаковый для всех устройств на сайте STN.</span><span class="sxs-lookup"><span data-stu-id="41c26-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="41c26-201">По умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и CceService.</span><span class="sxs-lookup"><span data-stu-id="41c26-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="41c26-202">Если пароли DomainAdmin, VMAdmin и CceService, возвращенные на шаге 1, отличаются, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="41c26-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="41c26-203">Выполните Set-CcCredential -AccountType DomainAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41c26-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="41c26-204">При запросе учетных данных старой учетной записи введите учетные данные, использованные для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="41c26-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="41c26-205">При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="41c26-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="41c26-206">Выполните Set-CcCredential -AccountType VmAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41c26-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="41c26-207">При запросе учетных данных старой учетной записи введите учетные данные, использованные для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="41c26-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="41c26-208">При запросе учетных данных новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="41c26-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="41c26-209">Запустите Exit-CcUpdate для перемещения устройства из режима обслуживания вручную.</span><span class="sxs-lookup"><span data-stu-id="41c26-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="41c26-210">После выполнения этих действий на всех устройствах на одном сайте STN удалите следующие файлы в корневом каталоге сайта:</span><span class="sxs-lookup"><span data-stu-id="41c26-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="41c26-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="41c26-211">CcLockFile</span></span>
    
    - <span data-ttu-id="41c26-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="41c26-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="41c26-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="41c26-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="41c26-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="41c26-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="41c26-215">Добавление нового домена SIP</span><span class="sxs-lookup"><span data-stu-id="41c26-215">Add a new SIP domain</span></span>
<span data-ttu-id="41c26-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="41c26-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="41c26-217">Чтобы добавить новый домен SIP (или несколько доменов SIP) в существующее развертывание Cloud Connector, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="41c26-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="41c26-218">Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и получили возможность добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="41c26-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="41c26-219">Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в подстройки "Добавление домена в [Microsoft 365" или "Office 365".](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="41c26-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="41c26-220">Обновите файл конфигурации Cloud Connector с помощью нового домена или доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="41c26-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="41c26-221">Запросите новый внешний сертификат Edge с дополнительными именами SAN для sip.domain для каждого домена SIP, определенного в конфигурации Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="41c26-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="41c26-222">Задан путь к новому внешнему сертификату edge следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41c26-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="41c26-223">Следуйте инструкциям по [изменению конфигурации](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) одного сайта или [изменению конфигурации нескольких сайтов.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)</span><span class="sxs-lookup"><span data-stu-id="41c26-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="41c26-224">Изменение основного домена SIP</span><span class="sxs-lookup"><span data-stu-id="41c26-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="41c26-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="41c26-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="41c26-226">Если необходимо изменить основной домен SIP в развертывании Cloud Connector, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="41c26-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="41c26-227">Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и получили возможность добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="41c26-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="41c26-228">Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в подстройки "Добавление домена в [Microsoft 365" или "Office 365".](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="41c26-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="41c26-229">Обновите файл конфигурации Cloud Connector с помощью нового домена SIP.</span><span class="sxs-lookup"><span data-stu-id="41c26-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="41c26-230">Запросите новый внешний сертификат Edge с дополнительными именами SAN для sip.domain для каждого домена SIP, определенного в конфигурации Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="41c26-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="41c26-231">Задан путь к новому внешнему сертификату edge следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41c26-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="41c26-232">Удалите регистрацию клиента для каждого устройства на сайте, вынеся следующий cmdlet в powerShell администратора в Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="41c26-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="41c26-233">Удалите регистрацию сайта для каждого сайта, выдав следующий cmdlet в Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="41c26-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="41c26-234">Чтобы удалить каждое устройство, с помощью администратора PowerShell в Cloud Connector выделили следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="41c26-235">Зарегистрируйте каждое устройство с помощью следующего cmdlet в администраторе PowerShell в Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="41c26-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="41c26-236">Установите каждое устройство по одному, задав в администраторе PowerShell в Cloud Connector следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41c26-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="41c26-237">Замена внешнего сертификата edge новым сертификатом</span><span class="sxs-lookup"><span data-stu-id="41c26-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="41c26-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="41c26-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="41c26-239">Если необходимо заменить внешний сертификат edge на устройствах Cloud Connector, необходимо получить новый сертификат edge, подготовить PFX-файл, содержащий закрытый ключ и полную цепочку сертификатов, а затем сделать следующее на каждом устройстве:</span><span class="sxs-lookup"><span data-stu-id="41c26-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="41c26-240">Переставьте устройство в режим обслуживания с помощью Enter-CcUpdate управления.</span><span class="sxs-lookup"><span data-stu-id="41c26-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="41c26-241">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41c26-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="41c26-242">Если пароль нового сертификата такой же, как и старый, импорт будет успешным.</span><span class="sxs-lookup"><span data-stu-id="41c26-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="41c26-243">Если пароль отличается, вы получите сообщение об ошибке пароля, и вам потребуется сбросить пароль, заведя Register-CcAppliance с параметром -Local, а затем повторите шаг 2.</span><span class="sxs-lookup"><span data-stu-id="41c26-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="41c26-244">Выйдите из режима обслуживания устройства с помощью cmdlet Exit -CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="41c26-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

