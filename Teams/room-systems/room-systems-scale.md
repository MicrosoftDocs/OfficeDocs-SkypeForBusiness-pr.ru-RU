---
title: Развертывание комнат Microsoft Teams с помощью System Center Configuration Manager
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Ознакомьтесь с этой статьей, чтобы узнать о том, как развертываются комнаты Microsoft Teams при больших масштабах развертывания.
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
ms.openlocfilehash: c8d460f4ad94adaccce9fb84b12e37ab5adc0cc6
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952752"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a><span data-ttu-id="77369-103">Развертывание комнат Microsoft Teams с помощью System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="77369-103">Deploy Microsoft Teams Rooms by using System Center Configuration Manager</span></span>

<span data-ttu-id="77369-104">В этой статье приведены все необходимые сведения для создания развертывания комнат Microsoft Teams с помощью System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="77369-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="77369-105">Благодаря простым в использовании методам, предоставляемым System Center Configuration Manager, вы можете развернуть операционную систему и другие приложения на нескольких целевых устройствах.</span><span class="sxs-lookup"><span data-stu-id="77369-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="77369-106">Используйте описанный ниже подход, чтобы пошагово настроить конфигурацию Configuration Manager, и настройте образцы пакетов и сценарии, предоставленные в этом руководстве для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="77369-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Процесс развертывания комнат Microsoft Teams с помощью Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="77369-108">Это решение было проверено только с развертываниями на основе Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="77369-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="77369-109">Следуйте указаниям производителя для конфигураций, которые не основаны на Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="77369-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="77369-110">Проверка предварительных требований</span><span class="sxs-lookup"><span data-stu-id="77369-110">Validate prerequisites</span></span>

