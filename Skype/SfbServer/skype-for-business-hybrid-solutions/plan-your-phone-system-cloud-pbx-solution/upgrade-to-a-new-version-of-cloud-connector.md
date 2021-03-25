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
ms.openlocfilehash: fea78c6b1b6ba3b2e644fef71d78b94aa3a244b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109135"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="b3944-103">Обновление Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b3944-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="b3944-104">Cloud Connector Edition завершит карьеру 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="b3944-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="b3944-105">После обновления организации до Teams узнайте, как подключить сеть локальной телефонии к Teams с помощью прямой [маршрутизации.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="b3944-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="b3944-106">Узнайте, как обновить развертывание Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="b3944-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="b3944-107">Если вы создали учетную запись клиента-клиента управления в Интернете и включили автоматические обновления, существующее развертывание Skype для бизнеса Cloud Connector Edition автоматически будет обновлено до более новой версии в соответствии с конфигурацией окна автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="b3944-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="b3944-108">Вы также можете выполнить ручное обновление.</span><span class="sxs-lookup"><span data-stu-id="b3944-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="b3944-109">Версии Cloud Connector Edition 1.4.1 и более поздние версии выполняют автоматические обновления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b3944-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="b3944-110">Если вы хотите перейти на последнюю версию (2.1) вручную, см. в разделе [Обновление](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) одного сайта до новой версии в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b3944-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="b3944-111">Автоматическое обновление требует запуска службы облачного соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="b3944-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="b3944-112">Ниже описан процесс автоматического обновления:</span><span class="sxs-lookup"><span data-stu-id="b3944-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="b3944-113">Процесс автоматического обновления будет работать в соответствии с расписанием, настроенным для автоматических обновлений.</span><span class="sxs-lookup"><span data-stu-id="b3944-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="b3944-114">Задачи обновления операционной системы</span><span class="sxs-lookup"><span data-stu-id="b3944-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="b3944-115">Проверка и загрузка обновлений операционной системы для всех VMs облачного соединитела.</span><span class="sxs-lookup"><span data-stu-id="b3944-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="b3944-116">Установите и обновите все VMs облачного соединителя один за другим и перезапустите.</span><span class="sxs-lookup"><span data-stu-id="b3944-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="b3944-117">После перезапуска VMs облачного соединитела проверьте, требуется ли еще один перезапуск.</span><span class="sxs-lookup"><span data-stu-id="b3944-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="b3944-118">После успешного исправления VMs облачного соединителя повторите процесс для хост-машины облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="b3944-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="b3944-119">После успешной загрузки хост-машины cloud Connector все оставшиеся задачи обновления операционной системы завершались.</span><span class="sxs-lookup"><span data-stu-id="b3944-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="b3944-120">Задачи обновления облачного соединитетеля</span><span class="sxs-lookup"><span data-stu-id="b3944-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="b3944-121">Скачайте и проверьте файл версии с сайта загрузки.</span><span class="sxs-lookup"><span data-stu-id="b3944-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="b3944-122">Скачайте новый файл msi версии.</span><span class="sxs-lookup"><span data-stu-id="b3944-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="b3944-123">Удалить старый файл msi; установите новый файл msi.</span><span class="sxs-lookup"><span data-stu-id="b3944-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="b3944-124">Скачайте новую версию битов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b3944-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="b3944-125">Зарегистрируйте устройство, позвонив в Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="b3944-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="b3944-126">Установите новую версию облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="b3944-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="b3944-127">Слейте старый прибор и переключение сетевого подключения к новому устройству.</span><span class="sxs-lookup"><span data-stu-id="b3944-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="b3944-128">При обновлении облачного соединителя до новой сборки может не обновляться.</span><span class="sxs-lookup"><span data-stu-id="b3944-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="b3944-129">Это может произойти, например, если окно PowerShell остается открытым во время автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="b3944-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="b3944-130">Чтобы загрузить обновленные комлеты, можно выполнить любой из следующих действий: > Закрыть PowerShell на устройстве облачного соединителя, а затем открыть PowerShell.> Или запустить Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="b3944-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="b3944-131">Обновление одного сайта до новой версии</span><span class="sxs-lookup"><span data-stu-id="b3944-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="b3944-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="b3944-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="b3944-133">Если на сайте имеется только один прибор, который необходимо обновить, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="b3944-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="b3944-134">Удалить существующую версию облачного соединителя в программах и функциях **панели \> \> управления.**</span><span class="sxs-lookup"><span data-stu-id="b3944-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="b3944-135">Установите новую версию CloudConnector.msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) от .</span><span class="sxs-lookup"><span data-stu-id="b3944-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="b3944-136">Подтвердите, что CloudConnector.ini для версии, которую вы устанавливаете, и что вы обновили все необходимые значения для среды.</span><span class="sxs-lookup"><span data-stu-id="b3944-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="b3944-137">Вы не можете использовать файл .ini из предыдущего выпуска.</span><span class="sxs-lookup"><span data-stu-id="b3944-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="b3944-138">Если вы обновляете облачный соединитель, [](prepare-your-cloud-connector-appliance.md) обратитесь к теме Подготовка устройства облачного соединители и убедитесь, что имя siteName и EnableReferSupport задайте правильное значение в CloudConnector.ini файле.</span><span class="sxs-lookup"><span data-stu-id="b3944-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="b3944-139">Запустите консоль PowerShell в качестве администратора и запустите следующий cmdlet для регистрации текущего устройства:</span><span class="sxs-lookup"><span data-stu-id="b3944-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="b3944-140">Запустите следующий cmdlet, чтобы скачать последнюю версию:</span><span class="sxs-lookup"><span data-stu-id="b3944-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="b3944-141">Запустите следующий cmdlet, чтобы начать установку:</span><span class="sxs-lookup"><span data-stu-id="b3944-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="b3944-142">Запустите следующий cmdlet, чтобы активировать новое развертывание и отключить предыдущую версию:</span><span class="sxs-lookup"><span data-stu-id="b3944-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="b3944-143">Если на сайте имеется несколько устройств, выполните следующие действия по обновлению каждого устройства по одному.</span><span class="sxs-lookup"><span data-stu-id="b3944-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="b3944-144">Если вы хотите обновить учетные данные администратора домена, администратора виртуальных машин, администратора безопасного режима и учетных данных администратора клиента, можно запустить этот код с параметром  _UpdateAllCredentials_ для сброса всех учетных данных:</span><span class="sxs-lookup"><span data-stu-id="b3944-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="b3944-145">Затем, когда вы начнете перейти на новую версию, вам будет назначен ввод новых учетных данных.</span><span class="sxs-lookup"><span data-stu-id="b3944-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="b3944-146">Если требуется только сбросить учетные данные администратора клиента, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b3944-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="b3944-147">Обновление нескольких сайтов до новой версии</span><span class="sxs-lookup"><span data-stu-id="b3944-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="b3944-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="b3944-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="b3944-149">Выполните действия по обновлению одного сайта и одновременному обновлению одного сайта для каждого сайта в развертывании.</span><span class="sxs-lookup"><span data-stu-id="b3944-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="b3944-150">Убедитесь в [том, что развертывание облачного соединиттеля](validate-your-cloud-connector-deployment.md) будет проверено после обновления каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="b3944-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
