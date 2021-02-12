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
ms.openlocfilehash: 327fc4e687377f5f1338bea2f623b526511a2992
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358935"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="1d894-103">Развертывание отдельного сайта в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1d894-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="1d894-104">Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="1d894-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="1d894-105">После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="1d894-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="1d894-106">Узнайте о развертывании одного сайта PSTN в Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="1d894-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="1d894-107">Вы можете развернуть Skype для бизнеса Cloud Connector Edition с поддержкой высокой доступности или без нее.</span><span class="sxs-lookup"><span data-stu-id="1d894-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="1d894-108">Если вы хотите включить ha, вам потребуется развернуть два или более устройств на сайте.</span><span class="sxs-lookup"><span data-stu-id="1d894-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="1d894-109">Вы также можете преобразовать существующее устройство для поддержки ha после его развертывания.</span><span class="sxs-lookup"><span data-stu-id="1d894-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="1d894-110">Развертывание первого устройства Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1d894-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="1d894-111">Чтобы развернуть первое устройство на сайте, откройте консоль PowerShell от учетной записи администратора и запустите следующий cmdlet для регистрации устройства:</span><span class="sxs-lookup"><span data-stu-id="1d894-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="1d894-112">Следуйте инструкциям, чтобы предоставить имя и пароль учетной записи администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="1d894-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="1d894-113">Используйте учетную запись, созданную для управления Cloud Connector в Интернете.</span><span class="sxs-lookup"><span data-stu-id="1d894-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="1d894-114">Кроме того, следуйте инструкциям по указанию пароля внешнего сертификата, пароля администратора безопасного режима, пароля администратора домена и пароля администратора ВМ.</span><span class="sxs-lookup"><span data-stu-id="1d894-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="1d894-115">В выпуске 1.4.2 и более ранних версиях следуйте инструкциям, чтобы предоставить пароль внешнего сертификата, пароль администратора безопасного режима, пароль администратора домена и пароль администратора ВМ.</span><span class="sxs-lookup"><span data-stu-id="1d894-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="1d894-116">В выпуске 2.0 и более поздних версиях следуйте инструкциям, чтобы предоставить пароль внешнего сертификата, пароль CceService и пароль CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="1d894-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="1d894-117">Чтобы начать установку, откройте консоль PowerShell от учетной записи администратора и запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1d894-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="1d894-118">Добавление устройства на существующий сайт</span><span class="sxs-lookup"><span data-stu-id="1d894-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="1d894-119">Вы можете расширить существующий сайт Cloud Connector для поддержки ha, добавив на него дополнительные устройства.</span><span class="sxs-lookup"><span data-stu-id="1d894-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="1d894-120">Выполните действия по подготовке устройства Cloud Connector, как описано в описании подготовки [устройства Cloud Connector.](prepare-your-cloud-connector-appliance.md)</span><span class="sxs-lookup"><span data-stu-id="1d894-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="1d894-121">Обратите внимание, что некоторые действия необходимы только для первого устройства в развертывании.</span><span class="sxs-lookup"><span data-stu-id="1d894-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="1d894-122">Подтвердим, что каталог сайта существует и правильно настроен для поддержки ha.</span><span class="sxs-lookup"><span data-stu-id="1d894-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="1d894-123">Чтобы обновить сведения о топологии в конфигурации организации Microsoft 365 или Office 365, запустите следующий cmdlet только на только что добавленном сервере.</span><span class="sxs-lookup"><span data-stu-id="1d894-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="1d894-124">Если вы хотите добавить несколько устройств одновременно, запустите его на каждом добавленном хост-сервере по одному:</span><span class="sxs-lookup"><span data-stu-id="1d894-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="1d894-125">Обновите топологию на существующих устройствах, выведя следующий cmdlet на каждом хост-сервере.</span><span class="sxs-lookup"><span data-stu-id="1d894-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="1d894-126">Запустите его только на существующих устройствах.</span><span class="sxs-lookup"><span data-stu-id="1d894-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="1d894-127">Следующий cmdlet следует запускать только на вновь добавленных серверах.</span><span class="sxs-lookup"><span data-stu-id="1d894-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="1d894-128">Не запускать этот cmdlet на существующем устройстве.</span><span class="sxs-lookup"><span data-stu-id="1d894-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="1d894-129">Если вы хотите добавить несколько устройств одновременно, запустите его на каждом добавленном хост-сервере по одному.</span><span class="sxs-lookup"><span data-stu-id="1d894-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="1d894-130">Если для каталога сайта был установлен путь к локальной папке, необходимо определить обой папку и использовать UNC-путь для каталога сайта на новом устройстве.</span><span class="sxs-lookup"><span data-stu-id="1d894-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="1d894-131">Можно оставить первый каталог сайта устройства с локальным путем или изменить его, чтобы использовать UNC-путь для папки в той же папке.</span><span class="sxs-lookup"><span data-stu-id="1d894-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="1d894-132">Если расположение общего каталога сайта изменяется, все ранее установленные устройства необходимо будет установить, а затем переустановить.</span><span class="sxs-lookup"><span data-stu-id="1d894-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="1d894-133">> Важно! Пароль для учетной записи CceService и учетной записи CABackupFile должен быть одинаковым на всех устройствах, развернутых на сайте, чтобы устройства могли получать доступ к папке каталога сайта и зашифрованному файлу резервной копии ЦС в каталоге сайта.</span><span class="sxs-lookup"><span data-stu-id="1d894-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="1d894-134">Удаление устройства с существующего сайта</span><span class="sxs-lookup"><span data-stu-id="1d894-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="1d894-135">Если вы хотите удалить устройство с существующего сайта:</span><span class="sxs-lookup"><span data-stu-id="1d894-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="1d894-136">Чтобы обновить сведения о топологии в конфигурации организации Microsoft 365 или Office 365, запустите следующий cmdlet только на серверах узла, которые требуется удалить с сайта.</span><span class="sxs-lookup"><span data-stu-id="1d894-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="1d894-137">Следующий cmdlet следует запускать только на серверах- серверах, с которых требуется удалить все виртуальные машины устройства.</span><span class="sxs-lookup"><span data-stu-id="1d894-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