<span data-ttu-id="77369-111">Для развертывания комнат Microsoft Teams с помощью Configuration Manager убедитесь, что выполняются следующие необходимые условия и требования.</span><span class="sxs-lookup"><span data-stu-id="77369-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="77369-112">Требования System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="77369-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="77369-113">Версия System Center Configuration Manager должна составлять не менее 1706 или выше.</span><span class="sxs-lookup"><span data-stu-id="77369-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="77369-114">Рекомендуем использовать 1710 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="77369-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="77369-115">Чтобы узнать о версиях Windows 10, поддерживаемых Configuration Manager, ознакомьтесь со статьей [поддержки Windows 10 в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) .</span><span class="sxs-lookup"><span data-stu-id="77369-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="77369-116">Должна быть установлена поддерживаемая версия комплекта средств для развертывания и оценки Windows (ADK) для Windows 10.</span><span class="sxs-lookup"><span data-stu-id="77369-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="77369-117">Ознакомьтесь с версиями [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) , которые можно использовать с различными версиями Configuration Manager, и убедитесь в том, что развертывание включает соответствующую версию.</span><span class="sxs-lookup"><span data-stu-id="77369-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="77369-118">Серверам системы сайта должна быть назначена роль точки распространения, и для [поддержки удаленной загрузки для развертывания в среде предзагрузочной среды (PXE)](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) необходимо включить образы загрузки.</span><span class="sxs-lookup"><span data-stu-id="77369-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="77369-119">Если поддержка PXE не включена, вы можете использовать [загрузочный носитель](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертывания.</span><span class="sxs-lookup"><span data-stu-id="77369-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="77369-120">Учетная запись сетевого доступа должна быть настроена для поддержки новых сценариев развертывания компьютера (исходного состояния).</span><span class="sxs-lookup"><span data-stu-id="77369-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="77369-121">Дополнительные сведения о настройке учетной записи для доступа к сети можно найти [в статье Управление учетными записями для доступа к содержимому в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="77369-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="77369-122">Мы рекомендуем включить [поддержку многоадресной рассылки](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), если вы наверняка хотите развернуть один и тот же образ Microsoft Teams в нескольких блоках одновременно.</span><span class="sxs-lookup"><span data-stu-id="77369-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="77369-123">Требования к сети</span><span class="sxs-lookup"><span data-stu-id="77369-123">Networking requirements</span></span>

-   <span data-ttu-id="77369-124">В сети должен быть сервер DHCP (Dynamic Host Configuration Protocol), настроенный для автоматического распространения IP-адресов в подсети, в которых будут развернуты единицы комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77369-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="77369-125">Продолжительность аренды DHCP должна быть больше, чем продолжительность развертывания образа.</span><span class="sxs-lookup"><span data-stu-id="77369-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="77369-126">В противном случае развертывание может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="77369-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="77369-127">Сеть, в том числе коммутаторы и виртуальные ЛВС (VLAN), должна быть настроена для поддержки PXE.</span><span class="sxs-lookup"><span data-stu-id="77369-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="77369-128">За дополнительными сведениями о модулях поддержки IP и конфигурации PXE обратитесь к поставщику сети.</span><span class="sxs-lookup"><span data-stu-id="77369-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="77369-129">Кроме того, если поддержка PXE не включена, вы можете использовать [загрузочный носитель](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертывания.</span><span class="sxs-lookup"><span data-stu-id="77369-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="77369-130">Для устройств Surface Pro Загрузка из сети (PXE) поддерживается только при использовании адаптера Ethernet или стыковочных станций от корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="77369-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="77369-131">Сторонние адаптеры Ethernet не поддерживают загрузку PXE с Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="77369-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="77369-132">Дополнительные сведения см. в разделе [адаптеры Ethernet и развертывание Surface](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="77369-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="77369-133">Настройка System Center Configuration Manager для развертывания операционной системы</span><span class="sxs-lookup"><span data-stu-id="77369-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="77369-134">В этой статье предполагается, что у вас уже есть работоспособное развертывание System Center Configuration Manager, а не все этапы, необходимые для развертывания и настройки Configuration Manager с нуля.</span><span class="sxs-lookup"><span data-stu-id="77369-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="77369-135">[Документация и руководство по конфигурации](https://docs.microsoft.com/sccm/) в System Center Configuration Manager — это отличный ресурс. Если вы еще не развернули Диспетчер конфигураций, мы рекомендуем вам приступить к этим ресурсам.</span><span class="sxs-lookup"><span data-stu-id="77369-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="77369-136">Чтобы убедиться в правильности настройки функций развертывания операционной системы (OSD), выполните указанные ниже инструкции.</span><span class="sxs-lookup"><span data-stu-id="77369-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="77369-137">Проверка и обновление Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="77369-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="77369-138">На консоли Configuration Manager перейдите в раздел **Администрирование** \> **обновлений и обслуживание**.</span><span class="sxs-lookup"><span data-stu-id="77369-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="77369-139">Проверьте установленную сборку и применимые обновления, которые еще не установлены.</span><span class="sxs-lookup"><span data-stu-id="77369-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="77369-140">Ознакомьтесь со [службой поддержки Windows 10 в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Если вам нужно обновить развертывание, выберите обновление, которое вы хотите установить, и нажмите кнопку **скачать**.</span><span class="sxs-lookup"><span data-stu-id="77369-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="77369-141">После завершения загрузки выберите обновление и щелкните **установить пакет обновления**.</span><span class="sxs-lookup"><span data-stu-id="77369-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="77369-142">Настройка точек распространения для поддержки PXE и многоадресной рассылки</span><span class="sxs-lookup"><span data-stu-id="77369-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="77369-143">На консоли Configuration Manager перейдите в раздел **точки распространения** **администрирования** \> .</span><span class="sxs-lookup"><span data-stu-id="77369-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="77369-144">Выберите сервер точки распространения, который будет обслуживать развертывание комнат Microsoft Teams, и нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="77369-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="77369-145">Откройте вкладку **PXE** и убедитесь, что включены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="77369-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="77369-146">Включение поддержки PXE для клиентов</span><span class="sxs-lookup"><span data-stu-id="77369-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="77369-147">Разрешить этой точке распространения отвечать на входящие запросы PXE</span><span class="sxs-lookup"><span data-stu-id="77369-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="77369-148">Включение неизвестной поддержки компьютера</span><span class="sxs-lookup"><span data-stu-id="77369-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="77369-149">*Необязательно:* Чтобы включить поддержку многоадресной рассылки, откройте вкладку **многоадресная рассылка** и убедитесь, что включены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="77369-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="77369-150">Одновременная отправка данных нескольким клиентам с помощью многоадресной рассылки</span><span class="sxs-lookup"><span data-stu-id="77369-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="77369-151">Настройка диапазона UDP-портов согласно рекомендациям сетевой группы</span><span class="sxs-lookup"><span data-stu-id="77369-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="77369-152">Настройка учетной записи доступа к сети</span><span class="sxs-lookup"><span data-stu-id="77369-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="77369-153">На консоли Configuration Manager перейдите на \> **сайт** **конфигурации сайта** **администрирования** \> , а затем выберите сайт.</span><span class="sxs-lookup"><span data-stu-id="77369-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="77369-154">В группе **Параметры** выберите пункт Настройка \> **распространения программного обеспечения** **компонентов сайта** .</span><span class="sxs-lookup"><span data-stu-id="77369-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="77369-155">Откройте вкладку **учетная запись сетевого доступа** . Настройте одну или несколько учетных записей, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="77369-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="77369-156">Для учетных записей не требуются никакие специальные права, Кроме того, чтобы **получить доступ к этому компьютеру прямо из сети** на сервере точки распространения.</span><span class="sxs-lookup"><span data-stu-id="77369-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="77369-157">Будет подходящимся универсальная учетная запись пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="77369-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="77369-158">Дополнительные сведения [можно найти в разделе Управление учетными записями для доступа к содержимому в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="77369-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="77369-159">Настройка загрузочного образа</span><span class="sxs-lookup"><span data-stu-id="77369-159">Configure a boot image</span></span>

1.  <span data-ttu-id="77369-160">В консоли Configuration Manager перейдите в раздел **загрузочные образы** **операционной системы** \> для **разработчиков программного обеспечения** \> .</span><span class="sxs-lookup"><span data-stu-id="77369-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="77369-161">Выберите пункт **загрузочный образ (x64)** и нажмите кнопку **свойства**.</span><span class="sxs-lookup"><span data-stu-id="77369-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="77369-162">Откройте вкладку **источник данных** и включите **развертывание этого загрузочного образа из точки распространения с поддержкой PXE**.</span><span class="sxs-lookup"><span data-stu-id="77369-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="77369-163">Выберите вкладку **Дополнительные компоненты** , чтобы установить необходимые компоненты:</span><span class="sxs-lookup"><span data-stu-id="77369-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="77369-164">Щелкните значок звездочки и выполните поиск по запросу **HTML (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="77369-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="77369-165">Нажмите кнопку **ОК** , чтобы добавить поддержку HTML-приложений в загрузочный образ.</span><span class="sxs-lookup"><span data-stu-id="77369-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="77369-166">*Необязательно:* Чтобы настроить взаимодействие с развертыванием, откройте вкладку **Настройка** .</span><span class="sxs-lookup"><span data-stu-id="77369-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="77369-167">Включите **поддержку команд (только для проверки)** , если вы хотите получать доступ к командной строке во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="77369-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="77369-168">Если этот параметр включен, вы можете запустить командную команду, выбрав **F8** в любое время развертывания.</span><span class="sxs-lookup"><span data-stu-id="77369-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="77369-169">Вы также можете указать собственное фоновое изображение, которое будет отображаться во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="77369-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="77369-170">Чтобы задать изображение, включите параметр **задать настраиваемый файл фонового изображения (путь UNC** и выберите фоновый рисунок).</span><span class="sxs-lookup"><span data-stu-id="77369-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="77369-171">При появлении запроса выберите **Да** , чтобы распространить обновленный образ загрузки на точки распространения.</span><span class="sxs-lookup"><span data-stu-id="77369-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="77369-172">Дополнительные сведения можно найти [в разделе Управление загрузочными образами с помощью System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="77369-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="77369-173">Вы можете создать загрузочный USB-носитель для запуска развертываний на основе последовательности задач Configuration Manager для сред без поддержки PXE.</span><span class="sxs-lookup"><span data-stu-id="77369-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="77369-174">Загрузочный носитель включает только загрузочный образ, необязательные команды предзапуска и их обязательные файлы, а также двоичные данные Configuration Manager для поддержки загрузки в Windows PE и подключения к Configuration Manager для оставшейся части процесса развертывания.</span><span class="sxs-lookup"><span data-stu-id="77369-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="77369-175">Дополнительные сведения [можно найти в разделе Создание загрузочного носителя](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="77369-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="77369-176">Создание пакетов Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="77369-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77369-177">Обязательная версия операционной системы для каждой версии установщика SRS меняется при каждом выпуске MSI-файла.</span><span class="sxs-lookup"><span data-stu-id="77369-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="77369-178">Чтобы определить самую подходящее версию операционной системы для данного MSI-файла, запустите сценарий настройки консоли один раз.</span><span class="sxs-lookup"><span data-stu-id="77369-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="77369-179">Дополнительные сведения можно найти в разделе [развертывание комнат Microsoft Teams с помощью System Center Configuration Manager](room-systems-scale.md).</span><span class="sxs-lookup"><span data-stu-id="77369-179">To learn more, see [Deploy Microsoft Teams Rooms by using System Center Configuration Manager](room-systems-scale.md).</span></span>

<span data-ttu-id="77369-180">Для развертывания и настройки единиц измерения в Microsoft Teams Configuration Manager требуется несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="77369-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="77369-181">Вам необходимо создать и настроить указанные ниже пакеты, а затем распространить их на системы сайта Configuration Manager, которым назначена роль сервера точки распространения.</span><span class="sxs-lookup"><span data-stu-id="77369-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="77369-182">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="77369-182">**Package name**</span></span>                     | <span data-ttu-id="77369-183">**Тип**</span><span class="sxs-lookup"><span data-stu-id="77369-183">**Type**</span></span>               | <span data-ttu-id="77369-184">**Описание**</span><span class="sxs-lookup"><span data-stu-id="77369-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="77369-185">SRS v2 — Пакет приложения SRS</span><span class="sxs-lookup"><span data-stu-id="77369-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="77369-186">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="77369-186">Software package</span></span>       | <span data-ttu-id="77369-187">Пакет для пакета развертывания комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77369-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="77369-188">SRS v2 — Пакет Sysprep</span><span class="sxs-lookup"><span data-stu-id="77369-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="77369-189">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="77369-189">Software package</span></span>       | <span data-ttu-id="77369-190">Упаковка для настраиваемого файла Unattend. XML для настройки комнат в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77369-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="77369-191">Пакет Срскомпутернаме v2-Set-</span><span class="sxs-lookup"><span data-stu-id="77369-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="77369-192">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="77369-192">Software package</span></span>       | <span data-ttu-id="77369-193">Упаковка для приложения HTML (HTA) для присвоения имени компьютера во время развертывания</span><span class="sxs-lookup"><span data-stu-id="77369-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="77369-194">SRS v2 — Настройка настройки SRS</span><span class="sxs-lookup"><span data-stu-id="77369-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="77369-195">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="77369-195">Software package</span></span>       | <span data-ttu-id="77369-196">Пакет для настройки развертывания приложения "комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="77369-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="77369-197">Пакет обновлений для SRS v2-OS</span><span class="sxs-lookup"><span data-stu-id="77369-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="77369-198">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="77369-198">Software package</span></span>       | <span data-ttu-id="77369-199">Пакет для развертывания обязательных обновлений операционной системы</span><span class="sxs-lookup"><span data-stu-id="77369-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="77369-200">SRS v2 — Пакет корневых сертификатов</span><span class="sxs-lookup"><span data-stu-id="77369-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="77369-201">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="77369-201">Software package</span></span>       | <span data-ttu-id="77369-202">Дополнительный пакет для развертывания корневого сертификата (не требуется для устройств, подключенных к домену)</span><span class="sxs-lookup"><span data-stu-id="77369-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="77369-203">SRS v2 — Пакет агента наблюдения (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="77369-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="77369-204">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="77369-204">Software package</span></span>       | <span data-ttu-id="77369-205">Дополнительный пакет для развертывания и настройки агента Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="77369-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="77369-206">Фоновый пакет для SRS v2-WinPE</span><span class="sxs-lookup"><span data-stu-id="77369-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="77369-207">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="77369-207">Software package</span></span>       | <span data-ttu-id="77369-208">Упаковка для настраиваемого фонового изображения для использования с образами загрузки</span><span class="sxs-lookup"><span data-stu-id="77369-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="77369-209">Windows 10 корпоративный</span><span class="sxs-lookup"><span data-stu-id="77369-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="77369-210">Образ операционной системы</span><span class="sxs-lookup"><span data-stu-id="77369-210">Operating system image</span></span> | <span data-ttu-id="77369-211">Пакет для установочного файла операционной системы (Install. wim)</span><span class="sxs-lookup"><span data-stu-id="77369-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="77369-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="77369-212">Surface Pro</span></span>                          | <span data-ttu-id="77369-213">Пакет драйвера</span><span class="sxs-lookup"><span data-stu-id="77369-213">Driver package</span></span>         | <span data-ttu-id="77369-214">Упаковка драйверов устройств и встроенного по для Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="77369-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="77369-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="77369-215">Surface Pro 4</span></span>                        | <span data-ttu-id="77369-216">Пакет драйвера</span><span class="sxs-lookup"><span data-stu-id="77369-216">Driver package</span></span>         | <span data-ttu-id="77369-217">Упаковка драйверов устройств и встроенного по для Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="77369-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="77369-218">Дополнительные сведения можно найти [в разделе пакеты и программы в System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="77369-218">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="77369-219">Создание папок для исходных файлов пакета</span><span class="sxs-lookup"><span data-stu-id="77369-219">Create folders for the package source files</span></span>

<span data-ttu-id="77369-220">Configuration Manager требует, чтобы файлы исходного кода были упорядочены в определенной структуре папок при их создании и обновлении.</span><span class="sxs-lookup"><span data-stu-id="77369-220">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="77369-221">Создайте следующую структуру папок на сайте центра администрирования System Center Configuration Manager или на основном сайте или на сервере общего доступа, который вы используете для размещения исходных файлов пакетов.</span><span class="sxs-lookup"><span data-stu-id="77369-221">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="77369-222">SRS v2 — Пакет агента наблюдения (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="77369-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="77369-223">Пакет обновлений для SRS v2-OS</span><span class="sxs-lookup"><span data-stu-id="77369-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="77369-224">SRS v2 — Пакет корневых сертификатов</span><span class="sxs-lookup"><span data-stu-id="77369-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="77369-225">Пакет Срскомпутернаме v2-Set-</span><span class="sxs-lookup"><span data-stu-id="77369-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="77369-226">SRS v2 — Пакет приложения SRS</span><span class="sxs-lookup"><span data-stu-id="77369-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="77369-227">SRS v2 — Настройка настройки SRS</span><span class="sxs-lookup"><span data-stu-id="77369-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="77369-228">SRS v2 — Пакет Sysprep</span><span class="sxs-lookup"><span data-stu-id="77369-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="77369-229">Дисков</span><span class="sxs-lookup"><span data-stu-id="77369-229">Drivers</span></span>
    -   <span data-ttu-id="77369-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="77369-230">Surface Pro</span></span>
    -   <span data-ttu-id="77369-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="77369-231">Surface Pro 4</span></span>
-   <span data-ttu-id="77369-232">Операционные системы</span><span class="sxs-lookup"><span data-stu-id="77369-232">Operating Systems</span></span>
    -   <span data-ttu-id="77369-233">Windows 10 корпоративный</span><span class="sxs-lookup"><span data-stu-id="77369-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="77369-234">Кроме того, вы можете [скачать](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) и использовать ZIP-файл, содержащий структуру папок для пакетов, необходимые сценарии и шаблон последовательности задач, которые нужно импортировать.</span><span class="sxs-lookup"><span data-stu-id="77369-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="77369-235">Создание пакета агента наблюдения</span><span class="sxs-lookup"><span data-stu-id="77369-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="77369-236">Скачайте агент мониторинга из <https://go.microsoft.com/fwlink/?LinkId=828603>.</span><span class="sxs-lookup"><span data-stu-id="77369-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="77369-237">Чтобы извлечь пакет в папку **пакета SRS v2 — Microsoft Monitoring Agent** , откройте окно командной строки и введите **MMASetup-AMD64. exe/c:** в командной строке.</span><span class="sxs-lookup"><span data-stu-id="77369-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="77369-238">На консоли Configuration Manager перейдите в раздел **пакеты** \> **управления** \> приложениями **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="77369-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="77369-239">Введите указанные ниже сведения, чтобы создать пакет.</span><span class="sxs-lookup"><span data-stu-id="77369-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="77369-240">Name<strong>(имя): SRS v2 — Пакет агента наблюдения (Майкрософт)</strong></span><span class="sxs-lookup"><span data-stu-id="77369-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="77369-241">Производитель<strong>: Корпорация Майкрософт</strong></span><span class="sxs-lookup"><span data-stu-id="77369-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="77369-242">Version<strong>: 8.1.11081.0</strong> (введите версию скачанного установочного файла)</span><span class="sxs-lookup"><span data-stu-id="77369-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="77369-243">Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке, которая входит в **состав пакета обновления SRS v2 — Microsoft Monitoring Agent** , и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="77369-244">Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="77369-245">Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="77369-246">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="77369-247">Создание пакета обновлений операционной системы</span><span class="sxs-lookup"><span data-stu-id="77369-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="77369-248">В папке **пакета обновления SRS v2-OS** создайте новый сценарий PowerShell с именем **Install-SRSv2-OS-Updates. ps1**.</span><span class="sxs-lookup"><span data-stu-id="77369-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="77369-249">Скопируйте приведенный ниже сценарий в сценарий **Install-SRSv2-OS-Updates. ps1** .</span><span class="sxs-lookup"><span data-stu-id="77369-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="77369-250">Кроме того, вы можете скачать сценарий Install-SRSv2-OS-Updates. ps1 [отсюда](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="77369-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="77369-251">Скачайте в ту же папку обязательные пакеты обновления для Windows.</span><span class="sxs-lookup"><span data-stu-id="77369-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="77369-252">На момент публикации этой статьи требовалось только [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) .</span><span class="sxs-lookup"><span data-stu-id="77369-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="77369-253">Установите флажок [настроить консоль комнат Microsoft Teams](console.md), чтобы узнать, требуются ли какие-либо другие обновления.</span><span class="sxs-lookup"><span data-stu-id="77369-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="77369-254">На консоли Configuration Manager перейдите в раздел **пакеты** \> **управления** \> приложениями **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="77369-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="77369-255">Введите указанные ниже сведения, чтобы создать пакет.</span><span class="sxs-lookup"><span data-stu-id="77369-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="77369-256">Name (имя): **SRS v2 — пакет обновлений операционной системы**</span><span class="sxs-lookup"><span data-stu-id="77369-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="77369-257">Производитель: Корпорация **Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="77369-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="77369-258">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="77369-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="77369-259">Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке **пакета обновления SRS v2-OS** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="77369-260">Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="77369-261">Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="77369-262">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="77369-263">Создание пакета корневого сертификата (необязательно)</span><span class="sxs-lookup"><span data-stu-id="77369-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="77369-264">Этот пакет создается для распространения корневого сертификата для устройств, которые не будут присоединены к домену Active Directory.</span><span class="sxs-lookup"><span data-stu-id="77369-264">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="77369-265">Этот пакет следует создавать только в том случае, если действуют оба указанных ниже условия.</span><span class="sxs-lookup"><span data-stu-id="77369-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="77369-266">Развертывание включает в себя локальный Lync или Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="77369-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="77369-267">Элементы комнат Microsoft Teams настроены для работы в Рабочей группе, а не участника домена.</span><span class="sxs-lookup"><span data-stu-id="77369-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="77369-268">Скопируйте корневой сертификат в папку " **SRS v2 – корневой пакет сертификатов** ".</span><span class="sxs-lookup"><span data-stu-id="77369-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="77369-269">На консоли Configuration Manager перейдите в раздел **пакеты** \> **управления** \> приложениями **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="77369-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="77369-270">Введите указанные ниже сведения, чтобы создать пакет.</span><span class="sxs-lookup"><span data-stu-id="77369-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="77369-271">Name (имя): **SRS v2 — Пакет корневого сертификата**</span><span class="sxs-lookup"><span data-stu-id="77369-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="77369-272">Изготовитель: *название своей организации*</span><span class="sxs-lookup"><span data-stu-id="77369-272">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="77369-273">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="77369-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="77369-274">Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке с **пакетом SRS v2 – корневой сертификат** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="77369-275">Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="77369-276">Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="77369-277">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="77369-278">Создание комплекта для развертывания комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77369-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="77369-279">Скачайте последнюю версию **комплекта для развертывания комнат Microsoft Teams** из <https://go.microsoft.com/fwlink/?linkid=851168>и установите ее на рабочую станцию.</span><span class="sxs-lookup"><span data-stu-id="77369-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="77369-280">Скопируйте содержимое из **файла C:\\Program Files (x86\\) из набора средств для развертывания системы комнаты Skype** в папку **пакета приложения SRS v2 — SRS** .</span><span class="sxs-lookup"><span data-stu-id="77369-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="77369-281">На консоли Configuration Manager перейдите в раздел **пакеты** \> **управления** \> приложениями **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="77369-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="77369-282">Введите указанные ниже сведения, чтобы создать пакет.</span><span class="sxs-lookup"><span data-stu-id="77369-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="77369-283">Name (имя): **SRS v2 — Пакет приложения SRS**</span><span class="sxs-lookup"><span data-stu-id="77369-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="77369-284">Производитель: Корпорация **Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="77369-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="77369-285">Version: **3.1.104.0** (введите версию скачанного установочного файла)</span><span class="sxs-lookup"><span data-stu-id="77369-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="77369-286">Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке **SRS v2 — Пакет приложения SRS** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="77369-287">Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="77369-288">Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="77369-289">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="77369-290">Создание пакета назначения имени компьютера</span><span class="sxs-lookup"><span data-stu-id="77369-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="77369-291">В папке **пакета SRS v2-Set-срскомпутернаме** создайте новое HTML-приложение с именем **Сет-срскомпутернаме. hta** .</span><span class="sxs-lookup"><span data-stu-id="77369-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="77369-292">Скопируйте приведенный ниже сценарий в файл **Сет-срскомпутернаме. hta** .</span><span class="sxs-lookup"><span data-stu-id="77369-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="77369-293">Кроме того, вы можете загрузить файл Сет-срскомпутернаме. hta [отсюда](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="77369-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="77369-294">На консоли Configuration Manager перейдите в раздел **пакеты** \> **управления** \> приложениями **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="77369-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="77369-295">Введите указанные ниже сведения, чтобы создать пакет.</span><span class="sxs-lookup"><span data-stu-id="77369-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="77369-296">Name (имя): " **SRS v2 — Установка и срскомпутернаме** "</span><span class="sxs-lookup"><span data-stu-id="77369-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="77369-297">Производитель: Корпорация **Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="77369-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="77369-298">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="77369-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="77369-299">Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке **пакета SRS v2-Set-срскомпутернаме** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="77369-300">Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="77369-301">Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="77369-302">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="77369-303">Создание пакета Sysprep</span><span class="sxs-lookup"><span data-stu-id="77369-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="77369-304">В папке **пакета SRS v2 – Sysprep** создайте новый XML-файл с именем **Unattend. XML** .</span><span class="sxs-lookup"><span data-stu-id="77369-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="77369-305">Скопируйте приведенный ниже текст в файл **Unattend. XML** .</span><span class="sxs-lookup"><span data-stu-id="77369-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="77369-306">Кроме того, вы можете загрузить файл Unattend. XML [отсюда](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="77369-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="77369-307">На консоли Configuration Manager перейдите в раздел **пакеты** \> **управления** \> приложениями **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="77369-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="77369-308">Введите указанные ниже сведения, чтобы создать пакет.</span><span class="sxs-lookup"><span data-stu-id="77369-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="77369-309">Name **(имя): SRS v2 — Пакет Sysprep**</span><span class="sxs-lookup"><span data-stu-id="77369-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="77369-310">Производитель: Корпорация **Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="77369-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="77369-311">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="77369-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="77369-312">Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке **пакета SRS v2 – Sysprep** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="77369-313">Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="77369-314">Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="77369-315">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="77369-316">Создание пакета Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="77369-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="77369-317">Получите носитель с Windows 10 корпоративный x64 и скопируйте файл **install. wim** в папку **Windows 10 Корпоративная\\для операционной системы** .</span><span class="sxs-lookup"><span data-stu-id="77369-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="77369-318">В консоли Configuration Manager перейдите в раздел \> \*\*\*\* \> **библиотеки программного обеспечения** операционной системы **и выберите**пункт **Добавить образ операционной системы**.</span><span class="sxs-lookup"><span data-stu-id="77369-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="77369-319">Укажите путь к файлу **install. wim** , который вы только что скопировали, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="77369-320">Обновите поле **Version** в соответствии с номером сборки для корпоративного образа Windows 10, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="77369-321">Ознакомьтесь со страницей **сведения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="77369-322">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-322">Select **Close**.</span></span>

<span data-ttu-id="77369-323">Дополнительные сведения можно найти [в разделе Управление образами операционной системы с помощью System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="77369-323">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="77369-324">Создание пакетов драйверов устройств Surface Pro</span><span class="sxs-lookup"><span data-stu-id="77369-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="77369-325">Комнаты Microsoft Teams поддерживаются как для Surface Pro, так и для Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="77369-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="77369-326">Для каждой модели Pro Surface, имеющейся в вашей среде, нужно создать пакет драйверов.</span><span class="sxs-lookup"><span data-stu-id="77369-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77369-327">Драйверы должны быть совместимы с версией Windows 10 Корпоративная сборка и пакетом развертывания комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77369-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="77369-328">Дополнительные сведения можно найти [в разделе Загрузка новейшего встроенного по и драйверов для устройств Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) и [Настройка консоли](console.md).</span><span class="sxs-lookup"><span data-stu-id="77369-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="77369-329">Загрузите последние версии драйверов и встроенного по.</span><span class="sxs-lookup"><span data-stu-id="77369-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="77369-330">Для Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="77369-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="77369-331">Для Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="77369-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="77369-332">Извлеките загруженный драйвер и встроенное по.</span><span class="sxs-lookup"><span data-stu-id="77369-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="77369-333">Откройте окно командной строки и введите в командной строке одну из указанных ниже команд.</span><span class="sxs-lookup"><span data-stu-id="77369-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="77369-334">На консоли Configuration Manager перейдите в раздел **драйверы** **операционной системы** \> **библиотеки** \> , а затем выберите команду **импортировать драйвер**.</span><span class="sxs-lookup"><span data-stu-id="77369-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="77369-335">Выберите **импортировать все драйверы в следующем сетевом пути (UNC)**, выберите исходную папку (например, C\\: _Sources\\Drivers\\Pro), а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="77369-336">На странице **Определение сведений для импортированных драйверов** выберите все указанные в списке драйверы и установите флажок **включить эти драйверы и разрешить компьютерам устанавливать их**.</span><span class="sxs-lookup"><span data-stu-id="77369-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="77369-337">Выберите **категории**, создайте новую категорию, соответствующую модели Surface, нажмите кнопку **ОК**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="77369-338">Выберите команду **создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="77369-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="77369-339">Укажите имя пакета, соответствующее модели Surface Pro, введите путь к папке, в которой нужно сохранить файлы пакета драйверов, нажмите кнопку **ОК**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="77369-340">На странице **образы загрузки** убедитесь, что не выбраны образы загрузки, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="77369-341">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-341">Select **Close**.</span></span>

11. <span data-ttu-id="77369-342">Перейдите к разделу **драйверы** \> **операционной системы** \> **библиотеки программного обеспечения** , выберите пункт \*\* \> создать\*\*папку и введите имя папки, соответствующей модели Surface Pro, для которой вы только что импортировали драйверы.</span><span class="sxs-lookup"><span data-stu-id="77369-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="77369-343">Переместите все импортированные драйверы в созданную папку, чтобы упростить навигацию и операцию.</span><span class="sxs-lookup"><span data-stu-id="77369-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="77369-344">Повторите эти действия для других моделей Surface Pro, которые вы можете использовать.</span><span class="sxs-lookup"><span data-stu-id="77369-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="77369-345">Дополнительные сведения можно найти [в разделе Управление драйверами в System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="77369-345">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="77369-346">Создание пакета конфигурации комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77369-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="77369-347">На консоли Configuration Manager перейдите в раздел **пакеты** \> **управления** \> приложениями **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="77369-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="77369-348">Введите указанные ниже сведения, чтобы создать пакет.</span><span class="sxs-lookup"><span data-stu-id="77369-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="77369-349">Name (имя): **SRS v2 — Настройка пакета установки SRS**</span><span class="sxs-lookup"><span data-stu-id="77369-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="77369-350">Производитель: Корпорация **Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="77369-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="77369-351">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="77369-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="77369-352">Установите флажок **Этот пакет включает исходные файлы** , введите путь к службе **SRS v2 — Настройка папки настройки SRS** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="77369-353">Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="77369-354">Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="77369-355">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="77369-356">Распространение пакетов Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="77369-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="77369-357">Все пакеты должны быть распределены на серверы, которым назначена роль точки распространения в иерархии Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="77369-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="77369-358">Следуйте приведенным ниже инструкциям, чтобы инициировать распространение пакетов.</span><span class="sxs-lookup"><span data-stu-id="77369-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="77369-359">Распространение пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="77369-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="77369-360">На консоли Configuration Manager перейдите в раздел \> **пакеты** \> **управления приложениями** **библиотеки программного обеспечения** .</span><span class="sxs-lookup"><span data-stu-id="77369-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="77369-361">Выберите все пакеты программного обеспечения, которые вы хотите распространить, а затем выберите команду **распространить содержимое**.</span><span class="sxs-lookup"><span data-stu-id="77369-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="77369-362">Просмотрите список пакетов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="77369-363">Добавьте в список всех серверов точки распространения (или групп точек распространения, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="77369-364">Нажмите кнопку **Далее**, а затем — кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="77369-365">Распространение пакетов драйверов.</span><span class="sxs-lookup"><span data-stu-id="77369-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="77369-366">В консоли Configuration Manager перейдите в раздел **пакеты драйверов** \> **операционных систем** \> **библиотеки программного обеспечения** .</span><span class="sxs-lookup"><span data-stu-id="77369-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="77369-367">Выберите все пакеты драйверов, которые вы хотите распространить, а затем выберите команду **распространить содержимое**.</span><span class="sxs-lookup"><span data-stu-id="77369-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="77369-368">Просмотрите список пакетов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="77369-369">Добавьте в список всех серверов точки распространения (или групп точек распространения, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="77369-370">Нажмите кнопку **Далее**, а затем — кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="77369-371">Распространение пакетов операционной системы.</span><span class="sxs-lookup"><span data-stu-id="77369-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="77369-372">В консоли Configuration Manager перейдите к \*\*\*\* \> **образам операционной системы**, заданной в \> **библиотеке программного обеспечения** .</span><span class="sxs-lookup"><span data-stu-id="77369-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="77369-373">Выберите все образы операционной системы, которые вы хотите распространить, а затем выберите команду **распространить содержимое**.</span><span class="sxs-lookup"><span data-stu-id="77369-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="77369-374">Просмотрите список пакетов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="77369-375">Добавьте в список всех серверов точки распространения (или групп точек распространения, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="77369-376">Нажмите кнопку **Далее**, а затем — кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="77369-377">Распространение пакетов может занять некоторое время, в зависимости от размера пакета, иерархии Configuration Manager, количества серверов точки распространения и пропускной способности, доступной в сети.</span><span class="sxs-lookup"><span data-stu-id="77369-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="77369-378">Все пакеты должны быть распределены, прежде чем вы сможете развернуть один из комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77369-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="77369-379">Вы можете просмотреть состояние распространения пакетов на консоли Configuration Manager, перейдя в режим **наблюдения за** \> состоянием **распространения** \> **содержимого**.</span><span class="sxs-lookup"><span data-stu-id="77369-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="77369-380">Последовательности задач Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="77369-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="77369-381">Для автоматизации шагов по развертыванию образа операционной системы на конечном компьютере используются последовательности задач с помощью System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="77369-381">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="77369-382">Чтобы развернуть единицу измерения Microsoft Teams автоматически в автоматическом режиме, создайте последовательность задач, которая ссылается на образ загрузки, который используется для запуска конечного компьютера с операционной системой комнат Microsoft Teams, который вы хотите установить, и все другое дополнительное содержимое, например другие приложения или обновления программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="77369-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="77369-383">Импорт последовательности примеров задач</span><span class="sxs-lookup"><span data-stu-id="77369-383">Import the sample task sequence</span></span>

<span data-ttu-id="77369-384">Вы можете скачать и легко импортировать примерную последовательность задач и настроить ее в соответствии с вашими потребностями.</span><span class="sxs-lookup"><span data-stu-id="77369-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="77369-385">[**Скачайте**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) пример последовательности задач и Скопируйте загруженный ZIP-файл в общее расположение.</span><span class="sxs-lookup"><span data-stu-id="77369-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="77369-386">В консоли Configuration Manager перейдите в раздел **последовательности задач**для \> **операционных систем** \> **библиотеки программного обеспечения** , а затем щелкните **Импорт последовательности задач**.</span><span class="sxs-lookup"><span data-stu-id="77369-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="77369-387">Нажмите кнопку **Обзор**, перейдите к папке, которую вы использовали в действии 1, выберите файл **развертывания Microsoft Teams (EN-US). zip** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="77369-388">Задайте для параметра **действие** **создать новый**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="77369-389">Подтвердите параметры и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="77369-390">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="77369-391">Убедитесь, что пакеты ссылок правильно связаны с каждым шагом последовательности задач.</span><span class="sxs-lookup"><span data-stu-id="77369-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="77369-392">Выберите импортированную последовательность задач и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="77369-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="77369-393">Откроется редактор последовательности задач, в котором выводятся все последовательные шаги, необходимые для развертывания и настройки единицы комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77369-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="77369-394">Пошаговое руководство и выполнение рекомендуемых обновлений:</span><span class="sxs-lookup"><span data-stu-id="77369-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="77369-395">**Перезагрузите компьютер в среде Windows PE**: это действие перезапускается, а затем загружается в среду PXE Windows.</span><span class="sxs-lookup"><span data-stu-id="77369-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="77369-396">Для этого шага никаких изменений не требуется.</span><span class="sxs-lookup"><span data-stu-id="77369-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="77369-397">**Разбить на разделы диск 0 — UEFI**: на этом этапе производится очистка конфигурации диска и создание секций на основе настроенных параметров.</span><span class="sxs-lookup"><span data-stu-id="77369-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="77369-398">Мы рекомендуем не вносить никаких изменений в этот этап.</span><span class="sxs-lookup"><span data-stu-id="77369-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="77369-399">**Задайте имя компьютера SRS**. Этот шаг включает HTML-приложение, которое предоставляет пользовательский интерфейс, чтобы задать имя компьютера для устройства Microsoft Teams в процессе развертывания.</span><span class="sxs-lookup"><span data-stu-id="77369-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="77369-400">Это необязательный шаг, но его можно отключить только в том случае, если вы хотите управлять именованием компьютеров с помощью альтернативного процесса.</span><span class="sxs-lookup"><span data-stu-id="77369-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="77369-401">Убедитесь в том, что установлен пакет **SRS v2-Set-срскомпутернаме** .</span><span class="sxs-lookup"><span data-stu-id="77369-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="77369-402">В противном случае перейдите к пакету и выберите его.</span><span class="sxs-lookup"><span data-stu-id="77369-402">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="77369-403">**Применение операционной системы**: на этом этапе задается образ операционной системы, который нужно развернуть, и файл ответов для автоматического использования Sysprep.</span><span class="sxs-lookup"><span data-stu-id="77369-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="77369-404">Убедитесь, что выбран правильный файл образа операционной системы Windows 10 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="77369-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="77369-405">Убедитесь в том, что **для выборочной установки используется автоматический или файл ответов Sysprep** , и выбран **пакет SRS v2-Sysprep** .</span><span class="sxs-lookup"><span data-stu-id="77369-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="77369-406">Кроме того, убедитесь, что для **имени файла** задано значение **Unattend. XML**.</span><span class="sxs-lookup"><span data-stu-id="77369-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="77369-407">**Применение параметров Windows**. на этом этапе собираются сведения о установке Windows.</span><span class="sxs-lookup"><span data-stu-id="77369-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="77369-408">Предоставьте сведения о лицензировании и регистрации, включая ключ продукта, пароль учетной записи локального администратора и часовой пояс (в зависимости от ваших потребностей).</span><span class="sxs-lookup"><span data-stu-id="77369-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="77369-409">**Примените параметры сети**. на этом шаге вы можете указать доменную рабочую группу или имя домена Active Directory и подразделение.</span><span class="sxs-lookup"><span data-stu-id="77369-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="77369-410">Для получения рекомендуемых действий, которые необходимо выполнить при развертывании комнат Microsoft Teams в качестве членов домена Актве, вы можете [присоединиться к домену системы комнаты Skype](domain-joining-considerations.md) .</span><span class="sxs-lookup"><span data-stu-id="77369-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="77369-411">**Применение драйверов.** Этот шаг и вложенные шаги используются для развертывания применимых драйверов устройств и микропрограмм на основе имеющейся модели Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="77369-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="77369-412">Обновите каждый шаг, чтобы указать соответствующий пакет драйвера, связанный с этим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="77369-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="77369-413">Каждый пакет драйвера настроен на использование фильтров инструментария управления Windows (WMI) для развертывания соответствующих драйверов и микропрограмм на основе модели Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="77369-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="77369-414">Настоятельно не рекомендуется изменять конфигурацию этих драйверов, в противном случае развертывание может завершиться сбоем.</span><span class="sxs-lookup"><span data-stu-id="77369-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="77369-415">**Настройка Windows и Configuration Manager**: на этом шаге развертывается и настраивается клиент Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="77369-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="77369-416">Обновите этот шаг, чтобы указать встроенный клиентский пакет Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="77369-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="77369-417">**Установка корневого сертификата**. Этот этап распространяет корневой сертификат для устройств, не присоединенных к домену, и поэтому является необязательным и отключенным по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77369-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="77369-418">Включите это действие, если вам нужно развернуть корневой сертификат в единицах комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77369-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="77369-419">Если вы хотите выполнить этот шаг, убедитесь, что выбран **пакет корневого сертификата SRS v2** и **отключено перенаправление 64-разрядной файловой системы** .</span><span class="sxs-lookup"><span data-stu-id="77369-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="77369-420">**Установка и настройка агента наблюдения**: на этом этапе устанавливается 64-разрядная версия агента монитора Microsoft Azure и настраивается агент для подключения к рабочей области в службе анализа журналов.</span><span class="sxs-lookup"><span data-stu-id="77369-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="77369-421">Этот шаг отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77369-421">This step is disabled by default.</span></span> <span data-ttu-id="77369-422">Этот этап следует активировать только в том случае, если вы собираетесь использовать агент наблюдения для наблюдения за работоспособностью модулей комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77369-422">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="77369-423">Измените этот шаг и обновите параметры командной строки, указав **идентификатор рабочей области** и **ключ рабочей области**.</span><span class="sxs-lookup"><span data-stu-id="77369-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="77369-424">Дополнительные сведения о том, как получить идентификатор рабочей области Operations Management Suite и первичный ключ, можно найти в разделе [Настройка тестовых устройств для мониторинга Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) .</span><span class="sxs-lookup"><span data-stu-id="77369-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="77369-425">Убедитесь, что выбран **пакет агента наблюдения за SRS v2 (Майкрософт** **) и отключено перенаправление 64-разрядной файловой системы** .</span><span class="sxs-lookup"><span data-stu-id="77369-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="77369-426">Дополнительные сведения о наблюдении за работоспособностью развертывания комнат Microsoft Teams можно найти в разделе [Планирование управления комнатами Microsoft Teams с помощью монитора Azure](azure-monitor-plan.md), [развертывание Microsoft Teams Management с помощью](azure-monitor-deploy.md) монитора Azure и [Управление устройствами Microsoft Teams с помощью монитора Azure](azure-monitor-manage.md).</span><span class="sxs-lookup"><span data-stu-id="77369-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="77369-427">**Копирование файлов конфигурации SRS v2**: на этом этапе выполняется копирование необходимых файлов настройки и конфигурации из комплекта средств развертывания комнат Microsoft Teams на локальный жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="77369-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="77369-428">Для этого шага настройка не требуется.</span><span class="sxs-lookup"><span data-stu-id="77369-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="77369-429">Убедитесь, что установлен **пакет приложения SRS v2** и **отключено перенаправление 64-разрядной файловой системы** .</span><span class="sxs-lookup"><span data-stu-id="77369-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="77369-430">**Install-SRSv2-OS-Updates: на**этом этапе развертываются все обязательные обновления операционной системы, необходимые для развертывания комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77369-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="77369-431">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="77369-431">Do the following:</span></span>
       -   <span data-ttu-id="77369-432">Установите флажок [настроить консоль Microsoft Teams](console.md) , чтобы узнать, какие обновления требуются.</span><span class="sxs-lookup"><span data-stu-id="77369-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="77369-433">Убедитесь, что **пакет обновлений для SRS v2 – OS** содержит все необходимые обновления.</span><span class="sxs-lookup"><span data-stu-id="77369-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="77369-434">Убедитесь, что установлен **пакет обновления SRS v2 – OS** .</span><span class="sxs-lookup"><span data-stu-id="77369-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="77369-435">Убедитесь, что для политики выполнения PowerShell задано значение **обход**.</span><span class="sxs-lookup"><span data-stu-id="77369-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="77369-436">**Перезагрузите компьютер**. это действие перезагружает компьютер после установки обязательных обновлений операционной системы.</span><span class="sxs-lookup"><span data-stu-id="77369-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="77369-437">Для этого шага настройка не требуется.</span><span class="sxs-lookup"><span data-stu-id="77369-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="77369-438">**Настройка компонентов Windows**: на этом этапе настраиваются необходимые компоненты Windows.</span><span class="sxs-lookup"><span data-stu-id="77369-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="77369-439">Для этого шага настройка не требуется.</span><span class="sxs-lookup"><span data-stu-id="77369-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="77369-440">**Перезагрузка компьютера**: после настройки компонентов Windows компьютер перезагружается.</span><span class="sxs-lookup"><span data-stu-id="77369-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="77369-441">Для этого шага настройка не требуется.</span><span class="sxs-lookup"><span data-stu-id="77369-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="77369-442">**Добавить местного пользователя Skype**: на этом этапе создается локальная учетная запись Skype, используемая для автоматического входа в Windows, и запуска приложения Microsoft Teams комнаты.</span><span class="sxs-lookup"><span data-stu-id="77369-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="77369-443">На этом этапе отсутствует связанный с ним пакет программного обеспечения, и для него не требуется настройка.</span><span class="sxs-lookup"><span data-stu-id="77369-443">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="77369-444">**Настройка и настройка приложения SRS**. на этом этапе производится установка приложения Microsoft Teams для следующей загрузки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="77369-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="77369-445">Убедитесь в том, что для **SRS v2 установлен флажок Настройка пакета настройки SRS** и **отключено перенаправление 64-разрядной файловой системы** .</span><span class="sxs-lookup"><span data-stu-id="77369-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77369-446">Очень важно, чтобы шаги последовательности задач должны быть в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="77369-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="77369-447">Изменение порядка шагов или Настройка дополнительных шагов может привести к сбою развертывания.</span><span class="sxs-lookup"><span data-stu-id="77369-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="77369-448">**Настройка и настройка шага приложения SRS** должна быть последним шагом последовательности задач, в противном случае развертывание может завершиться сбоем.</span><span class="sxs-lookup"><span data-stu-id="77369-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="77369-449">Создание развертывания для последовательности задач</span><span class="sxs-lookup"><span data-stu-id="77369-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="77369-450">Выберите последовательность задач, а затем нажмите кнопку **развернуть**.</span><span class="sxs-lookup"><span data-stu-id="77369-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="77369-451">Нажмите кнопку **Обзор** , чтобы выбрать целевую коллекцию для развертывания.</span><span class="sxs-lookup"><span data-stu-id="77369-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="77369-452">Выберите **все неизвестные компьютеры** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="77369-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="77369-453">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-453">Select **Next**.</span></span>

5. <span data-ttu-id="77369-454">В раскрывающемся списке **Цель** выберите пункт **доступно** .</span><span class="sxs-lookup"><span data-stu-id="77369-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="77369-455">Выберите **только носители и PXE** в списке **сделать доступным ниже** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="77369-456">Очень важно, чтобы **Цель** настроилась как **доступная**.</span><span class="sxs-lookup"><span data-stu-id="77369-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="77369-457">Убедитесь, что для **цели** **не** задано значение **обязательно**.</span><span class="sxs-lookup"><span data-stu-id="77369-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="77369-458">Кроме того, убедитесь в том, что вы выбрали **только носители и PXE** в разделе **сделать доступным для следующих вариантов**.</span><span class="sxs-lookup"><span data-stu-id="77369-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="77369-459">Установка этих значений для других пользователей может привести к тому, что все компьютеры будут получать образ развертывания комнат Microsoft Teams при загрузке.</span><span class="sxs-lookup"><span data-stu-id="77369-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="77369-460">Не указывайте расписание и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="77369-461">Не изменяйте что-либо в разделе **взаимодействие с пользователем** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="77369-462">Не изменяйте что-либо в разделе " **оповещения** " и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="77369-463">Не изменяйте ничего в разделе **точки распространения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="77369-464">Подтвердите параметры и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="77369-465">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="77369-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="77369-466">Проверка и устранение неполадок с решением</span><span class="sxs-lookup"><span data-stu-id="77369-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="77369-467">После того как вы закончите последовательности задач System Center Configuration Manager, вам потребуется выполнить тестовый запуск, чтобы убедиться в том, что последовательность задач может развернуть и настроить единицы комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77369-467">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="77369-468">Подключите тестовое устройство к проводной сети, используя один из поддерживаемых адаптеров Ethernet или стыковочный элемент Surface.</span><span class="sxs-lookup"><span data-stu-id="77369-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="77369-469">Если функция загрузки PXE не настроена для вашей среды, вы можете использовать образ загрузки, [созданный ранее](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) , для загрузки с USB-диска и подключения к Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="77369-469">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="77369-470">Получить доступ к встроенному по и инициировать загрузку PXE:</span><span class="sxs-lookup"><span data-stu-id="77369-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="77369-471">Убедитесь, что питание устройства Surface выключено.</span><span class="sxs-lookup"><span data-stu-id="77369-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="77369-472">Нажмите и удерживайте кнопку " **Громкость** ".</span><span class="sxs-lookup"><span data-stu-id="77369-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="77369-473">Нажмите и отпустите кнопку **Power** .</span><span class="sxs-lookup"><span data-stu-id="77369-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="77369-474">После того как устройство начнет загрузку, отпустите кнопку увеличить **уровень громкости** .</span><span class="sxs-lookup"><span data-stu-id="77369-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="77369-475">Выберите **Конфигурация загрузки**.</span><span class="sxs-lookup"><span data-stu-id="77369-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="77369-476">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="77369-476">Do one of the following:</span></span>

        -   <span data-ttu-id="77369-477">Выберите **загрузку PXE**и перетащите ее в верхнюю часть списка.</span><span class="sxs-lookup"><span data-stu-id="77369-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="77369-478">Вы также можете начать прокрутку влево на сетевом адаптере для немедленной загрузки устройства.</span><span class="sxs-lookup"><span data-stu-id="77369-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="77369-479">Это не повлияет на порядок загрузки.</span><span class="sxs-lookup"><span data-stu-id="77369-479">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="77369-480">Выберите USB-накопитель, на котором находится загрузочный носитель.</span><span class="sxs-lookup"><span data-stu-id="77369-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="77369-481">Нажмите кнопку **выход**и выберите **Перезапустить сейчас**.</span><span class="sxs-lookup"><span data-stu-id="77369-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="77369-482">При появлении соответствующего запроса нажмите кнопку **Ввод** для загрузки по сети.</span><span class="sxs-lookup"><span data-stu-id="77369-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="77369-483">Windows PE будет загружена в память, и начнется Мастер последовательности задач.</span><span class="sxs-lookup"><span data-stu-id="77369-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="77369-484">Нажмите кнопку **Далее** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="77369-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="77369-485">Выберите последовательность задач, которую вы импортировали ранее, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77369-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="77369-486">После применения конфигурации диска вам будет предложено указать имя компьютера для устройства.</span><span class="sxs-lookup"><span data-stu-id="77369-486">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="77369-487">Пользовательский интерфейс будет отображать рекомендуемое имя компьютера на основе серийного номера устройства Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="77369-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="77369-488">Вы можете либо оставить предложенное имя, либо указать новое.</span><span class="sxs-lookup"><span data-stu-id="77369-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="77369-489">Следуйте указаниям на экране назначения имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="77369-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="77369-490">После нажатия на кнопку " **сохранить**" начинается развертывание.</span><span class="sxs-lookup"><span data-stu-id="77369-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="77369-491">Оставшаяся часть процесса развертывания будет автоматически и не запрашивает ввод данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="77369-491">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="77369-492">После того как последовательность задач развертывания завершит настройку устройства, отобразится следующее окно конфигурации с запросом на настройку параметров приложения в комнатах Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77369-492">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Экран начальной настройки для приложения Microsoft Teams комнаты](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="77369-494">Подключите Surface Pro к консоли Microsoft Teams и настройте параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="77369-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="77369-495">Убедитесь в том, что возможности, указанные в разделе " [комнаты Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) ", работают на развернутом устройстве.</span><span class="sxs-lookup"><span data-stu-id="77369-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="77369-496">Для устранения неполадок, связанных с неудачной установкой, проверьте файл **смстс. log** , в котором регистрируются все действия, выполненные в последовательности задач Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="77369-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="77369-497">Файл СМСТС. log хранится в одном из нескольких путей в зависимости от этапа процесса сборки.</span><span class="sxs-lookup"><span data-stu-id="77369-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="77369-498">Убедитесь, что в приведенной ниже таблице указан путь к файлу СМСТС. log.</span><span class="sxs-lookup"><span data-stu-id="77369-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="77369-499">**Этап развертывания**</span><span class="sxs-lookup"><span data-stu-id="77369-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="77369-500">**Путь к журналу последовательностей задач**</span><span class="sxs-lookup"><span data-stu-id="77369-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="77369-501">Среда WinPE для форматирования жесткого диска</span><span class="sxs-lookup"><span data-stu-id="77369-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="77369-502">X:\\Windows\\temp\\смстслог\\смстс. log</span><span class="sxs-lookup"><span data-stu-id="77369-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="77369-503">Среда WinPE после форматирования жесткого диска</span><span class="sxs-lookup"><span data-stu-id="77369-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="77369-504">C:\\_SMSTaskSequence\\журналы\\смстслог\\смстс. log</span><span class="sxs-lookup"><span data-stu-id="77369-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="77369-505">Операционная система развернута перед установкой агента Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="77369-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="77369-506">c:\\_SMSTaskSequence\\журналы\\смстслог\\смстс. log</span><span class="sxs-lookup"><span data-stu-id="77369-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="77369-507">Операционная система и развернутый агент диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="77369-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="77369-508">% WINDIR%\\system32\\журналы\\\\CCM смстслог\\смстс. log</span><span class="sxs-lookup"><span data-stu-id="77369-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="77369-509">Выполнение последовательности задач завершено</span><span class="sxs-lookup"><span data-stu-id="77369-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="77369-510">% WINDIR%\\system32\\смстс\\журнал\\событий CCM</span><span class="sxs-lookup"><span data-stu-id="77369-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="77369-511">Вы можете в любое время нажать клавишу **F8** в течение последовательности задач, чтобы открыть консоль командной строки, а затем получить доступ к файлу смстс. log.</span><span class="sxs-lookup"><span data-stu-id="77369-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="77369-512">Для устранения проблем с загрузкой PXE проверьте два файла журнала на сервере Configuration Manager, которые относятся к действиям PXE.</span><span class="sxs-lookup"><span data-stu-id="77369-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="77369-513">**Пксеконтрол. log**, расположенный в каталоге журналов установки Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="77369-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="77369-514">**Смспксе. log**, расположенный в каталоге журналов точки управления Configuration Manager (MP)</span><span class="sxs-lookup"><span data-stu-id="77369-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="77369-515">Полный список журнальных файлов, которые можно использовать для дальнейшего устранения неполадок, возникающих при установке Configuration Manager, приведены [в статье файлы журнала в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="77369-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
