---
title: Развертывание комнат Microsoft Teams с помощью Microsoft Endpoint Configuration Manager
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
description: Узнайте, как развернуть комнаты Microsoft Teams в крупных развертываниях с помощью Microsoft Endpoint Configuration Manager.
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
ms.openlocfilehash: 1d8fc0090264a7a39051cfedb9c3584a08e3ebb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662424"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="fd191-103">Развертывание комнат Microsoft Teams с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fd191-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="fd191-104">В этой статье вы можете получить всю необходимую информацию для создания развернутых помещений Microsoft Teams с помощью Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fd191-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="fd191-105">С помощью простых в использовании методов, предоставляемых Configuration Manager, вы можете развернуть операционную систему и другие приложения на нескольких целевых устройствах.</span><span class="sxs-lookup"><span data-stu-id="fd191-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="fd191-106">Воспользуйтесь приведенной ниже инструкцией, чтобы помочь вам в настройке Configuration Manager, а также настроить образцы пакетов и сценариев, предоставленные в рамках этого руководства, при необходимости для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="fd191-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Процесс развертывания комнат Microsoft Teams с помощью Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="fd191-108">Это решение было протестировано только в развертываниях на основе Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="fd191-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="fd191-109">Следуйте инструкциям производителя для конфигураций, не основанных на Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="fd191-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="fd191-110">Проверка предварительных условий</span><span class="sxs-lookup"><span data-stu-id="fd191-110">Validate prerequisites</span></span>

