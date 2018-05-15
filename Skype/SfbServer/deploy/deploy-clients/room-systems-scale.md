---
title: Развертывание Скайп комнаты систем с помощью System Center Configuration Manager
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: В данном разделе приведены сведения о развертывании версии 2 Скайп комнаты систем на крупномасштабного развертывания в среде.
ms.openlocfilehash: 33ac42e42695a7881d6348aee32046223f97b418
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2018
---
# <a name="deploy-skype-room-systems-v2-by-using-system-center-configuration-manager"></a><span data-ttu-id="1fafd-103">Развертывание системы комнаты Скайп версии 2 с помощью System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1fafd-103">Deploy Skype Room Systems v2 by using System Center Configuration Manager</span></span>

<span data-ttu-id="1fafd-104">В этой статье приводятся все необходимые сведения для создания развертываний версии 2 Скайп комнаты систем с помощью System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="1fafd-104">This article gives you all the necessary information to create your Skype Room Systems v2 deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="1fafd-105">С помощью простых в использовании методы, предоставляемые с System Center Configuration Manager можно развернуть в операционной системе и другие приложения на нескольких устройствах.</span><span class="sxs-lookup"><span data-stu-id="1fafd-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="1fafd-106">Подход, показано ниже инструкции по конфигурации диспетчера конфигураций и настроить образец пакетов и сценарии, представленные в этом руководстве, необходимые для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1fafd-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Процесс развертывания систем комнаты Скайп версии 2 с помощью диспетчера конфигураций](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="1fafd-108">В этом решении протестирована только с развертываниями Surface Pro на основе.</span><span class="sxs-lookup"><span data-stu-id="1fafd-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="1fafd-109">Следуйте рекомендациям производителя для конфигураций, не основанных на Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="1fafd-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="1fafd-110">Проверка необходимых компонентов</span><span class="sxs-lookup"><span data-stu-id="1fafd-110">Validate prerequisites</span></span>

