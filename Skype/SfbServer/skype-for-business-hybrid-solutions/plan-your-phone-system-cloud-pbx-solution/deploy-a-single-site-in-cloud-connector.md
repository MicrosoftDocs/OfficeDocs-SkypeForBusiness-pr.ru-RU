---
title: Развертывание отдельного сайта в Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Узнайте о развертывании одного сайта PSTN в Cloud Connector Edition.
ms.openlocfilehash: 32c981b0f7de3d596dc25c3336000871db9fee65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094837"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="705d8-103">Развертывание отдельного сайта в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="705d8-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="705d8-104">Cloud Connector Edition завершит карьеру 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="705d8-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="705d8-105">После обновления организации до Teams узнайте, как подключить сеть локальной телефонии к Teams с помощью прямой [маршрутизации.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="705d8-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="705d8-106">Узнайте о развертывании одного сайта PSTN в Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="705d8-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="705d8-107">Вы можете развернуть skype for Business Cloud Connector Edition с поддержкой высокой доступности (HA) или без нее.</span><span class="sxs-lookup"><span data-stu-id="705d8-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="705d8-108">Если вы хотите включить ha, вам потребуется развернуть два или несколько устройств на сайте.</span><span class="sxs-lookup"><span data-stu-id="705d8-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="705d8-109">Вы также можете преобразовать существующий прибор в поддержку HA после его развертывания.</span><span class="sxs-lookup"><span data-stu-id="705d8-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="705d8-110">Развертывание первого устройства Skype для бизнеса cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="705d8-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="705d8-111">Чтобы развернуть первый аппарат на сайте, откройте консоль PowerShell в качестве администратора и запустите следующий cmdlet для регистрации устройства:</span><span class="sxs-lookup"><span data-stu-id="705d8-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="705d8-112">Следуйте инструкциям по предоставлению имени и пароля учетной записи администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="705d8-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="705d8-113">Используйте учетную запись, созданную для управления облачным подключением.</span><span class="sxs-lookup"><span data-stu-id="705d8-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="705d8-114">Кроме того, следуйте инструкциям по предоставлению внешнего пароля сертификата, пароля администратора безопасного режима, пароля администратора домена и пароля администратора VM.</span><span class="sxs-lookup"><span data-stu-id="705d8-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="705d8-115">В выпуске 1.4.2 и ранее также следуйте инструкциям по предоставлению внешнего пароля сертификата, пароля администратора безопасного режима, пароля администратора домена и пароля администратора VM.</span><span class="sxs-lookup"><span data-stu-id="705d8-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="705d8-116">В выпуске 2.0 и более поздней версии также следуйте инструкциям по предоставлению внешнего пароля сертификата, пароля CceService и пароля CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="705d8-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="705d8-117">Чтобы приступить к установке, откройте консоль PowerShell в качестве администратора и запустите следующий кодлет:</span><span class="sxs-lookup"><span data-stu-id="705d8-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="705d8-118">Добавление устройства на существующий сайт</span><span class="sxs-lookup"><span data-stu-id="705d8-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="705d8-119">Вы можете расширить существующий веб-сайт Облачного соединитетеля для поддержки HA, добавив на сайт дополнительные устройства.</span><span class="sxs-lookup"><span data-stu-id="705d8-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="705d8-120">Выполните действия по подготовке устройства облачного соединителю, как описано в ["Подготовка устройства облачного соединителю".](prepare-your-cloud-connector-appliance.md)</span><span class="sxs-lookup"><span data-stu-id="705d8-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="705d8-121">Обратите внимание, что некоторые действия необходимы только для первого устройства в развертывании.</span><span class="sxs-lookup"><span data-stu-id="705d8-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="705d8-122">Подтверди, что каталог сайта существует и правильно настроен для поддержки HA.</span><span class="sxs-lookup"><span data-stu-id="705d8-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="705d8-123">Запустите следующий комдлет только на недавно добавленном сервере хост,чтобы обновить топологию в конфигурации организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="705d8-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="705d8-124">Если вы хотите одновременно добавить несколько устройств, запустите cmdlet на каждом добавленном хост-сервере по одному:</span><span class="sxs-lookup"><span data-stu-id="705d8-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="705d8-125">Обнови топологию существующих устройств, задав следующие cmdlet на каждом сервере хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="705d8-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="705d8-126">Только запустите cmdlet на существующих устройствах.</span><span class="sxs-lookup"><span data-stu-id="705d8-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="705d8-127">Запустите следующий комдлет только на недавно добавленных серверах хост-серверов.</span><span class="sxs-lookup"><span data-stu-id="705d8-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="705d8-128">Не запускать этот комлет на существующем устройстве.</span><span class="sxs-lookup"><span data-stu-id="705d8-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="705d8-129">Если вы хотите одновременно добавить несколько устройств, запустите cmdlet на каждом добавленном сервере хост-сервера по одному.</span><span class="sxs-lookup"><span data-stu-id="705d8-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="705d8-130">Если каталог сайта был заданной локальной папке, необходимо определить файл для этой папки и использовать путь UNC для каталога сайтов в новом устройстве.</span><span class="sxs-lookup"><span data-stu-id="705d8-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="705d8-131">Вы можете оставить первый каталог сайта устройства с локальным путем или изменить его, чтобы использовать путь UNC для обмена в ту же папку.</span><span class="sxs-lookup"><span data-stu-id="705d8-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="705d8-132">Если расположение каталога общих сайтов изменяется, любые ранее установленные устройства необходимо отстраить, а затем переустановить.</span><span class="sxs-lookup"><span data-stu-id="705d8-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="705d8-133">> Важно: пароль для учетной записи CceService и учетной записи CABackupFile должен быть одинаковым для всех устройств, развернутых на сайте, чтобы устройства могли получать доступ к совместной записи каталога сайтов и зашифрованному файлу резервного копирования CA в каталоге сайтов.</span><span class="sxs-lookup"><span data-stu-id="705d8-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="705d8-134">Удаление устройства с существующего сайта</span><span class="sxs-lookup"><span data-stu-id="705d8-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="705d8-135">Если вы хотите удалить устройство с существующего сайта:</span><span class="sxs-lookup"><span data-stu-id="705d8-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="705d8-136">Запустите следующий комдлет только на серверах узла, которые необходимо удалить с сайта, чтобы обновить топологию в конфигурации организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="705d8-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="705d8-137">Запустите следующий комдлет только на серверах-хост-серверах, с которых необходимо удалить все виртуальные машины устройства.</span><span class="sxs-lookup"><span data-stu-id="705d8-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```