<span data-ttu-id="fd191-111">Чтобы развернуть комнаты Microsoft Teams с помощью Configuration Manager, убедитесь, что вы соответствуете следующим требованиям и требованиям.</span><span class="sxs-lookup"><span data-stu-id="fd191-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="fd191-112">Требования к Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fd191-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="fd191-113">Версия Microsoft Endpoint Configuration Manager должна быть не менее 1706 или выше.</span><span class="sxs-lookup"><span data-stu-id="fd191-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="fd191-114">Рекомендуем использовать 1710 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="fd191-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="fd191-115">Ознакомьтесь [со службой поддержки Windows 10 в Configuration Manager,](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) чтобы узнать о версиях Windows 10, которые поддерживает Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fd191-115">Check out [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="fd191-116">Необходимо установить поддерживаемую версию комплекта windows Assessment and Deployment Kit (ADK) для Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fd191-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="fd191-117">Просмотр версий [ADK Windows 10,](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) которые можно использовать с различными версиями Configuration Manager, и убедитесь, что в вашем развертывании есть правильная версия.</span><span class="sxs-lookup"><span data-stu-id="fd191-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="fd191-118">Системным серверам сайта должна быть назначена роль точки распространения, а изображения загрузки должны быть включены для поддержки среды выполнения [(PXE)](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) перед началом сетевого развертывания.</span><span class="sxs-lookup"><span data-stu-id="fd191-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="fd191-119">Если поддержка PXE не включена, вы можете использовать для развертывания [загружаемый носители.](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)</span><span class="sxs-lookup"><span data-stu-id="fd191-119">If PXE support isn't enabled, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="fd191-120">Учетная запись сетевого доступа должна быть настроена для поддержки новых сценариев развертывания на компьютере (без каретки).</span><span class="sxs-lookup"><span data-stu-id="fd191-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="fd191-121">Дополнительные информацию о настройке учетной записи сетевого доступа см. в записях, [используемых в Configuration Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="fd191-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="fd191-122">Мы рекомендуем включить поддержку [многоуровневой](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)трансляции, если вы, вероятно, одновременно развернете одно и то же изображение комнат Microsoft Teams в нескольких блоках.</span><span class="sxs-lookup"><span data-stu-id="fd191-122">We recommend that you enable [multicast support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="fd191-123">Требования к сети</span><span class="sxs-lookup"><span data-stu-id="fd191-123">Networking requirements</span></span>

-   <span data-ttu-id="fd191-124">В вашей сети должен быть сервер DHCP, настроенный для автоматического распространения IP-адресов на подсетей, в которых будут развернуты единицы комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd191-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd191-125">Длительность аренду DHCP должна быть установлена на более длительный срок, чем длительность развертывания изображений.</span><span class="sxs-lookup"><span data-stu-id="fd191-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="fd191-126">В противном случае развертывание может быть со сбойом.</span><span class="sxs-lookup"><span data-stu-id="fd191-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="fd191-127">Сеть, включая коммутаторы и виртуальные сети laNs (VLANs), должна быть настроена для поддержки PXE.</span><span class="sxs-lookup"><span data-stu-id="fd191-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="fd191-128">Для получения дополнительных сведений о ip-помощнике и конфигурации PXE обратитесь к поставщику сети.</span><span class="sxs-lookup"><span data-stu-id="fd191-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="fd191-129">Кроме того, вы можете использовать [загружаемый носители](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертывания, если поддержка PXE не включена.</span><span class="sxs-lookup"><span data-stu-id="fd191-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd191-130">Для устройств Surface Pro загрузка из сети (загрузка PXE) поддерживается только при использовании адаптеров Ethernet или док-станции от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fd191-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="fd191-131">Сторонние адаптеры Ethernet не поддерживают загрузку PXE с Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="fd191-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="fd191-132">Дополнительные [сведения см. в адаптаторах Ethernet и развертывании Surface.](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)</span><span class="sxs-lookup"><span data-stu-id="fd191-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="fd191-133">Настройка Microsoft Endpoint Configuration Manager для развертывания операционной системы</span><span class="sxs-lookup"><span data-stu-id="fd191-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="fd191-134">В этой статье предполагается, что у вас уже настроено здоровое развертывание Configuration Manager, а также не подробно о шагах, необходимых для развертывания и настройки Configuration Manager с нуля.</span><span class="sxs-lookup"><span data-stu-id="fd191-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="fd191-135">Документация [и рекомендации по настройке](https://docs.microsoft.com/configmgr/) в Диспетчере конфигураций конечной точки Майкрософт — отличный ресурс. рекомендуем начать с этих ресурсов, если вы еще не развернули Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fd191-135">The [documentation and the configuration guidance](https://docs.microsoft.com/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="fd191-136">Чтобы проверить правильность настройки компонентов OSD, следуйте инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="fd191-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="fd191-137">Проверка и обновление Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fd191-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="fd191-138">В консоли Configuration Manager перейдите в **"Обновления** \> **администрирования и обслуживание".**</span><span class="sxs-lookup"><span data-stu-id="fd191-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="fd191-139">Проверьте установленные сборки и соответствующие обновления, которые еще не установлены.</span><span class="sxs-lookup"><span data-stu-id="fd191-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="fd191-140">Просмотрите [поддержку Windows 10 в Configuration Manager;](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) если вам нужно обновить развертывание, выберите обновление, а затем выберите **"Скачать".**</span><span class="sxs-lookup"><span data-stu-id="fd191-140">Review [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="fd191-141">После завершения скачивания выберите обновление, а затем выберите **"Установить пакет обновления".**</span><span class="sxs-lookup"><span data-stu-id="fd191-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="fd191-142">Настройка точек распространения для поддержки PXE и многомерных трансляций</span><span class="sxs-lookup"><span data-stu-id="fd191-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="fd191-143">В консоли Configuration Manager перейдите в пункты **распространения** \> **"Администрирование".**</span><span class="sxs-lookup"><span data-stu-id="fd191-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="fd191-144">Выберите сервер точки распространения, который будет обслуживать развертывание комнат Microsoft Teams, а затем выберите **"Свойства".**</span><span class="sxs-lookup"><span data-stu-id="fd191-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="fd191-145">Выберите **вкладку PXE** и убедитесь, что включены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fd191-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="fd191-146">Включить поддержку PXE для клиентов</span><span class="sxs-lookup"><span data-stu-id="fd191-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="fd191-147">Разрешить этой точке рассылки отвечать на входящие запросы PXE</span><span class="sxs-lookup"><span data-stu-id="fd191-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="fd191-148">Включить поддержку неизвестного компьютера</span><span class="sxs-lookup"><span data-stu-id="fd191-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="fd191-149">*Необязательно:* Чтобы включить многоуровневую  поддержку, на вкладке "Многоуровневая" убедитесь, что включены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fd191-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="fd191-150">Включить многоуровневую трансляцию для одновременной отправки данных нескольким клиентам</span><span class="sxs-lookup"><span data-stu-id="fd191-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="fd191-151">Настройка диапазона портов UDP по рекомендации вашей сетевой группы</span><span class="sxs-lookup"><span data-stu-id="fd191-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="fd191-152">Настройка учетной записи сетевого доступа</span><span class="sxs-lookup"><span data-stu-id="fd191-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="fd191-153">В консоли Configuration Manager перейдите к сайтам **конфигурации** сайта администрирования \>  \> и выберите сайт.</span><span class="sxs-lookup"><span data-stu-id="fd191-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="fd191-154">В группе **"Параметры"** выберите **"Настройка распространения программного обеспечения для компонентов** \> **сайта".**</span><span class="sxs-lookup"><span data-stu-id="fd191-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="fd191-155">Выберите вкладку **"Учетная запись сетевого доступа".** Настроив одну или несколько учетных записей, выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="fd191-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="fd191-156">Учетным записям не требуются какие-либо особые права, за исключением доступа к данному компьютеру из сети **прямо** на сервере точки распространения.</span><span class="sxs-lookup"><span data-stu-id="fd191-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="fd191-157">Подходит общая учетная запись пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="fd191-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="fd191-158">Дополнительные сведения см. в [записях учетных записей, используемых в Configuration Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="fd191-158">For more information, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="fd191-159">Настройка изображения загрузки</span><span class="sxs-lookup"><span data-stu-id="fd191-159">Configure a boot image</span></span>

1.  <span data-ttu-id="fd191-160">В консоли Configuration Manager  перейдите к изображениям загрузки операционной системы \> **библиотеки** \> **программного обеспечения.**</span><span class="sxs-lookup"><span data-stu-id="fd191-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="fd191-161">Выберите **изображение загрузки (x64)** и выберите **"Свойства".**</span><span class="sxs-lookup"><span data-stu-id="fd191-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="fd191-162">Выберите **вкладку "Источник данных"** и включите развертывание этого изображения загрузки из точки распространения с **поддержкой PXE.**</span><span class="sxs-lookup"><span data-stu-id="fd191-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="fd191-163">Выберите **вкладку "Необязательные компоненты",** чтобы установить необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="fd191-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="fd191-164">Выберите значок звездки и в поиске **по запросу HTML (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="fd191-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="fd191-165">Чтобы **добавить поддержку** HTML-приложений к изображению загрузки, выберите "ОК".</span><span class="sxs-lookup"><span data-stu-id="fd191-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="fd191-166">*Необязательно:* Чтобы настроить параметры развертывания, выберите вкладку **"Настройка".**</span><span class="sxs-lookup"><span data-stu-id="fd191-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="fd191-167">Если **вы хотите** получать доступ к командной подсказке во время развертывания, в этой службе можно включить поддержку (только тестирование).</span><span class="sxs-lookup"><span data-stu-id="fd191-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="fd191-168">Если эта возможность включена, вы можете в любой момент во время развертывания запустить командную команду, наключив **F8.**</span><span class="sxs-lookup"><span data-stu-id="fd191-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="fd191-169">Вы также можете указать собственное фоновое изображение, которое будет отображаться во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="fd191-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="fd191-170">Чтобы задать изображение, в **выберите файл пользовательского фонового изображения (UNC-путь** и укажите фон).</span><span class="sxs-lookup"><span data-stu-id="fd191-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="fd191-171">При запросе выберите **"Да"** и распространить обновленное изображение загрузки по точкам распространения.</span><span class="sxs-lookup"><span data-stu-id="fd191-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="fd191-172">Дополнительные сведения см. в [управлении загрузкой изображений с помощью Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)</span><span class="sxs-lookup"><span data-stu-id="fd191-172">For more information, see [Manage boot images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="fd191-173">Вы можете создать usb-накопитель для загрузки, чтобы запускать последовательности задач Configuration Manager в средах, в которой нет поддержки PXE.</span><span class="sxs-lookup"><span data-stu-id="fd191-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="fd191-174">В загружаемом носитле содержится только изображение загрузки, необязательные предзаписные команды и необходимые файлы, а также файлы в Configuration Manager, поддерживаюющие загрузку в Windows PE и подключение к Configuration Manager до конца процесса развертывания.</span><span class="sxs-lookup"><span data-stu-id="fd191-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="fd191-175">Дополнительные сведения см. в теме ["Создание загружаемого носитела".](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)</span><span class="sxs-lookup"><span data-stu-id="fd191-175">For more information, see [Create bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="fd191-176">Создание пакетов Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fd191-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd191-177">Требуемая версия операционной системы для каждой версии установщика SRS изменяется в каждом выпуске MSI.</span><span class="sxs-lookup"><span data-stu-id="fd191-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="fd191-178">Чтобы определить лучшую версию операционной системы для данного MSI-сервера, запустите сценарий установки консоли один раз.</span><span class="sxs-lookup"><span data-stu-id="fd191-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="fd191-179">Подробнее см. в том, как развернуть [комнаты Microsoft Teams с помощью Microsoft Endpoint Configuration Manager.](rooms-scale.md)</span><span class="sxs-lookup"><span data-stu-id="fd191-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="fd191-180">Для развертывания и настройки комнат Microsoft Teams Manager требуется несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="fd191-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="fd191-181">Необходимо создать и настроить следующие пакеты, а затем распространить их в системах сайтов Configuration Manager, для которых назначена роль сервера точки распространения.</span><span class="sxs-lookup"><span data-stu-id="fd191-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="fd191-182">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="fd191-182">**Package name**</span></span>                     | <span data-ttu-id="fd191-183">**Тип**</span><span class="sxs-lookup"><span data-stu-id="fd191-183">**Type**</span></span>               | <span data-ttu-id="fd191-184">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fd191-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="fd191-185">SRS v2 - SRS Application Package</span><span class="sxs-lookup"><span data-stu-id="fd191-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="fd191-186">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="fd191-186">Software package</span></span>       | <span data-ttu-id="fd191-187">Пакет комплекта для развертывания комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd191-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="fd191-188">SRS v2 — Пакет Sysprep</span><span class="sxs-lookup"><span data-stu-id="fd191-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="fd191-189">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="fd191-189">Software package</span></span>       | <span data-ttu-id="fd191-190">Пакет для настраиваемой Unattended.xml для настройки единиц комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd191-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="fd191-191">SRS v2 - Set-SRSComputerName Package</span><span class="sxs-lookup"><span data-stu-id="fd191-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="fd191-192">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="fd191-192">Software package</span></span>       | <span data-ttu-id="fd191-193">Пакет для HTML-приложения (HTA) для назначения имени компьютера во время развертывания</span><span class="sxs-lookup"><span data-stu-id="fd191-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="fd191-194">SRS v2: настройка установки SRS</span><span class="sxs-lookup"><span data-stu-id="fd191-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="fd191-195">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="fd191-195">Software package</span></span>       | <span data-ttu-id="fd191-196">Пакет для настройки развертывания приложения "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="fd191-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="fd191-197">SRS версии 2 — пакет обновлений ОС</span><span class="sxs-lookup"><span data-stu-id="fd191-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="fd191-198">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="fd191-198">Software package</span></span>       | <span data-ttu-id="fd191-199">Пакет для развертывания обязательных обновлений операционной системы</span><span class="sxs-lookup"><span data-stu-id="fd191-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="fd191-200">SRS v2 — пакет корневого сертификата</span><span class="sxs-lookup"><span data-stu-id="fd191-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="fd191-201">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="fd191-201">Software package</span></span>       | <span data-ttu-id="fd191-202">Необязательно: пакет для развертывания корневого сертификата (не требуется для подразделений, присоединительных к домену)</span><span class="sxs-lookup"><span data-stu-id="fd191-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="fd191-203">Пакет агента мониторинга Майкрософт (SRS) 2</span><span class="sxs-lookup"><span data-stu-id="fd191-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="fd191-204">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="fd191-204">Software package</span></span>       | <span data-ttu-id="fd191-205">Необязательно: пакет для развертывания и настройки агента microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="fd191-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="fd191-206">SRS v2 — фоновый пакет WinPE</span><span class="sxs-lookup"><span data-stu-id="fd191-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="fd191-207">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="fd191-207">Software package</span></span>       | <span data-ttu-id="fd191-208">Пакет для пользовательского фонового изображения для загрузки изображений</span><span class="sxs-lookup"><span data-stu-id="fd191-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="fd191-209">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="fd191-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="fd191-210">Изображение операционной системы</span><span class="sxs-lookup"><span data-stu-id="fd191-210">Operating system image</span></span> | <span data-ttu-id="fd191-211">Пакет для файла установки операционной системы (install.wim)</span><span class="sxs-lookup"><span data-stu-id="fd191-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="fd191-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="fd191-212">Surface Pro</span></span>                          | <span data-ttu-id="fd191-213">Пакет драйвера</span><span class="sxs-lookup"><span data-stu-id="fd191-213">Driver package</span></span>         | <span data-ttu-id="fd191-214">Пакет для драйверов устройств и микропрограмм для Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="fd191-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="fd191-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="fd191-215">Surface Pro 4</span></span>                        | <span data-ttu-id="fd191-216">Пакет драйвера</span><span class="sxs-lookup"><span data-stu-id="fd191-216">Driver package</span></span>         | <span data-ttu-id="fd191-217">Пакет для драйверов устройств и микропрограмм для Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="fd191-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="fd191-218">Дополнительные сведения см. [в сведениях о пакетах и программах в Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="fd191-218">For more information, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="fd191-219">Создание папок для исходных файлов пакета</span><span class="sxs-lookup"><span data-stu-id="fd191-219">Create folders for the package source files</span></span>

<span data-ttu-id="fd191-220">Configuration Manager требует, чтобы исходные файлы пакетов были уорганы в определенную структуру папок при первом их созданном и обновлении.</span><span class="sxs-lookup"><span data-stu-id="fd191-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="fd191-221">Создайте следующую структуру папок на сайте центра администрирования Microsoft Endpoint Configuration Manager или основном сайте либо на сервере, который используется для обмена исходными файлами пакетов:</span><span class="sxs-lookup"><span data-stu-id="fd191-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="fd191-222">Пакет агента мониторинга Майкрософт (SRS) 2</span><span class="sxs-lookup"><span data-stu-id="fd191-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="fd191-223">SRS версии 2 — пакет обновлений ОС</span><span class="sxs-lookup"><span data-stu-id="fd191-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="fd191-224">SRS v2 — пакет корневого сертификата</span><span class="sxs-lookup"><span data-stu-id="fd191-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="fd191-225">SRS v2 - Set-SRSComputerName Package</span><span class="sxs-lookup"><span data-stu-id="fd191-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="fd191-226">SRS v2 - SRS Application Package</span><span class="sxs-lookup"><span data-stu-id="fd191-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="fd191-227">SRS v2: настройка установки SRS</span><span class="sxs-lookup"><span data-stu-id="fd191-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="fd191-228">SRS v2 — Пакет Sysprep</span><span class="sxs-lookup"><span data-stu-id="fd191-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="fd191-229">Драйверы</span><span class="sxs-lookup"><span data-stu-id="fd191-229">Drivers</span></span>
    -   <span data-ttu-id="fd191-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="fd191-230">Surface Pro</span></span>
    -   <span data-ttu-id="fd191-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="fd191-231">Surface Pro 4</span></span>
-   <span data-ttu-id="fd191-232">Операционные системы</span><span class="sxs-lookup"><span data-stu-id="fd191-232">Operating Systems</span></span>
    -   <span data-ttu-id="fd191-233">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="fd191-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="fd191-234">Вы также [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) можете скачать и использовать ZIP-файл со структурой папок для пакетов, нужными сценариями и шаблоном последовательностей задач, которые нужно импортировать.</span><span class="sxs-lookup"><span data-stu-id="fd191-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="fd191-235">Создание пакета агента мониторинга</span><span class="sxs-lookup"><span data-stu-id="fd191-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="fd191-236">Скачайте агент мониторинга из <https://go.microsoft.com/fwlink/?LinkId=828603> .</span><span class="sxs-lookup"><span data-stu-id="fd191-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="fd191-237">Извлекать пакет в папку пакета агента мониторинга **(Майкрософт) SRS v2,** открыв окно команднойMMASetup-AMD64.exe **/C:**     в командной подсказке.</span><span class="sxs-lookup"><span data-stu-id="fd191-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="fd191-238">В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**</span><span class="sxs-lookup"><span data-stu-id="fd191-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="fd191-239">Чтобы создать пакет, введите следующие данные:</span><span class="sxs-lookup"><span data-stu-id="fd191-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="fd191-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span><span class="sxs-lookup"><span data-stu-id="fd191-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="fd191-241">Производитель:<strong>Корпорация Майкрософт</strong></span><span class="sxs-lookup"><span data-stu-id="fd191-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="fd191-242">Версия:<strong>8.1.11081.0</strong> (введите версию загруженного файла установки)</span><span class="sxs-lookup"><span data-stu-id="fd191-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="fd191-243">Выберите этот **пакет содержит исходные** файлы, введите путь к **SRS v2 — папке** пакета агента мониторинга Майкрософт, а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="fd191-244">Выберите **"Не создавать программу",** а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="fd191-245">Просмотрите **страницу "Подтверждение параметров"** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="fd191-246">Выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="fd191-247">Создание пакета обновлений операционной системы</span><span class="sxs-lookup"><span data-stu-id="fd191-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="fd191-248">В папке пакета обновлений **ОС (SRS версии 2)** создайте новый сценарий PowerShell с **именемInstall-SRSv2-OS-Updates.ps1.**</span><span class="sxs-lookup"><span data-stu-id="fd191-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="fd191-249">Скопируйте ниже сценарий в **Install-SRSv2-OS-Updates.ps1** сценарий.</span><span class="sxs-lookup"><span data-stu-id="fd191-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="fd191-250">Вы также можете скачать сценарий Install-SRSv2-OS-Updates.ps1 [здесь.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="fd191-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="fd191-251">Скачайте обязательные пакеты Обновления Windows в ту же папку.</span><span class="sxs-lookup"><span data-stu-id="fd191-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="fd191-252">На момент публикации этой статьи требовалась только статья [KB4056892.](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)</span><span class="sxs-lookup"><span data-stu-id="fd191-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="fd191-253">Проверьте, [нужно ли настраивать консоль](console.md)комнат Microsoft Teams, чтобы узнать, требуются ли какие-либо другие обновления.</span><span class="sxs-lookup"><span data-stu-id="fd191-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="fd191-254">В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**</span><span class="sxs-lookup"><span data-stu-id="fd191-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="fd191-255">Чтобы создать пакет, введите следующие данные:</span><span class="sxs-lookup"><span data-stu-id="fd191-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="fd191-256">Имя: **SRS версии 2 — пакет обновлений ОС**</span><span class="sxs-lookup"><span data-stu-id="fd191-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="fd191-257">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="fd191-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="fd191-258">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="fd191-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="fd191-259">Выберите этот **пакет содержит исходные** файлы, введите путь к папке **SRS версии 2 — Пакет** обновлений ОС, а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="fd191-260">Выберите **"Не создавать программу",** а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="fd191-261">Просмотрите **страницу "Подтверждение параметров"** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="fd191-262">Выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="fd191-263">Создание пакета корневого сертификата (необязательно)</span><span class="sxs-lookup"><span data-stu-id="fd191-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="fd191-264">Этот пакет создается для распространения корневого сертификата для устройств, которые не будут соединены с доменом Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fd191-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="fd191-265">Создайте этот пакет только в том случае, если применяются оба следующих условия:</span><span class="sxs-lookup"><span data-stu-id="fd191-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="fd191-266">Развертывание включает в себя локальное развертывание Lync или Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fd191-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="fd191-267">Единицы комнат Microsoft Teams настроены для работы в группе, а не в составе домена.</span><span class="sxs-lookup"><span data-stu-id="fd191-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="fd191-268">Скопируйте корневой сертификат в папку корневого пакета **сертификатов SRS v2.**</span><span class="sxs-lookup"><span data-stu-id="fd191-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="fd191-269">В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**</span><span class="sxs-lookup"><span data-stu-id="fd191-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="fd191-270">Чтобы создать пакет, введите следующие данные:</span><span class="sxs-lookup"><span data-stu-id="fd191-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="fd191-271">Имя: **SRS v2 — пакет корневого сертификата**</span><span class="sxs-lookup"><span data-stu-id="fd191-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="fd191-272">Производитель: *название вашей организации*</span><span class="sxs-lookup"><span data-stu-id="fd191-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="fd191-273">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="fd191-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="fd191-274">Выберите этот **пакет, содержащий исходные** файлы, введите путь к папке **SRS v2 – Корневой** пакет сертификата и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="fd191-275">Выберите **"Не создавать программу",** а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="fd191-276">Просмотрите **страницу "Подтверждение параметров"** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="fd191-277">Выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="fd191-278">Создание пакета комплекта комплекта для развертывания комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd191-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="fd191-279">Скачайте последнюю версию комплекта **развертывания комнат Microsoft Teams** с рабочей станции и установите <https://go.microsoft.com/fwlink/?linkid=851168> его.</span><span class="sxs-lookup"><span data-stu-id="fd191-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="fd191-280">Скопируйте содержимое **из C: \\ Program Files (x86) \\ Skype Room System Deployment Kit** в папку **SRS V2 - SRS Application Package.**</span><span class="sxs-lookup"><span data-stu-id="fd191-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="fd191-281">В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**</span><span class="sxs-lookup"><span data-stu-id="fd191-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="fd191-282">Чтобы создать пакет, введите следующие данные:</span><span class="sxs-lookup"><span data-stu-id="fd191-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="fd191-283">Имя: **SRS v2 — пакет приложения SRS**</span><span class="sxs-lookup"><span data-stu-id="fd191-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="fd191-284">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="fd191-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="fd191-285">Версия: **3.1.104.0** (введите версию загруженного файла установки)</span><span class="sxs-lookup"><span data-stu-id="fd191-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="fd191-286">Выберите этот **пакет содержит исходные** файлы, введите путь к папке **SRS V2 – SRS Application Package** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="fd191-287">Выберите **"Не создавать программу",** а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="fd191-288">Просмотрите **страницу "Подтверждение параметров"** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="fd191-289">Выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="fd191-290">Создание пакета назначения имени компьютера</span><span class="sxs-lookup"><span data-stu-id="fd191-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="fd191-291">В **SRS v2 - Set-SRSComputerName Package** folder (Пакет пакета) создайте новое HTML-приложение **с именем Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="fd191-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="fd191-292">Скопируйте следующий сценарий в файл **Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="fd191-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="fd191-293">Кроме того, здесь можно скачать файл Set-SRSComputerName.hta. [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="fd191-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="fd191-294">В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**</span><span class="sxs-lookup"><span data-stu-id="fd191-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="fd191-295">Чтобы создать пакет, введите следующие данные:</span><span class="sxs-lookup"><span data-stu-id="fd191-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="fd191-296">Имя: **SRS v2 - Set-SRSComputerName Package**</span><span class="sxs-lookup"><span data-stu-id="fd191-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="fd191-297">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="fd191-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="fd191-298">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="fd191-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="fd191-299">Выберите этот **пакет содержит исходные файлы,** введите путь к **SRS v2 - Set-SRSComputerName package** folder, а затем выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="fd191-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="fd191-300">Выберите **"Не создавать программу",** а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="fd191-301">Просмотрите **страницу "Подтверждение параметров"** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="fd191-302">Выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="fd191-303">Создание пакета Sysprep</span><span class="sxs-lookup"><span data-stu-id="fd191-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="fd191-304">В **папке SRS v2 – Sysprep Package (Пакет Sysprep)** создайте новый XML-файл с **именемUnattend.xml.**</span><span class="sxs-lookup"><span data-stu-id="fd191-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="fd191-305">Скопируйте следующий текст в **Unattend.xml** файл.</span><span class="sxs-lookup"><span data-stu-id="fd191-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="fd191-306">Кроме того, здесь можно скачать Unattend.xml [файл.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="fd191-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="fd191-307">В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**</span><span class="sxs-lookup"><span data-stu-id="fd191-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="fd191-308">Чтобы создать пакет, введите следующие данные:</span><span class="sxs-lookup"><span data-stu-id="fd191-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="fd191-309">Name: **SRS v2 - Sysprep Package**</span><span class="sxs-lookup"><span data-stu-id="fd191-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="fd191-310">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="fd191-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="fd191-311">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="fd191-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="fd191-312">Выберите этот **пакет содержит исходные** файлы, введите путь к папке **SRS v2 – Sysprep Package** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="fd191-313">Выберите **"Не создавать программу",** а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="fd191-314">Просмотрите **страницу "Подтверждение параметров"** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="fd191-315">Выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="fd191-316">Создание пакета Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fd191-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="fd191-317">Получите носителей Windows 10 Корпоративный x64 и скопируйте **файл install.wim** в папку "Операционные системы **Windows \\ 10 Корпоративный".**</span><span class="sxs-lookup"><span data-stu-id="fd191-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="fd191-318">В консоли Configuration Manager  перейдите к изображениям операционной системы "Библиотека программного обеспечения" и выберите \>  \>  **"Добавить изображение операционной системы".**</span><span class="sxs-lookup"><span data-stu-id="fd191-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="fd191-319">Укажите путь к **файлу install.wim,** который вы только что скопировали, и выберите "Далее". </span><span class="sxs-lookup"><span data-stu-id="fd191-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="fd191-320">**Обновив поле "Версия"** в соответствие с номером сборки образа Windows 10 Enterprise, выберите "Далее". </span><span class="sxs-lookup"><span data-stu-id="fd191-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="fd191-321">Просмотрите **страницу "Сведения"** и выберите "Далее". </span><span class="sxs-lookup"><span data-stu-id="fd191-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="fd191-322">Выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-322">Select **Close**.</span></span>

<span data-ttu-id="fd191-323">Дополнительные сведения см. в [видео "Управление изображениями ОС с помощью Configuration Manager".](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)</span><span class="sxs-lookup"><span data-stu-id="fd191-323">For more information, see [Manage OS images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="fd191-324">Создание пакетов драйвера устройства Surface Pro</span><span class="sxs-lookup"><span data-stu-id="fd191-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="fd191-325">Комнаты Microsoft Teams поддерживаются как для Surface Pro, так и для Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="fd191-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="fd191-326">Вам нужно создать пакет драйвера для каждой модели Surface Pro, которая у вас есть в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="fd191-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd191-327">Драйверы должны быть совместимы с сборкой Windows 10 Enterprise и комплектом комплекта для развертывания Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="fd191-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="fd191-328">Дополнительные сведения см. в сведениях о скачии последних [версиях версий версий](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) постройки и драйверов для устройств Surface и [настройке консоли.](console.md)</span><span class="sxs-lookup"><span data-stu-id="fd191-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="fd191-329">Скачайте новейшие драйверы и программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="fd191-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="fd191-330">Для Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="fd191-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="fd191-331">Для Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="fd191-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="fd191-332">Извлеките скачаный драйвер и микропрограммы.</span><span class="sxs-lookup"><span data-stu-id="fd191-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="fd191-333">Откройте окно командной подсказки и введите в нее одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="fd191-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="fd191-334">В консоли Configuration Manager перейдите **к** драйверам операционных систем библиотеки программного обеспечения и выберите \>  \>  **"Импорт драйвера".**</span><span class="sxs-lookup"><span data-stu-id="fd191-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="fd191-335">Выберите "Импорт всех драйверов" на следующем сетевом пути **(UNC),** выберите папку-источник (например, C: _Sources Drivers Surface Pro), а затем выберите \\ \\ \\ **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="fd191-336">На странице **"Укажите** сведения о импортируемых драйверах" выберите все указанные драйверы, а затем выберите "Включить эти драйверы и разрешить их **установку компьютерами".**</span><span class="sxs-lookup"><span data-stu-id="fd191-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="fd191-337">Выберите **"Категории",** создайте новую категорию, которая соответствует модели Surface, выберите "ОК", а затем выберите **"Далее".** </span><span class="sxs-lookup"><span data-stu-id="fd191-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="fd191-338">Выберите **"Новый пакет".**</span><span class="sxs-lookup"><span data-stu-id="fd191-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="fd191-339">Укажите имя пакета, которое соответствует модели Surface Pro, введите путь к папке для хранения файлов пакета драйвера, выберите "ОК" и затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="fd191-340">Убедитесь, **что на** странице загрузок не выбраны изображения загрузки, и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="fd191-341">Выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-341">Select **Close**.</span></span>

11. <span data-ttu-id="fd191-342">Перейдите  в драйверы операционных систем библиотеки программного обеспечения, выберите папку "Создать папку" и введите имя папки, которая соответствует модели Surface Pro, для которую вы только что импортировали \>  \> драйверы. **\>**</span><span class="sxs-lookup"><span data-stu-id="fd191-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="fd191-343">Переместить все импортируемые драйверы в созданную папку, чтобы упростить навигацию и работу.</span><span class="sxs-lookup"><span data-stu-id="fd191-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="fd191-344">Повторите те же действия для других моделей Surface Pro, которые у вас могут быть.</span><span class="sxs-lookup"><span data-stu-id="fd191-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="fd191-345">Дополнительные сведения см. в [сведениях об управлении драйверами в Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers)</span><span class="sxs-lookup"><span data-stu-id="fd191-345">For more information, see [Manage drivers in Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="fd191-346">Создание пакета конфигурации комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd191-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="fd191-347">В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**</span><span class="sxs-lookup"><span data-stu-id="fd191-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="fd191-348">Чтобы создать пакет, введите следующие данные:</span><span class="sxs-lookup"><span data-stu-id="fd191-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="fd191-349">Имя: **SRS v2 — настройка пакета установки SRS**</span><span class="sxs-lookup"><span data-stu-id="fd191-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="fd191-350">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="fd191-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="fd191-351">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="fd191-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="fd191-352">Выберите этот **пакет содержит исходные** файлы, введите путь к **SRS v2 - Настройка папки установки SRS,** а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="fd191-353">Выберите **"Не создавать программу",** а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="fd191-354">Просмотрите **страницу "Подтверждение параметров"** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="fd191-355">Выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="fd191-356">Распространение пакетов Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fd191-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="fd191-357">Все пакеты должны быть распределены на серверы, которые имеют роль точки распространения в иерархии Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fd191-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="fd191-358">Следуйте инструкциям ниже, чтобы начать распространение пакета.</span><span class="sxs-lookup"><span data-stu-id="fd191-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="fd191-359">Распространение пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="fd191-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="fd191-360">В консоли Configuration Manager перейдите **к** пакетам управления приложениями \> **библиотеки** \> **программного обеспечения.**</span><span class="sxs-lookup"><span data-stu-id="fd191-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="fd191-361">Выберите все пакеты программного обеспечения, которые вы хотите распространить, и выберите **"Распространение содержимого".**</span><span class="sxs-lookup"><span data-stu-id="fd191-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="fd191-362">Просмотрите список пакетов и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="fd191-363">Добавьте в список все серверы точек рассылки (или группы точек рассылки, в зависимости от иерархии Configuration Manager), а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="fd191-364">Выберите **"Далее",** а затем выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="fd191-365">Распространение пакетов драйвера.</span><span class="sxs-lookup"><span data-stu-id="fd191-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="fd191-366">В консоли Configuration Manager перейдите **к** пакетам драйвера для операционной системы "Библиотека программного \>  \> **обеспечения".**</span><span class="sxs-lookup"><span data-stu-id="fd191-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="fd191-367">Выберите все пакеты драйверов, которые вы хотите распространить, и выберите **"Распространение содержимого".**</span><span class="sxs-lookup"><span data-stu-id="fd191-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="fd191-368">Просмотрите список пакетов и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="fd191-369">Добавьте в список все серверы точек рассылки (или группы точек рассылки, в зависимости от иерархии Configuration Manager), а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="fd191-370">Выберите **"Далее",** а затем выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="fd191-371">Распространение пакетов операционной системы.</span><span class="sxs-lookup"><span data-stu-id="fd191-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="fd191-372">В консоли Configuration Manager  перейдите к изображениям операционной системы "Библиотека программного \>  \> **обеспечения".**</span><span class="sxs-lookup"><span data-stu-id="fd191-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="fd191-373">Выберите все изображения операционной системы, которые вы хотите распространить, и выберите **"Распространение содержимого".**</span><span class="sxs-lookup"><span data-stu-id="fd191-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="fd191-374">Просмотрите список пакетов и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="fd191-375">Добавьте в список все серверы точек рассылки (или группы точек рассылки, в зависимости от иерархии Configuration Manager), а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="fd191-376">Выберите **"Далее",** а затем выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="fd191-377">Распространение пакетов может занять некоторое время в зависимости от размера пакета, иерархии Configuration Manager, количества серверов точек рассылки и пропускной способности, доступной в сети.</span><span class="sxs-lookup"><span data-stu-id="fd191-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="fd191-378">Перед началом развертывания комнат Microsoft Teams необходимо распределить все пакеты.</span><span class="sxs-lookup"><span data-stu-id="fd191-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="fd191-379">Вы можете просмотреть состояние распространения пакета в консоли Configuration Manager, на панели **мониторинга** состояния \>  \> **распространения содержимого.**</span><span class="sxs-lookup"><span data-stu-id="fd191-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="fd191-380">Последовательности задач Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fd191-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="fd191-381">С помощью Configuration Manager вы можете автоматизировать действия по развертыванию образа операционной системы на целевом компьютере с помощью последовательностей задач.</span><span class="sxs-lookup"><span data-stu-id="fd191-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="fd191-382">Для автоматического развертывания комнат Microsoft Teams необходимо создать последовательность задач, которая ссылается на изображение загрузки, используемого для запуска целевого компьютера комнат Microsoft Teams, образа операционной системы Windows 10 корпоративная, а также любое другое содержимое, например другие приложения или обновления программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="fd191-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="fd191-383">Импорт примеров последовательностей задач</span><span class="sxs-lookup"><span data-stu-id="fd191-383">Import the sample task sequence</span></span>

<span data-ttu-id="fd191-384">Вы можете легко скачать и импортировать образец последовательности задач и настроить его в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="fd191-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="fd191-385">[**Скачайте**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) образец последовательности задач и скопируйте скачаный ZIP-файл в общую папку.</span><span class="sxs-lookup"><span data-stu-id="fd191-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="fd191-386">В консоли Configuration Manager  перейдите к последовательностям задач "Библиотека программного обеспечения" операционной системы, а затем выберите \>  \>  **"Импорт последовательности задач".**</span><span class="sxs-lookup"><span data-stu-id="fd191-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="fd191-387">Выберите **"Обзор",** перейдите к общей папке, которая использовалась в шаге 1, выберите развертывание комнат **Microsoft Teams (ZIP-файл)** и затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="fd191-388">Выберите действие **"Создать", а** затем выберите **"Далее".** </span><span class="sxs-lookup"><span data-stu-id="fd191-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="fd191-389">Подтвердив параметры, а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="fd191-390">Выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="fd191-391">Проверьте правильность связей пакетов ссылок с каждым этапом последовательности задач.</span><span class="sxs-lookup"><span data-stu-id="fd191-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="fd191-392">Выберите последовательность импортируемых задач и выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="fd191-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="fd191-393">Откроется редактор последовательностей задач с каждым последовательным этапом, который необходимо развернуть и настроить в microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="fd191-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="fd191-394">Выполните все этапы и выполните рекомендуемые обновления.</span><span class="sxs-lookup"><span data-stu-id="fd191-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="fd191-395">**Перезапустите в Windows PE:** перезагрузите компьютер и загрузите его в Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="fd191-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="fd191-396">Для этого шага не требуется никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="fd191-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="fd191-397">**Диск partition 0 — UEFI**: этот шаг протирает конфигурацию диска и создает разделы на основе настроенных параметров.</span><span class="sxs-lookup"><span data-stu-id="fd191-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="fd191-398">Мы не рекомендуем вносить изменения в этот шаг.</span><span class="sxs-lookup"><span data-stu-id="fd191-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="fd191-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span><span class="sxs-lookup"><span data-stu-id="fd191-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="fd191-400">Это необязательный шаг, но его можно отключить только в том случае, если вы хотите управлять именой компьютера с помощью альтернативного процесса.</span><span class="sxs-lookup"><span data-stu-id="fd191-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="fd191-401">Убедитесь, что выбран **пакет SRS v2 Set-SRSComputerName.**</span><span class="sxs-lookup"><span data-stu-id="fd191-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="fd191-402">Если это не так, перейдите к пакету и выберите его.</span><span class="sxs-lookup"><span data-stu-id="fd191-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="fd191-403">**Применение операционной** системы: на этом шаге заданы развертывание образа операционной системы и несмежный Sysprep answer file to use.</span><span class="sxs-lookup"><span data-stu-id="fd191-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="fd191-404">Убедитесь, что выбран правильный файл образа операционной системы Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="fd191-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="fd191-405">Убедитесь, что для пользовательской установки включено использование неотвеченного или **Sysprep-ответа,** а также выбран пакет **SRS v2 - Sysprep Package.**</span><span class="sxs-lookup"><span data-stu-id="fd191-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="fd191-406">Убедитесь, **что для** имени файла установлено **unattend.xml.**</span><span class="sxs-lookup"><span data-stu-id="fd191-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="fd191-407">**Применение параметров Windows:** на этом этапе собираются сведения об установке Windows.</span><span class="sxs-lookup"><span data-stu-id="fd191-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="fd191-408">Включите сведения о лицензировании и регистрации, включая ключ продукта, пароль локальной учетной записи администратора и часовой пояс (в зависимости от потребностей).</span><span class="sxs-lookup"><span data-stu-id="fd191-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="fd191-409">**Применение параметров сети:** на этом этапе можно указать имя или доменное имя домена Active Directory или подразделение Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fd191-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="fd191-410">Дополнительные рекомендации по развертыванию комнат Microsoft Teams в качестве участников домена Actve Directory см. в вопросах о присоединении к домену системы комнат [Skype.](domain-joining-considerations.md)</span><span class="sxs-lookup"><span data-stu-id="fd191-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="fd191-411">**Применение драйверов:** Этот шаг и его подпрограммы используются для развертывания драйверов устройств и вычитаемого ПО на основе модели Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="fd191-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="fd191-412">Обновив каждый шаг, укажите соответствующий пакет драйвера, связанный с этим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="fd191-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="fd191-413">Каждый пакет драйвера настроен для использования фильтров WMI для развертывания соответствующих драйверов и постройки на основе моделей и моделей Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="fd191-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="fd191-414">Настоятельно рекомендуем не изменять конфигурацию этих драйверов, иначе развертывание может привести к сбой.</span><span class="sxs-lookup"><span data-stu-id="fd191-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="fd191-415">**Настройка Windows и Configuration Manager:** на этом этапе развертывается и настраивается клиент Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fd191-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="fd191-416">Обновив этот шаг, укажите встроенный пакет клиента Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fd191-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="fd191-417">**Установка корневого** сертификата. Этот шаг распространяет корневой сертификат для устройств, не присоединивательных к домену, и поэтому является необязательным и отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd191-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="fd191-418">В этом случае вам потребуется развернуть корневой сертификат в блоках комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd191-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="fd191-419">Если вам нужно сделать это, убедитесь, что выбраны **SRS V2 —** пакет корневых сертификатов и отключение перенаправления **64-битной** файловой системы.</span><span class="sxs-lookup"><span data-stu-id="fd191-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="fd191-420">**Установка и настройка** агента мониторинга. На этом этапе устанавливается 64-битная версия агента Microsoft Azure Monitor и настраивается подключение агента к рабочей области аналитики журналов.</span><span class="sxs-lookup"><span data-stu-id="fd191-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="fd191-421">Этот шаг по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="fd191-421">This step is disabled by default.</span></span> <span data-ttu-id="fd191-422">Этот шаг можно включить только в том случае, если вы собираетесь использовать агента мониторинга для отслеживания состояния комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd191-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="fd191-423">Отредактйте этот шаг и обновите параметры командной строки, указав свой **ИД** рабочей области и **ключ рабочей области.**</span><span class="sxs-lookup"><span data-stu-id="fd191-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="fd191-424">Дополнительные [сведения о получении ИД](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) рабочей области набора операций и первичного ключа см. в сведениях о настройке тестовых устройств для мониторинга Azure.</span><span class="sxs-lookup"><span data-stu-id="fd191-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="fd191-425">Убедитесь, что выбраны пакет агента мониторинга Майкрософт **(SRS 2)** и отключено перенаправление **64-битной** файловой системы.</span><span class="sxs-lookup"><span data-stu-id="fd191-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="fd191-426">Дополнительные сведения о мониторинге состояния развертывания комнат Microsoft Teams см. в планах управления комнатами Microsoft Teams с помощью [Azure Monitor,](azure-monitor-plan.md)развертывании управления комнатами [Microsoft Teams](azure-monitor-deploy.md) с помощью устройств Azure Monitor и управления устройствами комнат Microsoft Teams с помощью [Azure Monitor.](azure-monitor-manage.md)</span><span class="sxs-lookup"><span data-stu-id="fd191-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="fd191-427">**Копирование SRS файлов конфигурации v2:** на этом этапе необходимые файлы настройки и настройки копируется из комплекта развертывания Microsoft Teams Rooms на локальный жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="fd191-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="fd191-428">Для этого шага не требуется никаких настроек.</span><span class="sxs-lookup"><span data-stu-id="fd191-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="fd191-429">Убедитесь, что выбраны пакет приложений **SRS v2 — SRS Application Package** и **Disable 64-bit file system redirection (Отключить 64-битную** файловую систему).</span><span class="sxs-lookup"><span data-stu-id="fd191-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="fd191-430">**Install-SRSv2-OS-Updates:** на этом этапе развертываются все обязательные обновления операционной системы, необходимые для развертывания комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd191-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="fd191-431">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fd191-431">Do the following:</span></span>
       -   <span data-ttu-id="fd191-432">Проверьте, какие обновления необходимы для настройки консоли комнат [Microsoft Teams.](console.md)</span><span class="sxs-lookup"><span data-stu-id="fd191-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="fd191-433">Убедитесь, что пакет обновлений ОС версии **2 (SRS версии 2)** включает все необходимые обновления.</span><span class="sxs-lookup"><span data-stu-id="fd191-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="fd191-434">Убедитесь, что выбран **пакет обновлений SRS версии 2 —OS.**</span><span class="sxs-lookup"><span data-stu-id="fd191-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="fd191-435">Убедитесь, что политика выполнения PowerShell настроена на **"Обход".**</span><span class="sxs-lookup"><span data-stu-id="fd191-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="fd191-436">**Перезагрузите** компьютер: этот шаг перезагрузит компьютер после установки обязательных обновлений операционной системы.</span><span class="sxs-lookup"><span data-stu-id="fd191-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="fd191-437">Для этого шага не требуется никаких настроек.</span><span class="sxs-lookup"><span data-stu-id="fd191-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="fd191-438">**Настройка компонентов Windows:** на этом этапе настроены необходимые функции Windows.</span><span class="sxs-lookup"><span data-stu-id="fd191-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="fd191-439">Для этого шага не требуется никаких настроек.</span><span class="sxs-lookup"><span data-stu-id="fd191-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="fd191-440">**Перезагрузите** компьютер: этот шаг перезагрузит компьютер после настройки компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="fd191-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="fd191-441">Для этого шага не требуется никаких настроек.</span><span class="sxs-lookup"><span data-stu-id="fd191-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="fd191-442">**Добавить локального пользователя Skype:** на этом шаге создается локализованная учетная запись Skype, которая используется для автоматического входов в Windows и запуска приложения комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd191-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="fd191-443">Этот шаг не связан с программным пакетом, и для него не требуется его настройка.</span><span class="sxs-lookup"><span data-stu-id="fd191-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="fd191-444">**Настройка приложения SRS:** на этом этапе настроена установка приложения комнат Microsoft Teams для следующего загрузки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="fd191-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="fd191-445">Убедитесь, что выбраны **SRS v2 — настройка пакета установки SRS** и отключение перенаправления **64-битной** файловой системы.</span><span class="sxs-lookup"><span data-stu-id="fd191-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd191-446">Очень важно, чтобы шаги последовательности задач были должны быть упорядочены в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="fd191-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="fd191-447">Изменение порядка шагов или настройка дополнительных действий может нарушить развертывание.</span><span class="sxs-lookup"><span data-stu-id="fd191-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="fd191-448">**Настройка приложения SRS** должна быть последним этапом в последовательности задач, иначе развертывание может привести к сбойу.</span><span class="sxs-lookup"><span data-stu-id="fd191-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="fd191-449">Создание развертывания для последовательности задач</span><span class="sxs-lookup"><span data-stu-id="fd191-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="fd191-450">Выберите последовательность задач, а затем выберите **"Развернуть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="fd191-451">Выберите **целевую** коллекцию для развертывания, на ленте выберите "Обзор".</span><span class="sxs-lookup"><span data-stu-id="fd191-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="fd191-452">Выберите **"Все неизвестные компьютеры"** и выберите "ОК". </span><span class="sxs-lookup"><span data-stu-id="fd191-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="fd191-453">Выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-453">Select **Next**.</span></span>

5. <span data-ttu-id="fd191-454">В **списке** "Назначение" **выберите "Доступен".**</span><span class="sxs-lookup"><span data-stu-id="fd191-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="fd191-455">В списке "Сделать доступными" выберите "Только мультимедиа" и **"PXE",** а затем выберите **"Далее".** </span><span class="sxs-lookup"><span data-stu-id="fd191-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="fd191-456">Очень важно, чтобы **для назначения** было установлено значение "В **наличии".**</span><span class="sxs-lookup"><span data-stu-id="fd191-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="fd191-457">Убедитесь, что **для назначения** **не** установлено **обязательное назначение.**</span><span class="sxs-lookup"><span data-stu-id="fd191-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="fd191-458">Кроме того, убедитесь, что в области "Сделать доступными" выбраны только мультимедиа и **PXE.**</span><span class="sxs-lookup"><span data-stu-id="fd191-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="fd191-459">Если установить для этих значений другое значение, все компьютеры могут получить изображение развертывания комнат Microsoft Teams при загрузке.</span><span class="sxs-lookup"><span data-stu-id="fd191-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="fd191-460">Не укажите расписание и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="fd191-461">Не изменяя ничего в разделе **"Пользовательский интерфейс",** выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="fd191-462">Не изменяя ничего в разделе **"Оповещения",** выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="fd191-463">Не изменяя ничего в разделе **"Точки** распространения", выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="fd191-464">Подтвердив параметры, а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="fd191-465">Выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd191-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="fd191-466">Проверка и устранение неполадок с решением</span><span class="sxs-lookup"><span data-stu-id="fd191-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="fd191-467">После завершения последовательностей задач Microsoft Endpoint Configuration Manager необходимо выполнить тестовый запуск, чтобы проверить возможность развертывания и настройки единиц помещения Microsoft Teams в последовательности задач.</span><span class="sxs-lookup"><span data-stu-id="fd191-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="fd191-468">Подключите тестовое устройство к проводной сети с помощью одного из поддерживаемых адаптеров Ethernet или док-станции Surface.</span><span class="sxs-lookup"><span data-stu-id="fd191-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="fd191-469">Если функция загрузки PXE не настроена для вашей среды, вы можете использовать [](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) изображение загрузки на USB-устройстве флэш-памяти, созданном ранее, для загрузки с USB и подключения к Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fd191-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="fd191-470">Доступ к пошива и начало загрузки PXE:</span><span class="sxs-lookup"><span data-stu-id="fd191-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="fd191-471">Убедитесь, что устройство Surface выключено.</span><span class="sxs-lookup"><span data-stu-id="fd191-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="fd191-472">Нажмите и удерживайте **кнопку "Вверх".**</span><span class="sxs-lookup"><span data-stu-id="fd191-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="fd191-473">Нажмите и отпустите **кнопку питания.**</span><span class="sxs-lookup"><span data-stu-id="fd191-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="fd191-474">Когда устройство начнет загрузку, отпустите **кнопку "Вверх".**</span><span class="sxs-lookup"><span data-stu-id="fd191-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="fd191-475">Выберите **конфигурацию загрузки.**</span><span class="sxs-lookup"><span data-stu-id="fd191-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="fd191-476">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="fd191-476">Do one of the following:</span></span>

        -   <span data-ttu-id="fd191-477">Выберите **загрузку PXE** и перетащите ее в верхнюю часть списка.</span><span class="sxs-lookup"><span data-stu-id="fd191-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="fd191-478">Кроме того, вы можете провести пальцем влево по сетевому адаптеру, чтобы сразу же загрузить устройство.</span><span class="sxs-lookup"><span data-stu-id="fd191-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="fd191-479">Это не повлияет на порядок загрузки.</span><span class="sxs-lookup"><span data-stu-id="fd191-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="fd191-480">Выберите USB-устройство флэш-памяти, которое содержит мультимедиа загрузки.</span><span class="sxs-lookup"><span data-stu-id="fd191-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="fd191-481">Выберите **"Выйти"** и **"Перезапустить сейчас".**</span><span class="sxs-lookup"><span data-stu-id="fd191-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="fd191-482">При запросе выберите ввод **для службы** загрузки сети.</span><span class="sxs-lookup"><span data-stu-id="fd191-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="fd191-483">Windows PE загрузит в память, и запустится мастер последовательностей задач.</span><span class="sxs-lookup"><span data-stu-id="fd191-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="fd191-484">Чтобы **продолжить, выберите** "Далее".</span><span class="sxs-lookup"><span data-stu-id="fd191-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="fd191-485">Выберите последовательность задач, импортируемую ранее, и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd191-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="fd191-486">После настройки диска вам будет предложено указать имя компьютера для устройства.</span><span class="sxs-lookup"><span data-stu-id="fd191-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="fd191-487">В пользовательском интерфейсе будет отображаться рекомендуемое имя компьютера в зависимости от серийного номера устройства Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="fd191-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="fd191-488">Вы можете принять предложенное имя или указать новое.</span><span class="sxs-lookup"><span data-stu-id="fd191-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="fd191-489">Следуйте инструкциям на экране назначения имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="fd191-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="fd191-490">Когда вы на **выберете "Принять",** начнется развертывание.</span><span class="sxs-lookup"><span data-stu-id="fd191-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="fd191-491">Остальная часть процесса развертывания является автоматической, и пользователю больше не нужно ничего вводить.</span><span class="sxs-lookup"><span data-stu-id="fd191-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="fd191-492">Когда последовательность задач развертывания завершит настройку устройства, вы увидите следующий экран конфигурации с запросом на настройку параметров приложения комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd191-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Экран начальной настройки для приложения комнат Microsoft Teams](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="fd191-494">Подключите Surface Pro к консоли комнат Microsoft Teams и настройте параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="fd191-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="fd191-495">Проверьте возможности, перечисленные в справке [по комнатам Microsoft Teams,](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) на развернутом устройстве.</span><span class="sxs-lookup"><span data-stu-id="fd191-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="fd191-496">Чтобы устранить неполадки при сбойной установке, проверьте файл **SMSTS.log,** в котором регистрются все действия, выполненные в последовательности задач Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fd191-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="fd191-497">Файл SMSTS.log хранится по одному из нескольких путей в зависимости от этапа построения.</span><span class="sxs-lookup"><span data-stu-id="fd191-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="fd191-498">В таблице ниже идентифицировать путь к файлу SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="fd191-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="fd191-499">**Этап развертывания**</span><span class="sxs-lookup"><span data-stu-id="fd191-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="fd191-500">**Путь к журналу последовательностей задач**</span><span class="sxs-lookup"><span data-stu-id="fd191-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="fd191-501">WinPE до формата HDD</span><span class="sxs-lookup"><span data-stu-id="fd191-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="fd191-502">X: \\ \\ SMS-сообщения в Windows \\ Temp \\</span><span class="sxs-lookup"><span data-stu-id="fd191-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="fd191-503">WinPE после формата HDD</span><span class="sxs-lookup"><span data-stu-id="fd191-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="fd191-504">В. \\ _SMSTaskSequence \\ записи \\ SMS-сообщений \\ smstslog.log</span><span class="sxs-lookup"><span data-stu-id="fd191-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="fd191-505">Развернута операционная система до установки агента Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fd191-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="fd191-506">в. \\ _SMSTaskSequence \\ записи \\ SMS-сообщений \\ smstslog.log</span><span class="sxs-lookup"><span data-stu-id="fd191-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="fd191-507">Развернуты операционная система и агент Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fd191-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="fd191-508">%windir% \\ System32 \\ ccm \\ регистрет \\ Smstslog \\ SMSts.log</span><span class="sxs-lookup"><span data-stu-id="fd191-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="fd191-509">Последовательность задач завершена</span><span class="sxs-lookup"><span data-stu-id="fd191-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="fd191-510">%windir% \\ System32 \\ ccm \\ \\ регистрет smsts.log</span><span class="sxs-lookup"><span data-stu-id="fd191-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="fd191-511">Во время последовательности задач можно в любой момент выбрать **F8,** чтобы открыть консоль команд, а затем получить доступ к файлу SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="fd191-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="fd191-512">Чтобы устранить проблемы с загрузкой PXE, проверьте два файла журнала на сервере Configuration Manager, которые имеют определенные действия с PXE:</span><span class="sxs-lookup"><span data-stu-id="fd191-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="fd191-513">**Pxecontrol.log,** который находится в каталоге журналов установки Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fd191-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="fd191-514">**Smspxe.log**, расположенный в каталоге MP</span><span class="sxs-lookup"><span data-stu-id="fd191-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="fd191-515">Полный список файлов журнала, которые можно использовать для дальнейшего устранения неполадок при [](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)установке Configuration Manager, см. в справочнике по файлу журнала Диспетчера конфигураций Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd191-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files).</span></span>
