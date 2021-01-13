---
title: Установка средства планирования в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Прежде чем приступить к проектированию и планированию инфраструктуры Skype для бизнеса Server 2015 с помощью средства планирования Skype для бизнеса Server 2015, необходимо сначала установить средство планирования. Средство планирования не требуется развертывать на рабочей станции или сервере, который является частью домена или инфраструктуры, где планируется установить Skype для бизнеса Server 2015. В файле Readme, который сопровождает средство планирования, подробные сведения об установке и использовании средства. Некоторые сведения в файле Readme дублируются здесь для ясности.
ms.openlocfilehash: 902249e042694a37594c6dc0b753b0c1388c0729
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834729"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="ae6e7-106">Установка средства планирования в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ae6e7-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="ae6e7-107">Прежде чем приступить к проектированию и планированию инфраструктуры Skype для бизнеса Server 2015 с помощью средства планирования Skype для бизнеса Server 2015, необходимо сначала установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="ae6e7-108">Средство планирования не требуется развертывать на рабочей станции или сервере, который является частью домена или инфраструктуры, где планируется установить Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="ae6e7-109">В файле Readme, который сопровождает средство планирования, подробные сведения об установке и использовании средства.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="ae6e7-110">Некоторые сведения в файле Readme дублируются здесь для ясности.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae6e7-111">Средство планирования требует установки пользователем с правами администратора и разрешениями на компьютере, на котором будет установлено средство.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="ae6e7-112">Поддерживаемые операционные системы для установки и работы средства планирования:</span><span class="sxs-lookup"><span data-stu-id="ae6e7-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="ae6e7-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ae6e7-113">Windows 10</span></span>

- <span data-ttu-id="ae6e7-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="ae6e7-114">Windows 8</span></span>

- <span data-ttu-id="ae6e7-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ae6e7-115">Windows 8.1</span></span>

- <span data-ttu-id="ae6e7-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ae6e7-116">Windows Server 2012</span></span>

- <span data-ttu-id="ae6e7-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ae6e7-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="ae6e7-118">32-битный выпуск Windows 7</span><span class="sxs-lookup"><span data-stu-id="ae6e7-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="ae6e7-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="ae6e7-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="ae6e7-120">Windows Server 2008 R2 wow</span><span class="sxs-lookup"><span data-stu-id="ae6e7-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="ae6e7-121">Кроме того, для средства планирования требуется Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="ae6e7-122">После того как требования предустановки будут выполнены, можно установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="ae6e7-123">Установка средства планирования</span><span class="sxs-lookup"><span data-stu-id="ae6e7-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="ae6e7-124">Войдите на локальный компьютер в качестве члена группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="ae6e7-125">С помощью проводника или командного окна найдите каталог, в который вы скачали файлы установки средства планирования.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="ae6e7-126">Найдите SkypeForBusinessPlanningTool.msi.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-126">Locate the SkypeForBusinessPlanningTool.msi.</span></span> <span data-ttu-id="ae6e7-127">В проводнике Windows дважды щелкните файл.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-127">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="ae6e7-128">В командном окне введите имя файла  и нажмите ввод, чтобы запустить файл.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-128">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="ae6e7-129">На странице приветствия мастера настройки средства планирования Skype для бизнеса **Server 2015** нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="ae6e7-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="ae6e7-130">Просмотрите **лицензионный** договор,  выберите "Я принимаю условия лицензионного соглашения", если вы принимаете условия лицензионного соглашения, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="ae6e7-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="ae6e7-131">Выберите место установки файлов средства планирования.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-131">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="ae6e7-132">The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-132">The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span></span> <span data-ttu-id="ae6e7-133">Если вы хотите изменить место установки, нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="ae6e7-133">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="ae6e7-134">В **папке "Изменить назначение"** найдите или введите расположение для установки файлов, нажмите кнопку **"ОК"** и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="ae6e7-134">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="ae6e7-135">Установщик готов к установке средства планирования.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="ae6e7-136">Нажмите **кнопку** "Установить", чтобы начать процесс установки.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="ae6e7-137">Начнется установка и отобразит ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="ae6e7-138">После успешного завершения установки нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="ae6e7-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="ae6e7-139">Средство планирования готово к использованию.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="ae6e7-140">Необязательное программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="ae6e7-140">Optional Software</span></span>
<span data-ttu-id="ae6e7-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="ae6e7-141"><a name="Optional_Software"> </a></span></span>

