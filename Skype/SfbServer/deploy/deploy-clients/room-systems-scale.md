---
title: Развертывание комнат группами Майкрософт с использованием System Center Configuration Manager
author: jambirk
ms.author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: В данном разделе приведены сведения о развертывании комнат группами Майкрософт в крупномасштабного развертывания в среде.
ms.openlocfilehash: fe6ffee0c6ab86496204ab4e17b86cc84a70a2a7
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013038"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a><span data-ttu-id="09111-103">Развертывание комнат группами Майкрософт с использованием System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="09111-103">Deploy Microsoft Teams Rooms by using System Center Configuration Manager</span></span>

<span data-ttu-id="09111-104">В этой статье приводятся все необходимые сведения для создания развертываний комнат группами Майкрософт с помощью System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="09111-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="09111-105">С помощью простых в использовании методы, предоставляемые с System Center Configuration Manager можно развернуть в операционной системе и другие приложения на нескольких устройствах.</span><span class="sxs-lookup"><span data-stu-id="09111-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="09111-106">Подход, показано ниже инструкции по конфигурации диспетчера конфигураций и настроить образец пакетов и сценарии, представленные в этом руководстве, необходимые для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="09111-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Процесс развертывания комнат группами Майкрософт, с помощью диспетчера конфигураций](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="09111-108">В этом решении протестирована только с развертываниями Surface Pro на основе.</span><span class="sxs-lookup"><span data-stu-id="09111-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="09111-109">Следуйте рекомендациям производителя для конфигураций, не основанных на Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="09111-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="09111-110">Проверка необходимых компонентов</span><span class="sxs-lookup"><span data-stu-id="09111-110">Validate prerequisites</span></span>

