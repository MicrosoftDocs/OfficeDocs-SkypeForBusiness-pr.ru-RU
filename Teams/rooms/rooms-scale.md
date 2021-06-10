---
title: Развертывание Комнаты Microsoft Teams с помощью Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Узнайте, как развертывать Комнаты Microsoft Teams в крупных развертываниях с помощью Microsoft Endpoint Configuration Manager.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 2348d0f3e9d94aed80494155fbaab8288ddd97a6
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410115"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="2b09e-103">Развертывание Комнаты Microsoft Teams с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2b09e-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="2b09e-104">В этой статье вы можете получить все необходимые сведения для Комнаты Microsoft Teams развертывания с помощью Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2b09e-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="2b09e-105">С помощью простых в использовании методов, предоставляемых Configuration Manager, вы можете развернуть операционную систему и другие приложения на нескольких целевых устройствах.</span><span class="sxs-lookup"><span data-stu-id="2b09e-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="2b09e-106">Используйте подход, который приведен ниже, чтобы проецировать конфигурацию Configuration Manager и настроить образцы пакетов и сценариев, предоставленные в рамках этого руководства, при необходимости для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2b09e-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Комнаты Microsoft Teams с помощью Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="2b09e-108">Это решение было протестировано только в Surface Pro развертываниях на базе Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="2b09e-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="2b09e-109">Следуйте инструкциям производителя для конфигураций, которые не основаны на Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="2b09e-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="2b09e-110">Проверка предварительных условий</span><span class="sxs-lookup"><span data-stu-id="2b09e-110">Validate prerequisites</span></span>

