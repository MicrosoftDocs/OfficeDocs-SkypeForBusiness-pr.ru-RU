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
description: Сведения о том, как обновить развертывание Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359295"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="6b8e8-103">Обновление Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6b8e8-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="6b8e8-104">Cloud Connector Edition выйдет 31 июля 2021 вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="6b8e8-105">После обновления вашей организации до Teams Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="6b8e8-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="6b8e8-106">Сведения о том, как обновить развертывание Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="6b8e8-107">Если вы настроили учетную запись клиента управления через Интернет и включили автоматические обновления, существующее развертывание Skype для бизнеса Cloud Connector Edition будет автоматически обновлено до новой версии в соответствии с конфигурацией окна автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="6b8e8-108">Вы также можете выполнить обновление вручную.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="6b8e8-109">Версии Cloud Connector Edition 1.4.1 и более поздних версий выполняют автоматические обновления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="6b8e8-110">Если вы хотите выполнить обновление до последней версии (2,1) вручную, ознакомьтесь с разделом [обновление отдельного сайта до новой версии](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) , приведенной далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="6b8e8-111">Для автоматического обновления необходимо, чтобы была запущена служба Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="6b8e8-112">Ниже описан процесс автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="6b8e8-113">Процесс автоматического обновления будет выполняться в соответствии с расписанием, настроенным для автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="6b8e8-114">Задачи обновления операционной системы</span><span class="sxs-lookup"><span data-stu-id="6b8e8-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="6b8e8-115">Проверьте и загрузите обновления операционной системы для всех виртуальных машин Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="6b8e8-116">Установите и обновите все виртуальные машины Cloud Connector по одному и перезапустите.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="6b8e8-117">После перезапуска виртуальных машин Cloud Connector проверьте, требуется ли другая перезагрузка.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="6b8e8-118">После успешного исправления виртуальных машин Cloud Connector повторите этот процесс для хостного компьютера Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="6b8e8-119">После успешной загрузки хостного компьютера Cloud Connector все незавершенные задачи обновления операционной системы будут выполнены.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="6b8e8-120">Задачи по обновлению Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6b8e8-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="6b8e8-121">Скачайте и проверьте версию файла на сайте загрузки.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="6b8e8-122">Скачайте новый файл Version. msi.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="6b8e8-123">Удалите старый MSI файл; Установите новый файл MSI.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="6b8e8-124">Скачайте новую версию BITS для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="6b8e8-125">Зарегистрируйте устройство, вызвав Register – CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="6b8e8-126">Установите новую версию Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="6b8e8-127">Перестокует старое устройство и переключите сетевое подключение на новое устройство.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="6b8e8-128">При обновлении Cloud Connector до новой сборки командлеты Cloud Connector могут не обновляться.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="6b8e8-129">Это может произойти, например, если окно PowerShell остается открытым во время автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="6b8e8-130">Чтобы загрузить обновленные командлеты, выполните одно из следующих действий: > закрыть PowerShell на устройстве Cloud Connector, а затем снова открыть PowerShell. > или можно выполнить командлет Import – Module CloudConnector — Force.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="6b8e8-131">Обновление одного сайта до новой версии</span><span class="sxs-lookup"><span data-stu-id="6b8e8-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="6b8e8-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="6b8e8-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="6b8e8-133">Если на сайте, который вы хотите обновить, имеется только одно устройство, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6b8e8-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="6b8e8-134">Удалите существующую версию Cloud Connector в разделе программы \*\* \> \> и компоненты панели управления\*\*.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="6b8e8-135">Установите новую версию CloudConnector.msi из [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="6b8e8-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="6b8e8-136">Убедитесь, что у вас есть файл CloudConnector.ini для устанавливаемой версии, и что вы обновили все необходимые значения для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="6b8e8-137">Невозможно использовать ini-файл из предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="6b8e8-138">Если вы обновляете Cloud Connector, обратитесь к разделу [Подготовка устройства Cloud Connector](prepare-your-cloud-connector-appliance.md) и убедитесь, что для sitename и EnableReferSupport задано правильное значение в файле CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="6b8e8-139">Запустите консоль PowerShell от имени администратора и выполните следующий командлет, чтобы зарегистрировать текущее устройство:</span><span class="sxs-lookup"><span data-stu-id="6b8e8-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="6b8e8-140">Выполните следующий командлет, чтобы скачать последнюю версию:</span><span class="sxs-lookup"><span data-stu-id="6b8e8-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="6b8e8-141">Чтобы запустить установку, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="6b8e8-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="6b8e8-142">Выполните следующий командлет, чтобы активировать новое развертывание и отключить предыдущую версию:</span><span class="sxs-lookup"><span data-stu-id="6b8e8-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="6b8e8-143">Если на сайте несколько устройств, выполните описанные выше действия, чтобы обновить каждое устройство по одному.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="6b8e8-144">Чтобы изменить учетные данные администратора домена, администратора виртуальной машины, администратора безопасного режима и администратора клиента, можно выполнить командлет с параметром  _упдатеаллкредентиалс_ , чтобы сбросить все учетные данные:</span><span class="sxs-lookup"><span data-stu-id="6b8e8-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="6b8e8-145">Затем, когда вы начнете обновление до новой версии, вам будет предложено ввести новые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="6b8e8-146">Если вы хотите сбросить только учетные данные администратора клиента, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="6b8e8-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="6b8e8-147">Обновление нескольких сайтов до новой версии</span><span class="sxs-lookup"><span data-stu-id="6b8e8-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="6b8e8-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="6b8e8-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="6b8e8-149">Выполните действия по обновлению отдельного сайта, обновив один сайт за раз для каждого сайта в развертывании.</span><span class="sxs-lookup"><span data-stu-id="6b8e8-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="6b8e8-150">Перед обновлением каждого сайта убедитесь в том, что [развертывание Cloud Connector было проверено](validate-your-cloud-connector-deployment.md) .</span><span class="sxs-lookup"><span data-stu-id="6b8e8-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

