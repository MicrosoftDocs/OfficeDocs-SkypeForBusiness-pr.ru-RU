---
title: Обновление Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Сведения о процедуре обновлении развертывания Cloud Connector Edition.
ms.openlocfilehash: c2613069f1626f8fc7e28b4fb5a246fc7647cf98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286629"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="f6fa5-103">Обновление Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="f6fa5-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="f6fa5-104">Сведения о процедуре обновлении развертывания Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="f6fa5-p101">Если вы настроили автоматическое обновление для учетной записи интерактивного клиента управления, существующее развертывание Skype для бизнеса Cloud Connector Edition будет автоматически обновлено до последней версии в соответствии с параметрами периода обновления. При необходимости вы можете выполнить обновление вручную. </span><span class="sxs-lookup"><span data-stu-id="f6fa5-p101">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration. You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="f6fa5-107">Облачные версии Cloud Connector Editions 1.4.1 и более поздних версий выполняют автоматические обновления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="f6fa5-108">Если вы хотите выполнить обновление до последней версии (2,1) вручную, ознакомьтесь с разделом [обновление одного сайта до новой версии](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) , описанной ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="f6fa5-109">Для автоматического обновления необходимо, чтобы выполнялась служба облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="f6fa5-110">Далее описываются шаги процесса автоматического обновления:</span><span class="sxs-lookup"><span data-stu-id="f6fa5-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="f6fa5-111">Процесс автоматического обновления выполняется по установленному вами расписанию.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="f6fa5-112">Задачи по обновлению операционной системы</span><span class="sxs-lookup"><span data-stu-id="f6fa5-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="f6fa5-113">Проверяйте и загружайте обновления операционной системы во все виртуальные машины с облачными соединителями.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="f6fa5-114">Установка и обновление всех виртуальных машин соединителя по облаку по одной и перезапуску.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="f6fa5-115">После перезапуска виртуальных машин облачного соединителя убедитесь, что требуется другая перезагрузка.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="f6fa5-116">После того как виртуальные облачные соединители успешно исправлены, повторите процесс хостового компьютера с облачным соединителем.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="f6fa5-117">После успешной загрузки хоста с облачным соединителем все невыполненные задачи обновления операционной системы завершены.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="f6fa5-118">Задачи по обновлению облачного соединителя</span><span class="sxs-lookup"><span data-stu-id="f6fa5-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="f6fa5-119">Скачайте и проверьте файл версии с соответствующего сайта.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="f6fa5-120">Скачайте новую версию MSI-файла. </span><span class="sxs-lookup"><span data-stu-id="f6fa5-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="f6fa5-121">Удалите старый MSI-файл; Установите новый MSI-файл.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="f6fa5-122">Скачайте новую версию Skype для бизнеса (BITS).</span><span class="sxs-lookup"><span data-stu-id="f6fa5-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="f6fa5-123">Зарегистрируйте устройство с помощью командлета Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="f6fa5-124">Установка новой версии облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="f6fa5-125">Очистите старое устройство и переведите сетевое подключение на новое устройство.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="f6fa5-126">При обновлении облачного соединителя для новой сборки командлеты облачного соединителя могут не обновляться.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="f6fa5-127">Это может произойти, например, если окно PowerShell остается открытым во время автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="f6fa5-128">Чтобы загрузить обновленные командлеты, выполните одно из указанных ниже действий. _Гт_ закройте PowerShell на устройстве облачного соединителя, а затем снова откройте PowerShell. _Гт_ или можно выполнить командлет Import-Module Клаудконнектор-Force.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="f6fa5-129">Обновление отдельного сайта до новой версии</span><span class="sxs-lookup"><span data-stu-id="f6fa5-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="f6fa5-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="f6fa5-130"></span></span>

<span data-ttu-id="f6fa5-131">Если обновляемый сайт содержит только одно устройство, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="f6fa5-132">Удалите существующую версию облачного соединителя в **компонентах \> панели \> управления "программы и компоненты**".</span><span class="sxs-lookup"><span data-stu-id="f6fa5-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="f6fa5-133">Установите новую версию Клаудконнектор. msi FROM [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="f6fa5-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="f6fa5-134">Убедитесь, что вы используете файл CloudConnector.ini для устанавливаемой версии, а также что обновлены все необходимые значения среды.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="f6fa5-135">Не допускается использование INI-файла для предыдущего выпуска.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="f6fa5-136">Если вы обновляете облачный соединитель, ознакомьтесь с разделом [Подготовка вашего устройства облачного соединителя](prepare-your-cloud-connector-appliance.md) и убедитесь, что для sitename и енаблереферсуппорт задано правильное значение в файле клаудконнектор. ini.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="f6fa5-137">Запустите консоль PowerShell от имени администратора и выполните следующий командлет для регистрации текущего устройства:</span><span class="sxs-lookup"><span data-stu-id="f6fa5-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```
   Register-CcAppliance
   ```

5. <span data-ttu-id="f6fa5-138">Выполните следующий командлет, чтобы скачать последнюю версию:</span><span class="sxs-lookup"><span data-stu-id="f6fa5-138">Run the following cmdlet to download the latest version:</span></span>
    
   ```
   Start-CcDownload
   ```

6. <span data-ttu-id="f6fa5-139">Чтобы запустить установку, выполните следующий командлет: </span><span class="sxs-lookup"><span data-stu-id="f6fa5-139">Run the following cmdlet to start the installation:</span></span> 
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="f6fa5-140">Выполните следующий командлет, чтобы активировать новое развертывание и отключить предыдущую версию:</span><span class="sxs-lookup"><span data-stu-id="f6fa5-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```
   Switch-CcVersion
   ```

<span data-ttu-id="f6fa5-141">При наличии нескольких устройств на сайте выполните предыдущую процедуру, чтобы обновить устройства по одному.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="f6fa5-142">Если вы хотите обновить администратора домена, администратора виртуальных машин, администраторам безопасного режима и учетных данных администратора клиента, вы можете выполнить командлет с параметром _упдатеаллкредентиалс_ , чтобы сбросить все учетные данные:</span><span class="sxs-lookup"><span data-stu-id="f6fa5-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="f6fa5-143">В дальнейшем, когда вы начнете обновление, вам будет предложено ввести новые учетные данные. </span><span class="sxs-lookup"><span data-stu-id="f6fa5-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="f6fa5-144">Если вам требуется сбросить только учетные данные администратора клиента, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="f6fa5-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="f6fa5-145">Обновление нескольких сайтов до новой версии</span><span class="sxs-lookup"><span data-stu-id="f6fa5-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="f6fa5-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="f6fa5-146"></span></span>

<span data-ttu-id="f6fa5-p106">Выполните инструкции по обновлению отдельного сайта, обновляя по одному сайту за раз, пока не обновите все сайты в развертывании. Выполните рекомендации из раздела [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) после обновления каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="f6fa5-p106">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment. Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