<span data-ttu-id="1fafd-111">Для развертывания версии 2 Скайп комнаты систем с помощью Configuration Manager, убедитесь, что выполняются следующие необходимые условия и требования.</span><span class="sxs-lookup"><span data-stu-id="1fafd-111">To deploy Skype Room Systems v2 with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="1fafd-112">Требования к System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1fafd-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="1fafd-113">System Center Configuration Manager версии должен быть по крайней мере 1706 или выше.</span><span class="sxs-lookup"><span data-stu-id="1fafd-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="1fafd-114">Рекомендуется использовать 1710 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="1fafd-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="1fafd-115">Извлечение [поддержки для Windows 10 в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) , чтобы узнать о версиях Windows 10, поддерживаемые Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="1fafd-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="1fafd-116">Поддерживаемая версия Deployment Kit (ADK) для Windows 10 и оценки необходимо установить.</span><span class="sxs-lookup"><span data-stu-id="1fafd-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="1fafd-117">В разделе версий [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) , который можно использовать с разными версиями Configuration Manager и убедитесь, что ваше развертывание содержит правильную версию.</span><span class="sxs-lookup"><span data-stu-id="1fafd-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="1fafd-118">Серверы системы сайта должна быть назначена роль точки распространения и образы загрузки должна быть включена для [протокол удаленной загрузки поддержка выполнения среды (PXE)](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) для включения инициировал сети развертываний.</span><span class="sxs-lookup"><span data-stu-id="1fafd-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="1fafd-119">Если не включена поддержка PXE, можно использовать [загрузочного носителя](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="1fafd-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="1fafd-120">Учетная запись доступа к сети должен быть настроен для поддержки новых сценариев развертывания компьютера (исходное).</span><span class="sxs-lookup"><span data-stu-id="1fafd-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="1fafd-121">Для получения дополнительных сведений о конфигурации учетной записи доступа к сети, просмотрите [Управление учетными записями для доступа к контенту в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="1fafd-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="1fafd-122">Рекомендуется включить [поддержку многоадресной рассылки](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), если вы скорее всего развертывать один образ версии 2 Скайп комнаты систем на несколько единиц измерения в то же время.</span><span class="sxs-lookup"><span data-stu-id="1fafd-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Skype Room Systems v2 image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="1fafd-123">Требования к сети</span><span class="sxs-lookup"><span data-stu-id="1fafd-123">Networking requirements</span></span>

-   <span data-ttu-id="1fafd-124">Сети должен иметь протокол динамической конфигурации узла (DHCP) сервера, настроенного для автоматического распределения адрес IP-адресов для подсетей, где будет развертываться единиц измерения систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="1fafd-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Skype Room Systems v2 units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1fafd-125">Продолжительность аренды DHCP должно быть присвоено значение длиннее во время выполнения развертывания образа.</span><span class="sxs-lookup"><span data-stu-id="1fafd-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="1fafd-126">В противном случае может произойти сбой развертывания.</span><span class="sxs-lookup"><span data-stu-id="1fafd-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="1fafd-127">Сети, включая параметры и виртуальных локальных сетей (VLAN), необходимо настроить для поддержки PXE.</span><span class="sxs-lookup"><span data-stu-id="1fafd-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="1fafd-128">Обратитесь к поставщику сети Дополнительные сведения о конфигурации модуля поддержки IP-адресов и PXE.</span><span class="sxs-lookup"><span data-stu-id="1fafd-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="1fafd-129">Кроме того можно использовать [загрузочного носителя](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертываний, если не включена поддержка PXE.</span><span class="sxs-lookup"><span data-stu-id="1fafd-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1fafd-130">Surface Pro для устройств, настроен на загрузку из сети (загрузки PXE) поддерживается только при использовании Ethernet-адаптер или стыковочного узла корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1fafd-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="1fafd-131">Адаптеры Ethernet сторонних производителей не поддерживают PXE с Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="1fafd-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="1fafd-132">Для получения дополнительных сведений см [адаптеров Ethernet и контактной развертывания](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="1fafd-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="1fafd-133">Настройка System Center Configuration Manager для развертывания операционной системы</span><span class="sxs-lookup"><span data-stu-id="1fafd-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="1fafd-134">В этой статье предполагается, что уже имеется работоспособном развертыванию System Center Configuration Manager и не сведений о всех действий, необходимых для развертывания и настройки диспетчера конфигураций с нуля.</span><span class="sxs-lookup"><span data-stu-id="1fafd-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="1fafd-135">[Документация и руководство конфигурации](https://docs.microsoft.com/sccm/) на System Center Configuration Manager — это отличный ресурсов; Мы рекомендуем запустить с помощью этих ресурсов, если еще не развернут Диспетчер конфигураций.</span><span class="sxs-lookup"><span data-stu-id="1fafd-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="1fafd-136">Чтобы проверить правильность настройки функции развертывания (OSD) операционной системы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1fafd-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="1fafd-137">Проверка и обновление диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="1fafd-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="1fafd-138">В консоли диспетчера конфигураций выберите пункты **Администрирование** \> **обновления и обслуживание**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="1fafd-139">Проверка установленных построения и необходимые обновления, которые еще не были установлены.</span><span class="sxs-lookup"><span data-stu-id="1fafd-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="1fafd-140">Просмотрите [Поддержка Windows 10 в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Если вам потребуется обновить развертывание, установите обновление, которое вы хотите установить и выберите **Загрузка**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="1fafd-141">После завершения загрузки выберите обновление и выберите **Установка пакета обновления**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="1fafd-142">Настройка точки распространения для поддержки PXE и многоадресными рассылками</span><span class="sxs-lookup"><span data-stu-id="1fafd-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="1fafd-143">В консоли диспетчера конфигураций выберите пункты **Администрирование** \> **Точки распространения**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="1fafd-144">Выберите сервер точка распространения, который будет обслуживать развертывания систем комнаты Скайп версии 2 и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-144">Select the distribution point server that will serve the Skype Room Systems v2 deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="1fafd-145">Перейдите на вкладку **PXE** и убедитесь, что включены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1fafd-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span> 
    -   <span data-ttu-id="1fafd-146">Включение поддержки PXE для клиентов</span><span class="sxs-lookup"><span data-stu-id="1fafd-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="1fafd-147">Разрешить эта точка распространения для ответа на входящие запросы PXE</span><span class="sxs-lookup"><span data-stu-id="1fafd-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="1fafd-148">Включение поддержки неизвестный компьютер</span><span class="sxs-lookup"><span data-stu-id="1fafd-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="1fafd-149">*Необязательно:* Чтобы включить поддержку многоадресной рассылки, выберите вкладку **многоадресной рассылки** и убедитесь, что включены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1fafd-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="1fafd-150">Включение многоадресной рассылки для отправки данных одновременно нескольких клиентов</span><span class="sxs-lookup"><span data-stu-id="1fafd-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="1fafd-151">Настройка диапазона порт UDP-ПОРТ согласно рекомендации ваша группа сети</span><span class="sxs-lookup"><span data-stu-id="1fafd-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="1fafd-152">Настройка учетной записи доступа к сети</span><span class="sxs-lookup"><span data-stu-id="1fafd-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="1fafd-153">В консоли диспетчера конфигураций выберите пункты **Администрирование** \> **Конфигурации сайта** \> **сайтов**, а затем выберите сайт.</span><span class="sxs-lookup"><span data-stu-id="1fafd-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="1fafd-154">В группе **Параметры** выберите **Настройка компонентов сайта** \> **Распространения программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="1fafd-155">Выберите вкладку **Учетной записи доступа к сети** Set up один или несколько учетных записей, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="1fafd-156">Учетные записи не требуется никаких специальных прав, за исключением **доступ к компьютеру из сети** непосредственно на сервере точку распространения.</span><span class="sxs-lookup"><span data-stu-id="1fafd-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="1fafd-157">Учетная запись пользователя домена универсальный будет соответствующие.</span><span class="sxs-lookup"><span data-stu-id="1fafd-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="1fafd-158">Дополнительные сведения содержатся в разделе [Управление учетными записями для доступа к контенту в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="1fafd-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="1fafd-159">Настройка загрузочного образа</span><span class="sxs-lookup"><span data-stu-id="1fafd-159">Configure a boot image</span></span>

1.  <span data-ttu-id="1fafd-160">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционной системы** \> **Образы загрузки**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="1fafd-161">Выберите **в качестве загрузочного образа (x64)** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="1fafd-162">Перейдите на вкладку **Источник данных** и включите **развернуть этот образ загрузки из точки распространения PXE-enabled**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="1fafd-163">Перейдите на вкладку **Дополнительных компонентов** , чтобы установить необходимые компоненты:</span><span class="sxs-lookup"><span data-stu-id="1fafd-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="1fafd-164">Выберите значок «звезда», а поиск **HTML (WinPE HTA)**</span><span class="sxs-lookup"><span data-stu-id="1fafd-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="1fafd-165">Нажмите кнопку **ОК** для добавления поддержки HTML-код приложения в образ загрузки.</span><span class="sxs-lookup"><span data-stu-id="1fafd-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="1fafd-166">*Необязательно:* Чтобы настроить развертывание, перейдите на вкладку **настройки** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="1fafd-167">Включите **команда поддерживает (только для тестирования)** , если требуется предоставить доступ к командной строке во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="1fafd-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="1fafd-168">Если этот параметр включен, можно начать из командной строки, выбрав F8 в любой момент во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="1fafd-168">When this is enabled, you can         start a command prompt by selecting F8 at any time during the deployment.</span></span>
    -   <span data-ttu-id="1fafd-169">Можно также указать настраиваемые фонового изображения будет отображаться во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="1fafd-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="1fafd-170">Чтобы задать изображение, включите **указать файл изображения пользовательский фон (UNC-путь** и выберите пункт фон.</span><span class="sxs-lookup"><span data-stu-id="1fafd-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="1fafd-171">В ответ на запрос, выберите вариант **Да** и распространения измененный образ загрузки точкам распространения.</span><span class="sxs-lookup"><span data-stu-id="1fafd-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="1fafd-172">Для получения дополнительных сведений в разделе [Управление загрузки изображений с помощью System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="1fafd-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="1fafd-173">Можно создать носителя USB для запуска диспетчера конфигураций задач на основе последовательности развертывания в средах, которые не поддерживают PXE.</span><span class="sxs-lookup"><span data-stu-id="1fafd-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="1fafd-174">Загрузочный носитель содержит только в качестве загрузочного образа, дополнительные prestart команды и их необходимые файлы и двоичные файлы диспетчера конфигураций для поддержки загрузки среда Предустановки Windows и подключении к Configuration Manager для остальных процесса развертывания.</span><span class="sxs-lookup"><span data-stu-id="1fafd-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="1fafd-175">Для получения дополнительных сведений см [порядок создания загрузочного носителя](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="1fafd-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="1fafd-176">Создание пакетов Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1fafd-176">Create Configuration Manager packages</span></span>

<span data-ttu-id="1fafd-177">Диспетчер конфигурации требуется количество пакетов для развертывания и настройки единиц измерения версии 2 Скайп комнаты системы.</span><span class="sxs-lookup"><span data-stu-id="1fafd-177">Configuration Manager requires a number of packages to deploy and configure the Skype Room System v2 units.</span></span>

<span data-ttu-id="1fafd-178">Для создания и настройки следующих пакетов и затем распространение их системы сайтов Configuration Manager, которым назначены роли сервера точку распространения.</span><span class="sxs-lookup"><span data-stu-id="1fafd-178">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="1fafd-179">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="1fafd-179">**Package name**</span></span>                     | <span data-ttu-id="1fafd-180">**Тип**</span><span class="sxs-lookup"><span data-stu-id="1fafd-180">**Type**</span></span>               | <span data-ttu-id="1fafd-181">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1fafd-181">**Description**</span></span>                                                                        |
|--------------------------------------|------------------------|----------------------------------------------------------------------------------------|
| <span data-ttu-id="1fafd-182">SRS версии 2 - пакета приложения SRS</span><span class="sxs-lookup"><span data-stu-id="1fafd-182">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="1fafd-183">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="1fafd-183">Software package</span></span>       | <span data-ttu-id="1fafd-184">Пакет для набора развертывания систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="1fafd-184">Package for the Skype Room Systems v2 deployment kit</span></span>                                   |
| <span data-ttu-id="1fafd-185">SRS версии 2 - пакета Sysprep</span><span class="sxs-lookup"><span data-stu-id="1fafd-185">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="1fafd-186">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="1fafd-186">Software package</span></span>       | <span data-ttu-id="1fafd-187">Пакет для настраиваемых Unattended.xml для настройки единиц измерения систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="1fafd-187">Package for the custom Unattended.xml to configure Skype Room Systems v2 units</span></span>         |
| <span data-ttu-id="1fafd-188">SRS версии 2 - Set-SRSComputerName пакета</span><span class="sxs-lookup"><span data-stu-id="1fafd-188">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="1fafd-189">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="1fafd-189">Software package</span></span>       | <span data-ttu-id="1fafd-190">Пакет для приложения HTML (HTA) для назначения имени компьютера во время развертывания</span><span class="sxs-lookup"><span data-stu-id="1fafd-190">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span> |
| <span data-ttu-id="1fafd-191">SRS версии 2 - пакета обновления ОС</span><span class="sxs-lookup"><span data-stu-id="1fafd-191">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="1fafd-192">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="1fafd-192">Software package</span></span>       | <span data-ttu-id="1fafd-193">Пакет для развертывания обновлений обязательные операционной системы</span><span class="sxs-lookup"><span data-stu-id="1fafd-193">Package to deploy mandatory operating system updates</span></span>                                   |
| <span data-ttu-id="1fafd-194">SRS версии 2 - пакет корневого сертификата</span><span class="sxs-lookup"><span data-stu-id="1fafd-194">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="1fafd-195">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="1fafd-195">Software package</span></span>       | <span data-ttu-id="1fafd-196">Пакет для развертывания корневой сертификат (не требуется для единиц измерения, присоединенный к домену)</span><span class="sxs-lookup"><span data-stu-id="1fafd-196">Package to deploy the root certificate (not required for domain-joined units)</span></span>          |
| <span data-ttu-id="1fafd-197">SRS версии 2 - пакет агента Microsoft OMS</span><span class="sxs-lookup"><span data-stu-id="1fafd-197">SRS v2 - Microsoft OMS Agent Package</span></span> | <span data-ttu-id="1fafd-198">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="1fafd-198">Software package</span></span>       | <span data-ttu-id="1fafd-199">Пакет развертывания и настройки агента пакет управления Microsoft Operations</span><span class="sxs-lookup"><span data-stu-id="1fafd-199">Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>        |
| <span data-ttu-id="1fafd-200">SRS версии 2 - пакет WinPE фона</span><span class="sxs-lookup"><span data-stu-id="1fafd-200">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="1fafd-201">Пакет программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="1fafd-201">Software package</span></span>       | <span data-ttu-id="1fafd-202">Пакет для настраиваемых фонового изображения для использования с изображениями загрузки</span><span class="sxs-lookup"><span data-stu-id="1fafd-202">Package for the custom background image to use with boot images</span></span>                        |
| <span data-ttu-id="1fafd-203">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1fafd-203">Windows 10 Enterprise</span></span>                | <span data-ttu-id="1fafd-204">Образ операционной системы</span><span class="sxs-lookup"><span data-stu-id="1fafd-204">Operating system image</span></span> | <span data-ttu-id="1fafd-205">Пакет для файлов установки операционной системы (install.wim)</span><span class="sxs-lookup"><span data-stu-id="1fafd-205">Package for the operating system installation file (install.wim)</span></span>                       |
| <span data-ttu-id="1fafd-206">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="1fafd-206">Surface Pro</span></span>                          | <span data-ttu-id="1fafd-207">Пакет</span><span class="sxs-lookup"><span data-stu-id="1fafd-207">Driver package</span></span>         | <span data-ttu-id="1fafd-208">Пакет для драйверов устройств и встроенного по Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="1fafd-208">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                  |
| <span data-ttu-id="1fafd-209">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="1fafd-209">Surface Pro 4</span></span>                        | <span data-ttu-id="1fafd-210">Пакет</span><span class="sxs-lookup"><span data-stu-id="1fafd-210">Driver package</span></span>         | <span data-ttu-id="1fafd-211">Пакет для драйверов устройств и встроенного по Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="1fafd-211">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                |

<span data-ttu-id="1fafd-212">Для получения дополнительных сведений см [пакеты и программы в System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="1fafd-212">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="1fafd-213">Создайте папки для пакета исходных файлов</span><span class="sxs-lookup"><span data-stu-id="1fafd-213">Create folders for the package source files</span></span>

<span data-ttu-id="1fafd-214">Диспетчер конфигурации требуется исходных файлов пакета организовывать в определенную структуру папок при их работе и когда они обновлены.</span><span class="sxs-lookup"><span data-stu-id="1fafd-214">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="1fafd-215">Создайте следующую структуру папок на сайте центра администрирования System Center Configuration Manager или основного сайта или на сервере, используемом для узла пакет исходных файлов:</span><span class="sxs-lookup"><span data-stu-id="1fafd-215">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="1fafd-216">SRS версии 2 - пакет агента Microsoft OMS</span><span class="sxs-lookup"><span data-stu-id="1fafd-216">SRS v2 - Microsoft OMS Agent Package</span></span>
-   <span data-ttu-id="1fafd-217">SRS версии 2 - пакета обновления ОС</span><span class="sxs-lookup"><span data-stu-id="1fafd-217">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="1fafd-218">SRS версии 2 - пакет корневого сертификата</span><span class="sxs-lookup"><span data-stu-id="1fafd-218">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="1fafd-219">SRS версии 2 - Set-SRSComputerName пакета</span><span class="sxs-lookup"><span data-stu-id="1fafd-219">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="1fafd-220">SRS версии 2 - пакета приложения SRS</span><span class="sxs-lookup"><span data-stu-id="1fafd-220">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="1fafd-221">SRS версии 2 - пакета Sysprep</span><span class="sxs-lookup"><span data-stu-id="1fafd-221">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="1fafd-222">Драйверы</span><span class="sxs-lookup"><span data-stu-id="1fafd-222">Drivers</span></span>
    -   <span data-ttu-id="1fafd-223">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="1fafd-223">Surface Pro</span></span>
    -   <span data-ttu-id="1fafd-224">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="1fafd-224">Surface Pro 4</span></span>
-   <span data-ttu-id="1fafd-225">Операционные системы</span><span class="sxs-lookup"><span data-stu-id="1fafd-225">Operating Systems</span></span>
    -   <span data-ttu-id="1fafd-226">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1fafd-226">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="1fafd-227">Можно также [загрузить](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) и использовать ZIP-файл, который включает в себя структуру папок для пакетов, скрипты, которые необходимы для использования и шаблон последовательность задач, который необходимо импортировать.</span><span class="sxs-lookup"><span data-stu-id="1fafd-227">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-microsoft-operations-management-suite-agent-package"></a><span data-ttu-id="1fafd-228">Создание пакета Microsoft Operations Management Suite агента</span><span class="sxs-lookup"><span data-stu-id="1fafd-228">Create the Microsoft Operations Management Suite agent package</span></span>

1.  <span data-ttu-id="1fafd-229">Загрузите пакет управления Operations X-64 агента из <https://go.microsoft.com/fwlink/?LinkId=828603>.</span><span class="sxs-lookup"><span data-stu-id="1fafd-229">Download the Operations Management Suite X-64 agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2.  <span data-ttu-id="1fafd-230">Извлечь содержимое пакета в папку **SRS версии 2 - агент пакета Microsoft OMS** , открыв окно командной строки и введите в командной **строке/C: MMASetup AMD64.exe** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-230">Extract the package into the **SRS v2 - Microsoft OMS Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3.  <span data-ttu-id="1fafd-231">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-231">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="1fafd-232">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="1fafd-232">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="1fafd-233">Имя **: SRS версии 2 - пакета Microsoft OMS агента**</span><span class="sxs-lookup"><span data-stu-id="1fafd-233">Name **: SRS v2 - Microsoft OMS Agent Package**</span></span>

    -   <span data-ttu-id="1fafd-234">Производитель **: Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="1fafd-234">Manufacturer **: Microsoft Corporation**</span></span>

    -   <span data-ttu-id="1fafd-235">Версия **: 8.1.11081.0** (введите версию файла, загруженного установки)</span><span class="sxs-lookup"><span data-stu-id="1fafd-235">Version **: 8.1.11081.0** (enter the version of the downloaded installation file)</span></span>

    -   <span data-ttu-id="1fafd-236">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 - пакета OMS агента** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-236">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft OMS Agent Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="1fafd-237">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-237">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="1fafd-238">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-238">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="1fafd-239">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-239">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="1fafd-240">Создание пакета обновления операционной системы</span><span class="sxs-lookup"><span data-stu-id="1fafd-240">Create the operating system updates package</span></span>

1.  <span data-ttu-id="1fafd-241">В папке **SRS версии 2 - пакета обновления операционной системы** создайте новый сценарий PowerShell с именем **Install-SRSv2-OS-Updates.ps1**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-241">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2.  <span data-ttu-id="1fafd-242">Скопируйте приведенный ниже сценарий в сценарий **Install-SRSv2-OS-Updates.ps1** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-242">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="1fafd-243">Кроме того можно загрузить скрипт Install-SRSv2-OS-Updates.ps1 [здесь](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="1fafd-243">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="1fafd-244">Загрузка обязательных пакетов обновления Windows в ту же папку.</span><span class="sxs-lookup"><span data-stu-id="1fafd-244">Download the mandatory Windows Update packages into the same folder.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="1fafd-245">Во время публикации этой статьи только [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) не требуется.</span><span class="sxs-lookup"><span data-stu-id="1fafd-245">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="1fafd-246">Установите флажок [Настройка консоли версии 2 Скайп комнаты систем](console.md), чтобы увидеть, требуется ли обновлений.</span><span class="sxs-lookup"><span data-stu-id="1fafd-246">Check [Configure a Skype Room Systems v2 console](console.md), to see whether any other updates are required.</span></span>

4.  <span data-ttu-id="1fafd-247">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-247">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5.  <span data-ttu-id="1fafd-248">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="1fafd-248">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="1fafd-249">Имя: **SRS версии 2 – операционная система обновляет пакета**</span><span class="sxs-lookup"><span data-stu-id="1fafd-249">Name: **SRS v2 – OS Updates Package**</span></span>
    -   <span data-ttu-id="1fafd-250">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="1fafd-250">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="1fafd-251">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="1fafd-251">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="1fafd-252">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 - пакета обновления операционной системы** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-252">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6.  <span data-ttu-id="1fafd-253">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-253">Select **Do not create a program**, and then select **Next**.</span></span>

7.  <span data-ttu-id="1fafd-254">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-254">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8.  <span data-ttu-id="1fafd-255">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-255">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="1fafd-256">Создание пакета корневой сертификат (необязательно)</span><span class="sxs-lookup"><span data-stu-id="1fafd-256">Create the root certificate package (optional)</span></span>

<span data-ttu-id="1fafd-257">Создайте этот пакет для распространения корневой сертификат для устройств, которые не присоединен к домену Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1fafd-257">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="1fafd-258">Создайте этот пакет только в том случае, если применяются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="1fafd-258">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="1fafd-259">Развертывание включает локальной Lync или Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="1fafd-259">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="1fafd-260">Единицы v2 систем комнаты Скайп настраиваются для работы в составе рабочей группы, а не входит в домен.</span><span class="sxs-lookup"><span data-stu-id="1fafd-260">Skype Room Systems v2 units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="1fafd-261">Скопируйте корневой сертификат в папку **SRS версии 2 — пакет корневого сертификата** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-261">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="1fafd-262">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-262">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="1fafd-263">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="1fafd-263">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="1fafd-264">Имя: **SRS версии 2 — корневой сертификат пакета**</span><span class="sxs-lookup"><span data-stu-id="1fafd-264">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="1fafd-265">Производитель: *имя вашей организации*</span><span class="sxs-lookup"><span data-stu-id="1fafd-265">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="1fafd-266">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="1fafd-266">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="1fafd-267">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 — пакет корневого сертификата** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-267">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="1fafd-268">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-268">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="1fafd-269">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-269">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="1fafd-270">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-270">Select **Close**.</span></span>

### <a name="create-the-skype-room-systems-v2-deployment-kit-package"></a><span data-ttu-id="1fafd-271">Создайте пакет набора развертывания систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="1fafd-271">Create the Skype Room Systems v2 deployment kit package</span></span>

1.  <span data-ttu-id="1fafd-272">Загрузить последнюю версию **набора развертывания систем комнаты Скайп версии 2** из <https://go.microsoft.com/fwlink/?linkid=851168>и установить его на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="1fafd-272">Download the latest version of the **Skype Room Systems v2 deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="1fafd-273">Копировать содержимое из **C:\\Program Files (x86)\\Скайп комнаты системы Deployment Kit** в папку **SRS версии 2 - пакета приложения SRS** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-273">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="1fafd-274">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-274">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="1fafd-275">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="1fafd-275">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="1fafd-276">Имя: **SRS версии 2 – SRS пакета приложения**</span><span class="sxs-lookup"><span data-stu-id="1fafd-276">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="1fafd-277">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="1fafd-277">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="1fafd-278">Версия: **3.1.104.0** (введите версию файла, загруженного установки)</span><span class="sxs-lookup"><span data-stu-id="1fafd-278">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="1fafd-279">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 – SRS пакета приложения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-279">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="1fafd-280">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-280">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="1fafd-281">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-281">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="1fafd-282">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-282">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="1fafd-283">Создание пакета назначения имя компьютера</span><span class="sxs-lookup"><span data-stu-id="1fafd-283">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="1fafd-284">В папке **SRS версии 2 - пакет Set-SRSComputerName** Создание нового приложения HTML с именем **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-284">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="1fafd-285">Скопируйте приведенный ниже сценарий в файл **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-285">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="1fafd-286">Кроме того можно загрузить файл Set-SRSComputerName.hta [здесь](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="1fafd-286">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="1fafd-287">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-287">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="1fafd-288">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="1fafd-288">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="1fafd-289">Имя: **SRS версии 2 - Set-SRSComputerName пакета**</span><span class="sxs-lookup"><span data-stu-id="1fafd-289">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="1fafd-290">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="1fafd-290">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="1fafd-291">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="1fafd-291">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="1fafd-292">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 - Set-SRSComputerName пакет** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-292">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="1fafd-293">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-293">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="1fafd-294">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-294">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="1fafd-295">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-295">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="1fafd-296">Создание пакета Sysprep</span><span class="sxs-lookup"><span data-stu-id="1fafd-296">Create the Sysprep package</span></span>

1.  <span data-ttu-id="1fafd-297">В папке **SRS версии 2 – пакета Sysprep** создайте новый XML-файл с именем **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-297">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2.  <span data-ttu-id="1fafd-298">Скопируйте следующий текст в файл **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-298">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="1fafd-299">Кроме того можно загрузить файл Unattend.xml [здесь](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="1fafd-299">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
```
<?xml version="1.0" encoding="utf-8"?>
<unattend xmlns="urn:schemas-microsoft-com:unattend">
    <servicing>
        <package action="configure">
            <assemblyIdentity name="Microsoft-Windows-Foundation-Package" version="10.0.15063.0" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="" />
            <selection name="Client-DeviceLockdown" state="true" />
            <selection name="Client-EmbeddedLogon" state="true" />
            <selection name="Client-EmbeddedBootExp" state="true" />
            <selection name="Client-EmbeddedShellLauncher" state="true" />
            <selection name="Client-KeyboardFilter" state="true" />
            <selection name="Internet-Explorer-Optional-amd64" state="false" />
            <selection name="MediaPlayback" state="false" />
            <selection name="WindowsMediaPlayer" state="false" />
            <selection name="Xps-Foundation-Xps-Viewer" state="false" />
            <selection name="WorkFolders-Client" state="false" />
            <selection name="SMB1Protocol" state="false" />
            <selection name="SearchEngine-Client-Package" state="false" />
            <selection name="Printing-Foundation-Features" state="false" />
            <selection name="FaxServicesClientPackage" state="false" />
            <selection name="Printing-Foundation-InternetPrinting-Client" state="false" />
            <selection name="Printing-XPSServices-Features" state="false" />
            <selection name="Printing-PrintToPDFServices-Features" state="false" />
            <selection name="Microsoft-Hyper-V-Hypervisor" state="true" />
            <selection name="Microsoft-Hyper-V-All" state="true" />
            <selection name="Microsoft-Hyper-V" state="true" />
        </package>
    </servicing>
    <settings pass="auditSystem">
        <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
            <AutoLogon>
                <Enabled>true</Enabled>
                <Username>Admin</Username>
                <Password>
                    <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
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
    <settings pass="oobeSystem">
        <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        </component>
    </settings>
    <cpi:offlineImage cpi:source="wim://com-sccm01/_sources/capture/srscaptured.wim#SRSImage" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
</unattend>
```
3.  <span data-ttu-id="1fafd-300">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**и выберите команду **Создать пакет**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-300">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="1fafd-301">Введите следующие сведения для создания пакета.</span><span class="sxs-lookup"><span data-stu-id="1fafd-301">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="1fafd-302">Имя: **SRS версии 2 - пакета Sysprep**</span><span class="sxs-lookup"><span data-stu-id="1fafd-302">Name: **SRS v2 - Sysprep Package**</span></span>
    -   <span data-ttu-id="1fafd-303">Производитель: **Корпорация Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="1fafd-303">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="1fafd-304">Версия: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="1fafd-304">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="1fafd-305">Установите флажок **Этот пакет содержит исходные файлы** , введите путь к папке **SRS версии 2 – Sysprep пакет** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-305">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="1fafd-306">Выберите **не создавать программы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-306">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="1fafd-307">Просмотрите страницу **Подтвердите параметры** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-307">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="1fafd-308">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-308">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="1fafd-309">Создание пакета Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1fafd-309">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="1fafd-310">Получить Windows 10 Enterprise x64 мультимедиа и скопируйте в файл **install.wim** **операционные системы\\Windows 10 Enterprise** папки.</span><span class="sxs-lookup"><span data-stu-id="1fafd-310">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="1fafd-311">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционные системы** \> **Изображения операционной системы**и затем выберите **Добавить образ операционной системы**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-311">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="1fafd-312">Укажите путь к файлу **install.wim** , скопированные и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-312">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="1fafd-313">Обновить поле **версии** в соответствии с номер сборки Windows 10 Enterprise изображения и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-313">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="1fafd-314">Просмотрите страницу **сведений** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-314">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="1fafd-315">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-315">Select **Close**.</span></span>

<span data-ttu-id="1fafd-316">Для получения дополнительных сведений см. [Управление операционной системы с помощью System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="1fafd-316">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="1fafd-317">Создание пакетов драйвера устройства Surface Pro</span><span class="sxs-lookup"><span data-stu-id="1fafd-317">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="1fafd-318">Скайп комнаты систем v2 поддерживается для Surface Pro и Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="1fafd-318">Skype Room Systems v2 is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="1fafd-319">Вам необходимо создать пакет для каждой модели Surface Pro в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="1fafd-319">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

1.  <span data-ttu-id="1fafd-320">Загрузите последние драйверы и встроенного по.</span><span class="sxs-lookup"><span data-stu-id="1fafd-320">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="1fafd-321">Для Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="1fafd-321">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="1fafd-322">Для Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="1fafd-322">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>
> [!IMPORTANT]
> <span data-ttu-id="1fafd-323">Драйверы должны быть совместимы с построения Windows 10 Enterprise и версия набора развертывания версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="1fafd-323">The drivers must be compatible with the Windows 10 Enterprise build and the Skype Room Systems v2 deployment kit version.</span></span> <span data-ttu-id="1fafd-324">Дополнительные сведения можно [загрузить последние встроенного по и драйверы устройств поверхности](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span><span class="sxs-lookup"><span data-stu-id="1fafd-324">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span></span>
2.  <span data-ttu-id="1fafd-325">Извлеките загруженного драйвера и микропрограммы.</span><span class="sxs-lookup"><span data-stu-id="1fafd-325">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="1fafd-326">Откройте окно командной строки и в командной строке введите одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="1fafd-326">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="1fafd-327">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционные системы** \> **факторов**и выберите команду **Импорт драйвер**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-327">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="1fafd-328">Выберите **Импорт всех драйверов в сети по следующему пути (UNC)**, выберите папку источника (например, C:\\_Sources\\драйверы\\Surface Pro) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-328">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="1fafd-329">На странице **Укажите сведения для импортированных драйверов** выберите вышеперечисленных драйверов и выберите **Включить эти драйверы и разрешить компьютерах, чтобы установить их**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-329">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="1fafd-330">Выберите **категории**, создания новой категории, который соответствует поверхности модели, нажмите **кнопку OK**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-330">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="1fafd-331">Выберите **новый пакет**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-331">Select **New Package**.</span></span>

8.  <span data-ttu-id="1fafd-332">Укажите имя пакета, который соответствует Surface Pro модели, введите путь к папке для хранения файлов пакета драйвера, нажмите **ОК**и затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-332">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="1fafd-333">На странице **загрузки изображений** убедитесь, что выбраны не загрузки изображения и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-333">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="1fafd-334">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-334">Select **Close**.</span></span>

11. <span data-ttu-id="1fafd-335">Последовательно выберите пункты **Библиотеки программного обеспечения** \> **операционные системы** \> **драйверов**, выберите **папку \> создать папку**и введите имя папки, которая соответствует Surface Pro модели, который был только что импортирован драйверы.</span><span class="sxs-lookup"><span data-stu-id="1fafd-335">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="1fafd-336">Перемещение всех импортированных драйверов только что созданная папка для упрощения навигации и операции.</span><span class="sxs-lookup"><span data-stu-id="1fafd-336">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="1fafd-337">Повторите те же действия для других Surface Pro моделей, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="1fafd-337">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="1fafd-338">Дополнительные сведения содержатся в разделе [Управление драйверами в System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="1fafd-338">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="1fafd-339">Распространение пакетов Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1fafd-339">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="1fafd-340">Все пакеты должен распространяться на серверы, которые были назначены роли точки распространения в иерархии диспетчера конфигураций.</span><span class="sxs-lookup"><span data-stu-id="1fafd-340">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="1fafd-341">Следуйте приведенным ниже инструкциям для инициации пакет рассылки.</span><span class="sxs-lookup"><span data-stu-id="1fafd-341">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="1fafd-342">Распространение пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="1fafd-342">Distribute software packages.</span></span>

    1.  <span data-ttu-id="1fafd-343">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **Управление приложениями** \> **пакетов**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-343">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="1fafd-344">Установите все пакеты программного обеспечения, который необходимо отправить, а затем выберите **Распределения контента**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-344">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="1fafd-345">Просмотрите список пакетов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-345">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="1fafd-346">Добавление в список всех серверов рассылки (или точка группы рассылки, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-346">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="1fafd-347">Нажмите кнопку **Далее**и затем выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-347">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="1fafd-348">Распространение пакетов драйверов.</span><span class="sxs-lookup"><span data-stu-id="1fafd-348">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="1fafd-349">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционные системы** \> **Пакетов драйверов**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-349">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="1fafd-350">Установите все пакеты драйверов, который необходимо отправить, а затем выберите **Распределения контента**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-350">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="1fafd-351">Просмотрите список пакетов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-351">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="1fafd-352">Добавление в список всех серверов рассылки (или точка группы рассылки, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-352">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="1fafd-353">Нажмите кнопку **Далее**и затем выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-353">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="1fafd-354">Распространение пакетов операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1fafd-354">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="1fafd-355">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционные системы** \> **Изображений операционной системы**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-355">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="1fafd-356">Выделите все изображения операционной системы, который необходимо отправить, а затем выберите **Распределения контента**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-356">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="1fafd-357">Просмотрите список пакетов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-357">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="1fafd-358">Добавление в список всех серверов рассылки (или точка группы рассылки, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-358">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="1fafd-359">Нажмите кнопку **Далее**и затем выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-359">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="1fafd-360">Пакет рассылки может занять некоторое время, в зависимости от того, размер пакета, иерархии Configuration Manager, несколько серверов рассылки и пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="1fafd-360">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>

> <span data-ttu-id="1fafd-361">Перед началом развертывания единое систем комнаты Скайп версии 2, распространяемых всех пакетов.</span><span class="sxs-lookup"><span data-stu-id="1fafd-361">All the packages must be distributed before you can start deploying a Skype Room Systems v2 unit.</span></span>

> <span data-ttu-id="1fafd-362">Можно просмотреть состояние дистрибутива пакет в консоли диспетчера конфигураций, перейдя на **мониторинг** \> **Состояние рассылки** \> **Состояние содержимого**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-362">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="1fafd-363">Последовательности задач Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1fafd-363">Configuration Manager task sequences</span></span>

<span data-ttu-id="1fafd-364">Используйте последовательности задач с помощью System Center Configuration Manager для автоматизации действия для развертывания образа операционной системы на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1fafd-364">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="1fafd-365">Чтобы развернуть единое систем комнаты Скайп версии 2 в автоматическом режиме, создание последовательности задач, который ссылается образа загрузки, используемый для запуска компьютера конечной версии 2 Скайп комнаты систем, образ операционной системы Windows 10 Enterprise, необходимо установить и какие-либо другие дополнительное содержимое, например других приложений и обновлений программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="1fafd-365">To deploy a Skype Room Systems v2 unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Skype Room Systems v2 computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="1fafd-366">Импорт образца последовательности задач</span><span class="sxs-lookup"><span data-stu-id="1fafd-366">Import the sample task sequence</span></span>

<span data-ttu-id="1fafd-367">Загрузите и легко импортировать последовательность задач образца и настроить его в соответствии со своими потребностями.</span><span class="sxs-lookup"><span data-stu-id="1fafd-367">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="1fafd-368">[**Загрузить**]() пример последовательности задач и скопируйте загруженный ZIP-файл в общую папку.</span><span class="sxs-lookup"><span data-stu-id="1fafd-368">[**Download**]() the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="1fafd-369">В консоли диспетчера конфигураций, перейдите к **Библиотеке программного обеспечения** \> **операционные системы** \> **Последовательности задач**, а затем выберите **Импорт последовательности задач**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-369">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="1fafd-370">Выберите **Обзор**, перейдите в расположение общей папки, которые использовались на шаге 1, выберите **систем комнаты Скайп версии 2 развертывания (EN-US), ZIP-** файл и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-370">Select **Browse**, go to the shared folder location you used in step 1, select the **Skype Room Systems v2 Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="1fafd-371">Задайте **Действие** для **Создания новых**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-371">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="1fafd-372">Подтвердите параметры и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-372">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="1fafd-373">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-373">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="1fafd-374">Проверьте, правильно связанные пакеты Справочник по каждому шагу последовательность задач.</span><span class="sxs-lookup"><span data-stu-id="1fafd-374">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1.  <span data-ttu-id="1fafd-375">Выберите последовательность импортированных задач, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-375">Select the imported task sequence, and then select **Edit**.</span></span>

     <span data-ttu-id="1fafd-376">Редактора последовательность задач открывается и отображает каждого последовательного этапа, на котором необходимо развернуть и настроить единое систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="1fafd-376">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Skype Room Systems v2 unit.</span></span>

1.  <span data-ttu-id="1fafd-377">Познакомьтесь с помощью каждого шага и выполните рекомендуемые обновления.</span><span class="sxs-lookup"><span data-stu-id="1fafd-377">Walk through each step and complete the recommended updates:</span></span>

    1.  <span data-ttu-id="1fafd-378">**Перезапустите в среда Предустановки Windows**: это действие перезагрузки и затем загружается Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="1fafd-378">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="1fafd-379">Изменения не требуются для этого шага.</span><span class="sxs-lookup"><span data-stu-id="1fafd-379">No changes are required for this step.</span></span>

    2.  <span data-ttu-id="1fafd-380">**Раздел диска 0 – UEFI**: это действие стирание конфигурация диска и создает разделы, в зависимости от настроек параметров.</span><span class="sxs-lookup"><span data-stu-id="1fafd-380">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="1fafd-381">Мы рекомендуем не вносите никаких изменений в этот этап.</span><span class="sxs-lookup"><span data-stu-id="1fafd-381">We recommend that you not make any changes to this step.</span></span>

    3.  <span data-ttu-id="1fafd-382">**Задайте имя компьютера SRS**: этот этап включает в себя приложение HTML-код для предоставления пользовательского интерфейса для задания имени компьютера для единицы версии 2 Скайп комнаты систем во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="1fafd-382">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Skype Room Systems v2 unit during the deployment.</span></span>
        -  <span data-ttu-id="1fafd-383">Это необязательное действие, но она может быть отключена, только если вы собираетесь управлять именования через альтернативный процесс компьютера.</span><span class="sxs-lookup"><span data-stu-id="1fafd-383">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
        -  <span data-ttu-id="1fafd-384">Убедитесь, что установлен пакет **SRS v2 - Set-SRSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-384">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="1fafd-385">В противном случае перейдите к пакету и выберите его.</span><span class="sxs-lookup"><span data-stu-id="1fafd-385">If it isn’t, browse to the package and select it.</span></span>

    4.  <span data-ttu-id="1fafd-386">**Применение операционной системы**: это действие задает образа операционной системы для развертывания и файл ответов автоматической Sysprep для использования.</span><span class="sxs-lookup"><span data-stu-id="1fafd-386">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
        -  <span data-ttu-id="1fafd-387">Убедитесь, что выбран правильный файл образа операционной системы Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1fafd-387">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
        -  <span data-ttu-id="1fafd-388">Убедитесь, что включена **Автоматическая используйте или файла ответов Sysprep для выборочной установки** , и выбран **SRS версии 2 - пакета Sysprep** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-388">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="1fafd-389">Также убедитесь, что **Имя файла** задано значение **unattend.xml**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-389">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

    5.  <span data-ttu-id="1fafd-390">**Применение параметров Windows**: это действие собирает сведения об установке Windows.</span><span class="sxs-lookup"><span data-stu-id="1fafd-390">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
        -  <span data-ttu-id="1fafd-391">Предоставляют сведения о лицензировании и регистрации, включая ключ продукта, пароль учетной записи локального администратора и часового пояса (в зависимости от потребностей).</span><span class="sxs-lookup"><span data-stu-id="1fafd-391">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

    6.  <span data-ttu-id="1fafd-392">**Применение параметров сети**: это действие позволяет указать рабочая группа или домен Active Directory и подразделение.</span><span class="sxs-lookup"><span data-stu-id="1fafd-392">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>

    7.  <span data-ttu-id="1fafd-393">**Применить факторами:** Этот шаг и его дочерних действий используются для развертывания требуемых драйверов и встроенного по на основе модели Surface Pro, у вас есть.</span><span class="sxs-lookup"><span data-stu-id="1fafd-393">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="1fafd-394">Обновите каждый шаг, чтобы указать соответствующие пакет, связанный с этой развертывания.</span><span class="sxs-lookup"><span data-stu-id="1fafd-394">Update each step to specify the relevant driver package associated with this deployment.</span></span>
        -   <span data-ttu-id="1fafd-395">Каждый пакет настроен на использование фильтров инструментария управления Windows (WMI) для развертывания соответствующих факторов и встроенного по на основании Surface Pro одновременное внесение и модели.</span><span class="sxs-lookup"><span data-stu-id="1fafd-395">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
        -   <span data-ttu-id="1fafd-396">Настоятельно рекомендуется не изменять конфигурацию этих факторов, в противном случае возможны ошибки при развертывании.</span><span class="sxs-lookup"><span data-stu-id="1fafd-396">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

    8.  <span data-ttu-id="1fafd-397">**Настройка Windows и Диспетчер конфигураций**: это действие развертывает и настраивает клиент диспетчера конфигураций.</span><span class="sxs-lookup"><span data-stu-id="1fafd-397">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="1fafd-398">Обновите этот шаг, чтобы указать встроенных клиентский пакет диспетчера конфигураций.</span><span class="sxs-lookup"><span data-stu-id="1fafd-398">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

    9.  <span data-ttu-id="1fafd-399">**Установка корневого сертификата**: это действие распределяет корневой сертификат для устройств, не являющиеся – присоединенный к домену и поэтому является необязательным.</span><span class="sxs-lookup"><span data-stu-id="1fafd-399">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional.</span></span>
        -   <span data-ttu-id="1fafd-400">Удалите или отключите этот шаг, если вам не нужно развернуть корневой сертификат для единиц измерения версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="1fafd-400">Remove or disable this step if you don’t need to deploy a root certificate to the Skype Room Systems v2 units.</span></span>
        -   <span data-ttu-id="1fafd-401">Если нужно выполнить это действие, убедитесь, что выбран **SRS версии 2 — пакет корневого сертификата** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-401">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** is selected.</span></span>

    10. <span data-ttu-id="1fafd-402">**Установка и настройка агента OMS**: это действие устанавливает 64-разрядная версия агента Microsoft Operations Management Suite и настраивает агент для подключения к вашей рабочей области для анализа журнала.</span><span class="sxs-lookup"><span data-stu-id="1fafd-402">**Install and Configure OMS Agent**: This step installs the 64-bit version of the Microsoft Operations Management Suite agent and configures the agent to connect to your Log Analytics workspace.</span></span>
        -   <span data-ttu-id="1fafd-403">Отключите этот шаг только в том случае, если вы собираетесь использовать некоторые другие платформы позволяют отслеживать состояние единиц систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="1fafd-403">Disable this step only if you’re going to use some other platforms to monitor the health of your Skype Room Systems v2 units.</span></span>
        -   <span data-ttu-id="1fafd-404">Измените это действие и обновите параметры командной строки для указания **Идентификатора рабочей области** и **Рабочая область для ключа**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-404">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
        -   <span data-ttu-id="1fafd-405">[Компьютеры Windows подключиться к службе анализа журнала в Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) более подробные сведения о получении идентификатор операции управления Suite рабочей области и первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="1fafd-405">See [Connect Windows computers to the Log Analytics service in Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
        -   <span data-ttu-id="1fafd-406">Убедитесь, что выбран пункт **SRS версии 2 — пакет агента Microsoft OMS** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-406">Verify that the **SRS v2 – Microsoft OMS Agent Package** is selected.</span></span>
        -   <span data-ttu-id="1fafd-407">Дополнительные сведения о мониторинге работоспособности развертывания систем комнаты Скайп версии 2 в разделе [Управление планирование систем комнаты Скайп версии 2 с помощью OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) и [версии 2 развертывание системы Скайп помещений с OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span><span class="sxs-lookup"><span data-stu-id="1fafd-407">For more information about monitoring the health of your Skype Room Systems v2 deployment, see [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) and [Deploy Skype Room Systems v2 management with OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span></span>

    11. <span data-ttu-id="1fafd-408">**SRS копии файлов конфигурации версии 2**: это действие копирует необходимые файлы установки и настройки из набора развертывания систем комнаты Скайп версии 2 на локальный жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="1fafd-408">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Skype Room Systems v2 deployment kit to the local hard drive.</span></span> <span data-ttu-id="1fafd-409">Без настройки необходим для этого шага.</span><span class="sxs-lookup"><span data-stu-id="1fafd-409">No customization is required for this step.</span></span>

    12. <span data-ttu-id="1fafd-410">**Install-SRSv2-OS-обновлений**: это действие развертывает любые необходимые в случае развертывания систем комнаты Скайп версии 2 обновления обязательные операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1fafd-410">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Skype Room Systems v2 deployment.</span></span> <span data-ttu-id="1fafd-411">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1fafd-411">Do the following:</span></span>
        -   <span data-ttu-id="1fafd-412">Установите флажок [Настройка систем комнаты Скайп v2 консоли](console.md) видеть, какие обновления необходимы.</span><span class="sxs-lookup"><span data-stu-id="1fafd-412">Check [Configure a Skype Room Systems v2 console](console.md) to see which updates are required.</span></span>
        -   <span data-ttu-id="1fafd-413">Убедитесь, что ваш **SRS версии 2 — пакет обновления операционная система** включает все необходимые обновления.</span><span class="sxs-lookup"><span data-stu-id="1fafd-413">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
        -   <span data-ttu-id="1fafd-414">Убедитесь, что выбран пункт **SRS версии 2 — пакет обновления операционной системы** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-414">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
        -   <span data-ttu-id="1fafd-415">Убедитесь, что для **сервера-посредника**политику выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1fafd-415">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

    13. <span data-ttu-id="1fafd-416">**Перезапустите компьютер**: это действие перезагрузить компьютер после установки обновлений обязательные операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1fafd-416">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="1fafd-417">Без настройки необходим для этого шага.</span><span class="sxs-lookup"><span data-stu-id="1fafd-417">No customization is required for this step.</span></span>

    14. <span data-ttu-id="1fafd-418">**Добавление пользователя локальной Скайп**: на этом этапе создается локальная учетная запись Скайп используется для автоматического входа в Windows и запустите приложение Скайп комнаты систем версии 2.</span><span class="sxs-lookup"><span data-stu-id="1fafd-418">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Skype Room Systems v2 application.</span></span> <span data-ttu-id="1fafd-419">Этот шаг не имеет любой пакет программного обеспечения, связанные с ним и для его необходим без настройки.</span><span class="sxs-lookup"><span data-stu-id="1fafd-419">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

    15. <span data-ttu-id="1fafd-420">**Задать и настройке приложения SRS**: это действие устанавливает и настраивает приложения v2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="1fafd-420">**Set up and configure SRS application**: This step installs and configures the Skype Room Systems v2 application.</span></span> <span data-ttu-id="1fafd-421">Этот шаг использует локально скопированного бита для установки приложения и поэтому не имеют каких-либо программного обеспечения пакетов связанных с ним.</span><span class="sxs-lookup"><span data-stu-id="1fafd-421">This step uses the locally copied bits to install the application and therefore doesn’t have any software packages associated with it.</span></span> <span data-ttu-id="1fafd-422">Без настройки необходим для этого шага.</span><span class="sxs-lookup"><span data-stu-id="1fafd-422">No customization is required for this step.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="1fafd-423">Создание развертывания для последовательности задач</span><span class="sxs-lookup"><span data-stu-id="1fafd-423">Create deployment for the task sequence</span></span>

1.  <span data-ttu-id="1fafd-424">Выберите последовательность задач и затем выберите команду **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-424">Select the task sequence, and then select **Deploy**.</span></span>

2.  <span data-ttu-id="1fafd-425">Выберите **Обзор** для выбора целевой коллекции для развертывания.</span><span class="sxs-lookup"><span data-stu-id="1fafd-425">Select **Browse** to select target collection for deployment.</span></span>

3.  <span data-ttu-id="1fafd-426">Выберите **Все неизвестные компьютеры** и нажмите кнопку « **ОК»**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-426">Select **All Unknown Computers** and then select **OK**.</span></span>

4.  <span data-ttu-id="1fafd-427">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-427">Select **Next**.</span></span>

5.  <span data-ttu-id="1fafd-428">Выберите пункт **доступен** на **Цель** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="1fafd-428">Select **Available** on the **Purpose** drop down list.</span></span>

6.  <span data-ttu-id="1fafd-429">Выберите в списке **становится доступной для следующих** **только мультимедиа и PXE** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-429">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
> [!WARNING]
> <span data-ttu-id="1fafd-430">Очень важно, что **Цель** задано значение **доступен**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-430">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="1fafd-431">Убедитесь в том, что **Цель** — **не** присвоено значение **требуется**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-431">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="1fafd-432">Также убедитесь в том, выберите **только мультимедиа и PXE** в **становится доступной для следующих**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-432">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span> <span data-ttu-id="1fafd-433">Установка этих значений в какой-либо другой может привести к всех компьютеров для получения образа развертывания систем комнаты Скайп при загрузке.</span><span class="sxs-lookup"><span data-stu-id="1fafd-433">Setting these values to something else might cause all computers to get the Skype Room Systems deployment image when booted.</span></span>
7.  <span data-ttu-id="1fafd-434">Не указать любой расписания и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-434">Do not specify any schedule and select **Next**.</span></span>

8.  <span data-ttu-id="1fafd-435">Не изменять что-либо в разделе **Взаимодействие с пользователем** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-435">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9.  <span data-ttu-id="1fafd-436">Не изменять что-либо в разделе **оповещения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-436">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10.  <span data-ttu-id="1fafd-437">Не изменять что-либо в разделе **Точки распространения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-437">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11.  <span data-ttu-id="1fafd-438">Проверьте параметры и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-438">Confirm the settings and then select **Next**.</span></span>

12.  <span data-ttu-id="1fafd-439">Выберите команду **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-439">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="1fafd-440">Проверка и устранение неполадок решения</span><span class="sxs-lookup"><span data-stu-id="1fafd-440">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="1fafd-441">После выполнения последовательности задач System Center Configuration Manager, вам потребуются для выполнения теста для проверки, что последовательности задач развертывания и настройки единиц измерения систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="1fafd-441">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Skype Room Systems v2 units.</span></span>

1.  <span data-ttu-id="1fafd-442">Подключение устройства проверки проводной сети с помощью одного из поддерживаемых адаптеров Ethernet или с помощью контактной закрепления.</span><span class="sxs-lookup"><span data-stu-id="1fafd-442">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="1fafd-443">Если функциональные возможности загрузки PXE еще не была настроена для вашей среды, можно использовать в качестве загрузочного образа на USB флэш-диск [созданный ранее](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) для загрузки с USB и подключиться к диспетчеру конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1fafd-443">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="1fafd-444">Доступ к встроенного по и для начала загрузки PXE:</span><span class="sxs-lookup"><span data-stu-id="1fafd-444">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="1fafd-445">Убедитесь, что выключен устройств.</span><span class="sxs-lookup"><span data-stu-id="1fafd-445">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="1fafd-446">Нажмите и удерживайте кнопку **Увеличения громкости** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-446">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="1fafd-447">Нажмите клавишу и кнопку **питания** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-447">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="1fafd-448">После устройство начинает загрузку, выпуск кнопка **Увеличения громкости** .</span><span class="sxs-lookup"><span data-stu-id="1fafd-448">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="1fafd-449">Выберите **конфигурацию загрузки**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-449">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="1fafd-450">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="1fafd-450">Do one of the following:</span></span>

        -   <span data-ttu-id="1fafd-451">Выберите **загрузки PXE**и перетащите его в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="1fafd-451">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="1fafd-452">Кроме того будет предложено провести слева на сетевом адаптере для загрузки на устройство немедленно.</span><span class="sxs-lookup"><span data-stu-id="1fafd-452">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="1fafd-453">Это не влияет на порядок загрузки.</span><span class="sxs-lookup"><span data-stu-id="1fafd-453">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="1fafd-454">Выберите флэш-накопитель USB, в котором размещается загрузки мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="1fafd-454">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="1fafd-455">Выберите **Выход**и выберите пункт **Перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-455">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="1fafd-456">При появлении соответствующего запроса выберите параметр **ввести** для загрузки сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="1fafd-456">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="1fafd-457">Среда Предустановки Windows будет загружен в память, и будет запущен мастер последовательность задач.</span><span class="sxs-lookup"><span data-stu-id="1fafd-457">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="1fafd-458">Нажмите кнопку **Далее** для продолжения.</span><span class="sxs-lookup"><span data-stu-id="1fafd-458">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="1fafd-459">Выберите последовательность задач, который был импортирован ранее и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1fafd-459">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="1fafd-460">После применения конфигурации диска, будет предложено указать имя компьютера для устройства.</span><span class="sxs-lookup"><span data-stu-id="1fafd-460">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="1fafd-461">Пользовательский интерфейс будет отображаться имя рекомендуемые компьютера, на основании серийный номер устройства Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="1fafd-461">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="1fafd-462">Можно принять предлагаемое имя или указать новый.</span><span class="sxs-lookup"><span data-stu-id="1fafd-462">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="1fafd-463">Следуйте инструкциям на экране назначения имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="1fafd-463">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="1fafd-464">При выборе **принять**началом развертывания.</span><span class="sxs-lookup"><span data-stu-id="1fafd-464">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="1fafd-465">Процесс развертывания происходит автоматически и не запрашивать любые дополнительные пользовательского ввода.</span><span class="sxs-lookup"><span data-stu-id="1fafd-465">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="1fafd-466">По завершении настройки устройства последовательности задач развертывания вы увидите на следующем экране конфигурации запросом для настройки параметров приложения v2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="1fafd-466">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Skype Room Systems v2 application settings.</span></span>

    ![Начальный экран для систем комнаты Скайп версии 2 приложения](../../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="1fafd-468">Подключите Surface Pro консоли версии 2 Скайп комнаты систем и настройте параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="1fafd-468">Plug the Surface Pro into the Skype Room Systems v2 console, and configure the application settings.</span></span>

11.  <span data-ttu-id="1fafd-469">Проверка работы возможности, перечисленные в [справке версии 2 Скайп комнаты систем](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) на развернутое устройства.</span><span class="sxs-lookup"><span data-stu-id="1fafd-469">Validate that the capabilities listed in [Skype Room Systems v2 help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="1fafd-470">Для устранения сбоя установки проверьте файл **SMSTS.log** , который записывает все действия, описанные в последовательности задач Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="1fafd-470">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="1fafd-471">Файл SMSTS.log сохраняется на одном из нескольких путей, в зависимости от этапа построения.</span><span class="sxs-lookup"><span data-stu-id="1fafd-471">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="1fafd-472">Проверьте следующую таблицу для определения пути к файлу SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="1fafd-472">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="1fafd-473">**Этап развертывания**</span><span class="sxs-lookup"><span data-stu-id="1fafd-473">**Deployment phase**</span></span>                                                            | <span data-ttu-id="1fafd-474">**Путь к журналу последовательности задач**</span><span class="sxs-lookup"><span data-stu-id="1fafd-474">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="1fafd-475">WinPE, прежде чем формат жесткого диска</span><span class="sxs-lookup"><span data-stu-id="1fafd-475">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="1fafd-476">X:\\Windows\\Temp\\smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="1fafd-476">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="1fafd-477">WinPE после формат жесткого диска</span><span class="sxs-lookup"><span data-stu-id="1fafd-477">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="1fafd-478">C:\\_SMSTaskSequence\\журналы\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="1fafd-478">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="1fafd-479">Операционная система, развертывание, до установки агента Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1fafd-479">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="1fafd-480">c:\\_SMSTaskSequence\\журналы\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="1fafd-480">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="1fafd-481">Операционная система и диспетчер конфигурации агента развертывания</span><span class="sxs-lookup"><span data-stu-id="1fafd-481">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="1fafd-482">% windir %\\System32\\ccm\\журналы\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="1fafd-482">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="1fafd-483">Выполнение последовательности задач завершено</span><span class="sxs-lookup"><span data-stu-id="1fafd-483">Task sequence execution complete</span></span>                                                | <span data-ttu-id="1fafd-484">% windir %\\System32\\ccm\\журналы\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="1fafd-484">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="1fafd-485">Вы можете выбрать F8 в любой момент во время последовательность задач для открытия командной консоли и получать доступ к файлу SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="1fafd-485">You can select F8 at any time during the task sequence to open a command console and get access to the SMSTS.log file.</span></span>

<span data-ttu-id="1fafd-486">Чтобы устранить проблемы загрузки PXE, проверьте два файлы журнала на сервере Configuration Manager, которые специфичны для действия PXE:</span><span class="sxs-lookup"><span data-stu-id="1fafd-486">To resolve PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="1fafd-487">**Pxecontrol.log**, расположенный в каталоге журналы установки диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="1fafd-487">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="1fafd-488">**Smspxe.log**, находится в каталоге журналы точка управления диспетчер конфигурации (MP)</span><span class="sxs-lookup"><span data-stu-id="1fafd-488">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="1fafd-489">Полный список файлов журнала, которые можно использовать для устранения установки диспетчера конфигураций просмотрите [файлы журналов в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="1fafd-489">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
