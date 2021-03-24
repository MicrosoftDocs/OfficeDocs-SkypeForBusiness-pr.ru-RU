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
description: Узнайте, как подготовить устройство cloud Connector к развертыванию и использованию с помощью телефонной системы (Cloud PBX).
ms.openlocfilehash: 536e9b98520e4274e00d43d57224267f5b824dc9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092637"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="fa35c-103">Подготовка устройства Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="fa35c-103">Prepare your Cloud Connector appliance</span></span>

> [!Important]
> <span data-ttu-id="fa35c-104">Cloud Connector Edition завершит карьеру 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="fa35c-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="fa35c-105">После обновления организации до Teams узнайте, как подключить сеть локальной телефонии к Teams с помощью прямой [маршрутизации.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="fa35c-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="fa35c-106">Узнайте, как подготовить устройство cloud Connector к развертыванию и использованию с помощью телефонной системы (Cloud PBX).</span><span class="sxs-lookup"><span data-stu-id="fa35c-106">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="fa35c-107">В этом разделе описывается, как получить файлы установки Skype для бизнеса Cloud Connector Edition, установить программное обеспечение Cloud Connector и подготовить устройство Cloud Connector для развертывания.</span><span class="sxs-lookup"><span data-stu-id="fa35c-107">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="fa35c-108">После завершения всех действий в этом разделе вы будете готовы развернуть cloud Connector для одного сайта или нескольких сайтов.</span><span class="sxs-lookup"><span data-stu-id="fa35c-108">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="fa35c-109">Если у вас есть существующее развертывание облачного соединиттеля и вы еще не обновлены до версии 2.1 cloud Connector, см. в примере Обновление до новой версии облачного [соединитетеля.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="fa35c-109">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fa35c-110">Корпорация Майкрософт поддерживает текущую версию Cloud Connector Edition версии 2.1.</span><span class="sxs-lookup"><span data-stu-id="fa35c-110">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="fa35c-111">Если вы настраивали автоматическое обновление, облачный соединителю будет обновляться автоматически.</span><span class="sxs-lookup"><span data-stu-id="fa35c-111">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="fa35c-112">Если вы настроили ручное обновление, вам потребуется обновить версию 2.1 в течение 60 дней после ее выпуска.</span><span class="sxs-lookup"><span data-stu-id="fa35c-112">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="fa35c-113">Корпорация Майкрософт будет поддерживать предыдущую версию в течение 60 дней после выпуска 2.1, чтобы у вас было время на обновление.</span><span class="sxs-lookup"><span data-stu-id="fa35c-113">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="fa35c-114">Для облачной соединители версии 2.1 и более поздней версии устройство-платформа .NET Framework 4.6.1 или более позднее.</span><span class="sxs-lookup"><span data-stu-id="fa35c-114">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="fa35c-115">Для успешного развертывания, при запуске cmdlets для настройки Skype для бизнеса Cloud Connector Edition, всегда используйте тот же сеанс консоли, что и тот, в который вы начали.</span><span class="sxs-lookup"><span data-stu-id="fa35c-115">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="fa35c-116">Избегайте переключения на различные сеансы во время развертывания и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa35c-116">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="fa35c-117">Существуют некоторые действия, выполняемые только для первого устройства в развертывании: создание доли для каталога сайта, скачивание битов и подготовка файла виртуального жесткого диска (VHDX) из образа ISO Windows Server.</span><span class="sxs-lookup"><span data-stu-id="fa35c-117">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="fa35c-118">Скачайте установщик skype для бизнеса cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="fa35c-118">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="fa35c-119">На сервере хост-сервера, где будут работать VMs облачного соединителя, скачайте файлы установки: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="fa35c-119">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="fa35c-120">Хост-сервер должен иметь доступ к Интернету во время установки облачного соединителя, так как во время установки загружаются дополнительные файлы.</span><span class="sxs-lookup"><span data-stu-id="fa35c-120">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="fa35c-121">Запустите установщик и примите значения по умолчанию во время установки.</span><span class="sxs-lookup"><span data-stu-id="fa35c-121">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="fa35c-122">Подтверждение успешного завершения установки.</span><span class="sxs-lookup"><span data-stu-id="fa35c-122">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="fa35c-123">Проверка установки и настройка среды</span><span class="sxs-lookup"><span data-stu-id="fa35c-123">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="fa35c-124">Откройте консоль PowerShell в качестве администратора и подтвердите, что cmdlets Skype для бизнеса Cloud Connector Edition доступны с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fa35c-124">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="fa35c-125">Команда должна вернуть список командлетов для Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="fa35c-125">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="fa35c-126">Файлы VHD, SfBBits и VersionInfo будут храниться в **Каталоге сайтов.**</span><span class="sxs-lookup"><span data-stu-id="fa35c-126">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="fa35c-127">Расположение каталога сайтов  можно найти с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fa35c-127">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="fa35c-128">Команда должна вернуть расположение в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="fa35c-128">The command should return a location in your file system.</span></span> <span data-ttu-id="fa35c-129">Расположение может быть локальной папкой или файлом.</span><span class="sxs-lookup"><span data-stu-id="fa35c-129">The location can be a local folder or a file share.</span></span> <span data-ttu-id="fa35c-130">Расположение каталога  сайтов по умолчанию: %USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="fa35c-130">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="fa35c-131">Расположение по умолчанию должно быть изменено на файл на первом устройстве, созданном на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="fa35c-131">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="fa35c-132">Выбранное расположение должно быть:</span><span class="sxs-lookup"><span data-stu-id="fa35c-132">The location you select must be:</span></span>

   - <span data-ttu-id="fa35c-133">Создан на первом устройстве, созданном на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="fa35c-133">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="fa35c-134">Общая папка, доступная другим хост-серверам (устройствам) на том же сайте.</span><span class="sxs-lookup"><span data-stu-id="fa35c-134">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="fa35c-135">Чтобы настроить **каталог сайтов к** расположению, помимо по умолчанию, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fa35c-135">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="fa35c-136">При развертывании высокой доступности (HA) для сайта убедитесь, что вы  запустите этот код, чтобы установить каталог сайтов в одном расположении на каждом сервере узла на сайте.</span><span class="sxs-lookup"><span data-stu-id="fa35c-136">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="fa35c-137">При входе и развертывании каждого устройства на сайте убедитесь, что текущая учетная запись с логотипом имеет правильный доступ к **каталогу сайтов.**</span><span class="sxs-lookup"><span data-stu-id="fa35c-137">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="fa35c-138">Каталог **приборов** — это локальный рабочий корневой каталог для skype for Business Cloud Connector Edition, а также расположение, в котором сохраняются внешние сертификаты, экземпляры и журналы.</span><span class="sxs-lookup"><span data-stu-id="fa35c-138">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="fa35c-139">Расположение по умолчанию: %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="fa35c-139">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="fa35c-140">Чтобы найти расположение каталога **приборов,** запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fa35c-140">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="fa35c-141">Чтобы настроить **Каталог приборов** для расположения, помимо по умолчанию, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fa35c-141">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="fa35c-142">Каталог приборов должен быть установлен в локальной папке на устройстве.</span><span class="sxs-lookup"><span data-stu-id="fa35c-142">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="fa35c-143">Перед запуском  развертывания skype for Business Cloud Connector Edition необходимо установить только каталог приборов.</span><span class="sxs-lookup"><span data-stu-id="fa35c-143">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="fa35c-144">Если вы измените его после развертывания, вам потребуется передиплоять хост-сервер.</span><span class="sxs-lookup"><span data-stu-id="fa35c-144">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fa35c-145">Путь к **Каталогу приборов не должен** содержать пробелов.</span><span class="sxs-lookup"><span data-stu-id="fa35c-145">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="fa35c-146">Настройка пути для внешнего сертификата Edge</span><span class="sxs-lookup"><span data-stu-id="fa35c-146">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="fa35c-147">Запустите следующий комдлет, чтобы задать путь, в том числе имя файла, внешнему сертификату Edge.</span><span class="sxs-lookup"><span data-stu-id="fa35c-147">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="fa35c-148">Например: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="fa35c-148">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="fa35c-149">Сертификат должен содержать закрытые ключи.</span><span class="sxs-lookup"><span data-stu-id="fa35c-149">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="fa35c-150">Обратите внимание, что параметр -Target является специфическим для версий 1.4.2 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="fa35c-150">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="fa35c-151">Укажите полный путь к внешнему сертификату, включая имя файла.</span><span class="sxs-lookup"><span data-stu-id="fa35c-151">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="fa35c-152">Сертификат может храниться локально или в файлообме.</span><span class="sxs-lookup"><span data-stu-id="fa35c-152">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="fa35c-153">Если сертификат хранится в общей папке, общая папка должна быть создана на первом устройстве каждого сайта и должна быть доступна другими устройствами, принадлежащими к одному сайту.</span><span class="sxs-lookup"><span data-stu-id="fa35c-153">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="fa35c-154">Этот cmdlet копирует внешний сертификат в **Каталог приборов**.</span><span class="sxs-lookup"><span data-stu-id="fa35c-154">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fa35c-155">Если вы обновили версию **Cloud Connector версии 1.4.2** или более поздней версии, убедитесь, что подготовленный внешний сертификат содержит закрытые ключи и всю цепочку сертификатов, включая корневой сертификат CA и промежуточные сертификаты CA.</span><span class="sxs-lookup"><span data-stu-id="fa35c-155">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="fa35c-156">Если вы еще не обновили версию Облачного соединитетеля **1.4.2,** убедитесь, что подготовленный внешний сертификат содержит закрытые ключи.</span><span class="sxs-lookup"><span data-stu-id="fa35c-156">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="fa35c-157">Этот внешний сертификат должен быть выдан органом сертификации, которому по умолчанию доверяет Windows.</span><span class="sxs-lookup"><span data-stu-id="fa35c-157">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="fa35c-158">Настройка пути для внешнего шлюза PSTN/SBC</span><span class="sxs-lookup"><span data-stu-id="fa35c-158">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="fa35c-159">Если вы используете TLS между сервером-посредником и шлюзом PSTN/SBC, запустите следующий cmdlet, чтобы задать путь, включая имя файла, к сертификату шлюза.</span><span class="sxs-lookup"><span data-stu-id="fa35c-159">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="fa35c-160">Например: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="fa35c-160">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="fa35c-161">Сертификат должен содержать корневой ЦС и промежуточную цепочку для сертификата, назначенного шлюзу:</span><span class="sxs-lookup"><span data-stu-id="fa35c-161">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="fa35c-162">Обратите внимание, что параметр -Target является специфическим для версий 1.4.2 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="fa35c-162">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="fa35c-163">Создание виртуальных коммутаторов в Hyper-V Manager</span><span class="sxs-lookup"><span data-stu-id="fa35c-163">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="fa35c-164">Откройте **Hyper-V диспетчер**  >  **виртуальных коммутаторов** и выберите **New Virtual Switch Manager**.</span><span class="sxs-lookup"><span data-stu-id="fa35c-164">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="fa35c-165">Создайте внешний виртуальный переключатель и привязывайте его к физическому сетевому адаптеру, подключенного к внутреннему сетевому домену:</span><span class="sxs-lookup"><span data-stu-id="fa35c-165">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="fa35c-166">Выберите **Разрешить операционной системе управления совместно использовать этот сетевой адаптер** для этого виртуального переключателя.</span><span class="sxs-lookup"><span data-stu-id="fa35c-166">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="fa35c-167">Создайте внешний виртуальный переключатель и привязывайте его к физическому сетевому адаптеру, который будет перенаходить в Интернет:</span><span class="sxs-lookup"><span data-stu-id="fa35c-167">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="fa35c-168">De-select Разрешить операционной системе управления **совместно использовать этот сетевой адаптер** для этого виртуального коммутатора.</span><span class="sxs-lookup"><span data-stu-id="fa35c-168">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="fa35c-169">Установите имя переключателя, соединяющего сеть периметра с внутренним сетевым доменом **SfB CCE Corpnet Switch.**</span><span class="sxs-lookup"><span data-stu-id="fa35c-169">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="fa35c-170">Установите имя переключателя, соединяющего сеть периметра с **интернет-переключателем SfB CCE.**</span><span class="sxs-lookup"><span data-stu-id="fa35c-170">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="fa35c-171">Обновление файла CloudConnector.ini конфигурации</span><span class="sxs-lookup"><span data-stu-id="fa35c-171">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="fa35c-172">Подготовка файла CloudConnector.ini с помощью сведений, [](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) собранных в разделе Определение параметров развертывания в разделе [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="fa35c-172">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="fa35c-173">Чтобы обновить файл, сначала запустите следующий cmdlet, чтобы получить образец шаблона (CloudConnector.Sample.ini):</span><span class="sxs-lookup"><span data-stu-id="fa35c-173">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="fa35c-174">Пример шаблона хранится в **Каталоге приборов.**</span><span class="sxs-lookup"><span data-stu-id="fa35c-174">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="fa35c-175">После обновления с помощью значений для среды сохраните файл CloudConnector.ini в **Каталоге приборов.**</span><span class="sxs-lookup"><span data-stu-id="fa35c-175">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="fa35c-176">Вы можете запустить **Get-CcApplianceDirectory,** чтобы определить путь к **каталогу приборов.**</span><span class="sxs-lookup"><span data-stu-id="fa35c-176">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="fa35c-177">При обновлении файла .ini рассмотрим следующее:</span><span class="sxs-lookup"><span data-stu-id="fa35c-177">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="fa35c-178">Не все значения для файла .ini рассматриваются в этом разделе, здесь рассматриваются только значения с особым вниманием.</span><span class="sxs-lookup"><span data-stu-id="fa35c-178">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="fa35c-179">Полный список см. в разделе [Определение](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) параметров развертывания в разделе [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="fa35c-179">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="fa35c-180">Дополнительные сведения о том, какие значения необходимо изменить для дополнительных устройств или новых сайтов, см. в разделе Единый сайт с высокой доступностью [(HA)](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) по сравнению с многоэтапными развертываниями в разделе [Развертывание](deploy-multiple-sites-in-cloud-connector.md)нескольких сайтов в облачном соединители.</span><span class="sxs-lookup"><span data-stu-id="fa35c-180">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="fa35c-181">**Имя сайта:** По умолчанию значение **Site1**.</span><span class="sxs-lookup"><span data-stu-id="fa35c-181">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="fa35c-182">Перед развертыванием облачного соединителя необходимо обновить его, так как при запуске **Register-CcAppliance** для регистрации устройства на существующем или новом сайте, для регистрации на сайте будет использовать **имя siteName.**</span><span class="sxs-lookup"><span data-stu-id="fa35c-182">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="fa35c-183">Если вы хотите зарегистрировать устройство на новом сайте, значение **SiteName** должно быть уникальным и отличается от существующих сайтов.</span><span class="sxs-lookup"><span data-stu-id="fa35c-183">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="fa35c-184">Если вы хотите зарегистрировать устройство на существующем сайте, значение **siteName** в файле .ini должно совпадать с именем, определенным в конфигурации организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="fa35c-184">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="fa35c-185">Если вы копируете файл конфигурации с одного сайта на другой, убедитесь, что вы соответственно обновляете значение **для siteName** для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="fa35c-185">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="fa35c-186">**ServerName:** Имя сервера не должно содержать доменное имя и должно быть ограничено 15 символами.</span><span class="sxs-lookup"><span data-stu-id="fa35c-186">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="fa35c-187">**HardwareType:** Если значение не установлено или не будет равно нуль, будет использоваться значение **Normal** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fa35c-187">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="fa35c-188">Используйте **Normal,** если вы планируете развернуть более крупную версию облачного соединитель для поддержки 500 одновременных вызовов на одну хост-машину, как описано в [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="fa35c-188">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="fa35c-189">Используйте **Minimum** для меньшего развертывания, которое поддерживает 50 одновременных вызовов.</span><span class="sxs-lookup"><span data-stu-id="fa35c-189">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="fa35c-190">**Виртуальные переключатели Internet/Corpnet/Management: :** Добавьте имя созданных виртуальных коммутаторов.</span><span class="sxs-lookup"><span data-stu-id="fa35c-190">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="fa35c-191">Для виртуального переключателя управления оставьте значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fa35c-191">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="fa35c-192">Сценарий развертывания создаст виртуальный переключатель управления в начале развертывания и удалит его по завершению развертывания.</span><span class="sxs-lookup"><span data-stu-id="fa35c-192">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="fa35c-193">**ManagementIPPrefix:** ManagementIPPrefix в разделе Network должен быть другой подсети от других внутренних IPs.</span><span class="sxs-lookup"><span data-stu-id="fa35c-193">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="fa35c-194">Например, как показывает значение по умолчанию, Значение ManagementIPPrefix — 192.168.213.0, а значение AD IPAddress — 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="fa35c-194">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="fa35c-195">Сценарии развертывания создают адаптер сети управления на каждой виртуальной машине, назначают IP-адрес управления и подключают его к виртуальному переключательу управления.</span><span class="sxs-lookup"><span data-stu-id="fa35c-195">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="fa35c-196">Это позволяет хост-серверу подключаться к каждой виртуальной машине и управлять ими с помощью этой сети управления.</span><span class="sxs-lookup"><span data-stu-id="fa35c-196">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="fa35c-197">Виртуальный переключатель управления удаляется по завершению развертывания.</span><span class="sxs-lookup"><span data-stu-id="fa35c-197">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="fa35c-198">**Базовые конфигурации VM:** Параметры в этом разделе необходимо настроить для **cmdlet Convert-CcIsoToVhdx.**</span><span class="sxs-lookup"><span data-stu-id="fa35c-198">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="fa35c-199">Во время подготовки базового VM-изображения базовый VM будет подключен к внутреннему сетевому переключательу.</span><span class="sxs-lookup"><span data-stu-id="fa35c-199">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="fa35c-200">Для доступа к Интернету для VM важны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fa35c-200">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="fa35c-201">[Общие] BaseVMIP: IP-адрес corpnet, который будет назначен базовому VM.</span><span class="sxs-lookup"><span data-stu-id="fa35c-201">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="fa35c-202">[Сеть] CorpnetDefaultGateway: шлюз по умолчанию, который будет назначен базовому VM.</span><span class="sxs-lookup"><span data-stu-id="fa35c-202">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="fa35c-203">[Сеть] CorpnetDNSIPAddress: IP-адрес DNS, который будет назначен базовому VM.</span><span class="sxs-lookup"><span data-stu-id="fa35c-203">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="fa35c-204">[Сеть] WSUSServer: IP-адрес службы обновления Windows Server.</span><span class="sxs-lookup"><span data-stu-id="fa35c-204">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="fa35c-205">[Сеть] WSUSStatusServer: IP-адрес сервера состояния службы обновления Windows Server.</span><span class="sxs-lookup"><span data-stu-id="fa35c-205">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="fa35c-206">[Сеть] EnableReferSupport: это определит, включена или отключена поддержка SIP REFER в конфигурации магистрали в IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="fa35c-206">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="fa35c-207">**Внутренние IPs:**</span><span class="sxs-lookup"><span data-stu-id="fa35c-207">**Internal IPs:**</span></span>

  - <span data-ttu-id="fa35c-208">Убедитесь, что маска подсети CorpnetIPPrefixLength является правильной.</span><span class="sxs-lookup"><span data-stu-id="fa35c-208">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="fa35c-209">Убедитесь, что для этих внутренних IP-ip-адресов нет конфликтов.</span><span class="sxs-lookup"><span data-stu-id="fa35c-209">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="fa35c-210">**Внешние IPs:**</span><span class="sxs-lookup"><span data-stu-id="fa35c-210">**External IPs:**</span></span>

  - <span data-ttu-id="fa35c-211">Для IP-адресов mr public: укажите внешниеMRI-адреса для non-NAT или ExternalMRPublicIPs для NAT.</span><span class="sxs-lookup"><span data-stu-id="fa35c-211">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="fa35c-212">ExternalSIPIPs и ExternalMRIPs могут быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="fa35c-212">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="fa35c-213">Убедитесь, что маска подсети InternetIPPrefixLength является правильной.</span><span class="sxs-lookup"><span data-stu-id="fa35c-213">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="fa35c-214">Убедитесь, что для этих внешних IP-ip-адресов нет конфликтов.</span><span class="sxs-lookup"><span data-stu-id="fa35c-214">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="fa35c-215">**Шлюзы:**</span><span class="sxs-lookup"><span data-stu-id="fa35c-215">**Gateways:**</span></span>

  - <span data-ttu-id="fa35c-216">Если у вас есть только один шлюз, удалите раздел для вторичного шлюза.</span><span class="sxs-lookup"><span data-stu-id="fa35c-216">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="fa35c-217">Если у вас больше двух шлюзов, создайте дополнительные разделы, скопируя и вклеив существующий, а затем обновив его.</span><span class="sxs-lookup"><span data-stu-id="fa35c-217">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="fa35c-218">Убедитесь, что IP-адрес и порт шлюза (ы) являются правильными.</span><span class="sxs-lookup"><span data-stu-id="fa35c-218">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="fa35c-219">Чтобы поддерживать уровень ha шлюза PSTN, оставьте вторичный шлюз и добавьте дополнительные шлюзы, которые вы будете использовать.</span><span class="sxs-lookup"><span data-stu-id="fa35c-219">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="fa35c-220">Можно скопировать и вклеить существующую запись, а затем обновить ее.</span><span class="sxs-lookup"><span data-stu-id="fa35c-220">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="fa35c-221">Дополнительно можно обновить значение LocalRoute, чтобы ограничить исходящие номера вызовов.</span><span class="sxs-lookup"><span data-stu-id="fa35c-221">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="fa35c-222">Скачайте биты в каталог сайта</span><span class="sxs-lookup"><span data-stu-id="fa35c-222">Download the bits to the Site Directory</span></span>

<span data-ttu-id="fa35c-223">Запустите следующий cmdlet, чтобы скачать биты и версии файлов информации в **Каталог сайта**:</span><span class="sxs-lookup"><span data-stu-id="fa35c-223">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="fa35c-224">Этот шаг необходимо выполнить только для первого устройства.</span><span class="sxs-lookup"><span data-stu-id="fa35c-224">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="fa35c-225">Подготовка базового виртуального диска (VHDX) из загруженного файла ISO</span><span class="sxs-lookup"><span data-stu-id="fa35c-225">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="fa35c-226">На этом этапе готовится виртуальный жесткий диск (VHDX) из образа ISO Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="fa35c-226">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="fa35c-227">VHDX будет использоваться для создания виртуальных машин во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="fa35c-227">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="fa35c-228">Будет создана временная виртуальная машина (базовый VM), а Windows Server 2012 будет установлена из файла ISO.</span><span class="sxs-lookup"><span data-stu-id="fa35c-228">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="fa35c-229">После создания VM будут установлены некоторые необходимые компоненты и применено последнее обновление Windows.</span><span class="sxs-lookup"><span data-stu-id="fa35c-229">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="fa35c-230">В конце базовый VM будет обобщен (sysprep) и очищен, оставив только созданный виртуальный дисковый файл.</span><span class="sxs-lookup"><span data-stu-id="fa35c-230">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="fa35c-231">Этот шаг необходимо выполнить только для первого устройства.</span><span class="sxs-lookup"><span data-stu-id="fa35c-231">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="fa35c-232">Прежде чем приступить к этому шагу, убедитесь, что коммутатор corpnet создан.</span><span class="sxs-lookup"><span data-stu-id="fa35c-232">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="fa35c-233">Кроме того, подтвердим, что в файле CloudConnector.ini правильно настроены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fa35c-233">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="fa35c-234">[Сеть] CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="fa35c-234">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="fa35c-235">[Общие] BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="fa35c-235">[Common]BaseVMIP</span></span>

- <span data-ttu-id="fa35c-236">[Сеть] CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="fa35c-236">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="fa35c-237">[Сеть] CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="fa35c-237">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="fa35c-238">[Сеть] CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="fa35c-238">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="fa35c-239">Запустите консоль PowerShell в качестве администратора и запустите следующий cmdlet, чтобы преобразовать изображение ISO в виртуальный жесткий диск (VHD):</span><span class="sxs-lookup"><span data-stu-id="fa35c-239">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="fa35c-240">Укажите полный путь, включая имя файла, на изображение ISO.</span><span class="sxs-lookup"><span data-stu-id="fa35c-240">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="fa35c-241">Например: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="fa35c-241">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="fa35c-242">Созданный VHD-файл хранится в папке **Site Directory** \Bits\VHD.</span><span class="sxs-lookup"><span data-stu-id="fa35c-242">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="fa35c-243">Путь к каталогу  сайтов можно получить с помощью **Get-CcSiteDirectory.**</span><span class="sxs-lookup"><span data-stu-id="fa35c-243">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa35c-244">По умолчанию параметры прокси не настроены на базовом VM.</span><span class="sxs-lookup"><span data-stu-id="fa35c-244">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="fa35c-245">Если прокси-сервер требуется в сетевой среде для обновления VM с помощью Обновления Windows, необходимо добавить переключатель PauseBeforeUpdate при запуске "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="fa35c-245">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="fa35c-246">Перед обновлением Windows скрипт приостанавливется, и у вас будет возможность вручную настроить прокси-сервер в VM.</span><span class="sxs-lookup"><span data-stu-id="fa35c-246">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="fa35c-247">После установки прокси-сервера и доступа к Интернету vM можно возобновить сценарий для выполнения оставшихся действий.</span><span class="sxs-lookup"><span data-stu-id="fa35c-247">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="fa35c-248">Создание VHD для развертывания на нескольких узлах</span><span class="sxs-lookup"><span data-stu-id="fa35c-248">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="fa35c-249">Это необязательный шаг, который применяется только к развертыванию на нескольких узлах.</span><span class="sxs-lookup"><span data-stu-id="fa35c-249">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="fa35c-250">При развертывании развертывания на нескольких веб-узлах не требуется преобразовать ISO в VHD для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="fa35c-250">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="fa35c-251">Вы можете скопировать VHDX, созданный для первого сайта, на сервер узла для второго сайта.</span><span class="sxs-lookup"><span data-stu-id="fa35c-251">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="fa35c-252">Скопируйте файл в том же расположении файла **(папка Site Directory** \Bits\VHD) и с тем же именем файла на сервере узла для дополнительного сайта.</span><span class="sxs-lookup"><span data-stu-id="fa35c-252">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="fa35c-253">Установите политику выполнения PowerShell в RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="fa35c-253">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="fa35c-254">Предоставленные скрипты PowerShell требуют, чтобы политика выполнения была настроена на RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="fa35c-254">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="fa35c-255">Чтобы увидеть текущий параметр, откройте консоль PowerShell в качестве администратора и запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fa35c-255">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="fa35c-256">Если не установлено "RemoteSigned", запустите следующий cmdlet, чтобы изменить его:</span><span class="sxs-lookup"><span data-stu-id="fa35c-256">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="fa35c-257">Изменение локальной групповой политики на хост-машине (версии 1.4.1 и ранее)</span><span class="sxs-lookup"><span data-stu-id="fa35c-257">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="fa35c-258">Эта задача не требуется для версий Cloud Connector 1.4.2 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="fa35c-258">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="fa35c-259">Учетная запись CceService создается во время развертывания skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="fa35c-259">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="fa35c-260">Она запускает службу управления облачными соединителями и требует разрешения на cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="fa35c-260">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="fa35c-261">Необходимо изменить параметр групповой политики на хост-машине облачного соединитела, чтобы указать, что реестр пользователей не должен быть выгружен при отключении входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="fa35c-261">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="fa35c-262">Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fa35c-262">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="fa35c-263">Изменение параметра групповой политики</span><span class="sxs-lookup"><span data-stu-id="fa35c-263">To change the Group Policy setting</span></span>

1. <span data-ttu-id="fa35c-264">Откройте редактор **групповой политики,** задав gpedit.msc.</span><span class="sxs-lookup"><span data-stu-id="fa35c-264">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="fa35c-265">В **редакторе** групповой политики перейдите к административным шаблонам > System > UserProfile > Не принудительно разгрузите реестр пользователей при входе пользователя.</span><span class="sxs-lookup"><span data-stu-id="fa35c-265">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="fa35c-266">Установите значение **Включено**.</span><span class="sxs-lookup"><span data-stu-id="fa35c-266">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="fa35c-267">Настройка организации Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="fa35c-267">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="fa35c-268">Требуется организация Microsoft 365 или Office 365 с skype для бизнеса Online и телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="fa35c-268">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="fa35c-269">Убедитесь, что клиент настроен и настроен перед попыткой использования облачного соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="fa35c-269">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="fa35c-270">Некоторые действия по настройке Microsoft 365 и Office 365 требуют использования удаленной системы powerShell (TRPS) для настройки организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="fa35c-270">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="fa35c-271">**Это должно быть установлено на сервере хост-сервера.**</span><span class="sxs-lookup"><span data-stu-id="fa35c-271">**This should be installed on the host server.**</span></span> <span data-ttu-id="fa35c-272">Вы можете скачать модуль Skype для бизнеса Online для PowerShell из: Skype для бизнеса [Online, Windows PowerShell модуль](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="fa35c-272">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="fa35c-273">Создайте специальную учетную запись администратора Skype для бизнеса для управления облачным подключением, например CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fa35c-273">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="fa35c-274">Эта учетная запись будет использоваться устройством для добавления или удаления устройства, включить или отключить автоматическое обновление ОС, включить или отключить автоматическое двоичное обновление.</span><span class="sxs-lookup"><span data-stu-id="fa35c-274">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="fa35c-275">Установите пароль для этой учетной записи, чтобы никогда не истекал срок действия, чтобы не нужно менять его для службы каждый раз, когда он истекает.</span><span class="sxs-lookup"><span data-stu-id="fa35c-275">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>