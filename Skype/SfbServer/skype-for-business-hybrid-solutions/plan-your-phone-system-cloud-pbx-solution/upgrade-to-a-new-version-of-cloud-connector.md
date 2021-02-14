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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Узнайте, как обновить развертывание Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359295"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="0abf2-103">Обновление Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="0abf2-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="0abf2-104">Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="0abf2-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="0abf2-105">После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="0abf2-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="0abf2-106">Узнайте, как обновить развертывание Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="0abf2-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="0abf2-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically - according to your automatic update time window configuration.</span><span class="sxs-lookup"><span data-stu-id="0abf2-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="0abf2-108">Вы также можете выполнить обновление вручную.</span><span class="sxs-lookup"><span data-stu-id="0abf2-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="0abf2-109">Cloud Connector Edition версий 1.4.1 и более поздних версий выполняет автоматические обновления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0abf2-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="0abf2-110">Если вы хотите обновить до последней версии (2.1) вручную, см. раздел "Обновление одного сайта до новой версии" далее в этом разделе. [](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)</span><span class="sxs-lookup"><span data-stu-id="0abf2-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="0abf2-111">Автоматическое обновление требует, чтобы служба Cloud Connector была запущена.</span><span class="sxs-lookup"><span data-stu-id="0abf2-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="0abf2-112">Ниже описан процесс автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="0abf2-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="0abf2-113">Процесс автоматического обновления будет запускаться в соответствии с расписанием, настроенным для автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="0abf2-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="0abf2-114">Задачи обновления операционной системы</span><span class="sxs-lookup"><span data-stu-id="0abf2-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="0abf2-115">Проверьте и скачайте обновления операционной системы на все ВМ Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="0abf2-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="0abf2-116">Установите и обновите все ВМ Cloud Connector по одному и перезапустите.</span><span class="sxs-lookup"><span data-stu-id="0abf2-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="0abf2-117">После перезапуска ВМ Cloud Connector проверьте, требуется ли еще один перезапуск.</span><span class="sxs-lookup"><span data-stu-id="0abf2-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="0abf2-118">После успешного исправления ВМ Cloud Connector повторите процесс для хост-компьютера Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="0abf2-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="0abf2-119">После успешной загрузки хост-компьютера Cloud Connector все оставшиеся задачи обновления операционной системы будут выполнены.</span><span class="sxs-lookup"><span data-stu-id="0abf2-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="0abf2-120">Задачи обновления Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="0abf2-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="0abf2-121">Скачайте и проверьте файл версии с сайта загрузки.</span><span class="sxs-lookup"><span data-stu-id="0abf2-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="0abf2-122">Скачайте MSI-файл новой версии.</span><span class="sxs-lookup"><span data-stu-id="0abf2-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="0abf2-123">Удалить старый MSI-файл; установите новый MSI-файл.</span><span class="sxs-lookup"><span data-stu-id="0abf2-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="0abf2-124">Скачайте новую версию битов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0abf2-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="0abf2-125">Зарегистрируйте устройство, вызывая Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="0abf2-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="0abf2-126">Установите новую версию Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="0abf2-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="0abf2-127">Осушить старое устройство и переключить сетевое подключение на новое устройство.</span><span class="sxs-lookup"><span data-stu-id="0abf2-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="0abf2-128">При обновлении Cloud Connector до новой сборки, возможно, они не обновляются.</span><span class="sxs-lookup"><span data-stu-id="0abf2-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="0abf2-129">Это может произойти, например, если окно PowerShell остается открытым во время автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="0abf2-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="0abf2-130">Чтобы загрузить обновленные cmdlets, можно выполнить один из следующих действий: > Закрыть PowerShell на устройстве Cloud Connector, а затем повторно открыть PowerShell.> Или можно запустить Import-Module CloudConnector -Force.</span><span class="sxs-lookup"><span data-stu-id="0abf2-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="0abf2-131">Обновление отдельного сайта до новой версии</span><span class="sxs-lookup"><span data-stu-id="0abf2-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="0abf2-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="0abf2-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="0abf2-133">Если на сайте, который вы хотите обновить, есть только одно устройство, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="0abf2-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="0abf2-134">Удалить существующую версию Cloud Connector в программах и программах панели **управления. \> \>**</span><span class="sxs-lookup"><span data-stu-id="0abf2-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="0abf2-135">Установите новую версию CloudConnector.msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) из .</span><span class="sxs-lookup"><span data-stu-id="0abf2-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="0abf2-136">Подтвердите наличие CloudConnector.ini версии, которую вы устанавливаете, и что вы обновили все необходимые значения для среды.</span><span class="sxs-lookup"><span data-stu-id="0abf2-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="0abf2-137">Ini-файл из предыдущего выпуска использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="0abf2-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="0abf2-138">Если вы обновляете Cloud Connector, обратитесь к разделу "Подготовка устройства [Cloud Connector"](prepare-your-cloud-connector-appliance.md) и убедитесь, что для siteName и EnableReferSupport установлено правильное значение в файле CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="0abf2-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="0abf2-139">Запустите консоль PowerShell от учетной записи администратора и запустите следующий cmdlet для регистрации текущего устройства:</span><span class="sxs-lookup"><span data-stu-id="0abf2-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="0abf2-140">Чтобы скачать последнюю версию, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0abf2-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="0abf2-141">Чтобы запустить установку, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0abf2-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="0abf2-142">Чтобы активировать новое развертывание и отключить предыдущую версию, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0abf2-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="0abf2-143">Если на сайте несколько устройств, выполните следующие действия, чтобы обновить каждое устройство по одному.</span><span class="sxs-lookup"><span data-stu-id="0abf2-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="0abf2-144">Если требуется обновить учетные данные администратора домена, виртуальной машины, администратора безопасного режима и администратора клиента, можно выполнить его с параметром  _UpdateAllCredentials,_ чтобы сбросить все учетные данные:</span><span class="sxs-lookup"><span data-stu-id="0abf2-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="0abf2-145">Затем, когда вы начнете обновление до новой версии, вам будет назначено повышение, чтобы ввести новые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="0abf2-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="0abf2-146">Чтобы сбросить только учетные данные администратора клиента, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0abf2-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="0abf2-147">Обновление нескольких сайтов до новой версии</span><span class="sxs-lookup"><span data-stu-id="0abf2-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="0abf2-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="0abf2-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="0abf2-149">Выполните действия по обновлению отдельного сайта, обновляя по одному сайту за раз для каждого сайта в развертывании.</span><span class="sxs-lookup"><span data-stu-id="0abf2-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="0abf2-150">Убедитесь, что [развертывание Cloud Connector](validate-your-cloud-connector-deployment.md) развернуто и проверено после обновления каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="0abf2-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

