---
title: Установка средства планирования в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Прежде чем приступить к проектированию и планированию инфраструктуры Skype для бизнеса Server 2015 с помощью средства планирования Skype для бизнеса Server 2015, необходимо сначала установить средство планирования. Средство планирования не нужно развертывать на рабочей станции или сервере, входящем в домен или инфраструктуру, в которой вы планируете установить Skype для бизнеса Server 2015. В файле readme, прилагаемом к средству планирования, подробно описаны важные сведения об установке и использовании этого средства. Some of the information in the Readme file is duplicated here for clarity.
ms.openlocfilehash: 29cadae219faadb68a8a027de11309efc8e3f10b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816388"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="5fbcb-106">Установка средства планирования в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="5fbcb-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="5fbcb-107">Прежде чем приступить к проектированию и планированию инфраструктуры Skype для бизнеса Server 2015 с помощью средства планирования Skype для бизнеса Server 2015, необходимо сначала установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="5fbcb-108">Средство планирования не нужно развертывать на рабочей станции или сервере, входящем в домен или инфраструктуру, в которой вы планируете установить Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="5fbcb-109">В файле readme, прилагаемом к средству планирования, подробно описаны важные сведения об установке и использовании этого средства.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="5fbcb-110">Some of the information in the Readme file is duplicated here for clarity.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fbcb-111">Для установки средства планирования требуется установка пользователем с правами администратора и разрешениями на компьютере, на котором оно должно быть установлено.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="5fbcb-112">Ниже перечислены операционные системы, поддерживаемые при установке и работе средства планирования.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="5fbcb-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="5fbcb-113">Windows 10</span></span>

- <span data-ttu-id="5fbcb-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="5fbcb-114">Windows 8</span></span>

- <span data-ttu-id="5fbcb-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="5fbcb-115">Windows 8.1</span></span>

- <span data-ttu-id="5fbcb-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="5fbcb-116">Windows Server 2012</span></span>

- <span data-ttu-id="5fbcb-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5fbcb-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="5fbcb-118">Windows 7, 32-разрядный выпуск;</span><span class="sxs-lookup"><span data-stu-id="5fbcb-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="5fbcb-119">Windows 7, 64-разрядный выпуск с применением технологии Windows on Win32 (WOW);</span><span class="sxs-lookup"><span data-stu-id="5fbcb-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="5fbcb-120">Windows Server 2008 R2, с применением технологии WOW.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="5fbcb-121">Кроме того, для средства планирования требуется Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="5fbcb-122">После того как требования к предварительной установке выполнены, вы можете установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="5fbcb-123">Установка средства планирования</span><span class="sxs-lookup"><span data-stu-id="5fbcb-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="5fbcb-124">Войдите на локальный компьютер как член группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="5fbcb-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="5fbcb-125">С помощью проводника или командного окна найдите каталог, в который вы загрузили установочные файлы средства планирования.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="5fbcb-p103">Найдите файл SkypeForBusinessPlanningTool.msi. В проводнике дважды щелкните файл. В окне командной строки введите имя файла и нажмите клавишу **ВВОД**, чтобы запустить файл.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-p103">Locate the SkypeForBusinessPlanningTool.msi. In Windows Explorer, double-click the file. In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="5fbcb-129">На странице приветствия **Skype для бизнеса Server 2015, мастер установки средства планирования** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="5fbcb-130">Просмотрите **Лицензионное соглашение**, установите флажок **Я принимаю условия лицензионного соглашения**, если вы принимаете условия использования по лицензионному соглашению, и затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="5fbcb-p104">Выберите папку, в которую следует установить файлы средства планирования. Расположение по умолчанию – C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Если требуется изменить папку установки, нажмите кнопку **Изменить**. В окне **Изменение конечной папки** найдите или введите расположение для установки файлов, нажмите кнопку **ОК**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-p104">Choose where to install the Planning Tool files. The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. If you want to change the installation location, click **Change**. On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="5fbcb-135">Теперь Установщик готов установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="5fbcb-136">Click **Install** to begin the installation process.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="5fbcb-137">Начнется установка, и будет отображаться ход процесса.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="5fbcb-138">После успешного завершения установки нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="5fbcb-139">Средство планирования готово к использованию.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="5fbcb-140">Дополнительное программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="5fbcb-140">Optional Software</span></span>
<span data-ttu-id="5fbcb-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="5fbcb-141"><a name="Optional_Software"> </a></span></span>