<span data-ttu-id="2b09e-111">Чтобы развернуть Комнаты Microsoft Teams с помощью Configuration Manager, убедитесь, что вы соответствуете следующим требованиям и требованиям.</span><span class="sxs-lookup"><span data-stu-id="2b09e-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="2b09e-112">Microsoft Endpoint Configuration Manager требования</span><span class="sxs-lookup"><span data-stu-id="2b09e-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="2b09e-113">Microsoft Endpoint Configuration Manager версия должна быть не менее 1706 или выше.</span><span class="sxs-lookup"><span data-stu-id="2b09e-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="2b09e-114">Рекомендуем использовать 1710 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="2b09e-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="2b09e-115">Ознакомьтесь со Windows 10 в [Configuration Manager,](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) чтобы узнать о Windows 10, поддерживаемой Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2b09e-115">Check out [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="2b09e-116">Необходимо установить поддерживаемую версию Windows оценки и развертывания (ADK) для Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2b09e-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="2b09e-117">Просмотр версий Windows 10 [ADK,](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) которые можно использовать с различными версиями Configuration Manager, и убедитесь, что в развертывании используется правильная версия.</span><span class="sxs-lookup"><span data-stu-id="2b09e-117">See the versions of the [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="2b09e-118">Системным серверам сайтов должна быть назначена роль точки распространения, а изображения загрузки должны быть включены для поддержки среды предварительного выполнения [(PXE),](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) чтобы включить развертывание, инициированное сетью.</span><span class="sxs-lookup"><span data-stu-id="2b09e-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="2b09e-119">Если поддержка PXE не включена, вы можете использовать [загружаемые носители](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертывания.</span><span class="sxs-lookup"><span data-stu-id="2b09e-119">If PXE support isn't enabled, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="2b09e-120">Учетная запись сетевого доступа должна быть настроена для поддержки новых сценариев развертывания на компьютере (без метала).</span><span class="sxs-lookup"><span data-stu-id="2b09e-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="2b09e-121">Дополнительные информацию о настройке учетной записи сетевого доступа см. в записях учетных записей, [используемых в Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="2b09e-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="2b09e-122">Если вы, [](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)вероятно, развернете одно и то же изображение Комнаты Microsoft Teams в нескольких единицах одновременно, мы рекомендуем включить поддержку многоядерных трансляций.</span><span class="sxs-lookup"><span data-stu-id="2b09e-122">We recommend that you enable [multicast support](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="2b09e-123">Требования к сети</span><span class="sxs-lookup"><span data-stu-id="2b09e-123">Networking requirements</span></span>

-   <span data-ttu-id="2b09e-124">В вашей сети должен быть сервер DHCP, настроенный для автоматического распространения IP-адресов на подсети, в которых Комнаты Microsoft Teams будут развернуты единицы.</span><span class="sxs-lookup"><span data-stu-id="2b09e-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b09e-125">Длительность аренду DHCP должна быть установлена на более длительный срок, чем длительность развертывания изображений.</span><span class="sxs-lookup"><span data-stu-id="2b09e-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="2b09e-126">В противном случае может произойть сбой развертывания.</span><span class="sxs-lookup"><span data-stu-id="2b09e-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="2b09e-127">Сеть, включая коммутаторы и виртуальные сети laNs (VLANs), должна быть настроена для поддержки PXE.</span><span class="sxs-lookup"><span data-stu-id="2b09e-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="2b09e-128">Дополнительные сведения о помощнике по IP-адресам и конфигурации PXE можно найти у поставщика сети.</span><span class="sxs-lookup"><span data-stu-id="2b09e-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="2b09e-129">Кроме того, вы можете использовать загружаемые [носители](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертывания, если поддержка PXE не включена.</span><span class="sxs-lookup"><span data-stu-id="2b09e-129">Alternatively, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b09e-130">Для Surface Pro устройств загрузка из сети (загрузка PXE) поддерживается только при использовании адаптеров Ethernet или док-станции от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2b09e-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="2b09e-131">Сторонние адаптеры Ethernet не поддерживают загрузку PXE с помощью Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="2b09e-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="2b09e-132">Дополнительные [сведения см. в теме Адаптеры Ethernet и развертывание Surface.](/surface/ethernet-adapters-and-surface-device-deployment)</span><span class="sxs-lookup"><span data-stu-id="2b09e-132">See [Ethernet adapters and Surface deployment](/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="2b09e-133">Настройка Microsoft Endpoint Configuration Manager для развертывания операционной системы</span><span class="sxs-lookup"><span data-stu-id="2b09e-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="2b09e-134">В этой статье предполагается, что у вас уже есть нормальное развертывание Configuration Manager, а также не все действия, необходимые для развертывания и настройки Configuration Manager с нуля.</span><span class="sxs-lookup"><span data-stu-id="2b09e-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="2b09e-135">Документация [и инструкции по](/configmgr/) настройке Microsoft Endpoint Configuration Manager — отличный ресурс; рекомендуем начать с этих ресурсов, если вы еще не развернули Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2b09e-135">The [documentation and the configuration guidance](/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="2b09e-136">Чтобы проверить правильность настройки компонентов развертывания операционной системы (OSD), следуйте инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="2b09e-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="2b09e-137">Проверка и обновление Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2b09e-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="2b09e-138">В консоли Configuration Manager перейдите к **центру администрирования** \> **и обслуживания**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="2b09e-139">Проверьте установленные сборки и соответствующие обновления, которые еще не установлены.</span><span class="sxs-lookup"><span data-stu-id="2b09e-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="2b09e-140">Просмотрите [службу поддержки Windows 10 в Configuration Manager;](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) Если вам нужно обновить развертывание, выберите обновление, а затем выберите **Скачать**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-140">Review [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="2b09e-141">После завершения скачивания выберите обновление и выберите Установить **пакет обновления**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="2b09e-142">Настройка точек распространения для поддержки PXE и многомерных трансляций</span><span class="sxs-lookup"><span data-stu-id="2b09e-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="2b09e-143">В консоли Configuration Manager перейдите к пункту **Точки** \> **распространения администрирования**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="2b09e-144">Выберите сервер точек рассылки, который будет обслуживать развертывание Комнаты Microsoft Teams, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="2b09e-145">Выберите **вкладку PXE** и убедитесь, что включены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2b09e-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="2b09e-146">Включить поддержку PXE для клиентов</span><span class="sxs-lookup"><span data-stu-id="2b09e-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="2b09e-147">Разрешить этой точке рассылки отвечать на входящие запросы PXE</span><span class="sxs-lookup"><span data-stu-id="2b09e-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="2b09e-148">Включить поддержку неизвестного компьютера</span><span class="sxs-lookup"><span data-stu-id="2b09e-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="2b09e-149">*Необязательно:* Чтобы включить поддержку многоуровневой трансляции, на вкладке **Multicast** убедитесь, что включены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2b09e-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="2b09e-150">Включить многоуровневую передачу данных для одновременной отправки данных нескольким клиентам</span><span class="sxs-lookup"><span data-stu-id="2b09e-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="2b09e-151">Настройка диапазона портов UDP в процентах от рекомендации вашей сетевой группы</span><span class="sxs-lookup"><span data-stu-id="2b09e-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="2b09e-152">Настройка учетной записи сетевого доступа</span><span class="sxs-lookup"><span data-stu-id="2b09e-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="2b09e-153">В консоли Configuration Manager перейдите на сайт **администрирования** Сайтов \> **конфигурации** \> сайта и выберите сайт.</span><span class="sxs-lookup"><span data-stu-id="2b09e-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="2b09e-154">В группе **Параметры** выберите **Настроить распространение** программного обеспечения компонентов \> **сайта**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="2b09e-155">Выберите **вкладку Учетная запись сетевого** доступа. Настроив одну или несколько учетных записей, а затем выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="2b09e-156">Для учетных записей не требуются специальные права, за исключением доступа к этому компьютеру из сети **прямо** на сервере точек рассылки.</span><span class="sxs-lookup"><span data-stu-id="2b09e-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="2b09e-157">Подходит общую учетную запись пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="2b09e-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="2b09e-158">Дополнительные сведения см. в [записях учетных записей, используемых в Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="2b09e-158">For more information, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="2b09e-159">Настройка изображения загрузки</span><span class="sxs-lookup"><span data-stu-id="2b09e-159">Configure a boot image</span></span>

1.  <span data-ttu-id="2b09e-160">В консоли Configuration Manager перейдите к загрузке **изображений загрузки** операционной системы библиотеки \>  \> **программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="2b09e-161">Выберите **Загрузка изображения (x64)** и **свойства**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="2b09e-162">Выберите **вкладку Источник** данных и включите развернуть это изображение загрузки из точки распространения с поддержкой **PXE.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="2b09e-163">Выберите **вкладку Необязательные компоненты,** чтобы установить необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="2b09e-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="2b09e-164">Выберите значок звезды и в поиске **по запросу HTML (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="2b09e-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="2b09e-165">Чтобы **добавить поддержку** HTML-приложения к изображению загрузки, выберите ОК.</span><span class="sxs-lookup"><span data-stu-id="2b09e-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="2b09e-166">*Необязательно:* Чтобы настроить параметры развертывания, выберите **вкладку Настройка.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="2b09e-167">В этой службе можно включить поддержку **(только тестирование),** если вы хотите получить доступ к командной подсказке во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="2b09e-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="2b09e-168">Если эта возможность включена, во время развертывания можно запустить командную команду, выбрав **F8.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="2b09e-169">Вы также можете указать пользовательское фоновое изображение, которое будет отображаться во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="2b09e-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="2b09e-170">Чтобы задать изображение, вите Укажите пользовательский файл фонового изображения **(UNC-путь** и выберите фон).</span><span class="sxs-lookup"><span data-stu-id="2b09e-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="2b09e-171">При запросе выберите **Да** и распространить обновленное изображение загрузки по точкам распространения.</span><span class="sxs-lookup"><span data-stu-id="2b09e-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="2b09e-172">Дополнительные сведения см. в [теме Управление загрузкой изображений с помощью Configuration Manager.](/configmgr/osd/get-started/manage-boot-images)</span><span class="sxs-lookup"><span data-stu-id="2b09e-172">For more information, see [Manage boot images with Configuration Manager](/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="2b09e-173">Вы можете создать загружаемый USB-носители, чтобы инициировать развертывание последовательностей задач Configuration Manager для среды, в которой нет поддержки PXE.</span><span class="sxs-lookup"><span data-stu-id="2b09e-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="2b09e-174">В загружаемом носителе содержится только изображение загрузки, необязательные предварительные команды и необходимые файлы, а также файлы-файлы Configuration Manager, которые поддерживают загрузку в Windows PE и подключение к Configuration Manager для остальной части процесса развертывания.</span><span class="sxs-lookup"><span data-stu-id="2b09e-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="2b09e-175">Дополнительные сведения см. в [теме Создание загружаемых мультимедиа.](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)</span><span class="sxs-lookup"><span data-stu-id="2b09e-175">For more information, see [Create bootable media](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="2b09e-176">Создание пакетов Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2b09e-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b09e-177">Требуемая версия операционной системы для каждой версии установщика SRS изменяется с каждым выпуском MSI.</span><span class="sxs-lookup"><span data-stu-id="2b09e-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="2b09e-178">Чтобы определить версию операционной системы для данного MSI-сервера, запустите сценарий настройки консоли один раз.</span><span class="sxs-lookup"><span data-stu-id="2b09e-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="2b09e-179">Дополнительные см. в [Комнаты Microsoft Teams с помощью Microsoft Endpoint Configuration Manager.](rooms-scale.md)</span><span class="sxs-lookup"><span data-stu-id="2b09e-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="2b09e-180">Configuration Manager требуется несколько пакетов для развертывания и настройки Комнаты Microsoft Teams единиц.</span><span class="sxs-lookup"><span data-stu-id="2b09e-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="2b09e-181">Вам нужно создать и настроить следующие пакеты, а затем распространить их на системы сайтов Configuration Manager, для которых назначена роль сервера точки распространения.</span><span class="sxs-lookup"><span data-stu-id="2b09e-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="2b09e-182">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="2b09e-182">**Package name**</span></span>                     | <span data-ttu-id="2b09e-183">**Тип**</span><span class="sxs-lookup"><span data-stu-id="2b09e-183">**Type**</span></span>               | <span data-ttu-id="2b09e-184">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2b09e-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="2b09e-185">Пакет приложений SRS v2 — SRS</span><span class="sxs-lookup"><span data-stu-id="2b09e-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="2b09e-186">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="2b09e-186">Software package</span></span>       | <span data-ttu-id="2b09e-187">Пакет для набора Комнаты Microsoft Teams развертывания</span><span class="sxs-lookup"><span data-stu-id="2b09e-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="2b09e-188">SRS v2 — пакет Sysprep</span><span class="sxs-lookup"><span data-stu-id="2b09e-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="2b09e-189">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="2b09e-189">Software package</span></span>       | <span data-ttu-id="2b09e-190">Пакет для настраиваемой Unattended.xml для настройки Комнаты Microsoft Teams единиц</span><span class="sxs-lookup"><span data-stu-id="2b09e-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="2b09e-191">Пакет SRS для Set-SRSComputerName 2</span><span class="sxs-lookup"><span data-stu-id="2b09e-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="2b09e-192">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="2b09e-192">Software package</span></span>       | <span data-ttu-id="2b09e-193">Пакет для HTML-приложения (HTA) для назначения имени компьютера во время развертывания</span><span class="sxs-lookup"><span data-stu-id="2b09e-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="2b09e-194">SRS v2 — настройка настройки SRS</span><span class="sxs-lookup"><span data-stu-id="2b09e-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="2b09e-195">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="2b09e-195">Software package</span></span>       | <span data-ttu-id="2b09e-196">Пакет для настройки развертывания приложения Комнаты Microsoft Teams приложений</span><span class="sxs-lookup"><span data-stu-id="2b09e-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="2b09e-197">Пакет обновлений ОС SRS версии 2</span><span class="sxs-lookup"><span data-stu-id="2b09e-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="2b09e-198">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="2b09e-198">Software package</span></span>       | <span data-ttu-id="2b09e-199">Пакет для развертывания обязательных обновлений операционной системы</span><span class="sxs-lookup"><span data-stu-id="2b09e-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="2b09e-200">SRS v2 — корневой пакет сертификата</span><span class="sxs-lookup"><span data-stu-id="2b09e-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="2b09e-201">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="2b09e-201">Software package</span></span>       | <span data-ttu-id="2b09e-202">Необязательно: пакет для развертывания корневого сертификата (не требуется для подразделений, присоединимых к домену)</span><span class="sxs-lookup"><span data-stu-id="2b09e-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="2b09e-203">Пакет SRS для Microsoft Monitoring Agent 2</span><span class="sxs-lookup"><span data-stu-id="2b09e-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="2b09e-204">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="2b09e-204">Software package</span></span>       | <span data-ttu-id="2b09e-205">Необязательно: пакет для развертывания и настройки агента Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="2b09e-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="2b09e-206">SRS v2 — фоновый пакет WinPE</span><span class="sxs-lookup"><span data-stu-id="2b09e-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="2b09e-207">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="2b09e-207">Software package</span></span>       | <span data-ttu-id="2b09e-208">Пакет для пользовательского фонового изображения для загрузки изображений</span><span class="sxs-lookup"><span data-stu-id="2b09e-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="2b09e-209">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="2b09e-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="2b09e-210">Изображение операционной системы</span><span class="sxs-lookup"><span data-stu-id="2b09e-210">Operating system image</span></span> | <span data-ttu-id="2b09e-211">Пакет для установщика операционной системы (install.wim)</span><span class="sxs-lookup"><span data-stu-id="2b09e-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="2b09e-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="2b09e-212">Surface Pro</span></span>                          | <span data-ttu-id="2b09e-213">Пакет драйвера</span><span class="sxs-lookup"><span data-stu-id="2b09e-213">Driver package</span></span>         | <span data-ttu-id="2b09e-214">Пакет для драйверов устройств и программного обеспечения для Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="2b09e-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="2b09e-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="2b09e-215">Surface Pro 4</span></span>                        | <span data-ttu-id="2b09e-216">Пакет драйвера</span><span class="sxs-lookup"><span data-stu-id="2b09e-216">Driver package</span></span>         | <span data-ttu-id="2b09e-217">Пакет для драйверов устройств и программного обеспечения для Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="2b09e-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="2b09e-218">Дополнительные сведения см. в [теме Пакеты и программы в Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="2b09e-218">For more information, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="2b09e-219">Создание папок для исходных файлов пакета</span><span class="sxs-lookup"><span data-stu-id="2b09e-219">Create folders for the package source files</span></span>

<span data-ttu-id="2b09e-220">Configuration Manager требует, чтобы исходные файлы пакетов были уорганы в определенную структуру папок при их первом и обновлении.</span><span class="sxs-lookup"><span data-stu-id="2b09e-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="2b09e-221">Создайте следующую структуру папок на сайте Microsoft Endpoint Configuration Manager администрирования или основном сайте либо на сервере, который используется для создания исходных файлов пакетов:</span><span class="sxs-lookup"><span data-stu-id="2b09e-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="2b09e-222">Пакет SRS для Microsoft Monitoring Agent 2</span><span class="sxs-lookup"><span data-stu-id="2b09e-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="2b09e-223">Пакет обновлений ОС SRS версии 2</span><span class="sxs-lookup"><span data-stu-id="2b09e-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="2b09e-224">SRS v2 — корневой пакет сертификата</span><span class="sxs-lookup"><span data-stu-id="2b09e-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="2b09e-225">Пакет SRS для Set-SRSComputerName 2</span><span class="sxs-lookup"><span data-stu-id="2b09e-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="2b09e-226">Пакет приложений SRS v2 — SRS</span><span class="sxs-lookup"><span data-stu-id="2b09e-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="2b09e-227">SRS v2 — настройка настройки SRS</span><span class="sxs-lookup"><span data-stu-id="2b09e-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="2b09e-228">SRS v2 — пакет Sysprep</span><span class="sxs-lookup"><span data-stu-id="2b09e-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="2b09e-229">Драйверы</span><span class="sxs-lookup"><span data-stu-id="2b09e-229">Drivers</span></span>
    -   <span data-ttu-id="2b09e-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="2b09e-230">Surface Pro</span></span>
    -   <span data-ttu-id="2b09e-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="2b09e-231">Surface Pro 4</span></span>
-   <span data-ttu-id="2b09e-232">Операционные системы</span><span class="sxs-lookup"><span data-stu-id="2b09e-232">Operating Systems</span></span>
    -   <span data-ttu-id="2b09e-233">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="2b09e-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="2b09e-234">Вы также [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) можете скачать и использовать ZIP-файл, который содержит структуру папок для пакетов, нужные сценарии и шаблон последовательности задач, которые нужно импортировать.</span><span class="sxs-lookup"><span data-stu-id="2b09e-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="2b09e-235">Создание пакета агента мониторинга</span><span class="sxs-lookup"><span data-stu-id="2b09e-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="2b09e-236">Скачайте агент мониторинга из <https://go.microsoft.com/fwlink/?LinkId=828603> .</span><span class="sxs-lookup"><span data-stu-id="2b09e-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="2b09e-237">Извлекать пакет в папку **SRS v2 – Microsoft Monitoring Agent Package** ( Пакет), открыв окно командной подсказки и вводяMMASetup-AMD64.exe **/C:** в командной подсказке.</span><span class="sxs-lookup"><span data-stu-id="2b09e-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="2b09e-238">В консоли Configuration Manager  перейдите к пакету управления приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="2b09e-239">Введите следующую информацию для создания пакета:</span><span class="sxs-lookup"><span data-stu-id="2b09e-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="2b09e-240">Имя:<strong>SRS v2 — пакет Microsoft Monitoring Agent</strong></span><span class="sxs-lookup"><span data-stu-id="2b09e-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="2b09e-241">Производитель:<strong>Корпорация Майкрософт</strong></span><span class="sxs-lookup"><span data-stu-id="2b09e-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="2b09e-242">Версия:<strong>8.1.11081.0</strong> (введите версию загруженного установного файла)</span><span class="sxs-lookup"><span data-stu-id="2b09e-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="2b09e-243">Выберите этот **пакет содержит исходные** файлы, введите путь к **SRS v2 - Microsoft Monitoring Agent пакет** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="2b09e-244">Выберите **Не создавать программу**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="2b09e-245">Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="2b09e-246">Выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="2b09e-247">Создание пакета обновлений операционной системы</span><span class="sxs-lookup"><span data-stu-id="2b09e-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="2b09e-248">В **папке Пакет обновления ОС SRS версии 2** создайте новый сценарий PowerShell с именем **Install-SRSv2-OS-Updates.ps1.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="2b09e-249">Скопируйте ниже сценарий **вInstall-SRSv2-OS-Updates.ps1** сценарий.</span><span class="sxs-lookup"><span data-stu-id="2b09e-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="2b09e-250">Кроме того, вы можете скачать сценарий Install-SRSv2-OS-Updates.ps1 [отсюда](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="2b09e-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. <span data-ttu-id="2b09e-251">Скачайте обязательные пакеты Windows обновления в ту же папку.</span><span class="sxs-lookup"><span data-stu-id="2b09e-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2b09e-252">На момент публикации этой статьи требовался только [KB4056892.](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)</span><span class="sxs-lookup"><span data-stu-id="2b09e-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="2b09e-253">Чтобы [узнать, требуется ли Комнаты Microsoft Teams,](console.md)проверьте, требуются ли какие-либо другие обновления.</span><span class="sxs-lookup"><span data-stu-id="2b09e-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="2b09e-254">В консоли Configuration Manager  перейдите к пакету управления приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="2b09e-255">Введите следующую информацию для создания пакета:</span><span class="sxs-lookup"><span data-stu-id="2b09e-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="2b09e-256">Имя: **SRS версии 2 — пакет обновлений ОС**</span><span class="sxs-lookup"><span data-stu-id="2b09e-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="2b09e-257">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="2b09e-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="2b09e-258">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2b09e-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="2b09e-259">Выберите этот **пакет содержит исходные** файлы, введите путь к папке Пакет обновлений **ОС SRS версии 2 и** затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="2b09e-260">Выберите **Не создавать программу**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="2b09e-261">Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="2b09e-262">Выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="2b09e-263">Создание корневого пакета сертификата (необязательно)</span><span class="sxs-lookup"><span data-stu-id="2b09e-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="2b09e-264">Этот пакет создается для распространения корневого сертификата для устройств, которые не будут соединены с доменом Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b09e-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="2b09e-265">Создайте этот пакет только в том случае, если применяются оба следующих условия:</span><span class="sxs-lookup"><span data-stu-id="2b09e-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="2b09e-266">Развертывание включает в себя локальное развертывание Lync или Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2b09e-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="2b09e-267">Комнаты Microsoft Teams настроены для работы в группе, а не в составе домена.</span><span class="sxs-lookup"><span data-stu-id="2b09e-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="2b09e-268">Скопируйте корневой сертификат в **папку SRS v2 — корневой пакет сертификата.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="2b09e-269">В консоли Configuration Manager  перейдите к пакету управления приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="2b09e-270">Введите следующую информацию для создания пакета:</span><span class="sxs-lookup"><span data-stu-id="2b09e-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="2b09e-271">Имя: **SRS v2 — корневой пакет сертификата**</span><span class="sxs-lookup"><span data-stu-id="2b09e-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="2b09e-272">Производитель: *название вашей организации*</span><span class="sxs-lookup"><span data-stu-id="2b09e-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="2b09e-273">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2b09e-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="2b09e-274">Выберите этот **пакет содержит исходные** файлы, введите путь к папке **SRS v2 —** Корневой пакет сертификата, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="2b09e-275">Выберите **Не создавать программу**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="2b09e-276">Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="2b09e-277">Выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="2b09e-278">Создание пакета Комнаты Microsoft Teams развертывания</span><span class="sxs-lookup"><span data-stu-id="2b09e-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="2b09e-279">Скачайте последнюю версию набора Комнаты Microsoft Teams **из** <https://go.microsoft.com/fwlink/?linkid=851168> и установите его на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="2b09e-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="2b09e-280">Скопируйте содержимое **из C: \\ Program Files (x86) \\ Skype Room System Deployment Kit** в папку пакетов приложений **SRS v2 — SRS.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="2b09e-281">В консоли Configuration Manager  перейдите к пакету управления приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="2b09e-282">Введите следующую информацию для создания пакета:</span><span class="sxs-lookup"><span data-stu-id="2b09e-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="2b09e-283">Имя: **SRS v2 — пакет приложения SRS**</span><span class="sxs-lookup"><span data-stu-id="2b09e-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="2b09e-284">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="2b09e-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="2b09e-285">Версия: **3.1.104.0** (введите версию загруженного установного файла)</span><span class="sxs-lookup"><span data-stu-id="2b09e-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="2b09e-286">Выберите этот **пакет содержит исходные файлы,** введите путь к папке пакет приложений **SRS v2 – SRS,** а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="2b09e-287">Выберите **Не создавать программу**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="2b09e-288">Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="2b09e-289">Выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="2b09e-290">Создание пакета назначения имени компьютера</span><span class="sxs-lookup"><span data-stu-id="2b09e-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="2b09e-291">В **папке пакетов SRS v2 – Set-SRSComputerName создайте** новое HTML-приложение с именем **Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="2b09e-292">Скопируйте следующий сценарий в файл **Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="2b09e-293">Кроме того, здесь можно скачать файл Set-SRSComputerName.hta. [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2b09e-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  <span data-ttu-id="2b09e-294">В консоли Configuration Manager  перейдите к пакету управления приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="2b09e-295">Введите следующую информацию для создания пакета:</span><span class="sxs-lookup"><span data-stu-id="2b09e-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="2b09e-296">Имя: **SRS v2 — пакет Set-SRSComputerName**</span><span class="sxs-lookup"><span data-stu-id="2b09e-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="2b09e-297">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="2b09e-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="2b09e-298">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2b09e-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="2b09e-299">Выберите этот **пакет содержит исходные файлы,** введите путь к **SRS v2 - Set-SRSComputerName пакет** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="2b09e-300">Выберите **Не создавать программу**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="2b09e-301">Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="2b09e-302">Выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="2b09e-303">Создание пакета Sysprep</span><span class="sxs-lookup"><span data-stu-id="2b09e-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="2b09e-304">В **папке SRS v2 – Sysprep Package (Пакет Sysprep)** создайте новый XML-файл с именем **Unattend.xml.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="2b09e-305">Скопируйте следующий текст в **Unattend.xml** файл.</span><span class="sxs-lookup"><span data-stu-id="2b09e-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="2b09e-306">Кроме того, вы можете скачать Unattend.xml [здесь.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2b09e-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. <span data-ttu-id="2b09e-307">В консоли Configuration Manager перейдите к **пакету управления** приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="2b09e-308">Введите следующую информацию для создания пакета:</span><span class="sxs-lookup"><span data-stu-id="2b09e-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="2b09e-309">Имя: **SRS v2 — пакет Sysprep**</span><span class="sxs-lookup"><span data-stu-id="2b09e-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="2b09e-310">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="2b09e-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="2b09e-311">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2b09e-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="2b09e-312">Выберите этот **пакет содержит исходные** файлы, введите путь к папке **SRS v2 – Sysprep Package** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="2b09e-313">Выберите **Не создавать программу**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="2b09e-314">Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="2b09e-315">Выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="2b09e-316">Создание пакета Windows 10 Корпоративная пакета</span><span class="sxs-lookup"><span data-stu-id="2b09e-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="2b09e-317">Получите файл Windows 10 Корпоративная x64 и скопируйте **файл install.wim** в папку Windows 10 Корпоративная **операционных \\** систем.</span><span class="sxs-lookup"><span data-stu-id="2b09e-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="2b09e-318">В консоли Configuration Manager перейдите в **библиотеку** программного обеспечения Операционные системы Изображения операционной системы \>  \> , а затем выберите **Добавить изображение операционной системы**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="2b09e-319">Укажите путь к только что **скопированного WIM-файлу** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="2b09e-320">**Обновив поле** Версия в соответствие с номером сборки изображения Windows 10 Корпоративная, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="2b09e-321">Просмотрите **страницу Сведения** и выберите **далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="2b09e-322">Выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-322">Select **Close**.</span></span>

<span data-ttu-id="2b09e-323">Дополнительные сведения см. в [управлении изображениями ОС с помощью Configuration Manager.](/configmgr/osd/get-started/manage-operating-system-images)</span><span class="sxs-lookup"><span data-stu-id="2b09e-323">For more information, see [Manage OS images with Configuration Manager](/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="2b09e-324">Создание Surface Pro пакетов драйверов устройств</span><span class="sxs-lookup"><span data-stu-id="2b09e-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="2b09e-325">Комнаты Microsoft Teams поддерживается как для Surface Pro, так и для Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="2b09e-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="2b09e-326">Необходимо создать пакет драйвера для каждой модели Surface Pro в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="2b09e-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b09e-327">Драйверы должны быть совместимы с сборкой Windows 10 Корпоративная и версией Комнаты Microsoft Teams комплекта развертывания.</span><span class="sxs-lookup"><span data-stu-id="2b09e-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="2b09e-328">Дополнительные сведения см. в дополнительных сведениях [Скачивание](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) последней версии постройки и драйверов для устройств Surface и [Настройка консоли.](console.md)</span><span class="sxs-lookup"><span data-stu-id="2b09e-328">For more information, see [Download the latest firmware and drivers for Surface devices](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="2b09e-329">Скачайте последние драйверы и программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="2b09e-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="2b09e-330">Для Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="2b09e-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="2b09e-331">Для Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="2b09e-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="2b09e-332">Извлеките скачаный драйвер и программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="2b09e-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="2b09e-333">Откройте окно командной подсказки и введите одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="2b09e-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="2b09e-334">В консоли Configuration Manager перейдите к **драйверам операционных** систем библиотеки программного обеспечения \>  \> и выберите **Импорт драйвера**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="2b09e-335">Выберите Импортировать все драйверы по следующему сетевому пути **(UNC),** выберите папку-источник (например, C: \\ _Sources Drivers Surface Pro) и выберите \\ \\ **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="2b09e-336">На странице **Укажите сведения** об импортируемых драйверах выберите все указанные драйверы, а затем выберите включить эти драйверы и разрешить их **установку компьютерам.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="2b09e-337">Выберите **Категории**, создайте новую категорию, которая соответствует модели Surface, выберите **ОК**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="2b09e-338">Выберите **Новый пакет**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="2b09e-339">Укажите имя пакета, которое соответствует модели Surface Pro, введите путь к папке для хранения файлов пакета драйвера, выберите **ОК**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="2b09e-340">**Убедитесь, что на** странице загрузки изображений не выбрано ни один загрузки изображений, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="2b09e-341">Выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-341">Select **Close**.</span></span>

11. <span data-ttu-id="2b09e-342">Перейдите  в папку Драйверы операционных систем библиотеки программного обеспечения , выберите папку Создать папку и введите имя папки, которое соответствует модели Surface Pro, для которую вы только что \>  \> импортировали драйверы. **\>**</span><span class="sxs-lookup"><span data-stu-id="2b09e-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="2b09e-343">Переместить все импортируемые драйверы в только что созданную папку, чтобы упростить навигацию и работу.</span><span class="sxs-lookup"><span data-stu-id="2b09e-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="2b09e-344">Повторите эти же действия для Surface Pro моделей.</span><span class="sxs-lookup"><span data-stu-id="2b09e-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="2b09e-345">Дополнительные сведения см. в [теме Управление драйверами в Configuration Manager.](/configmgr/osd/get-started/manage-drivers)</span><span class="sxs-lookup"><span data-stu-id="2b09e-345">For more information, see [Manage drivers in Configuration Manager](/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="2b09e-346">Создание Комнаты Microsoft Teams конфигурации</span><span class="sxs-lookup"><span data-stu-id="2b09e-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="2b09e-347">В консоли Configuration Manager перейдите к **пакету управления** приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="2b09e-348">Введите следующую информацию для создания пакета:</span><span class="sxs-lookup"><span data-stu-id="2b09e-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="2b09e-349">Имя: **SRS v2 — настройка пакета установки SRS**</span><span class="sxs-lookup"><span data-stu-id="2b09e-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="2b09e-350">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="2b09e-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="2b09e-351">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2b09e-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="2b09e-352">Выберите поле **Этот пакет содержит исходные** файлы, введите путь к **папке SRS v2 — Настройка папки SRS Setup** и затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="2b09e-353">Выберите **Не создавать программу**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="2b09e-354">Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="2b09e-355">Выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="2b09e-356">Распространение пакетов Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2b09e-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="2b09e-357">Все пакеты должны быть распределены по серверам, для которые назначена роль точки распространения в иерархии Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2b09e-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="2b09e-358">Следуйте инструкциям ниже, чтобы начать распространение пакета.</span><span class="sxs-lookup"><span data-stu-id="2b09e-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="2b09e-359">Распространение пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="2b09e-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="2b09e-360">В консоли Configuration Manager перейдите к пакету **управления** приложениями библиотеки \> **программного** \> **обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="2b09e-361">Выберите все пакеты программного обеспечения, которые вы хотите распространить, и выберите **Распространение содержимого**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="2b09e-362">Просмотрите список пакетов и выберите **далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="2b09e-363">Добавьте в список все серверы точек рассылки (или группы точек рассылки в зависимости от иерархии Configuration Manager), а затем выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="2b09e-364">Выберите **Далее**, а затем **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="2b09e-365">Распространение пакетов драйверов.</span><span class="sxs-lookup"><span data-stu-id="2b09e-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="2b09e-366">В консоли Configuration Manager перейдите к пакету драйвера для операционной системы **библиотеки** \>  \> **программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="2b09e-367">Выберите все пакеты драйверов, которые вы хотите распространить, и выберите **Распространение содержимого**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="2b09e-368">Просмотрите список пакетов и выберите **далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="2b09e-369">Добавьте в список все серверы точек рассылки (или группы точек рассылки в зависимости от иерархии Configuration Manager), а затем выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="2b09e-370">Выберите **Далее**, а затем **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="2b09e-371">Распространение пакетов операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2b09e-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="2b09e-372">В консоли Configuration Manager перейдите к изображению **операционной** системы библиотеки \>  \> **программного обеспечения .**</span><span class="sxs-lookup"><span data-stu-id="2b09e-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="2b09e-373">Выберите все изображения операционной системы, которые вы хотите распространить, и выберите **Распространение содержимого**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="2b09e-374">Просмотрите список пакетов и выберите **далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="2b09e-375">Добавьте в список все серверы точек рассылки (или группы точек рассылки в зависимости от иерархии Configuration Manager), а затем выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="2b09e-376">Выберите **Далее**, а затем **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="2b09e-377">Распространение пакета может занять некоторое время в зависимости от размера пакета, иерархии Configuration Manager, количества серверов точек рассылки и пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="2b09e-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="2b09e-378">Перед началом развертывания нужно распределить все пакеты Комнаты Microsoft Teams разных единиц.</span><span class="sxs-lookup"><span data-stu-id="2b09e-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="2b09e-379">Состояние распространения пакета можно просмотреть в консоли Configuration  Manager в окте Мониторинг состояния содержимого \>  \> **о распространении.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="2b09e-380">Последовательности задач Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2b09e-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="2b09e-381">Последовательности задач с Configuration Manager используются для автоматизации действий по развертыванию образа операционной системы на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="2b09e-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="2b09e-382">Чтобы автоматически развернуть Комнаты Microsoft Teams, необходимо создать последовательность задач, которая ссылается на загрузку, используемую для запуска целевого Комнаты Microsoft Teams компьютера, образа операционной системы Windows 10 Корпоративная, которое вы хотите установить, и другого дополнительного содержимого, например других приложений или обновлений программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="2b09e-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="2b09e-383">Импорт примера последовательности задач</span><span class="sxs-lookup"><span data-stu-id="2b09e-383">Import the sample task sequence</span></span>

<span data-ttu-id="2b09e-384">Вы можете скачать и легко импортировать образец последовательности задач и настроить ее в нужное время.</span><span class="sxs-lookup"><span data-stu-id="2b09e-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="2b09e-385">[**Скачайте**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) образец последовательности задач и скопируйте скачаный ZIP-файл в общую папку.</span><span class="sxs-lookup"><span data-stu-id="2b09e-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="2b09e-386">В консоли Configuration Manager  перейдите в библиотеку программных систем Последовательности задач , а затем \>  \> выберите **Импорт последовательности задач**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="2b09e-387">Выберите **Обзор**, перейдите к общей папке, которая использовалась в шаге 1, выберите файл Комнаты Microsoft Teams развертывания **(EN-US).zip** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="2b09e-388">Установите **для действия** действие **Создать,** а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="2b09e-389">Подтвердив параметры, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="2b09e-390">Выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="2b09e-391">Проверьте правильность связей пакетов ссылок с каждым этапом последовательности задач.</span><span class="sxs-lookup"><span data-stu-id="2b09e-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="2b09e-392">Выберите последовательность импортируемых задач и выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="2b09e-393">Откроется редактор последовательностей задач, в который будут отображены все последовательные этапы, необходимые для развертывания и настройки Комнаты Microsoft Teams задач.</span><span class="sxs-lookup"><span data-stu-id="2b09e-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="2b09e-394">Выполните каждый шаг и выполните рекомендуемые обновления.</span><span class="sxs-lookup"><span data-stu-id="2b09e-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="2b09e-395">**Перезапустить в Windows PE:** этот шаг перезапустится, а затем загрузит компьютер в Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="2b09e-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="2b09e-396">Для этого шага не требуется никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="2b09e-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="2b09e-397">**Диск раздела 0 – UEFI:** этот шаг протирает конфигурацию диска и создает разделы на основе настроенных параметров.</span><span class="sxs-lookup"><span data-stu-id="2b09e-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="2b09e-398">Мы не рекомендуем вносить никаких изменений в этот шаг.</span><span class="sxs-lookup"><span data-stu-id="2b09e-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="2b09e-399">**Set SRS Computer Name**(Имя компьютера SRS). Этот этап включает HTML-приложение, которое предоставляет пользовательский интерфейс для установки имени компьютера Комнаты Microsoft Teams во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="2b09e-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="2b09e-400">Это необязательный шаг, но его можно отключить только в том случае, если вы хотите управлять именами компьютеров с помощью альтернативного процесса.</span><span class="sxs-lookup"><span data-stu-id="2b09e-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="2b09e-401">Убедитесь, что выбран пакет **SRS v2 — Set-SRSComputerName.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="2b09e-402">Если это не так, перейдите к пакету и выберите его.</span><span class="sxs-lookup"><span data-stu-id="2b09e-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="2b09e-403">**Применить операционную** систему: на этом шаге заданы образ операционной системы, который нужно развернуть, и файл ответа Sysprep, который нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="2b09e-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="2b09e-404">Убедитесь, что Windows 10 Корпоративная выбран правильный файл изображения операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2b09e-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="2b09e-405">Убедитесь, что включено использование неотвеченного или **Sysprep-файла** ответа для пользовательской установки и выбран пакет **SRS v2 — Sysprep.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="2b09e-406">Также убедитесь, **что** для имени файла **установленоunattend.xml**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="2b09e-407">**Применить Windows Параметры.** На этом этапе собираются сведения о Windows установке.</span><span class="sxs-lookup"><span data-stu-id="2b09e-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="2b09e-408">У вас есть сведения о лицензировании и регистрации, включая ключ продукта, пароль учетной записи локального администратора и часовой пояс (в зависимости от потребностей).</span><span class="sxs-lookup"><span data-stu-id="2b09e-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="2b09e-409">**Применение сетевого Параметры:** на этом этапе можно указать имя группы или домена Active Directory и подразделения.</span><span class="sxs-lookup"><span data-stu-id="2b09e-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="2b09e-410">Рекомендации [Skype](domain-joining-considerations.md) по развертыванию Комнаты Microsoft Teams в качестве членов домена Actve Directory см. в Skype домене "Система комнат".</span><span class="sxs-lookup"><span data-stu-id="2b09e-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="2b09e-411">**Применение драйверов:** Этот шаг и его подпрограммы используются для развертывания соответствующих драйверов устройств и программного обеспечения на основе Surface Pro модели.</span><span class="sxs-lookup"><span data-stu-id="2b09e-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="2b09e-412">Обновите каждый шаг, чтобы указать соответствующий пакет драйвера, связанный с этим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="2b09e-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="2b09e-413">Каждый пакет драйвера настроен для использования Windows средств управления (WMI) для развертывания соответствующих драйверов и программного обеспечения на основе Surface Pro и модели.</span><span class="sxs-lookup"><span data-stu-id="2b09e-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="2b09e-414">Настоятельно рекомендуем не изменять конфигурацию этих драйверов, иначе развертывание может привести к сбойу.</span><span class="sxs-lookup"><span data-stu-id="2b09e-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="2b09e-415">**Настройка Windows и Configuration Manager.** На этом этапе развертывается и настраивается клиент Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2b09e-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="2b09e-416">Обновив этот шаг, укажите встроенный пакет клиента Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2b09e-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="2b09e-417">**Установка корневого** сертификата. Этот шаг распространяет корневой сертификат для устройств, не присоединиваых к домену, и поэтому является необязательным и по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="2b09e-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="2b09e-418">В этом случае следует развернуть корневой сертификат в Комнаты Microsoft Teams единицам.</span><span class="sxs-lookup"><span data-stu-id="2b09e-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="2b09e-419">Если вам нужно сделать это, убедитесь, что выбраны **SRS v2 —** пакет корневого сертификата и Отключение перенаправления **64-битной** файловой системы.</span><span class="sxs-lookup"><span data-stu-id="2b09e-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="2b09e-420">**Установка и настройка** агента мониторинга. На этом этапе устанавливается 64-битная версия агента Microsoft Azure Monitor и настраивается подключение агента к рабочей области аналитики журналов.</span><span class="sxs-lookup"><span data-stu-id="2b09e-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="2b09e-421">Этот шаг по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="2b09e-421">This step is disabled by default.</span></span> <span data-ttu-id="2b09e-422">Этот шаг можно включить только в том случае, если вы собираетесь использовать агент мониторинга для отслеживания состояния Комнаты Microsoft Teams единиц.</span><span class="sxs-lookup"><span data-stu-id="2b09e-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="2b09e-423">Отредактируете этот шаг и обновите параметры командной строки, указав свой **ИД рабочей** области и ключ **рабочей области.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="2b09e-424">Дополнительные [сведения о том,](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) как получить ИД рабочей области набора операций и первичный ключ, см. в настройках тестовых устройств для мониторинга Azure.</span><span class="sxs-lookup"><span data-stu-id="2b09e-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="2b09e-425">Убедитесь, что выбраны **SRS v2 – Microsoft Monitoring Agent package** and **Disable 64-bit file system redirection** (Перенаправление 64-битной файловой системы).</span><span class="sxs-lookup"><span data-stu-id="2b09e-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="2b09e-426">Дополнительные сведения о мониторинге состояния развертывания Комнаты Microsoft Teams см. в Комнаты Microsoft Teams управления проектами с помощью [Azure Monitor](azure-monitor-plan.md), Развертывание управления Комнаты Microsoft Teams с помощью [Azure Monitor](azure-monitor-deploy.md) и Управление устройствами Комнаты Microsoft Teams с помощью [Azure Monitor.](azure-monitor-manage.md)</span><span class="sxs-lookup"><span data-stu-id="2b09e-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="2b09e-427">**Копирование SRS файлов конфигурации v2.** На этом этапе необходимые файлы настройки и конфигурации копируется из набора Комнаты Microsoft Teams на локальный жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="2b09e-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="2b09e-428">Для этого шага не требуется никаких настроек.</span><span class="sxs-lookup"><span data-stu-id="2b09e-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="2b09e-429">Убедитесь, что выбраны **SRS v2 — пакет** приложений SRS и Отключение перенаправления **64-битной** файловой системы.</span><span class="sxs-lookup"><span data-stu-id="2b09e-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="2b09e-430">**Install-SRSv2-OS-Updates:** на этом этапе развертываются все обязательные обновления операционной системы, необходимые для Комнаты Microsoft Teams развертывания.</span><span class="sxs-lookup"><span data-stu-id="2b09e-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="2b09e-431">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2b09e-431">Do the following:</span></span>
       -   <span data-ttu-id="2b09e-432">Чтобы [узнать, какие обновления необходимы, Комнаты Microsoft Teams](console.md) настроить консоль Комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2b09e-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="2b09e-433">Убедитесь, что пакет **обновлений ОС SRS версии 2** – OS включает все необходимые обновления.</span><span class="sxs-lookup"><span data-stu-id="2b09e-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="2b09e-434">Убедитесь, что выбран пакет **обновлений SRS версии 2** – OS.</span><span class="sxs-lookup"><span data-stu-id="2b09e-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="2b09e-435">Убедитесь в том, что для политики выполнения PowerShell задано **"Обход"**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="2b09e-436">**Перезагрузить** компьютер: этот шаг перезагрузит компьютер после установки обязательных обновлений операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2b09e-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="2b09e-437">Для этого шага не требуется никаких настроек.</span><span class="sxs-lookup"><span data-stu-id="2b09e-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="2b09e-438">**Настройка Windows** компонентов: на этом этапе настраиваются необходимые Windows компонентов.</span><span class="sxs-lookup"><span data-stu-id="2b09e-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="2b09e-439">Для этого шага не требуется никаких настроек.</span><span class="sxs-lookup"><span data-stu-id="2b09e-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="2b09e-440">**Перезагрузить** компьютер: этот шаг перезагрузит компьютер после Windows настройки функций.</span><span class="sxs-lookup"><span data-stu-id="2b09e-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="2b09e-441">Для этого шага не требуется никаких настроек.</span><span class="sxs-lookup"><span data-stu-id="2b09e-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="2b09e-442">**Добавить локального пользователя Skype:** на этом этапе создается локализованная учетная запись Skype, которая используется для автоматического Windows и запуска Комнаты Microsoft Teams приложения.</span><span class="sxs-lookup"><span data-stu-id="2b09e-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="2b09e-443">Этот шаг не связан с программным пакетом, и для него не требуется его настройка.</span><span class="sxs-lookup"><span data-stu-id="2b09e-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="2b09e-444">**Настройка приложения SRS.** На этом этапе Комнаты Microsoft Teams установки приложений для следующей загрузки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2b09e-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="2b09e-445">Убедитесь, что выбраны **SRS v2 —** Настройка пакета установки SRS и Отключение перенаправления **64-битной** файловой системы.</span><span class="sxs-lookup"><span data-stu-id="2b09e-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b09e-446">Очень важно, чтобы последовательность действий задачи была в предоставленной последовательности.</span><span class="sxs-lookup"><span data-stu-id="2b09e-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="2b09e-447">Изменение порядка шагов или настройка дополнительных действий может привести к разрыву развертывания.</span><span class="sxs-lookup"><span data-stu-id="2b09e-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="2b09e-448">**Настройка приложения SRS** должна быть последним этапом в последовательности задач, в противном случае развертывание может привести к сбойу.</span><span class="sxs-lookup"><span data-stu-id="2b09e-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="2b09e-449">Создание развертывания для последовательности задач</span><span class="sxs-lookup"><span data-stu-id="2b09e-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="2b09e-450">Выберите последовательность задач и выберите **развернуть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="2b09e-451">Чтобы **выбрать целевую** коллекцию для развертывания, выберите обзор.</span><span class="sxs-lookup"><span data-stu-id="2b09e-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="2b09e-452">Выберите **Все неизвестные компьютеры,** а затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="2b09e-453">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-453">Select **Next**.</span></span>

5. <span data-ttu-id="2b09e-454">В **списке** **Назначение** выберите доступен.</span><span class="sxs-lookup"><span data-stu-id="2b09e-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="2b09e-455">В списке Сделать доступным  для следующего списка выберите только мультимедиа и **PXE,** а затем выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="2b09e-456">Очень важно, чтобы для **назначения** было установлено значение **Доступен**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="2b09e-457">Убедитесь, что **для назначения** **не задалось** **обязательное.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="2b09e-458">Кроме того, убедитесь, что в области Сделать доступными для следующих сетей выбраны только мультимедиа **и** **PXE.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="2b09e-459">Установка этих значений для другого параметра может привести к тому, что все компьютеры получат изображение Комнаты Microsoft Teams развертывания при загрузке.</span><span class="sxs-lookup"><span data-stu-id="2b09e-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="2b09e-460">Не укажите расписание и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="2b09e-461">Не изменяя ничего в разделе **Пользовательский интерфейс,** выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="2b09e-462">Не изменяя ничего в разделе **Оповещения,** выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="2b09e-463">Не изменяя ничего в разделе **Точки распространения,** выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="2b09e-464">Подтвердить параметры и затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="2b09e-465">Выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="2b09e-466">Проверка и устранение неполадок с решением</span><span class="sxs-lookup"><span data-stu-id="2b09e-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="2b09e-467">После завершения Microsoft Endpoint Configuration Manager задач необходимо выполнить тестовый запуск, чтобы проверить, можно ли развернуть и Комнаты Microsoft Teams задач.</span><span class="sxs-lookup"><span data-stu-id="2b09e-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="2b09e-468">Подключение тестового устройства к проводной сети с помощью одного из поддерживаемых адаптеров Ethernet или док-станции Surface.</span><span class="sxs-lookup"><span data-stu-id="2b09e-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="2b09e-469">Если функциональность загрузки PXE еще не настроена для вашей среды, вы [](/configmgr/osd/deploy-use/create-bootable-media) можете использовать изображение загрузки на USB-устройстве флэш-памяти, созданном ранее, для загрузки с USB-устройства и подключения к Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2b09e-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="2b09e-470">Доступ к программному обеспечения и инициировать загрузку PXE:</span><span class="sxs-lookup"><span data-stu-id="2b09e-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="2b09e-471">Убедитесь, что устройство Surface отключено.</span><span class="sxs-lookup"><span data-stu-id="2b09e-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="2b09e-472">Нажмите и удерживайте **кнопку "Вверх".**</span><span class="sxs-lookup"><span data-stu-id="2b09e-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="2b09e-473">Нажмите и отпустите **кнопку** Питания.</span><span class="sxs-lookup"><span data-stu-id="2b09e-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="2b09e-474">Когда устройство начнет загрузку, отпустите **кнопку "Вверх** громкости".</span><span class="sxs-lookup"><span data-stu-id="2b09e-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="2b09e-475">Выберите **Конфигурация загрузки**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="2b09e-476">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="2b09e-476">Do one of the following:</span></span>

        -   <span data-ttu-id="2b09e-477">Выберите **загрузку PXE** и перетащите ее в верхнюю часть списка.</span><span class="sxs-lookup"><span data-stu-id="2b09e-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="2b09e-478">Кроме того, вы можете провести пальцем влево по сетевому адаптеру, чтобы сразу же загрузить его на устройство.</span><span class="sxs-lookup"><span data-stu-id="2b09e-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="2b09e-479">Это не повлияет на порядок загрузки.</span><span class="sxs-lookup"><span data-stu-id="2b09e-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="2b09e-480">Выберите USB-устройство флэш-памяти, на которое вмещается загрузочный носитор.</span><span class="sxs-lookup"><span data-stu-id="2b09e-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="2b09e-481">Выберите **Выход**, а затем **перезапустите**.</span><span class="sxs-lookup"><span data-stu-id="2b09e-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="2b09e-482">При запросе выберите Ввод **для службы** загрузки сети.</span><span class="sxs-lookup"><span data-stu-id="2b09e-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="2b09e-483">Windows PE загрузит в память, и запустится мастер последовательностей задач.</span><span class="sxs-lookup"><span data-stu-id="2b09e-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="2b09e-484">Чтобы **продолжить, выберите** Далее.</span><span class="sxs-lookup"><span data-stu-id="2b09e-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="2b09e-485">Выберите последовательность задач, которую вы импортировали ранее, а затем выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="2b09e-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="2b09e-486">После настройки диска вам будет предложено указать имя компьютера для устройства.</span><span class="sxs-lookup"><span data-stu-id="2b09e-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="2b09e-487">В пользовательском интерфейсе будет отображаться рекомендуемое имя компьютера в зависимости от серийного номера Surface Pro устройства.</span><span class="sxs-lookup"><span data-stu-id="2b09e-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="2b09e-488">Вы можете принять предложенное имя или указать новое.</span><span class="sxs-lookup"><span data-stu-id="2b09e-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="2b09e-489">Следуйте инструкциям на экране назначения имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="2b09e-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="2b09e-490">Когда вы **наберетсяе Принять,** начнется развертывание.</span><span class="sxs-lookup"><span data-stu-id="2b09e-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="2b09e-491">Остальная часть процесса развертывания является автоматической, и пользователю больше не нужно вводить данные.</span><span class="sxs-lookup"><span data-stu-id="2b09e-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="2b09e-492">После завершения настройки устройства в последовательности задач развертывания вы увидите следующий экран конфигурации с запросом на настройку Комнаты Microsoft Teams приложения.</span><span class="sxs-lookup"><span data-stu-id="2b09e-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Экран начальной настройки для Комнаты Microsoft Teams приложения](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="2b09e-494">Подключите Surface Pro к консоли Комнаты Microsoft Teams и настройте параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="2b09e-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="2b09e-495">Проверьте возможности, перечисленные в Комнаты Microsoft Teams [справки,](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) на развернутом устройстве.</span><span class="sxs-lookup"><span data-stu-id="2b09e-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="2b09e-496">Чтобы устранить неполадки при установке, проверьте **файл SMSTS.log,** в котором регистрются все действия, выполненные в последовательности задач Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2b09e-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="2b09e-497">Файл SMSTS.log хранится по одному из нескольких путей в зависимости от этапа сборки.</span><span class="sxs-lookup"><span data-stu-id="2b09e-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="2b09e-498">В таблице ниже идентифицировать путь к файлу SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="2b09e-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="2b09e-499">**Этап развертывания**</span><span class="sxs-lookup"><span data-stu-id="2b09e-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="2b09e-500">**Путь в журнале последовательностей задач**</span><span class="sxs-lookup"><span data-stu-id="2b09e-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="2b09e-501">Формат WinPE до HDD</span><span class="sxs-lookup"><span data-stu-id="2b09e-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="2b09e-502">X: \\ Windows \\ \\ SMS-сообщения \\ Temp.log</span><span class="sxs-lookup"><span data-stu-id="2b09e-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="2b09e-503">WinPE после формата HDD</span><span class="sxs-lookup"><span data-stu-id="2b09e-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="2b09e-504">В. \\ _SMSTaskSequence \\ Журнал \\ SMS-сообщений \\ smstslog.log</span><span class="sxs-lookup"><span data-stu-id="2b09e-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="2b09e-505">Развернута операционная система до установки агента Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2b09e-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="2b09e-506">в: \\ _SMSTaskSequence \\ Журнал \\ SMS-сообщений \\ smstslog.log</span><span class="sxs-lookup"><span data-stu-id="2b09e-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="2b09e-507">Развернуты операционная система и агент Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2b09e-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="2b09e-508">%windir% \\ System32 \\ ccm \\ logs \\ Smstslog \\ SMSts.log</span><span class="sxs-lookup"><span data-stu-id="2b09e-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="2b09e-509">Последовательность задач завершена</span><span class="sxs-lookup"><span data-stu-id="2b09e-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="2b09e-510">%windir% \\ System32 \\ ccm \\ logs \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="2b09e-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="2b09e-511">Вы можете в любой момент выбрать **F8** в последовательности задач, чтобы открыть консоль, а затем получить доступ к файлу SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="2b09e-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="2b09e-512">Чтобы устранить проблемы с загрузкой PXE, проверьте два файла журнала на сервере Configuration Manager, которые являются специфическими для действий PXE:</span><span class="sxs-lookup"><span data-stu-id="2b09e-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="2b09e-513">**Pxecontrol.log**, расположенный в каталоге журналов установки Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2b09e-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="2b09e-514">**Smspxe.log**, расположенный в каталоге MP в пунктах управления Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2b09e-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="2b09e-515">Полный список файлов журналов, которые можно использовать для дальнейшего устранения неполадок при установке Configuration Manager, см. в Microsoft Endpoint Configuration Manager [журнале.](/configmgr/core/plan-design/hierarchy/log-files)</span><span class="sxs-lookup"><span data-stu-id="2b09e-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](/configmgr/core/plan-design/hierarchy/log-files).</span></span>
