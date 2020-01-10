---
title: Развертывание одного сайта в Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Сведения о развертывании отдельного сайта ТСОП в Cloud Connector Edition.
ms.openlocfilehash: a2cc8933276bc85b19ee79559ca4bcf9e88a079f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001029"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="31f04-103">Развертывание одного сайта в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="31f04-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="31f04-104">Сведения о развертывании отдельного сайта ТСОП в Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="31f04-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="31f04-105">Вы можете развернуть Skype для бизнеса Cloud Connector Edition с поддержкой высокой доступности (или без нее).</span><span class="sxs-lookup"><span data-stu-id="31f04-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="31f04-106">Чтобы реализовать поддержку высокой доступности, необходимо развернуть несколько устройств на сайте.</span><span class="sxs-lookup"><span data-stu-id="31f04-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="31f04-107">Кроме того, вы можете преобразовать существующие устройства после развертывания для поддержки высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="31f04-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="31f04-108">Развертывание первого устройства Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="31f04-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="31f04-109">Чтобы развернуть первое устройство сайта, откройте консоль PowerShell с правами администратора и выполните следующий командлет, чтобы зарегистрировать устройство:</span><span class="sxs-lookup"><span data-stu-id="31f04-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="31f04-p102">Необходимо указать учетную запись и пароль администратора клиента, следуя инструкциям. Используйте учетную запись, созданную для управления Cloud Connector через Интернет. Также необходимо согласно инструкциям предоставить пароль внешнего сертификата, администратора безопасного режима, администратора домена и администратора виртуальной машины. </span><span class="sxs-lookup"><span data-stu-id="31f04-p102">Follow the instructions to provide the tenant admin account name and password. Use the account you have created for Cloud Connector online management. Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="31f04-113">В выпуске 1.4.2 и более ранних версиях также следуйте инструкциям, чтобы предоставить пароль внешнего сертификата, пароль администратора для безопасного режима, пароль администратора домена и пароль администратора виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="31f04-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="31f04-114">В выпуске 2.0 и более поздних выпусках выполните инструкции по указанию пароля внешнего сертификата, а также паролей CceService и CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="31f04-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="31f04-115">Чтобы запустить установку, откройте консоль PowerShell от имени администратора и выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="31f04-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="31f04-116">Добавление устройства в существующий сайт</span><span class="sxs-lookup"><span data-stu-id="31f04-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="31f04-117">Вы можете увеличить существующий сайт облачного соединителя для поддержки высокой доступности, добавив на сайт дополнительные устройства.</span><span class="sxs-lookup"><span data-stu-id="31f04-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="31f04-118">Выполните действия для подготовки управляющего устройства облачного соединителя, как описано в статье [Подготовка устройства облачного соединителя](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="31f04-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="31f04-119">Обратите внимание, что некоторые шаги выполняются только при развертывании первого устройства.</span><span class="sxs-lookup"><span data-stu-id="31f04-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="31f04-120">Убедитесь, что каталог сайта существует и настроен соответствующим образом для поддержки высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="31f04-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="31f04-p104">Следующий командлет необходимо выполнять только на вновь добавленном сервере узла, чтобы обновить данные топологии в конфигурации клиента Office 365. Если вы хотите добавить несколько устройств одновременно, последовательно выполните командлет на каждом вновь добавляемом сервере узла:</span><span class="sxs-lookup"><span data-stu-id="31f04-p104">Run the following cmdlet only on the newly added host server to update topology information in your Office 365 tenant configuration. If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="31f04-p105">Обновите топологию на существующих устройствах, выполнив следующий командлет на каждом сервере узла. Этот командлет необходимо выполнять только на существующих устройствах.</span><span class="sxs-lookup"><span data-stu-id="31f04-p105">Update the topology on existing appliances by running the following cmdlet on each host server. Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="31f04-125">Выполните следующий командлет только для новых добавленных серверов узлов.</span><span class="sxs-lookup"><span data-stu-id="31f04-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="31f04-126">Не выполняйте этот командлет на существующем устройстве.</span><span class="sxs-lookup"><span data-stu-id="31f04-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="31f04-127">Если вы хотите одновременно добавить несколько устройств, выполните командлет на каждом добавленном сервере узла по одному.</span><span class="sxs-lookup"><span data-stu-id="31f04-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="31f04-128">Если для каталога сайта был установлен путь к локальной папке, необходимо указать общую папку для этой папки и использовать путь UNC для каталога сайта на новом устройстве.</span><span class="sxs-lookup"><span data-stu-id="31f04-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="31f04-129">Можно оставить первый каталог сайта устройства с локальным путем или изменить его, чтобы использовать путь UNC для общего доступа к той же папке.</span><span class="sxs-lookup"><span data-stu-id="31f04-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="31f04-130">При изменении расположения общего каталога сайта все ранее установленные устройства необходимо удалить, а затем переустановить.</span><span class="sxs-lookup"><span data-stu-id="31f04-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="31f04-131">> внимание! пароль для учетной записи Кцесервице и учетной записи Кабаккупфиле должны быть одинаковыми на всех устройствах, развернутых на сайте, чтобы устройства могли получать доступ к общему каталогу сайта и файлу резервной копии зашифрованного ЦС в каталоге сайтов.</span><span class="sxs-lookup"><span data-stu-id="31f04-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="31f04-132">Удаление устройства из существующего сайта</span><span class="sxs-lookup"><span data-stu-id="31f04-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="31f04-133">Если требуется удалить устройство из существующего сайта, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="31f04-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="31f04-134">Следующий командлет необходимо выполнять только на тех серверах узла, которые вы хотите удалить с сайта, чтобы обновить данные топологии в конфигурации клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="31f04-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Office 365 tenant configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="31f04-135">Следующий командлет необходимо выполнять только на тех серверах узла, с которых вы хотите удалить все виртуальные машины устройства.</span><span class="sxs-lookup"><span data-stu-id="31f04-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