<span data-ttu-id="5fbcb-142">Средство планирования Skype для бизнеса Server 2015 предназначено для экспорта в Microsoft Excel и Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="5fbcb-143">Несмотря на то, что эти приложения не требуются для работы средства планирования, они добавляют значительные значения в развертывание и документацию проекта.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="5fbcb-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="5fbcb-144">Microsoft Excel</span></span>

<span data-ttu-id="5fbcb-145">Экспорт проекта в Microsoft Excel приводит к созданию отчета, в котором отображаются семь вкладок в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="5fbcb-146">Summary (сводка) — отображает сведения о конфигурации сайта, включая количество пользователей, настройки емкости и сведения о профиле сервера.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="5fbcb-147">Профиль оборудования — отображает отчет о рекомендуемых конфигурациях оборудования для серверов, указанных в топологии, включая ЦП, память, диск и сетевой интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="5fbcb-148">Также указывается количество и рекомендуемые характеристики для серверных компонентов.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="5fbcb-149">Кроме того, определяется сайт для каждого сервера, чтобы обеспечить полное представление требований сервера для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="5fbcb-150">Требования к портам: отображение отчета обо всех включенных портах и связь с балансировкой нагрузки системы доменных имен (DNS) и балансировщик нагрузки оборудования (ХЛБ).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="5fbcb-151">Следует использовать этот отчет для планирования конфигураций брандмауэра, DNS LB и HLB.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="5fbcb-152">Сводный отчет: Общие сведения о параметрах, которые необходимы для настройки сети пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="5fbcb-153">Отчет о сертификатах — отображает имя субъекта и альтернативные имена субъектов, необходимые для сертификатов, необходимых для получения запущенных пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="5fbcb-154">Отчет о брандмауэре: Отображает исходные и конечные порты и IP-адреса для внешних и внутренних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="5fbcb-155">DNS-отчет: отображает полные доменные имена (FQDN) и IP/VIP, необходимые для каждой создаваемой записи DNS.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="5fbcb-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="5fbcb-156">Microsoft Visio</span></span>

<span data-ttu-id="5fbcb-p110">Экспорт проекта в Microsoft Visio приводит к созданию схемы для использования в целях документирования настроенной топологии и инфраструктуры. Импортированную схему диаграммы можно редактировать и переупорядочивать для удовлетворения ваших требований в отношении документирования. Стандартная схема Visio будет включать в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="5fbcb-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="5fbcb-160">Если на вашем макете требуется больше трех серверов переднего плана, будет создана дополнительная страница для пула переднего плана, серверов переднего плана, компьютера с SQL Server, IP-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="5fbcb-161">Глобальная топология: схема настроенных сайтов Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="5fbcb-162">Вкладка "имя сайта" — отображает топологию конфигурации сайта с пограничным сервером, брандмауэром, коммутируемой телефонной сетью (PSTN) с шлюзами и внутренним развертыванием сервера.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="5fbcb-163">Внутреннее развертывание состоит из настроенных серверов и пулов, в том числе интерфейсных пулов, серверов SQL Server, доменных служб Active Directory, режиссеров, серверов единой системы обмена сообщениями Exchange, серверов почтовых ящиков, сервера Exchange Web Apps. Серверы обновлений и сохраняемые серверы чата.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="5fbcb-164">Схема пограничного сетевого графика-схема подробностей настройки пограничного сервера с помощью соответствующих IP-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="5fbcb-165">DNS load balancing and hardware load balancers are also included.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="5fbcb-166">Кроме того, отображаются режиссеры и внешний сервер или пул переднего плана с соответствующей службой DNS фунтов или ХЛБ и назначенным IP-адресом (средство планирования поддерживает оба адреса IPv4 и IPv6) и полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fbcb-167">См. также</span><span class="sxs-lookup"><span data-stu-id="5fbcb-167">See also</span></span>
<span data-ttu-id="5fbcb-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="5fbcb-168"><a name="Optional_Software"> </a></span></span>

[<span data-ttu-id="5fbcb-169">Installing the Planning Tool</span><span class="sxs-lookup"><span data-stu-id="5fbcb-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
