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
description: Сведения о развертывании одного сайта PSTN в Cloud Connector Edition.
ms.openlocfilehash: 327fc4e687377f5f1338bea2f623b526511a2992
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358935"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="56d66-103">Развертывание отдельного сайта в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="56d66-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="56d66-104">Cloud Connector Edition выйдет 31 июля 2021 вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="56d66-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="56d66-105">После обновления вашей организации до Teams Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="56d66-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="56d66-106">Сведения о развертывании одного сайта PSTN в Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="56d66-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="56d66-107">Вы можете развернуть Skype для бизнеса Cloud Connector Edition с поддержкой высокого уровня доступности или без нее.</span><span class="sxs-lookup"><span data-stu-id="56d66-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="56d66-108">Если вы хотите включить HA, вам потребуется развернуть два или больше устройств на сайте.</span><span class="sxs-lookup"><span data-stu-id="56d66-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="56d66-109">Вы также можете преобразовать существующее устройство для поддержки высокой доступности после развертывания.</span><span class="sxs-lookup"><span data-stu-id="56d66-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="56d66-110">Развертывание первого устройства Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="56d66-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="56d66-111">Чтобы развернуть первое устройство на сайте, откройте консоль PowerShell от имени администратора и выполните следующий командлет, чтобы зарегистрировать устройство:</span><span class="sxs-lookup"><span data-stu-id="56d66-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="56d66-112">Следуйте инструкциям, чтобы указать имя и пароль учетной записи администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="56d66-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="56d66-113">Используйте учетную запись, созданную для управления Cloud Connector Online.</span><span class="sxs-lookup"><span data-stu-id="56d66-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="56d66-114">Кроме того, следуйте инструкциям по предоставлению пароля внешнего сертификата, пароля администратора безопасного режима, пароля администратора домена и пароля администратора виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="56d66-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="56d66-115">В 1.4.2 и более ранних версиях также следуйте инструкциям по предоставлению пароля внешнего сертификата, пароля администратора безопасного режима, пароля администратора домена и пароля администратора виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="56d66-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="56d66-116">В выпуске 2,0 и более поздних версиях также следуйте инструкциям по предоставлению пароля внешнего сертификата, пароля CceService и пароля CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="56d66-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="56d66-117">Чтобы начать установку, откройте консоль PowerShell от имени администратора и выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="56d66-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="56d66-118">Добавление устройства к существующему сайту</span><span class="sxs-lookup"><span data-stu-id="56d66-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="56d66-119">Вы можете расширить существующий сайт Cloud Connector для поддержки высокой доступности, добавив на сайт дополнительные устройства.</span><span class="sxs-lookup"><span data-stu-id="56d66-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="56d66-120">Выполните действия, необходимые для подготовки устройства Cloud Connector, как описано в статье [Подготовка устройства Cloud Connector](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="56d66-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="56d66-121">Обратите внимание, что некоторые действия необходимы только для первого устройства в развертывании.</span><span class="sxs-lookup"><span data-stu-id="56d66-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="56d66-122">Убедитесь, что каталог сайтов существует и правильно настроен для поддержки высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="56d66-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="56d66-123">Выполните следующий командлет только на вновь добавленном сервере узла, чтобы обновить сведения о топологии в конфигурации организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="56d66-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="56d66-124">Если вы хотите добавить несколько устройств одновременно, выполните командлет на каждом добавленном сервере узла один за одним:</span><span class="sxs-lookup"><span data-stu-id="56d66-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="56d66-125">Обновите топологию на существующих устройствах, выполнив следующий командлет на каждом сервере узла.</span><span class="sxs-lookup"><span data-stu-id="56d66-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="56d66-126">Запускать командлет только на существующих устройствах.</span><span class="sxs-lookup"><span data-stu-id="56d66-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="56d66-127">Выполните следующий командлет только для новых добавленных серверов узлов.</span><span class="sxs-lookup"><span data-stu-id="56d66-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="56d66-128">Не запускайте этот командлет на существующем устройстве.</span><span class="sxs-lookup"><span data-stu-id="56d66-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="56d66-129">Если вы хотите добавить несколько устройств одновременно, выполните командлет на каждом добавленном сервере узла по одному.</span><span class="sxs-lookup"><span data-stu-id="56d66-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="56d66-130">Если для каталога сайтов задан путь к локальной папке, необходимо определить общий файловый ресурс для этой папки и использовать UNC-путь к каталогу сайта на новом устройстве.</span><span class="sxs-lookup"><span data-stu-id="56d66-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="56d66-131">Вы можете оставить первый каталог сайта устройства с локальным путем или изменить его, чтобы использовать UNC-путь к папке в той же папке.</span><span class="sxs-lookup"><span data-stu-id="56d66-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="56d66-132">Если расположение общего каталога сайтов изменяется, все ранее установленные устройства необходимо удалить, а затем повторно установить.</span><span class="sxs-lookup"><span data-stu-id="56d66-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="56d66-133">> важно! пароль для учетной записи CceService и учетной записи CABackupFile должны быть одинаковыми на всех устройствах, развернутых на сайте, чтобы устройства могли получить доступ к общему ресурсу каталога сайтов и файлу резервной копии зашифрованного центра сертификации в каталоге сайтов.</span><span class="sxs-lookup"><span data-stu-id="56d66-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="56d66-134">Удаление устройства из существующего сайта</span><span class="sxs-lookup"><span data-stu-id="56d66-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="56d66-135">Если вы хотите удалить устройство из существующего сайта:</span><span class="sxs-lookup"><span data-stu-id="56d66-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="56d66-136">Выполните следующий командлет только на тех серверах узлов, которые необходимо удалить с сайта, чтобы обновить сведения о топологии в конфигурации Microsoft 365 или Office 365 Организации.</span><span class="sxs-lookup"><span data-stu-id="56d66-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="56d66-137">Выполните следующий командлет только на тех серверах узла, из которых вы хотите удалить все виртуальные машины устройства.</span><span class="sxs-lookup"><span data-stu-id="56d66-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


