---
title: Подготовка устройства Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Узнайте о сведения о подготовке устройства облачных соединитель для развертывания и использования с телефонной системой в Office 365 (облако УАТС).
ms.openlocfilehash: 3716c7c4b9d4b8daa0a4995ed7e3d77b400b587f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240884"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="38b2b-103">Подготовка устройства Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="38b2b-103">Prepare your Cloud Connector appliance</span></span>

<span data-ttu-id="38b2b-104">Узнайте о сведения о подготовке устройства облачных соединитель для развертывания и использования с телефонной системой в Office 365 (облако УАТС).</span><span class="sxs-lookup"><span data-stu-id="38b2b-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>

<span data-ttu-id="38b2b-105">В этом разделе описывается, как получить файлы установки Skype для бизнеса Cloud Connector Edition, установить программное обеспечение Cloud Connector и подготовить устройство Cloud Connector к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="38b2b-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="38b2b-106">После выполнения всех шагов, которые приводятся в этом разделе, вы будете готовы к развертыванию Cloud Connector для одного или нескольких сайтов.</span><span class="sxs-lookup"><span data-stu-id="38b2b-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="38b2b-107">Если у вас есть существующее развертывание соединителя облачных и вы еще не был обновлен для соединителя облачных версии 2.1, видеть [обновление до новой версии облачных соединителя](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="38b2b-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="38b2b-108">Майкрософт поддерживает текущую версию Edition соединителя облаке, версии 2.1.</span><span class="sxs-lookup"><span data-stu-id="38b2b-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="38b2b-109">Если у вас настроено автоматическое обновление, Cloud Connector обновится автоматически.</span><span class="sxs-lookup"><span data-stu-id="38b2b-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="38b2b-110">Если вы настроили по запросу, необходимо обновить до версии 2.1 в течение 60 дней после его выпуска.</span><span class="sxs-lookup"><span data-stu-id="38b2b-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="38b2b-111">Корпорация Майкрософт будет поддержка предыдущей версии 60 дней после выпуска 2.1, чтобы разрешить время обновления.</span><span class="sxs-lookup"><span data-stu-id="38b2b-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="38b2b-112">Для соединителя облачных версии 2.1 и более поздних версий appliance узла необходимо наличие .NET Framework 4.6.1 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="38b2b-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="38b2b-113">Для успешного развертывания при выполнении командлетов для настройки Скайп облаке соединитель для выпуска для бизнеса, всегда используйте одного сеанса консоли, которая запущена в.</span><span class="sxs-lookup"><span data-stu-id="38b2b-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="38b2b-114">Не рекомендуется переключаться на другие сеансы в процессе развертывания и настройки.</span><span class="sxs-lookup"><span data-stu-id="38b2b-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="38b2b-115">Некоторые шаги выполняются только для первого устройства в развертывании: создание общего каталога сайта, загрузка необходимых компонентов и подготовка файла виртуального жесткого диска (VHDX) на основе ISO-образа Windows Server.</span><span class="sxs-lookup"><span data-stu-id="38b2b-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="38b2b-116">Загрузка установщика Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="38b2b-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="38b2b-117">На сервере размещения, которой будет запускаться виртуальных машин соединителя облаке, загрузите файлы установки: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="38b2b-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="38b2b-118">Во время установки Cloud Connector сервер узла должен иметь доступ к Интернету, так как ему потребуется скачивать дополнительные файлы.</span><span class="sxs-lookup"><span data-stu-id="38b2b-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="38b2b-119">Запустите установщик и примите значения по умолчанию во время установки.</span><span class="sxs-lookup"><span data-stu-id="38b2b-119">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="38b2b-120">Убедитесь, что установка завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="38b2b-120">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="38b2b-121">Проверка установки и настройка среды</span><span class="sxs-lookup"><span data-stu-id="38b2b-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="38b2b-122">Откройте консоль PowerShell от имени администратора и убедитесь, что Скайп по командлетам соединителя Cloud Business Edition доступны с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="38b2b-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```
   Get-Command *-Cc*
   ```

    <span data-ttu-id="38b2b-123">Команда должна вернуть список командлетов для Скайп облаке соединитель для выпуска для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="38b2b-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="38b2b-124">Файлы VHD, SfBBits и VersionInfo будут храниться в **каталоге сайтов**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="38b2b-125">Чтобы узнать расположение **каталога веб-сайтов**, запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="38b2b-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="38b2b-126">Команда должна вернуть расположение в вашей файловой системе.</span><span class="sxs-lookup"><span data-stu-id="38b2b-126">The command should return a location in your file system.</span></span> <span data-ttu-id="38b2b-127">Это может быть локальная или общая папка.</span><span class="sxs-lookup"><span data-stu-id="38b2b-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="38b2b-128">Расположение **каталога веб-сайтов** по умолчанию: %USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="38b2b-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="38b2b-129">На первом устройстве, созданном на каждом сайте, в качестве расположения по умолчанию следует указать общую папку.</span><span class="sxs-lookup"><span data-stu-id="38b2b-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="38b2b-130">Необходимо выбрать следующее местоположение:</span><span class="sxs-lookup"><span data-stu-id="38b2b-130">The location you select must be:</span></span>

   - <span data-ttu-id="38b2b-131">Создается на первом устройстве, создаваемом для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="38b2b-131">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="38b2b-132">Общая папка, доступная другим серверам узла (устройства) в рамках того же сайта.</span><span class="sxs-lookup"><span data-stu-id="38b2b-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="38b2b-133">Чтобы выбрать для **каталога сайтов** расположение, отличное от заданного по умолчанию, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="38b2b-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="38b2b-134">При развертывании высокой доступности для сайта убедитесь, что командлет задает одинаковое расположение **каталога сайтов** на каждом сервере узла сайта.</span><span class="sxs-lookup"><span data-stu-id="38b2b-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="38b2b-135">После входа в систему и развертывание каждого устройства на сайте, убедитесь в том, что текущая учетная запись пользователя для доступа к **Каталога сайтов**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="38b2b-136">**Устройство для каталогов** является корневым каталогом локального рабочее для Скайп для соединителя Cloud Business Edition и расположение для сохранения внешнего сертификатов, экземпляры и журналы.</span><span class="sxs-lookup"><span data-stu-id="38b2b-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="38b2b-137">Расположение по умолчанию: %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="38b2b-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="38b2b-138">Чтобы узнать расположение **каталога устройств**, запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="38b2b-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="38b2b-139">Чтобы выбрать для **каталога устройств** расположение, отличное от заданного по умолчанию, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="38b2b-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="38b2b-140">В качестве каталога устройства необходимо задать локальную папку на устройстве.</span><span class="sxs-lookup"><span data-stu-id="38b2b-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="38b2b-141">**Устройство для каталога** следует устанавливать только в том случае, прежде чем начать Скайп для развертывания соединителя Cloud Business Edition.</span><span class="sxs-lookup"><span data-stu-id="38b2b-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="38b2b-142">Если изменить его после развертывания, потребуется выполнить развертывание сервера узла снова.</span><span class="sxs-lookup"><span data-stu-id="38b2b-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="38b2b-143">Путь к **каталогу устройств** не должен содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="38b2b-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="38b2b-144">Задайте путь к внешнему сертификату пограничного компонента</span><span class="sxs-lookup"><span data-stu-id="38b2b-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="38b2b-p107">Выполните следующий командлет, чтобы задать путь с именем файла к внешнему сертификату пограничного компонента. Пример: C:\certs\cce\ap.contoso.com.pfx. Сертификат должен содержать закрытые ключи.</span><span class="sxs-lookup"><span data-stu-id="38b2b-p107">Run the following cmdlet to set the path, including the file name, to the external Edge certificate. For example: C:\certs\cce\ap.contoso.com.pfx. The certificate must contain private keys.</span></span>

  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="38b2b-148">Обратите внимание, что параметр -Target относится к версии 1.4.2 и более поздним версиям.</span><span class="sxs-lookup"><span data-stu-id="38b2b-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="38b2b-149">Укажите полный путь к внешнему сертификату, включая имя файла.</span><span class="sxs-lookup"><span data-stu-id="38b2b-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="38b2b-150">Сертификат может храниться как локально, так и в общей папке.</span><span class="sxs-lookup"><span data-stu-id="38b2b-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="38b2b-151">Если сертификат хранится в общей папке, она должна создаваться на первом устройстве для каждого сайта и должна быть доступна другим устройствам, принадлежащим тому же сайту.</span><span class="sxs-lookup"><span data-stu-id="38b2b-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="38b2b-152">Этот командлет копирует внешний сертификат в **каталог устройства**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="38b2b-153">**Если вы обновили Cloud Connector до версии 1.4.2 или более поздней версии**, убедитесь, что подготовленный внешний сертификат содержит закрытые ключи и полную цепочку сертификатов, включая корневые и промежуточные сертификаты ЦС.</span><span class="sxs-lookup"><span data-stu-id="38b2b-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="38b2b-154">**Если вы еще НЕ выполнили обновление Cloud Connector до версии 1.4.2**, убедитесь, что подготовленный внешний сертификат содержит закрытые ключи.</span><span class="sxs-lookup"><span data-stu-id="38b2b-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="38b2b-155">Такой внешний сертификат должен быть выдан центром сертификации, который по умолчанию является доверенным в Windows.</span><span class="sxs-lookup"><span data-stu-id="38b2b-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="38b2b-156">Задайте путь к внешнему сертификату шлюза ТСОП/SBC</span><span class="sxs-lookup"><span data-stu-id="38b2b-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="38b2b-157">Если между сервером-посредником и шлюзом ТСОП/SBC используется протокол TLS, выполните следующий командлет, чтобы задать путь с именем файла к сертификату шлюза.</span><span class="sxs-lookup"><span data-stu-id="38b2b-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="38b2b-158">Например: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="38b2b-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="38b2b-159">Этот сертификат должен содержать корневой ЦС и промежуточную цепочку для сертификата, назначенного шлюзу:</span><span class="sxs-lookup"><span data-stu-id="38b2b-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="38b2b-160">Обратите внимание, что параметр -Target относится к версии 1.4.2 и более поздним версиям.</span><span class="sxs-lookup"><span data-stu-id="38b2b-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="38b2b-161">Создание виртуальных коммутаторов в диспетчере Hyper-V</span><span class="sxs-lookup"><span data-stu-id="38b2b-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="38b2b-162">Откройте **Диспетчер Hyper-V** > **виртуального коммутатора**и выберите **Новый диспетчер виртуальной переключатель**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="38b2b-163">Создайте внешний виртуальный коммутатор и привяжите его к физическому сетевому адаптеру, который подключен к домену внутренней сети:</span><span class="sxs-lookup"><span data-stu-id="38b2b-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="38b2b-164">Установите для этого виртуального коммутатора флажок **Разрешить операционной системе управления общий доступ к этому сетевому адаптеру**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="38b2b-165">Создайте внешний виртуального коммутатора и привязка к физической сетевой адаптер, направляемые в Интернет:</span><span class="sxs-lookup"><span data-stu-id="38b2b-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="38b2b-166">Снимите флажок **Разрешить общий доступ к данному сетевому адаптеру управляющей операционной системе** для этого виртуального коммутатора.</span><span class="sxs-lookup"><span data-stu-id="38b2b-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="38b2b-167">Задайте имя коммутатора, который подключается сети периметра к внутренней сети домена **SfB системы CCE Corpnet переключиться**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="38b2b-168">Задайте имя коммутатора, подключающегося к Интернет, **SfB системы CCE Internet переключиться**сети периметра.</span><span class="sxs-lookup"><span data-stu-id="38b2b-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="38b2b-169">Изменение файла конфигурации CloudConnector.ini</span><span class="sxs-lookup"><span data-stu-id="38b2b-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="38b2b-170">Подготовка файла CloudConnector.ini, с помощью сведения, собранные в [Определение параметров развертывания](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) в разделе [Планирование Скайп облаке соединитель для выпуска для бизнеса](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="38b2b-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="38b2b-171">Чтобы изменить файл, сначала выполните следующий командлет, чтобы получить пример шаблона (CloudConnector.Sample.ini):</span><span class="sxs-lookup"><span data-stu-id="38b2b-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```
Export-CcConfigurationSampleFile
```

<span data-ttu-id="38b2b-172">Пример шаблона хранится в **каталоге устройств**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-172">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="38b2b-173">Изменив файл с помощью значений для своей среды, сохраните его как CloudConnector.ini в **каталоге устройств**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-173">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="38b2b-174">Чтобы определить путь к **каталогу устройств**, можно выполнить командлет **Get-CcApplianceDirectory**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-174">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="38b2b-175">При внесении изменений в INI-файл учтите следующие аспекты.</span><span class="sxs-lookup"><span data-stu-id="38b2b-175">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="38b2b-176">В этом разделе рассматриваются не все значения для файла INI, только ее с особое внимание можно найти здесь.</span><span class="sxs-lookup"><span data-stu-id="38b2b-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="38b2b-177">Полный список обратитесь к разделу [Определение параметров развертывания](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) в разделе [Планирование Скайп облаке соединитель для выпуска для бизнеса](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="38b2b-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="38b2b-178">Дополнительные сведения о том, какие значения необходимо изменить для добавления дополнительных устройств или сайтов, см. в разделе[Сравнение развертывания отдельного сайта с высокой доступностью и развертывания с несколькими сайтами](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) статьи[Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="38b2b-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="38b2b-p113">**SiteName**. По умолчанию имеет значение **Site1**. Это значение необходимо обновить до начала развертывания Cloud Connector, поскольку при выполнении командлета **Register-CcAppliance** для регистрации устройства на существующем или новом сайте значение **SiteName** будет использоваться командлетом для определения сайта, который требуется зарегистрировать.</span><span class="sxs-lookup"><span data-stu-id="38b2b-p113">**SiteName:** The default value is **Site1**. You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="38b2b-181">Если вы хотите зарегистрировать устройство на новом сайте, значение **SiteName** должно быть уникальным и отличаться от существующих сайтов.</span><span class="sxs-lookup"><span data-stu-id="38b2b-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="38b2b-182">Если необходимо зарегистрировать appliance к существующему сайту, значение для **SiteName** в INI-файле должно совпадать с именем, определенных в конфигурации клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="38b2b-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="38b2b-183">Если вы копируете файл конфигурации с одного сайта на другой, для каждого сайта необходимо соответствующим образом обновить значение **SiteName**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="38b2b-184">**ServerName**. Имя сервера не должно содержать имя домена и должно иметь длину не более 15 символов. </span><span class="sxs-lookup"><span data-stu-id="38b2b-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="38b2b-185">**HardwareType:** Если не заданы или оставьте значение null, будет использоваться значение по умолчанию **Normal** .</span><span class="sxs-lookup"><span data-stu-id="38b2b-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="38b2b-186">Используйте **Обычный** , если вы планируете развернуть большей версии облачных соединитель для поддержки 500 одновременных звонков на главном компьютере, как описано в статье [Plan для Скайп облаке соединитель для выпуска для бизнеса](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="38b2b-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="38b2b-187">Для меньших развертываний, в которых поддерживается до 50 параллельных звонков, следует использовать значение **Минимум**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="38b2b-188">**Виртуальных коммутаторов управление/корпоративной сети и через Интернет:**: Добавление имени виртуальных коммутаторов были созданы.</span><span class="sxs-lookup"><span data-stu-id="38b2b-188">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="38b2b-189">Для виртуального коммутатора управления оставьте значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38b2b-189">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="38b2b-190">Сценарий развертывания будет создание виртуального коммутатора управления в начале развертывания и удалите его после завершения развертывания.</span><span class="sxs-lookup"><span data-stu-id="38b2b-190">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="38b2b-p117">**ManagementIPPrefix**. Префикс ManagementIPPrefix в разделе Network (Сеть) должен принадлежать к подсети, к которой не принадлежат другие внутренние IP-адреса. Например, как указано в значении по умолчанию, значение параметра ManagementIPPrefix — 192.168.213.0, а AD IPAddress — 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="38b2b-p117">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs. For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="38b2b-p118">Сценарии развертывания создают сетевой адаптер управления на каждой виртуальной машине, назначают ему IP-адрес управления и подключают его к виртуальному коммутатору управления. Это позволяет серверу узла подключаться к виртуальным машинам и управлять ими с помощью этой сети управления. Виртуальный коммутатор управления удаляется после завершения развертывания.</span><span class="sxs-lookup"><span data-stu-id="38b2b-p118">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch. This enables the host server to connect to and manage each virtual machine via this management network. The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="38b2b-196">**Специальные конфигурации** для базовой виртуальной машины. В этом разделе настраиваются **Convert-CcIsoToVhdx** параметры для командлета .</span><span class="sxs-lookup"><span data-stu-id="38b2b-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="38b2b-p119">При подготовке образа базовой виртуальной машины эта машина будет подключена к коммутатору внутренней сети. Следующие ключевые параметры необходимы для обеспечения доступа виртуальной машины к Интернету:</span><span class="sxs-lookup"><span data-stu-id="38b2b-p119">During base VM image preparation, the base VM will be connected to the internal network switch. The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="38b2b-199">[Common]BaseVMIP — IP-адрес корпоративной сети, назначаемый базовой виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="38b2b-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="38b2b-200">[Network]CorpnetDefaultGateway — шлюз по умолчанию, назначаемый базовой виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="38b2b-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="38b2b-201">[Network]CorpnetDNSIPAddress — IP-адрес DNS, назначаемый базовой виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="38b2b-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="38b2b-202">[Network]WSUSServer — IP-адрес службы Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="38b2b-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="38b2b-203">[Network]WSUSStatusServer — IP-адрес сервера состояния WSUS.</span><span class="sxs-lookup"><span data-stu-id="38b2b-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="38b2b-204">[Network]EnableReferSupport — параметр, определяющий, включена ли поддержка SIP REFER в конфигурации магистрали для IP/УАТС.</span><span class="sxs-lookup"><span data-stu-id="38b2b-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="38b2b-205">**Внутренние IP-адреса**</span><span class="sxs-lookup"><span data-stu-id="38b2b-205">**Internal IPs:**</span></span>

  - <span data-ttu-id="38b2b-206">Убедитесь в том, что маска подсети CorpnetIPPrefixLength является правильным.</span><span class="sxs-lookup"><span data-stu-id="38b2b-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="38b2b-207">Убедитесь, что нет конфликтов IP-адресов для этих внутреннего IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="38b2b-207">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="38b2b-208">**Внешние IP-адреса**</span><span class="sxs-lookup"><span data-stu-id="38b2b-208">**External IPs:**</span></span>

  - <span data-ttu-id="38b2b-209">Для MR общедоступный IP-адрес: указать либо ExternalMRIPs не преобразования сетевых адресов или ExternalMRPublicIPs для преобразование сетевых адресов.</span><span class="sxs-lookup"><span data-stu-id="38b2b-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="38b2b-210">ExternalSIPIPs и ExternalMRIPs могут быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="38b2b-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="38b2b-211">Убедитесь в том, что маска подсети InternetIPPrefixLength является правильным.</span><span class="sxs-lookup"><span data-stu-id="38b2b-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="38b2b-212">Убедитесь, что нет конфликтов IP-адресов для этих внешних IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="38b2b-212">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="38b2b-213">**Шлюзы**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-213">**Gateways:**</span></span>

  - <span data-ttu-id="38b2b-p120">Если у вас только один шлюз, удалите раздел для второго шлюза. Если вы используете несколько шлюзов, для создания дополнительных разделов скопируйте существующий раздел и измените данные в нем соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="38b2b-p120">If you have only one gateway, remove the section for the secondary gateway. If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="38b2b-216">Убедитесь, что IP-адрес и порт шлюза(-ов) указаны правильно.</span><span class="sxs-lookup"><span data-stu-id="38b2b-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="38b2b-217">Чтобы обеспечить поддержку высокой доступности на уровне шлюза ТСОП, оставьте второй шлюз и добавьте необходимые для работы дополнительные шлюзы.</span><span class="sxs-lookup"><span data-stu-id="38b2b-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="38b2b-218">Можно скопировать и вставить существующей записи и затем обновите его.</span><span class="sxs-lookup"><span data-stu-id="38b2b-218">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="38b2b-219">Кроме того можно обновить значение LocalRoute для ограничения номеров исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="38b2b-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="38b2b-220">Загрузка BITS-файлов в каталог сайтов</span><span class="sxs-lookup"><span data-stu-id="38b2b-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="38b2b-221">Выполните следующий командлет, чтобы скачать файлы компонентов и сведений о версии в **каталог сайта**:</span><span class="sxs-lookup"><span data-stu-id="38b2b-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="38b2b-222">Этот шаг необходимо выполнять только для первого устройства.</span><span class="sxs-lookup"><span data-stu-id="38b2b-222">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="38b2b-223">Подготовьте базовый виртуальный диск (VHDX) на основе скачанного ISO-файла</span><span class="sxs-lookup"><span data-stu-id="38b2b-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="38b2b-224">В рамках этой процедуры мы подготовим файл виртуального жесткого диска (VHDX) на основе ISO-образа Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="38b2b-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="38b2b-225">VHDX-файл будет использоваться для создания виртуальных машин во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="38b2b-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="38b2b-226">Будет создан временный виртуальной машины (базовый виртуальной Машины) и Windows Server 2012 будет установлено ISO-файл.</span><span class="sxs-lookup"><span data-stu-id="38b2b-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="38b2b-227">После создания виртуальной машины потребуется установить некоторые обязательные компоненты и применить последние обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="38b2b-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="38b2b-228">И наконец, мы выполним подготовку базовой виртуальной машины к использованию (sysprep) и очистим ее, оставив только созданный файл виртуального диска.</span><span class="sxs-lookup"><span data-stu-id="38b2b-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="38b2b-229">Этот шаг необходимо выполнять только для первого устройства.</span><span class="sxs-lookup"><span data-stu-id="38b2b-229">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="38b2b-p123">Прежде чем переходить к этой процедуре, убедитесь, что создан коммутатор корпоративной сети. Кроме того, проверьте правильность настройки следующих параметров в файле CloudConnector.ini:</span><span class="sxs-lookup"><span data-stu-id="38b2b-p123">Before proceeding with this step, make sure that the corpnet switch is created. Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="38b2b-232">[Network]CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="38b2b-232">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="38b2b-233">[Common]BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="38b2b-233">[Common]BaseVMIP</span></span>

- <span data-ttu-id="38b2b-234">[Network]CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="38b2b-234">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="38b2b-235">[Network]CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="38b2b-235">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="38b2b-236">[Network]CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="38b2b-236">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="38b2b-237">Запустите консоль PowerShell от имени администратора и выполните следующий командлет, чтобы преобразовать ISO-образ в виртуальный жесткий диск (VHD):</span><span class="sxs-lookup"><span data-stu-id="38b2b-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="38b2b-p124">Укажите полный путь, включая имя файла, к ISO-образу. Например: C:\ISO\WindowsServer2012.iso.</span><span class="sxs-lookup"><span data-stu-id="38b2b-p124">Specify the full path, including file name, to the ISO image. For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="38b2b-240">Созданный файл виртуального жесткого диска хранится в папке \Bits\VHD **Каталога сайтов** .</span><span class="sxs-lookup"><span data-stu-id="38b2b-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="38b2b-241">Путь к **каталогу сайтов** можно получить, выполнив командлет **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38b2b-242">По умолчанию параметры прокси-сервера не настроены для базовой виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="38b2b-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="38b2b-243">При необходимости использования прокси-сервера для обновления виртуальной Машины с помощью центра обновления Windows в сетевой среде следует добавить параметр - PauseBeforeUpdate при запуске «Convert-CcIsoToVhdx».</span><span class="sxs-lookup"><span data-stu-id="38b2b-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="38b2b-244">Скрипт будет приостановлено до обновления Windows и иметь возможность вручную настроить прокси-сервер, на виртуальной Машине.</span><span class="sxs-lookup"><span data-stu-id="38b2b-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="38b2b-245">После указания прокси-сервера (что позволит виртуальной машине получать доступ к Интернету) можно возобновить сценарий для выполнения оставшихся действий.</span><span class="sxs-lookup"><span data-stu-id="38b2b-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="38b2b-246">Создание VHD-файлов для развертывания с несколькими сайтами</span><span class="sxs-lookup"><span data-stu-id="38b2b-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="38b2b-247">Это дополнительная процедура, применимая только к многосайтовым развертываниям.</span><span class="sxs-lookup"><span data-stu-id="38b2b-247">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="38b2b-p127">В развертывании такого типа нет необходимости преобразовать ISO в VHD для каждого сайта. Можно скопировать VHDX-файл, созданный для первого сайта, на узел сервера для второго сайта.</span><span class="sxs-lookup"><span data-stu-id="38b2b-p127">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site. You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="38b2b-250">Скопируйте файл в ту же папку файл (папка \Bits\VHD **Каталога веб-сайтов** ) и с тем же именем, на хост-сервера для дополнительных сайта.</span><span class="sxs-lookup"><span data-stu-id="38b2b-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="38b2b-251">Задание значения RemoteSigned для политики выполнения PowerShell</span><span class="sxs-lookup"><span data-stu-id="38b2b-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="38b2b-p128">Указанные здесь сценарии PowerShell требуют, чтобы для политики выполнения было задано значение RemoteSigned. Чтобы узнать текущую настройку, откройте консоль PowerShell от имени администратора, а затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="38b2b-p128">The PowerShell scripts provided require that the execution policy be set to RemoteSigned. To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```
Get-ExecutionPolicy
```

<span data-ttu-id="38b2b-254">Если значение RemoteSigned не задано, выполните этот командлет, чтобы изменить его:</span><span class="sxs-lookup"><span data-stu-id="38b2b-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="38b2b-255">Изменение локальной групповой политики на хост-компьютере (версии 1.4.1 и более ранние)</span><span class="sxs-lookup"><span data-stu-id="38b2b-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="38b2b-256">Эта задача не выполняется для Cloud Connector версии 1.4.2 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="38b2b-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="38b2b-257">Учетная запись CceService создается во время развертывания Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="38b2b-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="38b2b-258">Он запускается облачная служба управления Connector и требуется разрешение на удаление cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="38b2b-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="38b2b-259">Необходимо изменить параметр групповой политики на хост-компьютере Cloud Connector, чтобы указать, что реестр пользователя не следует выгружать при выходе пользователя из системы.</span><span class="sxs-lookup"><span data-stu-id="38b2b-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="38b2b-260">Следуйте инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="38b2b-260">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="38b2b-261">Изменение параметра групповой политики</span><span class="sxs-lookup"><span data-stu-id="38b2b-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="38b2b-262">Откройте **Редактор групповой политики** , выполнив gpedit.msc.</span><span class="sxs-lookup"><span data-stu-id="38b2b-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="38b2b-263">В **редакторе групповых политик** перейдите в раздел «Административные шаблоны» > «Система» > UserProfile > «Не выполнять принудительную выгрузку реестра пользователя при его выходе из системы». </span><span class="sxs-lookup"><span data-stu-id="38b2b-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="38b2b-264">Присвойте ей значение **включено**.</span><span class="sxs-lookup"><span data-stu-id="38b2b-264">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="38b2b-265">Настройка клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="38b2b-265">Set up your Office 365 tenant</span></span>

<span data-ttu-id="38b2b-266">Необходим клиента Office 365 с помощью Скайп для бизнеса в Интернет и телефонной системой в Office 365.</span><span class="sxs-lookup"><span data-stu-id="38b2b-266">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="38b2b-267">Убедитесь в том, Установка и настроен перед попыткой использования соединителя облачных вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="38b2b-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="38b2b-268">Некоторые действия программы установки Office 365 требуется настройка клиента Office 365 с помощью PowerShell удаленного клиента (TRPS).</span><span class="sxs-lookup"><span data-stu-id="38b2b-268">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="38b2b-269">**Ее необходимо установить на сервере узла.**</span><span class="sxs-lookup"><span data-stu-id="38b2b-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="38b2b-270">Вы можете загрузить Скайп для бизнеса в Интернет модуль для PowerShell из: [Скайп для бизнеса в Интернет, модуля Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="38b2b-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="38b2b-271">Создание выделенной Скайп для учетной записи администратора предприятия для соединителя облачных online управления, например CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="38b2b-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="38b2b-272">Эта учетная запись будет использоваться для добавления и удаления устройств, включения и отключения автоматического обновления ОС, включения и отключения автоматического обновления двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="38b2b-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="38b2b-273">Задайте для этой учетной записи бессрочный пароль, чтобы упростить работу со службой.</span><span class="sxs-lookup"><span data-stu-id="38b2b-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