<span data-ttu-id="09111-111">Для развертывания Microsoft комнат групп с помощью диспетчера конфигураций, убедитесь, что выполняются следующие необходимые условия и требования.</span><span class="sxs-lookup"><span data-stu-id="09111-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="09111-112">Требования к System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="09111-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="09111-113">System Center Configuration Manager версии должен быть по крайней мере 1706 или выше.</span><span class="sxs-lookup"><span data-stu-id="09111-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="09111-114">Рекомендуется использовать 1710 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="09111-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="09111-115">Извлечение [поддержки для Windows 10 в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) , чтобы узнать о версиях Windows 10, поддерживаемые Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="09111-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="09111-116">Поддерживаемая версия Deployment Kit (ADK) для Windows 10 и оценки необходимо установить.</span><span class="sxs-lookup"><span data-stu-id="09111-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="09111-117">В разделе версий [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) , который можно использовать с разными версиями Configuration Manager и убедитесь, что ваше развертывание содержит правильную версию.</span><span class="sxs-lookup"><span data-stu-id="09111-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="09111-118">Серверы системы сайта должна быть назначена роль точки распространения и образы загрузки должна быть включена для [протокол удаленной загрузки поддержка выполнения среды (PXE)](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) для включения инициировал сети развертываний.</span><span class="sxs-lookup"><span data-stu-id="09111-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="09111-119">Если не включена поддержка PXE, можно использовать [загрузочного носителя](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="09111-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="09111-120">Учетная запись доступа к сети должен быть настроен для поддержки новых сценариев развертывания компьютера (исходное).</span><span class="sxs-lookup"><span data-stu-id="09111-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="09111-121">Для получения дополнительных сведений о конфигурации учетной записи доступа к сети, просмотрите [Управление учетными записями для доступа к контенту в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="09111-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="09111-122">Рекомендуется включить [поддержку многоадресной рассылки](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), если вы скорее всего развертывать один образ комнат группами Майкрософт для нескольких единиц измерения в то же время.</span><span class="sxs-lookup"><span data-stu-id="09111-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="09111-123">Требования к сети</span><span class="sxs-lookup"><span data-stu-id="09111-123">Networking requirements</span></span>

-   <span data-ttu-id="09111-124">Сети должен иметь протокол динамической конфигурации узла (DHCP) сервера, настроенного для автоматического распределения адрес IP-адресов для подсетей, где будет развертываться единицы комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09111-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09111-125">Продолжительность аренды DHCP должно быть присвоено значение длиннее во время выполнения развертывания образа.</span><span class="sxs-lookup"><span data-stu-id="09111-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="09111-126">В противном случае может произойти сбой развертывания.</span><span class="sxs-lookup"><span data-stu-id="09111-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="09111-127">Сети, включая параметры и виртуальных локальных сетей (VLAN), необходимо настроить для поддержки PXE.</span><span class="sxs-lookup"><span data-stu-id="09111-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="09111-128">Обратитесь к поставщику сети Дополнительные сведения о конфигурации модуля поддержки IP-адресов и PXE.</span><span class="sxs-lookup"><span data-stu-id="09111-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="09111-129">Кроме того можно использовать [загрузочного носителя](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертываний, если не включена поддержка PXE.</span><span class="sxs-lookup"><span data-stu-id="09111-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09111-130">Surface Pro для устройств, настроен на загрузку из сети (загрузки PXE) поддерживается только при использовании Ethernet-адаптер или стыковочного узла корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09111-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="09111-131">Адаптеры Ethernet сторонних производителей не поддерживают PXE с Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="09111-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="09111-132">Для получения дополнительных сведений см [адаптеров Ethernet и контактной развертывания](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="09111-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="09111-133">Настройка System Center Configuration Manager для развертывания операционной системы</span><span class="sxs-lookup"><span data-stu-id="09111-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="09111-134">В этой статье предполагается, что уже имеется работоспособном развертыванию System Center Configuration Manager и не сведений о всех действий, необходимых для развертывания и настройки диспетчера конфигураций с нуля.</span><span class="sxs-lookup"><span data-stu-id="09111-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="09111-135">[Документация и руководство конфигурации](https://docs.microsoft.com/sccm/) на System Center Configuration Manager — это отличный ресурсов; Мы рекомендуем запустить с помощью этих ресурсов, если еще не развернут Диспетчер конфигураций.</span><span class="sxs-lookup"><span data-stu-id="09111-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="09111-136">Чтобы проверить правильность настройки функции развертывания (OSD) операционной системы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="09111-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="09111-137">Проверка и обновление диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="09111-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="09111-138">В консоли диспетчера конфигураций выберите пункты **Администрирование** \> **обновления и обслуживание**.</span><span class="sxs-lookup"><span data-stu-id="09111-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="09111-139">Проверка установленных построения и необходимые обновления, которые еще не были установлены.</span><span class="sxs-lookup"><span data-stu-id="09111-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="09111-140">Просмотрите [Поддержка Windows 10 в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Если вам потребуется обновить развертывание, установите обновление, которое вы хотите установить и выберите **Загрузка**.</span><span class="sxs-lookup"><span data-stu-id="09111-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="09111-141">После завершения загрузки выберите обновление и выберите **Установка пакета обновления**.</span><span class="sxs-lookup"><span data-stu-id="09111-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="09111-142">Настройка точки распространения для поддержки PXE и многоадресными рассылками</span><span class="sxs-lookup"><span data-stu-id="09111-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="09111-143">В консоли диспетчера конфигураций выберите пункты **Администрирование** \> **Точки распространения**.</span><span class="sxs-lookup"><span data-stu-id="09111-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="09111-144">Выберите сервер точка распространения, которое будет обслуживать развертывания комнат группами Майкрософт, а затем выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="09111-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="09111-145">Перейдите на вкладку **PXE** и убедитесь, что включены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="09111-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="09111-146">Включение поддержки PXE для клиентов</span><span class="sxs-lookup"><span data-stu-id="09111-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="09111-147">Разрешить эта точка распространения для ответа на входящие запросы PXE</span><span class="sxs-lookup"><span data-stu-id="09111-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="09111-148">Включение поддержки неизвестный компьютер</span><span class="sxs-lookup"><span data-stu-id="09111-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="09111-149">*Необязательно:* Чтобы включить поддержку многоадресной рассылки, выберите вкладку **многоадресной рассылки** и убедитесь, что включены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="09111-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="09111-150">Включение многоадресной рассылки для отправки данных одновременно нескольких клиентов</span><span class="sxs-lookup"><span data-stu-id="09111-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="09111-151">Настройка диапазона порт UDP-ПОРТ согласно рекомендации ваша группа сети</span><span class="sxs-lookup"><span data-stu-id="09111-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="09111-152">Настройка учетной записи доступа к сети</span><span class="sxs-lookup"><span data-stu-id="09111-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="09111-153">В консоли диспетчера конфигураций выберите пункты **Администрирование** \> **Конфигурации сайта** \> **сайтов**, а затем выберите сайт.</span><span class="sxs-lookup"><span data-stu-id="09111-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="09111-154">В группе **Параметры** выберите **Настройка компонентов сайта** \> **Распространения программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="09111-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="09111-155">Выберите вкладку **Учетной записи доступа к сети** Set up один или несколько учетных записей, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="09111-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="09111-156">Учетные записи не требуется никаких специальных прав, за исключением **доступ к компьютеру из сети** непосредственно на сервере точку распространения.</span><span class="sxs-lookup"><span data-stu-id="09111-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="09111-157">Учетная запись пользователя домена универсальный будет соответствующие.</span><span class="sxs-lookup"><span data-stu-id="09111-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="09111-158">Дополнительные сведения содержатся в разделе [Управление учетными записями для доступа к контенту в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="09111-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="09111-159">Настройка загрузочного образа</span><span class="sxs-lookup"><span data-stu-id="09111-159">Configure a boot image</span></span>

1.  <span data-ttu-id="09111-160">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционной системы** \> **Образы загрузки**.</span><span class="sxs-lookup"><span data-stu-id="09111-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="09111-161">Выберите **в качестве загрузочного образа (x64)** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="09111-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="09111-162">Перейдите на вкладку **Источник данных** и включите **развернуть этот образ загрузки из точки распространения PXE-enabled**.</span><span class="sxs-lookup"><span data-stu-id="09111-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="09111-163">Перейдите на вкладку **Дополнительных компонентов** , чтобы установить необходимые компоненты:</span><span class="sxs-lookup"><span data-stu-id="09111-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="09111-164">Выберите значок «звезда», а поиск **HTML (WinPE HTA)**</span><span class="sxs-lookup"><span data-stu-id="09111-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="09111-165">Нажмите кнопку **ОК** для добавления поддержки HTML-код приложения в образ загрузки.</span><span class="sxs-lookup"><span data-stu-id="09111-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="09111-166">*Необязательно:* Чтобы настроить развертывание, перейдите на вкладку **настройки** .</span><span class="sxs-lookup"><span data-stu-id="09111-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="09111-167">Включите **команда поддерживает (только для тестирования)** , если требуется предоставить доступ к командной строке во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="09111-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="09111-168">Если этот параметр включен, можно начать из командной строки, выбрав **F8** в любой момент во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="09111-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="09111-169">Можно также указать настраиваемые фонового изображения будет отображаться во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="09111-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="09111-170">Чтобы задать изображение, включите **указать файл изображения пользовательский фон (UNC-путь** и выберите пункт фон.</span><span class="sxs-lookup"><span data-stu-id="09111-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="09111-171">В ответ на запрос, выберите вариант **Да** и распространения измененный образ загрузки точкам распространения.</span><span class="sxs-lookup"><span data-stu-id="09111-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="09111-172">Для получения дополнительных сведений в разделе [Управление загрузки изображений с помощью System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="09111-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="09111-173">Можно создать носителя USB для запуска диспетчера конфигураций задач на основе последовательности развертывания в средах, которые не поддерживают PXE.</span><span class="sxs-lookup"><span data-stu-id="09111-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="09111-174">Загрузочный носитель содержит только в качестве загрузочного образа, дополнительные prestart команды и их необходимые файлы и двоичные файлы диспетчера конфигураций для поддержки загрузки среда Предустановки Windows и подключении к Configuration Manager для остальных процесса развертывания.</span><span class="sxs-lookup"><span data-stu-id="09111-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="09111-175">Для получения дополнительных сведений см [порядок создания загрузочного носителя](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="09111-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="09111-176">Создание пакетов Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="09111-176">Create Configuration Manager packages</span></span>

<span data-ttu-id="09111-177">Диспетчер конфигурации требуется количество пакетов для развертывания и настройки единиц измерения комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09111-177">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="09111-178">Для создания и настройки следующих пакетов и затем распространение их системы сайтов Configuration Manager, которым назначены роли сервера точку распространения.</span><span class="sxs-lookup"><span data-stu-id="09111-178">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="09111-179">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="09111-179">**Package name**</span></span>                     | <span data-ttu-id="09111-180">**Тип**</span><span class="sxs-lookup"><span data-stu-id="09111-180">**Type**</span></span>               | <span data-ttu-id="09111-181">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="09111-181">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="09111-182">SRS версии 2 - пакета приложения SRS</span><span class="sxs-lookup"><span data-stu-id="09111-182">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="09111-183">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="09111-183">Software package</span></span>       | <span data-ttu-id="09111-184">Пакет для набора развертывания Microsoft группами комнат</span><span class="sxs-lookup"><span data-stu-id="09111-184">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="09111-185">SRS версии 2 - пакета Sysprep</span><span class="sxs-lookup"><span data-stu-id="09111-185">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="09111-186">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="09111-186">Software package</span></span>       | <span data-ttu-id="09111-187">Пакет для настраиваемых Unattended.xml для настройки единиц измерения комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="09111-187">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="09111-188">SRS версии 2 - Set-SRSComputerName пакета</span><span class="sxs-lookup"><span data-stu-id="09111-188">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="09111-189">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="09111-189">Software package</span></span>       | <span data-ttu-id="09111-190">Пакет для приложения HTML (HTA) для назначения имени компьютера во время развертывания</span><span class="sxs-lookup"><span data-stu-id="09111-190">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="09111-191">SRS версии 2 - настройки программы установки (SRS)</span><span class="sxs-lookup"><span data-stu-id="09111-191">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="09111-192">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="09111-192">Software package</span></span>       | <span data-ttu-id="09111-193">Пакет для настройки развертывания приложения Microsoft группами комнат</span><span class="sxs-lookup"><span data-stu-id="09111-193">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="09111-194">SRS версии 2 - пакета обновления ОС</span><span class="sxs-lookup"><span data-stu-id="09111-194">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="09111-195">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="09111-195">Software package</span></span>       | <span data-ttu-id="09111-196">Пакет для развертывания обновлений обязательные операционной системы</span><span class="sxs-lookup"><span data-stu-id="09111-196">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="09111-197">SRS версии 2 - пакет корневого сертификата</span><span class="sxs-lookup"><span data-stu-id="09111-197">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="09111-198">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="09111-198">Software package</span></span>       | <span data-ttu-id="09111-199">Необязательно - пакет для развертывания корневой сертификат (не требуется для единиц измерения, присоединенный к домену)</span><span class="sxs-lookup"><span data-stu-id="09111-199">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="09111-200">SRS версии 2 - мониторинг агента пакета Microsoft</span><span class="sxs-lookup"><span data-stu-id="09111-200">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="09111-201">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="09111-201">Software package</span></span>       | <span data-ttu-id="09111-202">Необязательно — пакет развертывания и настройки агента пакет управления Microsoft Operations</span><span class="sxs-lookup"><span data-stu-id="09111-202">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="09111-203">SRS версии 2 - пакет WinPE фона</span><span class="sxs-lookup"><span data-stu-id="09111-203">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="09111-204">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="09111-204">Software package</span></span>       | <span data-ttu-id="09111-205">Пакет для настраиваемых фонового изображения для использования с изображениями загрузки</span><span class="sxs-lookup"><span data-stu-id="09111-205">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="09111-206">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="09111-206">Windows 10 Enterprise</span></span>                | <span data-ttu-id="09111-207">Образ операционной системы</span><span class="sxs-lookup"><span data-stu-id="09111-207">Operating system image</span></span> | <span data-ttu-id="09111-208">Пакет для файлов установки операционной системы (install.wim)</span><span class="sxs-lookup"><span data-stu-id="09111-208">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="09111-209">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="09111-209">Surface Pro</span></span>                          | <span data-ttu-id="09111-210">Пакет</span><span class="sxs-lookup"><span data-stu-id="09111-210">Driver package</span></span>         | <span data-ttu-id="09111-211">Пакет для драйверов устройств и встроенного по Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="09111-211">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="09111-212">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="09111-212">Surface Pro 4</span></span>                        | <span data-ttu-id="09111-213">Пакет</span><span class="sxs-lookup"><span data-stu-id="09111-213">Driver package</span></span>         | <span data-ttu-id="09111-214">Пакет для драйверов устройств и встроенного по Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="09111-214">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="09111-215">Для получения дополнительных сведений см [пакеты и программы в System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="09111-215">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="09111-216">Создайте папки для пакета исходных файлов</span><span class="sxs-lookup"><span data-stu-id="09111-216">Create folders for the package source files</span></span>

<span data-ttu-id="09111-217">Диспетчер конфигурации требуется исходных файлов пакета организовывать в определенную структуру папок при их работе и когда они обновлены.</span><span class="sxs-lookup"><span data-stu-id="09111-217">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="09111-218">Создайте следующую структуру папок на сайте центра администрирования System Center Configuration Manager или основного сайта или на сервере, используемом для узла пакет исходных файлов:</span><span class="sxs-lookup"><span data-stu-id="09111-218">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="09111-219">SRS версии 2 - мониторинг агента пакета Microsoft</span><span class="sxs-lookup"><span data-stu-id="09111-219">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="09111-220">SRS версии 2 - пакета обновления ОС</span><span class="sxs-lookup"><span data-stu-id="09111-220">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="09111-221">SRS версии 2 - пакет корневого сертификата</span><span class="sxs-lookup"><span data-stu-id="09111-221">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="09111-222">SRS версии 2 - Set-SRSComputerName пакета</span><span class="sxs-lookup"><span data-stu-id="09111-222">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="09111-223">SRS версии 2 - пакета приложения SRS</span><span class="sxs-lookup"><span data-stu-id="09111-223">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="09111-224">SRS версии 2 - настройки программы установки (SRS)</span><span class="sxs-lookup"><span data-stu-id="09111-224">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="09111-225">SRS версии 2 - пакета Sysprep</span><span class="sxs-lookup"><span data-stu-id="09111-225">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="09111-226">Драйверы</span><span class="sxs-lookup"><span data-stu-id="09111-226">Drivers</span></span>
    -   <span data-ttu-id="09111-227">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="09111-227">Surface Pro</span></span>
    -   <span data-ttu-id="09111-228">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="09111-228">Surface Pro 4</span></span>
-   <span data-ttu-id="09111-229">Операционные системы</span><span class="sxs-lookup"><span data-stu-id="09111-229">Operating Systems</span></span>
    -   <span data-ttu-id="09111-230">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="09111-230">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="09111-231">Можно также [загрузить](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) и использовать ZIP-файл, который включает в себя структуру папок для пакетов, скрипты, которые необходимы для использования и шаблон последовательность задач, который необходимо импортировать.</span><span class="sxs-lookup"><span data-stu-id="09111-231">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="09111-232">Создание пакета агента мониторинг</span><span class="sxs-lookup"><span data-stu-id="09111-232">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="09111-233">Загрузить агента мониторинг из <https://go.microsoft.com/fwlink/?LinkId=828603>.</span><span class="sxs-lookup"><span data-stu-id="09111-233">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="09111-234">Извлечь содержимое пакета в папку **SRS версии 2 - пакета мониторинга агента** , открыв окно командной строки и введите в командной **строке/C: MMASetup AMD64.exe** .</span><span class="sxs-lookup"><span data-stu-id="09111-234">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="09111-235">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="09111-235">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="09111-236">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="09111-236">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="09111-237">Имя<strong>: SRS версии 2 - мониторинг агента пакета Microsoft</strong></span><span class="sxs-lookup"><span data-stu-id="09111-237">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="09111-238">Производитель<strong>: Корпорация Майкрософт</strong></span><span class="sxs-lookup"><span data-stu-id="09111-238">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="09111-239">Версия<strong>: 8.1.11081.0</strong> (введите версию файла, загруженного установки)</span><span class="sxs-lookup"><span data-stu-id="09111-239">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="09111-240">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 - пакет агент мониторинга Microsoft** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-240">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="09111-241">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-241">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="09111-242">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-242">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="09111-243">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-243">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="09111-244">Создание пакета обновления операционной системы</span><span class="sxs-lookup"><span data-stu-id="09111-244">Create the operating system updates package</span></span>

1. <span data-ttu-id="09111-245">В папке **SRS версии 2 - пакета обновления операционной системы** создайте новый сценарий PowerShell с именем **Install-SRSv2-OS-Updates.ps1**.</span><span class="sxs-lookup"><span data-stu-id="09111-245">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="09111-246">Скопируйте приведенный ниже сценарий в сценарий **Install-SRSv2-OS-Updates.ps1** .</span><span class="sxs-lookup"><span data-stu-id="09111-246">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="09111-247">Кроме того можно загрузить скрипт Install-SRSv2-OS-Updates.ps1 [здесь](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="09111-247">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="09111-248">Загрузка обязательных пакетов обновления Windows в ту же папку.</span><span class="sxs-lookup"><span data-stu-id="09111-248">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="09111-249">Во время публикации этой статьи только [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) не требуется.</span><span class="sxs-lookup"><span data-stu-id="09111-249">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="09111-250">Установите флажок [Настройка консоли комнат группами Майкрософт](console.md), чтобы увидеть, требуется ли обновлений.</span><span class="sxs-lookup"><span data-stu-id="09111-250">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="09111-251">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="09111-251">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="09111-252">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="09111-252">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="09111-253">Имя: **SRS версии 2 – операционная система обновляет пакета**</span><span class="sxs-lookup"><span data-stu-id="09111-253">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="09111-254">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="09111-254">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="09111-255">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="09111-255">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="09111-256">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 - пакета обновления операционной системы** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-256">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="09111-257">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-257">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="09111-258">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-258">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="09111-259">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-259">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="09111-260">Создание пакета корневой сертификат (необязательно)</span><span class="sxs-lookup"><span data-stu-id="09111-260">Create the root certificate package (optional)</span></span>

<span data-ttu-id="09111-261">Создайте этот пакет для распространения корневой сертификат для устройств, которые не присоединен к домену Active Directory.</span><span class="sxs-lookup"><span data-stu-id="09111-261">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="09111-262">Создайте этот пакет только в том случае, если применяются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="09111-262">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="09111-263">Развертывание включает локальной Lync или Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="09111-263">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="09111-264">Единицы комнат группами Майкрософт будут настроены для работы в составе рабочей группы, а не входит в домен.</span><span class="sxs-lookup"><span data-stu-id="09111-264">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="09111-265">Скопируйте корневой сертификат в папку **SRS версии 2 — пакет корневого сертификата** .</span><span class="sxs-lookup"><span data-stu-id="09111-265">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="09111-266">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="09111-266">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="09111-267">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="09111-267">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="09111-268">Имя: **SRS версии 2 — корневой сертификат пакета**</span><span class="sxs-lookup"><span data-stu-id="09111-268">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="09111-269">Производитель: *имя вашей организации*</span><span class="sxs-lookup"><span data-stu-id="09111-269">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="09111-270">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="09111-270">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="09111-271">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 — пакет корневого сертификата** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-271">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="09111-272">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-272">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="09111-273">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-273">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="09111-274">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-274">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="09111-275">Создать пакет развертывания комплект Microsoft группами комнат</span><span class="sxs-lookup"><span data-stu-id="09111-275">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="09111-276">Загрузить последнюю версию **набора развертывания Microsoft группами комнат** из <https://go.microsoft.com/fwlink/?linkid=851168>и установить его на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="09111-276">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="09111-277">Копировать содержимое из **C:\\Program Files (x86)\\Скайп комнаты системы Deployment Kit** в папку **SRS версии 2 - пакета приложения SRS** .</span><span class="sxs-lookup"><span data-stu-id="09111-277">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="09111-278">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="09111-278">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="09111-279">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="09111-279">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="09111-280">Имя: **SRS версии 2 – SRS пакета приложения**</span><span class="sxs-lookup"><span data-stu-id="09111-280">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="09111-281">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="09111-281">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="09111-282">Версия: **3.1.104.0** (введите версию файла, загруженного установки)</span><span class="sxs-lookup"><span data-stu-id="09111-282">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="09111-283">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 – SRS пакета приложения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-283">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="09111-284">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-284">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="09111-285">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-285">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="09111-286">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-286">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="09111-287">Создание пакета назначения имя компьютера</span><span class="sxs-lookup"><span data-stu-id="09111-287">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="09111-288">В папке **SRS версии 2 - пакет Set-SRSComputerName** Создание нового приложения HTML с именем **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="09111-288">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="09111-289">Скопируйте приведенный ниже сценарий в файл **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="09111-289">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="09111-290">Кроме того можно загрузить файл Set-SRSComputerName.hta [здесь](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="09111-290">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```
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
3.  <span data-ttu-id="09111-291">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="09111-291">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="09111-292">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="09111-292">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="09111-293">Имя: **SRS версии 2 - Set-SRSComputerName пакета**</span><span class="sxs-lookup"><span data-stu-id="09111-293">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="09111-294">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="09111-294">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="09111-295">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="09111-295">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="09111-296">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 - Set-SRSComputerName пакет** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-296">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="09111-297">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-297">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="09111-298">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-298">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="09111-299">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-299">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="09111-300">Создание пакета Sysprep</span><span class="sxs-lookup"><span data-stu-id="09111-300">Create the Sysprep package</span></span>

1. <span data-ttu-id="09111-301">В папке **SRS версии 2 – пакета Sysprep** создайте новый XML-файл с именем **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="09111-301">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="09111-302">Скопируйте следующий текст в файл **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="09111-302">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="09111-303">Кроме того можно загрузить файл Unattend.xml [здесь](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="09111-303">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
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
3. <span data-ttu-id="09111-304">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="09111-304">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="09111-305">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="09111-305">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="09111-306">Имя: **SRS версии 2 - пакета Sysprep**</span><span class="sxs-lookup"><span data-stu-id="09111-306">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="09111-307">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="09111-307">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="09111-308">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="09111-308">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="09111-309">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 – Sysprep пакет** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-309">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="09111-310">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-310">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="09111-311">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-311">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="09111-312">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-312">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="09111-313">Создание пакета Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="09111-313">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="09111-314">Получить Windows 10 Enterprise x64 мультимедиа и скопируйте в файл **install.wim** **операционные системы\\Windows 10 Enterprise** папки.</span><span class="sxs-lookup"><span data-stu-id="09111-314">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="09111-315">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционные системы** \> **Изображения операционной системы**и затем выберите **Добавить образ операционной системы**.</span><span class="sxs-lookup"><span data-stu-id="09111-315">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="09111-316">Укажите путь к файлу **install.wim** , скопированные и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-316">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="09111-317">Обновить поле **версии** в соответствии с номер сборки Windows 10 Enterprise изображения и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-317">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="09111-318">Просмотрите страницу **сведений** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-318">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="09111-319">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-319">Select **Close**.</span></span>

<span data-ttu-id="09111-320">Для получения дополнительных сведений см. [Управление операционной системы с помощью System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="09111-320">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="09111-321">Создание пакетов драйвера устройства Surface Pro</span><span class="sxs-lookup"><span data-stu-id="09111-321">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="09111-322">Комнат группами Майкрософт поддерживается для Surface Pro и Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="09111-322">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="09111-323">Вам необходимо создать пакет для каждой модели Surface Pro в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="09111-323">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09111-324">Драйверы должен быть совместим с Windows 10 Enterprise построения и версия набора развертывания комнат группы Microsoft.</span><span class="sxs-lookup"><span data-stu-id="09111-324">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="09111-325">Дополнительные сведения можно [загрузить последние встроенного по и драйверы устройств контактной](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) и [Настройка консоли](console.md).</span><span class="sxs-lookup"><span data-stu-id="09111-325">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="09111-326">Загрузите последние драйверы и встроенного по.</span><span class="sxs-lookup"><span data-stu-id="09111-326">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="09111-327">Для Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="09111-327">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="09111-328">Для Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="09111-328">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="09111-329">Извлеките загруженного драйвера и микропрограммы.</span><span class="sxs-lookup"><span data-stu-id="09111-329">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="09111-330">Откройте окно командной строки и в командной строке введите одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="09111-330">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="09111-331">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционные системы** \> **факторов**и выберите команду **Импорт драйвер**.</span><span class="sxs-lookup"><span data-stu-id="09111-331">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="09111-332">Выберите **Импорт всех драйверов в сети по следующему пути (UNC)**, выберите папку источника (например, C:\\_Sources\\драйверы\\Surface Pro) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-332">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="09111-333">На странице **Укажите сведения для импортированных драйверов** выберите вышеперечисленных драйверов и выберите **Включить эти драйверы и разрешить компьютерах, чтобы установить их**.</span><span class="sxs-lookup"><span data-stu-id="09111-333">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="09111-334">Выберите **категории**, создания новой категории, который соответствует поверхности модели, нажмите **кнопку OK**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-334">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="09111-335">Выберите **новый пакет**.</span><span class="sxs-lookup"><span data-stu-id="09111-335">Select **New Package**.</span></span>

8.  <span data-ttu-id="09111-336">Укажите имя пакета, который соответствует Surface Pro модели, введите путь к папке для хранения файлов пакета драйвера, нажмите **ОК**и затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-336">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="09111-337">На странице **загрузки изображений** убедитесь, что выбраны не загрузки изображения и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-337">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="09111-338">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-338">Select **Close**.</span></span>

11. <span data-ttu-id="09111-339">Последовательно выберите пункты **Библиотеки программного обеспечения** \> **операционные системы** \> **драйверов**, выберите **папку \> создать папку**и введите имя папки, которая соответствует Surface Pro модели, который был только что импортирован драйверы.</span><span class="sxs-lookup"><span data-stu-id="09111-339">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="09111-340">Перемещение всех импортированных драйверов только что созданная папка для упрощения навигации и операции.</span><span class="sxs-lookup"><span data-stu-id="09111-340">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="09111-341">Повторите те же действия для других Surface Pro моделей, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="09111-341">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="09111-342">Дополнительные сведения содержатся в разделе [Управление драйверами в System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="09111-342">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="09111-343">Создание пакета конфигурации комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="09111-343">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="09111-344">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="09111-344">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="09111-345">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="09111-345">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="09111-346">Имя: **SRS версии 2 — Настройка пакета установки SRS**</span><span class="sxs-lookup"><span data-stu-id="09111-346">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="09111-347">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="09111-347">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="09111-348">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="09111-348">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="09111-349">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 — Настройка программы установки SRS** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-349">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="09111-350">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-350">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="09111-351">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-351">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="09111-352">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-352">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="09111-353">Распространение пакетов Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="09111-353">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="09111-354">Все пакеты должен распространяться на серверы, которые были назначены роли точки распространения в иерархии диспетчера конфигураций.</span><span class="sxs-lookup"><span data-stu-id="09111-354">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="09111-355">Следуйте приведенным ниже инструкциям для инициации пакет рассылки.</span><span class="sxs-lookup"><span data-stu-id="09111-355">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="09111-356">Распространение пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="09111-356">Distribute software packages.</span></span>

    1.  <span data-ttu-id="09111-357">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**.</span><span class="sxs-lookup"><span data-stu-id="09111-357">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="09111-358">Установите все пакеты программного обеспечения, который необходимо отправить, а затем выберите **Распределения контента**.</span><span class="sxs-lookup"><span data-stu-id="09111-358">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="09111-359">Просмотрите список пакетов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-359">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="09111-360">Добавление в список всех серверов рассылки (или точка группы рассылки, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-360">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="09111-361">Нажмите кнопку **Далее**и затем выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-361">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="09111-362">Распространение пакетов драйверов.</span><span class="sxs-lookup"><span data-stu-id="09111-362">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="09111-363">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционные системы** \> **Пакетов драйверов**.</span><span class="sxs-lookup"><span data-stu-id="09111-363">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="09111-364">Установите все пакеты драйверов, который необходимо отправить, а затем выберите **Распределения контента**.</span><span class="sxs-lookup"><span data-stu-id="09111-364">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="09111-365">Просмотрите список пакетов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-365">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="09111-366">Добавление в список всех серверов рассылки (или точка группы рассылки, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-366">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="09111-367">Нажмите кнопку **Далее**и затем выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-367">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="09111-368">Распространение пакетов операционной системы.</span><span class="sxs-lookup"><span data-stu-id="09111-368">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="09111-369">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционные системы** \> **Изображений операционной системы**.</span><span class="sxs-lookup"><span data-stu-id="09111-369">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="09111-370">Выделите все изображения операционной системы, который необходимо отправить, а затем выберите **Распределения контента**.</span><span class="sxs-lookup"><span data-stu-id="09111-370">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="09111-371">Просмотрите список пакетов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-371">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="09111-372">Добавление в список всех серверов рассылки (или точка группы рассылки, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-372">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="09111-373">Нажмите кнопку **Далее**и затем выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-373">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="09111-374">Пакет рассылки может занять некоторое время, в зависимости от того, размер пакета, иерархии Configuration Manager, несколько серверов рассылки и пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="09111-374">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="09111-375">Перед началом развертывания подразделения Microsoft группами комнат распространяемых всех пакетов.</span><span class="sxs-lookup"><span data-stu-id="09111-375">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="09111-376">Можно просмотреть состояние дистрибутива пакет в консоли диспетчера конфигураций, перейдя на **мониторинг** \> **Состояние рассылки** \> **Состояние содержимого**.</span><span class="sxs-lookup"><span data-stu-id="09111-376">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="09111-377">Последовательности задач Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="09111-377">Configuration Manager task sequences</span></span>

<span data-ttu-id="09111-378">Используйте последовательности задач с помощью System Center Configuration Manager для автоматизации действия для развертывания образа операционной системы на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="09111-378">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="09111-379">Чтобы развернуть единицы комнат группами Майкрософт в автоматическом режиме, создание последовательности задач, который ссылается загрузки изображение, используемое для запуска на конечном компьютере комнат группами Майкрософт, образ операционной системы Windows 10 Enterprise, необходимо установить и какие-либо другие дополнительное содержимое, например других приложений и обновлений программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="09111-379">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="09111-380">Импорт образца последовательности задач</span><span class="sxs-lookup"><span data-stu-id="09111-380">Import the sample task sequence</span></span>

<span data-ttu-id="09111-381">Загрузите и легко импортировать последовательность задач образца и настроить его в соответствии со своими потребностями.</span><span class="sxs-lookup"><span data-stu-id="09111-381">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="09111-382">[**Загрузить**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) пример последовательности задач и скопируйте загруженный ZIP-файл в общую папку.</span><span class="sxs-lookup"><span data-stu-id="09111-382">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="09111-383">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционные системы** \> **Последовательности задач**, а затем выберите **Импорт последовательности задач**.</span><span class="sxs-lookup"><span data-stu-id="09111-383">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="09111-384">Выберите **Обзор**, перейдите в расположение общей папки, которые использовались на шаге 1, выберите **Microsoft Deployment комнат группами (EN-US) ZIP-** файл и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-384">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="09111-385">Задайте **Действие** для **Создания новых**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-385">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="09111-386">Подтвердите параметры и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-386">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="09111-387">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-387">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="09111-388">Проверьте, правильно связанные пакеты Справочник по каждому шагу последовательность задач.</span><span class="sxs-lookup"><span data-stu-id="09111-388">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="09111-389">Выберите последовательность импортированных задач, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="09111-389">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="09111-390">Редактор последовательность задач открывает и отображает каждого последовательного этапа, на котором необходимо развернуть и настроить единицы комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09111-390">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="09111-391">Познакомьтесь с помощью каждого шага и выполните рекомендуемые обновления.</span><span class="sxs-lookup"><span data-stu-id="09111-391">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="09111-392">**Перезапустите в среда Предустановки Windows**: это действие перезагрузки и затем загружается Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="09111-392">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="09111-393">Изменения не требуются для этого шага.</span><span class="sxs-lookup"><span data-stu-id="09111-393">No changes are required for this step.</span></span>

   2. <span data-ttu-id="09111-394">**Раздел диска 0 – UEFI**: это действие стирание конфигурация диска и создает разделы, в зависимости от настроек параметров.</span><span class="sxs-lookup"><span data-stu-id="09111-394">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="09111-395">Мы рекомендуем не вносите никаких изменений в этот этап.</span><span class="sxs-lookup"><span data-stu-id="09111-395">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="09111-396">**Задайте имя компьютера SRS**: этот этап включает в себя HTML приложения предоставляют пользовательский Интерфейс для задания имени компьютера для единицы комнат группами Майкрософт во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="09111-396">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="09111-397">Это необязательное действие, но она может быть отключена, только если вы собираетесь управлять именования через альтернативный процесс компьютера.</span><span class="sxs-lookup"><span data-stu-id="09111-397">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="09111-398">Убедитесь, что установлен пакет **SRS v2 - Set-SRSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="09111-398">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="09111-399">В противном случае перейдите к пакету и выберите его.</span><span class="sxs-lookup"><span data-stu-id="09111-399">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="09111-400">**Применение операционной системы**: это действие задает образа операционной системы для развертывания и файл ответов автоматической Sysprep для использования.</span><span class="sxs-lookup"><span data-stu-id="09111-400">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="09111-401">Убедитесь, что выбран правильный файл образа операционной системы Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="09111-401">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="09111-402">Убедитесь, что включена **Автоматическая используйте или файла ответов Sysprep для выборочной установки** , и выбран **SRS версии 2 - пакета Sysprep** .</span><span class="sxs-lookup"><span data-stu-id="09111-402">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="09111-403">Также убедитесь, что **Имя файла** задано значение **unattend.xml**.</span><span class="sxs-lookup"><span data-stu-id="09111-403">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="09111-404">**Применение параметров Windows**: это действие собирает сведения об установке Windows.</span><span class="sxs-lookup"><span data-stu-id="09111-404">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="09111-405">Предоставляют сведения о лицензировании и регистрации, включая ключ продукта, пароль учетной записи локального администратора и часового пояса (в зависимости от потребностей).</span><span class="sxs-lookup"><span data-stu-id="09111-405">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="09111-406">**Применение параметров сети**: это действие позволяет указать рабочая группа или домен Active Directory и подразделение.</span><span class="sxs-lookup"><span data-stu-id="09111-406">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="09111-407">В разделе [Система комнаты Скайп домена присоединение вопросы](domain-joining-considerations.md) рекомендованные действия, которые необходимо выполнить в развертывании единицы комнат группами Майкрософт как участники домена Actve Directory.</span><span class="sxs-lookup"><span data-stu-id="09111-407">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="09111-408">**Применить факторами:** Этот шаг и его дочерних действий используются для развертывания требуемых драйверов и встроенного по на основе модели Surface Pro, у вас есть.</span><span class="sxs-lookup"><span data-stu-id="09111-408">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="09111-409">Обновите каждый шаг, чтобы указать соответствующие пакет, связанный с этой развертывания.</span><span class="sxs-lookup"><span data-stu-id="09111-409">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="09111-410">Каждый пакет настроен на использование фильтров инструментария управления Windows (WMI) для развертывания соответствующих факторов и встроенного по на основании Surface Pro одновременное внесение и модели.</span><span class="sxs-lookup"><span data-stu-id="09111-410">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="09111-411">Настоятельно рекомендуется не изменять конфигурацию этих факторов, в противном случае возможны ошибки при развертывании.</span><span class="sxs-lookup"><span data-stu-id="09111-411">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="09111-412">**Настройка Windows и Диспетчер конфигураций**: это действие развертывает и настраивает клиент диспетчера конфигураций.</span><span class="sxs-lookup"><span data-stu-id="09111-412">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="09111-413">Обновите этот шаг, чтобы указать встроенных клиентский пакет диспетчера конфигураций.</span><span class="sxs-lookup"><span data-stu-id="09111-413">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="09111-414">**Установка корневого сертификата**: это действие распределяет корневой сертификат для устройств, не являющиеся – присоединенный к домену и поэтому необязательно и отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="09111-414">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="09111-415">Включите этот шаг, если вам нужно развернуть корневой сертификат единицы комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09111-415">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="09111-416">Если нужно выполнить это действие, убедитесь, что выбраны **SRS v2 — пакет корневого сертификата** и **системы в режиме одобрения администратором отключить 64-разрядная версия файла** .</span><span class="sxs-lookup"><span data-stu-id="09111-416">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="09111-417">**Установка и настройка агента мониторинг**: это действие устанавливает 64-разрядная версия агента монитор Microsoft Azure и настраивает агент для подключения к вашей рабочей области для анализа журнала.</span><span class="sxs-lookup"><span data-stu-id="09111-417">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="09111-418">Это действие по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="09111-418">This step is disabled by default.</span></span> <span data-ttu-id="09111-419">Включите этот шаг только в том случае, если вы собираетесь использовать агент мониторинга позволяют отслеживать состояние единиц комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09111-419">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="09111-420">Измените это действие и обновите параметры командной строки для указания **Идентификатора рабочей области** и **Рабочая область для ключа**.</span><span class="sxs-lookup"><span data-stu-id="09111-420">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="09111-421">[Настройка тестовых устройств для наблюдение за Azure](azure-monitor.md#configure-test-devices-for-azure-monitoring) более подробные сведения о получении идентификатор операции управления Suite рабочей области и первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="09111-421">See [Configure test devices for Azure Monitoring](azure-monitor.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="09111-422">Убедитесь, что выбраны **SRS v2 — пакет агент мониторинга Microsoft** и **системы в режиме одобрения администратором отключить 64-разрядная версия файла** .</span><span class="sxs-lookup"><span data-stu-id="09111-422">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="09111-423">Дополнительные сведения о мониторинге работоспособности развертывания комнат группами Майкрософт в разделе [Управление планирование комнат группы Microsoft Azure монитор](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Управление группами Майкрософт развернуть комнат с Azure монитор](azure-monitor.md) и [Управление Microsoft Групп устройств комнат с монитором Azure](../../manage/skype-room-systems-v2/azure-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="09111-423">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](../../manage/skype-room-systems-v2/azure-monitor.md).</span></span>

   11. <span data-ttu-id="09111-424">**SRS копии файлов конфигурации версии 2**: это действие копирует необходимые файлы установки и настройки набор средств развертывания Microsoft группами комнат на локальный жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="09111-424">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="09111-425">Без настройки необходим для этого шага.</span><span class="sxs-lookup"><span data-stu-id="09111-425">No customization is required for this step.</span></span>
       -   <span data-ttu-id="09111-426">Убедитесь, что выбраны **v2 SRS – SRS пакета приложения** и **системы в режиме одобрения администратором отключить 64-разрядная версия файла** .</span><span class="sxs-lookup"><span data-stu-id="09111-426">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="09111-427">**Install-SRSv2-OS-обновлений**: это действие развертывает любые необходимые требований для развертывания Microsoft группами комнат обновления обязательные операционной системы.</span><span class="sxs-lookup"><span data-stu-id="09111-427">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="09111-428">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="09111-428">Do the following:</span></span>
       -   <span data-ttu-id="09111-429">Установите флажок [Настройка консоли комнат группами Майкрософт](console.md) , чтобы видеть, какие обновления необходимы.</span><span class="sxs-lookup"><span data-stu-id="09111-429">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="09111-430">Убедитесь, что ваш **SRS версии 2 — пакет обновления операционная система** включает все необходимые обновления.</span><span class="sxs-lookup"><span data-stu-id="09111-430">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="09111-431">Убедитесь, что выбран пункт **SRS версии 2 — пакет обновления операционной системы** .</span><span class="sxs-lookup"><span data-stu-id="09111-431">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="09111-432">Убедитесь, что для **сервера-посредника**политику выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09111-432">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="09111-433">**Перезапустите компьютер**: это действие перезагрузить компьютер после установки обновлений обязательные операционной системы.</span><span class="sxs-lookup"><span data-stu-id="09111-433">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="09111-434">Без настройки необходим для этого шага.</span><span class="sxs-lookup"><span data-stu-id="09111-434">No customization is required for this step.</span></span>

   14. <span data-ttu-id="09111-435">**Настройка компонентов Windows**: этот шаг выполняется настройка необходимых компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="09111-435">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="09111-436">Без настройки необходим для этого шага.</span><span class="sxs-lookup"><span data-stu-id="09111-436">No customization is required for this step.</span></span>

   15. <span data-ttu-id="09111-437">**Перезапустите компьютер**: это действие перезагрузить компьютер после настройки компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="09111-437">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="09111-438">Без настройки необходим для этого шага.</span><span class="sxs-lookup"><span data-stu-id="09111-438">No customization is required for this step.</span></span>

   16. <span data-ttu-id="09111-439">**Добавление пользователя локальной Скайп**: на этом этапе создается локальная учетная запись Скайп используется для автоматического входа в Windows и запустите приложение комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09111-439">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="09111-440">Этот шаг не имеет любой пакет программного обеспечения, связанные с ним и для его необходим без настройки.</span><span class="sxs-lookup"><span data-stu-id="09111-440">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="09111-441">**Задать и настройке приложения SRS**: этот шаг выполняется настройка установки приложения комнат группами Майкрософт для следующей загрузки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="09111-441">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="09111-442">Убедитесь, что выбраны **SRS версии 2 — Настройка пакета установки SRS** и **системы в режиме одобрения администратором отключить 64-разрядная версия файла** .</span><span class="sxs-lookup"><span data-stu-id="09111-442">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09111-443">Очень важно, что действия последовательность задач должны быть в порядке следования.</span><span class="sxs-lookup"><span data-stu-id="09111-443">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="09111-444">Изменение порядка шагов или настроить дополнительные действия может перестать работать развертывания.</span><span class="sxs-lookup"><span data-stu-id="09111-444">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="09111-445">**Задать и настройке приложения SRS** шаг должен быть последний шаг в последовательности задач, в противном случае возможны ошибки при развертывании.</span><span class="sxs-lookup"><span data-stu-id="09111-445">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="09111-446">Создание развертывания для последовательности задач</span><span class="sxs-lookup"><span data-stu-id="09111-446">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="09111-447">Выберите последовательность задач и затем выберите команду **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="09111-447">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="09111-448">Выберите **Обзор** для выбора целевой коллекции для развертывания.</span><span class="sxs-lookup"><span data-stu-id="09111-448">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="09111-449">Выберите **Все неизвестные компьютеры** и нажмите кнопку « **ОК»**.</span><span class="sxs-lookup"><span data-stu-id="09111-449">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="09111-450">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-450">Select **Next**.</span></span>

5. <span data-ttu-id="09111-451">Выберите пункт **доступен** на **Цель** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="09111-451">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="09111-452">Выберите в списке **становится доступной для следующих** **только мультимедиа и PXE** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-452">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="09111-453">Очень важно, что **Цель** задано значение **доступен**.</span><span class="sxs-lookup"><span data-stu-id="09111-453">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="09111-454">Убедитесь в том, что **Цель** — **не** присвоено значение **требуется**.</span><span class="sxs-lookup"><span data-stu-id="09111-454">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="09111-455">Также убедитесь в том, выберите **только мультимедиа и PXE** в **становится доступной для следующих**.</span><span class="sxs-lookup"><span data-stu-id="09111-455">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="09111-456">Установка этих значений в какой-либо другой может привести к всех компьютеров для получения образа развертывания комнат группами Майкрософт при загрузке.</span><span class="sxs-lookup"><span data-stu-id="09111-456">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="09111-457">Не указать любой расписания и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-457">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="09111-458">Не изменять что-либо в разделе **Взаимодействие с пользователем** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-458">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="09111-459">Не изменять что-либо в разделе **оповещения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-459">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="09111-460">Не изменять что-либо в разделе **Точки распространения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-460">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="09111-461">Проверьте параметры и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-461">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="09111-462">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="09111-462">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="09111-463">Проверка и устранение неполадок решения</span><span class="sxs-lookup"><span data-stu-id="09111-463">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="09111-464">После выполнения последовательности задач System Center Configuration Manager, вам потребуются для выполнения теста для проверки, что последовательности задач развертывания и настройки единиц измерения комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="09111-464">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="09111-465">Подключение устройства проверки проводной сети с помощью одного из поддерживаемых адаптеров Ethernet или с помощью контактной закрепления.</span><span class="sxs-lookup"><span data-stu-id="09111-465">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="09111-466">Если функциональные возможности загрузки PXE еще не была настроена для вашей среды, можно использовать в качестве загрузочного образа на USB флэш-диск [созданный ранее](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) для загрузки с USB и подключиться к диспетчеру конфигурации.</span><span class="sxs-lookup"><span data-stu-id="09111-466">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="09111-467">Доступ к встроенного по и для начала загрузки PXE:</span><span class="sxs-lookup"><span data-stu-id="09111-467">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="09111-468">Убедитесь, что выключен устройств.</span><span class="sxs-lookup"><span data-stu-id="09111-468">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="09111-469">Нажмите и удерживайте кнопку **Увеличения громкости** .</span><span class="sxs-lookup"><span data-stu-id="09111-469">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="09111-470">Нажмите клавишу и кнопку **питания** .</span><span class="sxs-lookup"><span data-stu-id="09111-470">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="09111-471">После устройство начинает загрузку, выпуск кнопка **Увеличения громкости** .</span><span class="sxs-lookup"><span data-stu-id="09111-471">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="09111-472">Выберите **конфигурацию загрузки**.</span><span class="sxs-lookup"><span data-stu-id="09111-472">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="09111-473">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="09111-473">Do one of the following:</span></span>

        -   <span data-ttu-id="09111-474">Выберите **загрузки PXE**и перетащите его в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="09111-474">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="09111-475">Кроме того будет предложено провести слева на сетевом адаптере для загрузки на устройство немедленно.</span><span class="sxs-lookup"><span data-stu-id="09111-475">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="09111-476">Это не влияет на порядок загрузки.</span><span class="sxs-lookup"><span data-stu-id="09111-476">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="09111-477">Выберите флэш-накопитель USB, в котором размещается загрузки мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="09111-477">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="09111-478">Выберите **Выход**и выберите пункт **Перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="09111-478">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="09111-479">При появлении соответствующего запроса выберите параметр **ввести** для загрузки сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="09111-479">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="09111-480">Среда Предустановки Windows будет загружен в память, и будет запущен мастер последовательность задач.</span><span class="sxs-lookup"><span data-stu-id="09111-480">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="09111-481">Нажмите кнопку **Далее** для продолжения.</span><span class="sxs-lookup"><span data-stu-id="09111-481">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="09111-482">Выберите последовательность задач, который был импортирован ранее и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09111-482">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="09111-483">После применения конфигурации диска, будет предложено указать имя компьютера для устройства.</span><span class="sxs-lookup"><span data-stu-id="09111-483">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="09111-484">Пользовательский интерфейс будет отображаться имя рекомендуемые компьютера, на основании серийный номер устройства Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="09111-484">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="09111-485">Можно принять предлагаемое имя или указать новый.</span><span class="sxs-lookup"><span data-stu-id="09111-485">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="09111-486">Следуйте инструкциям на экране назначения имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="09111-486">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="09111-487">При выборе **принять**началом развертывания.</span><span class="sxs-lookup"><span data-stu-id="09111-487">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="09111-488">Процесс развертывания происходит автоматически и не запрашивать любые дополнительные пользовательского ввода.</span><span class="sxs-lookup"><span data-stu-id="09111-488">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="09111-489">По завершении настройки устройства последовательности задач развертывания вы увидите на следующем экране конфигурации запросом для настройки параметров приложения Microsoft группами комнат.</span><span class="sxs-lookup"><span data-stu-id="09111-489">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Начальный экран для приложения Microsoft группами комнат](../../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="09111-491">Подключите Surface Pro консоли комнат группами Майкрософт и настройте параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="09111-491">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="09111-492">Проверка работы возможности, перечисленные в [справке по Microsoft группами комнат](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) на развернутое устройства.</span><span class="sxs-lookup"><span data-stu-id="09111-492">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="09111-493">Для устранения сбоя установки проверьте файл **SMSTS.log** , который записывает все действия, описанные в последовательности задач Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="09111-493">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="09111-494">Файл SMSTS.log сохраняется на одном из нескольких путей, в зависимости от этапа построения.</span><span class="sxs-lookup"><span data-stu-id="09111-494">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="09111-495">Проверьте следующую таблицу для определения пути к файлу SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="09111-495">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="09111-496">**Этап развертывания**</span><span class="sxs-lookup"><span data-stu-id="09111-496">**Deployment phase**</span></span>                                                            | <span data-ttu-id="09111-497">**Путь к журналу последовательности задач**</span><span class="sxs-lookup"><span data-stu-id="09111-497">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="09111-498">WinPE, прежде чем формат жесткого диска</span><span class="sxs-lookup"><span data-stu-id="09111-498">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="09111-499">X:\\Windows\\Temp\\smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="09111-499">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="09111-500">WinPE после формат жесткого диска</span><span class="sxs-lookup"><span data-stu-id="09111-500">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="09111-501">C:\\_SMSTaskSequence\\журналы\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="09111-501">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="09111-502">Операционная система, развертывание, до установки агента Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="09111-502">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="09111-503">c:\\_SMSTaskSequence\\журналы\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="09111-503">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="09111-504">Операционная система и диспетчер конфигурации агента развертывания</span><span class="sxs-lookup"><span data-stu-id="09111-504">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="09111-505">% windir %\\System32\\ccm\\журналы\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="09111-505">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="09111-506">Выполнение последовательности задач завершено</span><span class="sxs-lookup"><span data-stu-id="09111-506">Task sequence execution complete</span></span>                                                | <span data-ttu-id="09111-507">% windir %\\System32\\ccm\\журналы\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="09111-507">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="09111-508">Выберите **F8** в любой момент во время последовательности задач, чтобы открыть консоль командной строки и затем получите доступ к файлу SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="09111-508">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="09111-509">Для устранения неполадок загрузки PXE, проверьте два файлы журнала на сервере Configuration Manager, которые специфичны для PXE действия:</span><span class="sxs-lookup"><span data-stu-id="09111-509">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="09111-510">**Pxecontrol.log**, расположенный в каталоге журналы установки диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="09111-510">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="09111-511">**Smspxe.log**, находится в каталоге журналы точка управления диспетчер конфигурации (MP)</span><span class="sxs-lookup"><span data-stu-id="09111-511">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="09111-512">Полный список файлов журнала, которые можно использовать для устранения установки диспетчера конфигураций просмотрите [файлы журналов в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="09111-512">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
