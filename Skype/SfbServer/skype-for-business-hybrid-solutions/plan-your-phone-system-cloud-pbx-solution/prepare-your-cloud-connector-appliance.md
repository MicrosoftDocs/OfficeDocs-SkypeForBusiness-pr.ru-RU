---
title: Подготовка устройства Cloud Connector
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
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Сведения о подготовке устройства Cloud Connector к развертыванию и использованию с телефонной системой (облачная УАТС).
ms.openlocfilehash: d00002719ed8aaac7d0f0fb0e5ceb5722acc289c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220069"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="5f665-103">Подготовка устройства Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="5f665-103">Prepare your Cloud Connector appliance</span></span>

<span data-ttu-id="5f665-104">Сведения о подготовке устройства Cloud Connector к развертыванию и использованию с телефонной системой (облачная УАТС).</span><span class="sxs-lookup"><span data-stu-id="5f665-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="5f665-105">В этом разделе описывается, как получить установочные файлы Skype для бизнеса Cloud Connector Edition, установить программное обеспечение Cloud Connector и подготовить ваше устройство Cloud Connector к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="5f665-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="5f665-106">После выполнения всех действий, описанных в этом разделе, вы будете готовы к развертыванию Cloud Connector для одного или нескольких сайтов.</span><span class="sxs-lookup"><span data-stu-id="5f665-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="5f665-107">Если у вас есть развертывание Cloud Connector и вы еще не выполнили обновление до Cloud Connector версии 2,1, ознакомьтесь со статьей [обновление до новой версии Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5f665-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5f665-108">Корпорация Майкрософт поддерживает текущую версию Cloud Connector Edition версии 2,1.</span><span class="sxs-lookup"><span data-stu-id="5f665-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="5f665-109">Если вы настроили автоматическое обновление, Cloud Connector обновится автоматически.</span><span class="sxs-lookup"><span data-stu-id="5f665-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="5f665-110">Если вы настроили обновление вручную, вам потребуется выполнить обновление до версии 2,1 в течение 60 дней с момента ее выпуска.</span><span class="sxs-lookup"><span data-stu-id="5f665-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="5f665-111">Корпорация Майкрософт будет поддерживать предыдущую версию в течение 60 дней после выпуска 2,1, чтобы разрешить время обновления.</span><span class="sxs-lookup"><span data-stu-id="5f665-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="5f665-112">Для Cloud Connector версии 2,1 и более поздних версий на ведущем устройстве должно быть установлено приложение .NET Framework 4.6.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="5f665-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5f665-113">При успешном развертывании при запуске командлетов для настройки Skype для бизнеса Cloud Connector Edition всегда используйте тот же сеанс консоли, что и в начале работы.</span><span class="sxs-lookup"><span data-stu-id="5f665-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="5f665-114">Не следует переключаться на другие сеансы во время развертывания и настройки.</span><span class="sxs-lookup"><span data-stu-id="5f665-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="5f665-115">Существует несколько действий, которые можно выполнить только для первого устройства в развертывании: создание общего ресурса для каталога сайтов, Загрузка BITS и подготовка файла виртуального жесткого диска (VHDX) из образа Windows Server ISO.</span><span class="sxs-lookup"><span data-stu-id="5f665-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="5f665-116">Загрузка установщика Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="5f665-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="5f665-117">Скачайте файлы установки на сервер узла, на котором будут запускаться виртуальные машины Cloud Connector: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="5f665-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="5f665-118">Во время установки Cloud Connector сервер узла должен иметь доступ к Интернету, так как во время установки будут загружены дополнительные файлы.</span><span class="sxs-lookup"><span data-stu-id="5f665-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="5f665-119">Запустите установщик и примите значения по умолчанию во время установки.</span><span class="sxs-lookup"><span data-stu-id="5f665-119">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="5f665-120">Убедитесь, что установка успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="5f665-120">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="5f665-121">Проверка установки и настройка среды</span><span class="sxs-lookup"><span data-stu-id="5f665-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="5f665-122">Откройте консоль PowerShell от имени администратора и убедитесь, что командлеты Skype для бизнеса Cloud Connector Edition доступны, используя следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5f665-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="5f665-123">Команда должна вернуть список командлетов Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="5f665-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="5f665-124">Файлы VHD, SfBBits и VersionInfo будут храниться в **каталоге сайтов**.</span><span class="sxs-lookup"><span data-stu-id="5f665-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="5f665-125">Расположение **каталога сайтов** можно найти с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="5f665-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="5f665-126">Команда должна вернуть расположение в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="5f665-126">The command should return a location in your file system.</span></span> <span data-ttu-id="5f665-127">Расположением может быть локальная папка или файловый ресурс.</span><span class="sxs-lookup"><span data-stu-id="5f665-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="5f665-128">Расположение по умолчанию для **каталога сайтов** :%UserProfile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="5f665-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="5f665-129">Расположение по умолчанию должно быть заменено на общую папку на первом устройстве, созданном на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="5f665-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="5f665-130">Необходимо выбрать следующее расположение:</span><span class="sxs-lookup"><span data-stu-id="5f665-130">The location you select must be:</span></span>

   - <span data-ttu-id="5f665-131">Создается на первом устройстве, созданном на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="5f665-131">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="5f665-132">Общая папка, доступная другим серверам узлов (устройствам) на том же сайте.</span><span class="sxs-lookup"><span data-stu-id="5f665-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="5f665-133">Чтобы задать для **каталога сайтов** расположение, отличное от используемого по умолчанию, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5f665-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="5f665-134">При развертывании высокого уровня доступности для сайта обязательно выполните командлет, чтобы задать для **каталога сайтов** одно и то же расположение на каждом сервере узла в пределах сайта.</span><span class="sxs-lookup"><span data-stu-id="5f665-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="5f665-135">При входе в систему и развертывании каждого устройства на сайте убедитесь, что текущая учетная запись входа имеет право доступа к **каталогу сайта**.</span><span class="sxs-lookup"><span data-stu-id="5f665-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="5f665-136">**Каталог Appliance** является локальным рабочим корневым каталогом для Skype для бизнеса Cloud Connector Edition и расположением, в котором сохраняются внешние сертификаты, экземпляры и журналы.</span><span class="sxs-lookup"><span data-stu-id="5f665-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="5f665-137">Расположение по умолчанию:%Усерпрофиле%\клаудконнектор\апплианцерут.</span><span class="sxs-lookup"><span data-stu-id="5f665-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="5f665-138">Чтобы найти расположение **каталога устройств**, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5f665-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="5f665-139">Чтобы задать для **каталога устройств** расположение, отличное от используемого по умолчанию, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5f665-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="5f665-140">Для каталога устройства должна быть задана локальная папка на устройстве.</span><span class="sxs-lookup"><span data-stu-id="5f665-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="5f665-141">**Каталог устройств** необходимо задать только перед запуском развертывания Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="5f665-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="5f665-142">Если вы измените его после развертывания, вам потребуется повторно развернуть сервер узла.</span><span class="sxs-lookup"><span data-stu-id="5f665-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5f665-143">Путь к **каталогу устройств** не должен содержать пробелов.</span><span class="sxs-lookup"><span data-stu-id="5f665-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="5f665-144">Задание пути для внешнего пограничного сертификата</span><span class="sxs-lookup"><span data-stu-id="5f665-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="5f665-145">Выполните следующий командлет, чтобы задать путь, включая имя файла, к внешнему пограничному сертификату.</span><span class="sxs-lookup"><span data-stu-id="5f665-145">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="5f665-146">Пример: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="5f665-146">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="5f665-147">Сертификат должен содержать закрытые ключи.</span><span class="sxs-lookup"><span data-stu-id="5f665-147">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="5f665-148">Обратите внимание, что параметр-target относится только к версиям 1.4.2 и более поздним версиям.</span><span class="sxs-lookup"><span data-stu-id="5f665-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="5f665-149">Укажите полный путь к внешнему сертификату, включая имя файла.</span><span class="sxs-lookup"><span data-stu-id="5f665-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="5f665-150">Сертификат может храниться локально или на общем файловом ресурсе.</span><span class="sxs-lookup"><span data-stu-id="5f665-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="5f665-151">Если сертификат хранится в общей папке, Общая папка должна быть создана на первом устройстве каждого сайта и должна быть доступна другим устройствам, принадлежащим к тому же сайту.</span><span class="sxs-lookup"><span data-stu-id="5f665-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="5f665-152">Этот командлет копирует внешний сертификат в **каталог устройства**.</span><span class="sxs-lookup"><span data-stu-id="5f665-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5f665-153">**Если вы обновили версию Cloud Connector версии 1.4.2 или более поздней**, убедитесь, что подготовленный внешний сертификат содержит закрытые ключи и цепочку сертификатов, включая сертификат КОРНЕВОГО центра сертификации и сертификаты ПРОМЕЖУТОЧНОГО центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="5f665-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="5f665-154">**Если вы еще не обновили версию Cloud Connector версии 1.4.2**, убедитесь, что подготовленный внешний сертификат содержит закрытые ключи.</span><span class="sxs-lookup"><span data-stu-id="5f665-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="5f665-155">Этот внешний сертификат должен быть выдан центром сертификации, который по умолчанию является доверенным для Windows.</span><span class="sxs-lookup"><span data-stu-id="5f665-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="5f665-156">Задайте путь к внешнему сертификату шлюза PSTN/SBC</span><span class="sxs-lookup"><span data-stu-id="5f665-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="5f665-157">Если вы используете протокол TLS между сервером-посредником и шлюзом PSTN/SBC, выполните следующий командлет, чтобы задать путь, включая имя файла, к сертификату шлюза.</span><span class="sxs-lookup"><span data-stu-id="5f665-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="5f665-158">Пример: К:\цертс\кце\сбк.Контосо.ком.цер.</span><span class="sxs-lookup"><span data-stu-id="5f665-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="5f665-159">Сертификат должен содержать корневой центр сертификации и промежуточную цепь для сертификата, назначенного шлюзу:</span><span class="sxs-lookup"><span data-stu-id="5f665-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="5f665-160">Обратите внимание, что параметр-target относится только к версиям 1.4.2 и более поздним версиям.</span><span class="sxs-lookup"><span data-stu-id="5f665-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="5f665-161">Создание виртуальных коммутаторов в диспетчере Hyper – V</span><span class="sxs-lookup"><span data-stu-id="5f665-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="5f665-162">Откройте **Hyper-V Manager**  >  **Диспетчер виртуальных коммутаторов**Hyper – V и выберите команду **создать диспетчер виртуальных коммутаторов**.</span><span class="sxs-lookup"><span data-stu-id="5f665-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="5f665-163">Создайте внешний виртуальный коммутатор и привяжите его к физическому сетевому адаптеру, подключенному к домену внутренней сети:</span><span class="sxs-lookup"><span data-stu-id="5f665-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="5f665-164">Выберите **разрешить операционной системе управления общий доступ к этому сетевому адаптеру** для этого виртуального коммутатора.</span><span class="sxs-lookup"><span data-stu-id="5f665-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="5f665-165">Создайте внешний виртуальный коммутатор и привяжите его к физическому сетевому адаптеру, который пересылается в Интернет:</span><span class="sxs-lookup"><span data-stu-id="5f665-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="5f665-166">Снимите флажок **Разрешить управление операционной системой, чтобы предоставить общий доступ к этому сетевому адаптеру** для этого виртуального коммутатора.</span><span class="sxs-lookup"><span data-stu-id="5f665-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="5f665-167">Задайте имя коммутатора, который подключает сеть периметра к домену внутренней сети **SFB CCE**.</span><span class="sxs-lookup"><span data-stu-id="5f665-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="5f665-168">Задайте имя коммутатора, который подключает сеть периметра к **коммутатору Интернета SFB CCE Internet**.</span><span class="sxs-lookup"><span data-stu-id="5f665-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="5f665-169">Обновление файла конфигурации CloudConnector. ini</span><span class="sxs-lookup"><span data-stu-id="5f665-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="5f665-170">Подготовьте файл CloudConnector. ini, используя сведения, собранные в разделе [Определение параметров развертывания](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) в разделе [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="5f665-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="5f665-171">Чтобы обновить файл, сначала выполните следующий командлет, чтобы получить пример шаблона (CloudConnector. Sample. ini):</span><span class="sxs-lookup"><span data-stu-id="5f665-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="5f665-172">Пример шаблона хранится в **каталоге устройств**.</span><span class="sxs-lookup"><span data-stu-id="5f665-172">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="5f665-173">После того как вы обновите их значениями для вашей среды, сохраните файл как CloudConnector. ini в **каталоге устройств**.</span><span class="sxs-lookup"><span data-stu-id="5f665-173">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="5f665-174">Командлет **Get – CcApplianceDirectory** можно использовать, чтобы определить путь к **каталогу устройств**.</span><span class="sxs-lookup"><span data-stu-id="5f665-174">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="5f665-175">При обновлении ini-файла учитывайте следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="5f665-175">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="5f665-176">В этом разделе рассматриваются не все значения для ini-файла, в данном разделе рассматриваются только те, которые связаны с особыми аспектами.</span><span class="sxs-lookup"><span data-stu-id="5f665-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="5f665-177">Полный список представлен в разделе [Определение параметров развертывания](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) раздела [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="5f665-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="5f665-178">Для получения дополнительных сведений о том, какие значения необходимо изменить для дополнительных устройств или новых сайтов, ознакомьтесь с разделом [один сайт с высокой доступностью (HA) по сравнению с развертыванием](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) нескольких сайтов в разделе [развертывание нескольких сайтов в Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5f665-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="5f665-179">**SiteName:** Значение по умолчанию — **site1**.</span><span class="sxs-lookup"><span data-stu-id="5f665-179">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="5f665-180">Перед развертыванием Cloud Connector необходимо обновить его, так как при запуске **Register-CcAppliance** для регистрации устройства на существующем или новом сайте командлет будет использовать **SiteName** , чтобы определить, какой сайт нужно зарегистрировать.</span><span class="sxs-lookup"><span data-stu-id="5f665-180">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="5f665-181">Если вы хотите зарегистрировать устройство на новом сайте, значение **SiteName** должно быть уникальным и отличаться от существующих сайтов.</span><span class="sxs-lookup"><span data-stu-id="5f665-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="5f665-182">Если вы хотите зарегистрировать устройство на существующем сайте, значение **SiteName** в ini-файле должно быть соответствующим имени, определенному в конфигурации организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f665-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="5f665-183">При копировании файла конфигурации с одного сайта на другой необходимо соответствующим образом обновить значение **SiteName** для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="5f665-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="5f665-184">**ServerName:** Имя сервера не должно содержать имя домена и должно содержать не более 15 символов.</span><span class="sxs-lookup"><span data-stu-id="5f665-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="5f665-185">**Хардваретипе:** Если вы не задаете или не оставляете значение null, будет использоваться значение по умолчанию **Normal** .</span><span class="sxs-lookup"><span data-stu-id="5f665-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="5f665-186">Используйте параметр **Normal** , если планируется развертывание более крупной версии Cloud Connector для поддержки 500 одновременных вызовов на хост-компьютере, как описано в статье [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="5f665-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="5f665-187">Используйте **минимум** для развертывания меньшего размера, поддерживающего одновременные вызовы 50.</span><span class="sxs-lookup"><span data-stu-id="5f665-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="5f665-188">**Виртуальные коммутаторы Интернета/корпоративной сети/управления:**: добавьте имя созданных виртуальных коммутаторов.</span><span class="sxs-lookup"><span data-stu-id="5f665-188">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="5f665-189">В качестве виртуального коммутатора управления оставьте значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5f665-189">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="5f665-190">Сценарий развертывания создаст виртуальный коммутатор управления в начале развертывания и удалит его после завершения развертывания.</span><span class="sxs-lookup"><span data-stu-id="5f665-190">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="5f665-191">**ManagementIPPrefix:** ManagementIPPrefix в разделе Network должен быть другой подсетью с другими внутренними IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="5f665-191">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="5f665-192">Например, в качестве значения по умолчанию отображается ManagementIPPrefix 192.168.213.0, в то время как AD IPAddress — 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="5f665-192">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="5f665-193">Сценарии развертывания создают сетевой адаптер управления на каждой виртуальной машине, назначают IP-адрес управления и подключают его к виртуальному коммутатору управления.</span><span class="sxs-lookup"><span data-stu-id="5f665-193">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="5f665-194">Это позволяет ведущему серверу подключаться к виртуальным машинам и управлять ими через эту сеть управления.</span><span class="sxs-lookup"><span data-stu-id="5f665-194">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="5f665-195">Виртуальный коммутатор управления удаляется после завершения развертывания.</span><span class="sxs-lookup"><span data-stu-id="5f665-195">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="5f665-196">**Конфигурации базовых ВМ:** Параметры в этом разделе необходимо настроить для командлета **Convert – CcIsoToVhdx** .</span><span class="sxs-lookup"><span data-stu-id="5f665-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="5f665-197">Во время подготовки образа базовой ВИРТУАЛЬНОЙ машины базовая виртуальная машина будет подключена к коммутатору внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="5f665-197">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="5f665-198">Чтобы виртуальная машина могла получить доступ к Интернету, необходимы следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="5f665-198">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="5f665-199">Общую Басевмип: IP-адрес в корпоративной сети, назначаемый основной виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="5f665-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="5f665-200">Сетью Корпнетдефаултгатевай: шлюз по умолчанию, назначаемый основной виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="5f665-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="5f665-201">Сетью CorpnetDNSIPAddress: IP-адрес DNS, назначаемый основной виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="5f665-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="5f665-202">Сетью Всуссервер: IP-адрес службы обновления Windows Server.</span><span class="sxs-lookup"><span data-stu-id="5f665-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="5f665-203">Сетью Всусстатуссервер: IP-адрес сервера состояния службы обновления Windows Server.</span><span class="sxs-lookup"><span data-stu-id="5f665-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="5f665-204">Сетью EnableReferSupport: этот параметр определяет, включена ли поддержка SIP или отключена в конфигурации магистрали для IP/УАТС.</span><span class="sxs-lookup"><span data-stu-id="5f665-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="5f665-205">**Внутренние IP-адреса:**</span><span class="sxs-lookup"><span data-stu-id="5f665-205">**Internal IPs:**</span></span>

  - <span data-ttu-id="5f665-206">Убедитесь, что CorpnetIPPrefixLength маска подсети правильная.</span><span class="sxs-lookup"><span data-stu-id="5f665-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="5f665-207">Убедитесь в отсутствии конфликтов IP-адресов для этих внутренних IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="5f665-207">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="5f665-208">**Внешние IP-адреса:**</span><span class="sxs-lookup"><span data-stu-id="5f665-208">**External IPs:**</span></span>

  - <span data-ttu-id="5f665-209">Для общедоступного IP-адреса MR: укажите либо ExternalMRIPs для не-NAT, либо ExternalMRPublicIPs для NAT.</span><span class="sxs-lookup"><span data-stu-id="5f665-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="5f665-210">Екстерналсипипс и ExternalMRIPs могут быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="5f665-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="5f665-211">Убедитесь, что Интернетиппрефиксленгс маска подсети правильная.</span><span class="sxs-lookup"><span data-stu-id="5f665-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="5f665-212">Убедитесь в отсутствии конфликтов IP-адресов для этих внешних IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="5f665-212">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="5f665-213">**Шлюзы**</span><span class="sxs-lookup"><span data-stu-id="5f665-213">**Gateways:**</span></span>

  - <span data-ttu-id="5f665-214">Если у вас только один шлюз, удалите раздел для дополнительного шлюза.</span><span class="sxs-lookup"><span data-stu-id="5f665-214">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="5f665-215">Если у вас больше двух шлюзов, создайте дополнительные разделы, скопировав и вставив существующий, а затем обновив его.</span><span class="sxs-lookup"><span data-stu-id="5f665-215">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="5f665-216">Убедитесь, что IP-адрес и порт шлюза (-ов) указаны правильно.</span><span class="sxs-lookup"><span data-stu-id="5f665-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="5f665-217">Для поддержки высокой доступности шлюза PSTN оставьте дополнительный шлюз и добавьте любые дополнительные шлюзы, которые будут использоваться.</span><span class="sxs-lookup"><span data-stu-id="5f665-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="5f665-218">Вы можете скопировать и вставить существующую запись, а затем обновить ее.</span><span class="sxs-lookup"><span data-stu-id="5f665-218">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="5f665-219">При необходимости вы можете изменить значение LocalRoute, чтобы ограничить номера исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="5f665-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="5f665-220">Загрузка BITS в каталог сайтов</span><span class="sxs-lookup"><span data-stu-id="5f665-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="5f665-221">Выполните следующий командлет, чтобы скачать файлы сведений о битах и версии в **Каталог сайтов**:</span><span class="sxs-lookup"><span data-stu-id="5f665-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="5f665-222">Этот шаг необходимо выполнить только для первого устройства.</span><span class="sxs-lookup"><span data-stu-id="5f665-222">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="5f665-223">Подготовка базового виртуального диска (VHDX) из загруженного ISO-файла</span><span class="sxs-lookup"><span data-stu-id="5f665-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="5f665-224">На этом этапе подготавливается файл виртуального жесткого диска (VHDX) из ISO-образа Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="5f665-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="5f665-225">VHDX будет использоваться для создания виртуальных машин во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="5f665-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="5f665-226">Будет создана временная виртуальная машина (базовая ВИРТУАЛЬная машина), и Windows Server 2012 будет установлена из ISO-файла.</span><span class="sxs-lookup"><span data-stu-id="5f665-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="5f665-227">После создания виртуальной машины будут установлены некоторые необходимые компоненты, и будет применено Последнее обновление Windows.</span><span class="sxs-lookup"><span data-stu-id="5f665-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="5f665-228">В конце базовая виртуальная машина будет обобщена (Sysprep) и очищена, оставив только созданный файл виртуального диска.</span><span class="sxs-lookup"><span data-stu-id="5f665-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="5f665-229">Этот шаг необходимо выполнить только для первого устройства.</span><span class="sxs-lookup"><span data-stu-id="5f665-229">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="5f665-230">Перед выполнением этого действия Убедитесь, что переключатель в корпоративной сети создан.</span><span class="sxs-lookup"><span data-stu-id="5f665-230">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="5f665-231">Кроме того, убедитесь, что в файле CloudConnector. ini правильно настроены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="5f665-231">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="5f665-232">Сетью CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="5f665-232">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="5f665-233">Общую басевмип</span><span class="sxs-lookup"><span data-stu-id="5f665-233">[Common]BaseVMIP</span></span>

- <span data-ttu-id="5f665-234">Сетью CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="5f665-234">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="5f665-235">Сетью корпнетдефаултгатевай</span><span class="sxs-lookup"><span data-stu-id="5f665-235">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="5f665-236">Сетью CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="5f665-236">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="5f665-237">Запустите консоль PowerShell от имени администратора и выполните следующий командлет, чтобы преобразовать образ ISO в виртуальный жесткий диск (VHD):</span><span class="sxs-lookup"><span data-stu-id="5f665-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="5f665-238">Укажите полный путь, включая имя файла, к ISO-образу.</span><span class="sxs-lookup"><span data-stu-id="5f665-238">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="5f665-239">Пример: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="5f665-239">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="5f665-240">Созданный VHD-файл хранится в папке \Битс\вхд **каталога сайтов** .</span><span class="sxs-lookup"><span data-stu-id="5f665-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="5f665-241">Путь к **каталогу сайтов** можно получить с помощью команды **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="5f665-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f665-242">По умолчанию параметры прокси-сервера не настроены на основной виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="5f665-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="5f665-243">Если в сетевой среде требуется прокси-сервер для обновления виртуальной машины с помощью центра обновления Windows, необходимо добавить параметр-PauseBeforeUpdate при выполнении "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="5f665-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="5f665-244">Сценарий будет приостановлен до обновления Windows, и у вас будет возможность вручную настроить прокси-сервер на виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="5f665-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="5f665-245">После настройки прокси-сервера и того, что виртуальная машина может получить доступ к Интернету, можно возобновить сценарий, чтобы выполнить оставшиеся действия.</span><span class="sxs-lookup"><span data-stu-id="5f665-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="5f665-246">Создание виртуальных жестких дисков для развертывания с несколькими сайтами</span><span class="sxs-lookup"><span data-stu-id="5f665-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="5f665-247">Это необязательный шаг, который применяется только для развертываний с несколькими сайтами.</span><span class="sxs-lookup"><span data-stu-id="5f665-247">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="5f665-248">При развертывании развертывания с несколькими сайтами не требуется преобразовывать ISO-файл в VHD для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="5f665-248">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="5f665-249">Вы можете скопировать VHDX-файл, созданный для первого сайта, на сервер узла для второго сайта.</span><span class="sxs-lookup"><span data-stu-id="5f665-249">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="5f665-250">Скопируйте файл в то же расположение ( **Каталог сайтов** \битс\вхд) и с тем же именем на сервер узла для дополнительного сайта.</span><span class="sxs-lookup"><span data-stu-id="5f665-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="5f665-251">Установка RemoteSigned для политики выполнения PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f665-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="5f665-252">В сценариях PowerShell требуется, чтобы для политики выполнения было задано значение RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="5f665-252">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="5f665-253">Чтобы просмотреть текущую настройку, откройте консоль PowerShell от имени администратора, а затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5f665-253">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="5f665-254">Если для него не задано значение "RemoteSigned", выполните следующий командлет, чтобы изменить его:</span><span class="sxs-lookup"><span data-stu-id="5f665-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="5f665-255">Изменение локальной групповой политики на хост-компьютере (версии 1.4.1 и более ранних)</span><span class="sxs-lookup"><span data-stu-id="5f665-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="5f665-256">Эта задача не является обязательной для Cloud Connector Versions 1.4.2 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="5f665-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="5f665-257">Учетная запись CceService создается во время развертывания Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="5f665-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="5f665-258">Он запускает службу управления Cloud Connector и требует разрешения на удаление cloudconnector. msi.</span><span class="sxs-lookup"><span data-stu-id="5f665-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="5f665-259">Необходимо изменить параметр групповой политики на компьютере узла Cloud Connector, чтобы указать, что реестр пользователя не должен выгружаться при выходе пользователя из системы.</span><span class="sxs-lookup"><span data-stu-id="5f665-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="5f665-260">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5f665-260">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="5f665-261">Изменение параметра групповой политики</span><span class="sxs-lookup"><span data-stu-id="5f665-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="5f665-262">Откройте **редактор групповых политик** , выполнив gpedit. msc.</span><span class="sxs-lookup"><span data-stu-id="5f665-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="5f665-263">В **редакторе групповой политики**перейдите к разделу административные шаблоны > системе > UserProfile > не выгружать реестр пользователя при выходе пользователя из системы.</span><span class="sxs-lookup"><span data-stu-id="5f665-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="5f665-264">Присвойте его значению **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="5f665-264">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="5f665-265">Настройка организации Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="5f665-265">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="5f665-266">Необходима организация Microsoft 365 или Office 365 с Skype для бизнеса Online и телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="5f665-266">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="5f665-267">Перед попыткой использовать Cloud Connector убедитесь, что клиент настроен и настроен.</span><span class="sxs-lookup"><span data-stu-id="5f665-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="5f665-268">Некоторые действия по установке Microsoft 365 и Office 365 требуют использования удаленной оболочки клиента (TRPS) для настройки организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f665-268">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="5f665-269">**Этот параметр должен быть установлен на сервере узла.**</span><span class="sxs-lookup"><span data-stu-id="5f665-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="5f665-270">Вы можете скачать модуль Skype для бизнеса Online для PowerShell из: [Skype для бизнеса Online, модуль Windows PowerShell](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="5f665-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="5f665-271">Создайте выделенную учетную запись администратора Skype для бизнеса для управления Cloud Connector Online, например CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5f665-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="5f665-272">Эта учетная запись будет использоваться устройством для добавления или удаления устройства, включения или отключения автоматического обновления ОС, включения или отключения автоматического двоичного обновления.</span><span class="sxs-lookup"><span data-stu-id="5f665-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="5f665-273">Задайте для пароля для этой учетной записи срок действия не ограничен, чтобы не изменять его для службы каждый раз, когда она истечет.</span><span class="sxs-lookup"><span data-stu-id="5f665-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