<span data-ttu-id="ae6e7-142">Средство планирования Skype для бизнеса Server 2015 предназначено для экспорта в Microsoft Excel и Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="ae6e7-143">Хотя эти приложения не требуются для работы средства планирования, они имеют существенное значение для развертывания и документации по проекту.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="ae6e7-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="ae6e7-144">Microsoft Excel</span></span>

<span data-ttu-id="ae6e7-145">При экспорте дизайна в Microsoft Excel создается отчет, отображающий семь вкладок в электронных таблицах:</span><span class="sxs-lookup"><span data-stu-id="ae6e7-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="ae6e7-146">Сводка. Отображает сведения о конфигурации сайта, включая количество пользователей, параметры емкости и данные профиля сервера.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="ae6e7-147">Профиль оборудования — отображает отчет о рекомендуемых конфигурациях оборудования для серверов, указанных в топологии, включая ЦП, память, диск и сетевой интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="ae6e7-148">Также включены количество и рекомендуемые спецификации для серверных компонентов.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="ae6e7-149">Кроме того, каждый сервер определяется сайтом для предоставления полного представления требований к серверу для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="ae6e7-150">Требования к портам — отображает отчет о всех включенных портах и связи с балансировой нагрузки на DNS и аппаратными балансировщиков нагрузки (HLB).</span><span class="sxs-lookup"><span data-stu-id="ae6e7-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="ae6e7-151">Этот отчет следует использовать для планирования конфигураций брандмауэра и DNS LB и HLB.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="ae6e7-152">Сводный отчет — отображает общую сводку параметров, необходимых для настройки сети edge Server.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="ae6e7-153">Отчет о сертификатах— отображает имя субъекта и альтернативные имена субъектов, необходимые для сертификатов, необходимых для запуска серверов.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="ae6e7-154">Отчет по брандмауэру: отображает порты источника и назначения, а также IP-адреса для внешних и внутренних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="ae6e7-155">Отчет DNS — отображает полное доменное имя и IP-/VIP-адреса, необходимые для каждой создаваемой записи DNS.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="ae6e7-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="ae6e7-156">Microsoft Visio</span></span>

<span data-ttu-id="ae6e7-157">Экспорт проекта в Microsoft Visio создает схему для использования в документации по настроенной топологии и инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-157">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure.</span></span> <span data-ttu-id="ae6e7-158">Импортированную схему можно изменить и переустановить в удовлетворении потребностей в документации.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-158">The imported diagram can be edited and rearranged to meet your documentation needs.</span></span> <span data-ttu-id="ae6e7-159">Типичная схема Visio включает:</span><span class="sxs-lookup"><span data-stu-id="ae6e7-159">The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="ae6e7-160">Если проект достаточно большой и требует более трех серверов переднего сервера, будет создана дополнительная страница для пула переднего сервера, серверов переднего сервера, компьютера с SQL Server, IP-адресов и FQDNs.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="ae6e7-161">Глобальная топология — схема настроенных сайтов Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="ae6e7-162">Вкладка "Имя сайта" — отображает топологию конфигурации сайта с использованием edge Server, брандмауэра, телефонной сети общего перейти к сети (STN) со шлюзами и развертывания внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="ae6e7-163">Внутреннее развертывание состоит из настроенных серверов и пулов, включая пулы переднего сервера, серверы на основе SQL Server, доменные службы Active Directory, директоры, серверы единой системы обмена сообщениями Exchange, серверы почтовых ящиков Exchange, серверы Office Web Apps, серверы-посредники и серверы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="ae6e7-164">Схема сети edge — схема конфигурации сервера с связанными IP-адресами и FQDNs.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="ae6e7-165">Также включены балансировка нагрузки на DNS и аппаратные балансировщиков нагрузки.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="ae6e7-166">Кроме того, отображаются директоры и сервер переднего плана или пул переднего плана с связанной DNS-нагрузкой или HLB и назначенным IP-адресом (средство планирования поддерживает адреса IPv4 и IPv6) и FQDN.</span><span class="sxs-lookup"><span data-stu-id="ae6e7-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae6e7-167">См. также</span><span class="sxs-lookup"><span data-stu-id="ae6e7-167">See also</span></span>
<span data-ttu-id="ae6e7-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="ae6e7-168"><a name="Optional_Software"> </a></span></span>

[<span data-ttu-id="ae6e7-169">Установка средства планирования</span><span class="sxs-lookup"><span data-stu-id="ae6e7-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
