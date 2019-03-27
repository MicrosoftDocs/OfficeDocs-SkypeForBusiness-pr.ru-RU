---
title: Установка средства планирования в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Перед началом разработки и планирование вашей Скайп для инфраструктуры Business Server 2015 с помощью Скайп для средство планирования 2015 Business Server, необходимо сначала установить средство планирования. Средство планирования не нужно развертывать на рабочей станции или сервере, который является частью инфраструктуры или домена, где предполагается установить Скайп для Business Server 2015. Readme-файле средство планирования подробно описываются важные сведения об установке и с помощью средства. Some of the information in the Readme file is duplicated here for clarity.
ms.openlocfilehash: 616cec026dfc5890cffc3975ea421d98ec13e412
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884134"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="8d307-106">Установка средства планирования в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="8d307-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="8d307-107">Перед началом разработки и планирование вашей Скайп для инфраструктуры Business Server 2015 с помощью Скайп для средство планирования 2015 Business Server, необходимо сначала установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="8d307-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="8d307-108">Средство планирования не нужно развертывать на рабочей станции или сервере, который является частью инфраструктуры или домена, где предполагается установить Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8d307-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="8d307-109">Readme-файле средство планирования подробно описываются важные сведения об установке и с помощью средства.</span><span class="sxs-lookup"><span data-stu-id="8d307-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="8d307-110">Some of the information in the Readme file is duplicated here for clarity.</span><span class="sxs-lookup"><span data-stu-id="8d307-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d307-111">Средство планирования требует установки пользователем с правами администратора и разрешения на локальном компьютере, на котором необходимо установить средство.</span><span class="sxs-lookup"><span data-stu-id="8d307-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="8d307-112">Поддерживаемые операционные системы для установки и средство планирования операций являются:</span><span class="sxs-lookup"><span data-stu-id="8d307-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="8d307-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8d307-113">Windows 10</span></span>

- <span data-ttu-id="8d307-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="8d307-114">Windows 8</span></span>

- <span data-ttu-id="8d307-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="8d307-115">Windows 8.1</span></span>

- <span data-ttu-id="8d307-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8d307-116">Windows Server 2012</span></span>

- <span data-ttu-id="8d307-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8d307-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="8d307-118">Windows 7, 32-разрядный выпуск;</span><span class="sxs-lookup"><span data-stu-id="8d307-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="8d307-119">Windows 7, 64-разрядный выпуск с применением технологии Windows on Win32 (WOW);</span><span class="sxs-lookup"><span data-stu-id="8d307-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="8d307-120">Windows Server 2008 R2, с применением технологии WOW.</span><span class="sxs-lookup"><span data-stu-id="8d307-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="8d307-121">Кроме того средство планирования требуется Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="8d307-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="8d307-122">После предварительной установки требований, затем можно установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="8d307-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="8d307-123">Установка средства планирования</span><span class="sxs-lookup"><span data-stu-id="8d307-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="8d307-124">Войдите на локальный компьютер как член группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="8d307-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="8d307-125">С помощью проводника Windows или окно командной строки, перейдите в каталог, в которую было загружено средство планирования установочных файлов.</span><span class="sxs-lookup"><span data-stu-id="8d307-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="8d307-p103">Найдите файл SkypeForBusinessPlanningTool.msi. В проводнике дважды щелкните файл. В окне командной строки введите имя файла и нажмите клавишу **ВВОД**, чтобы запустить файл.</span><span class="sxs-lookup"><span data-stu-id="8d307-p103">Locate the SkypeForBusinessPlanningTool.msi. In Windows Explorer, double-click the file. In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="8d307-129">На странице приветствия **Skype для бизнеса Server 2015, мастер установки средства планирования** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8d307-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="8d307-130">Просмотрите **Лицензионное соглашение**, установите флажок **Я принимаю условия лицензионного соглашения**, если вы принимаете условия использования по лицензионному соглашению, и затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8d307-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="8d307-p104">Выберите папку, в которую следует установить файлы средства планирования. Расположение по умолчанию – C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Если требуется изменить папку установки, нажмите кнопку **Изменить**. В окне **Изменение конечной папки** найдите или введите расположение для установки файлов, нажмите кнопку **ОК**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8d307-p104">Choose where to install the Planning Tool files. The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. If you want to change the installation location, click **Change**. On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="8d307-135">Установщик готов к установке средства планирования.</span><span class="sxs-lookup"><span data-stu-id="8d307-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="8d307-136">Click **Install** to begin the installation process.</span><span class="sxs-lookup"><span data-stu-id="8d307-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="8d307-137">Начнется установка, и будет отображаться ход процесса.</span><span class="sxs-lookup"><span data-stu-id="8d307-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="8d307-138">После успешного завершения установки нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8d307-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="8d307-139">Средство планирования готов к использованию.</span><span class="sxs-lookup"><span data-stu-id="8d307-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="8d307-140">Дополнительное программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="8d307-140">Optional Software</span></span>
<span data-ttu-id="8d307-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="8d307-141"></span></span>

<span data-ttu-id="8d307-142">Скайп для средство планирования Business Server 2015 предназначен для экспорта в Microsoft Excel и Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="8d307-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="8d307-143">Хотя эти приложения не требуются для работы средства планирования, имеют значительные значение для развертывания и документации к проекту.</span><span class="sxs-lookup"><span data-stu-id="8d307-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="8d307-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="8d307-144">Microsoft Excel</span></span>

<span data-ttu-id="8d307-145">Экспорт проекта в Microsoft Excel приводит к созданию отчета, в котором отображаются семь вкладок в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="8d307-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="8d307-146">Сводка по-Отображение сведений о конфигурации сайта, включая число пользователей, параметры емкости и сведения о профиле сервера.</span><span class="sxs-lookup"><span data-stu-id="8d307-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="8d307-147">Профиль оборудования — отображает отчет на рекомендуемые конфигурации оборудования для серверов, которые указаны в топологии, включая ЦП, памяти, диска и сетевого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8d307-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="8d307-148">Также указывается количество и рекомендуемые характеристики для серверных компонентов.</span><span class="sxs-lookup"><span data-stu-id="8d307-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="8d307-149">Кроме того, определяется сайт для каждого сервера, чтобы обеспечить полное представление требований сервера для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="8d307-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="8d307-150">Порты требования - отображается отчет об все порты, для которых включено и связь для балансировки доменных имен (DNS Фунтов) и аппаратных балансировщиков нагрузки (HLB).</span><span class="sxs-lookup"><span data-stu-id="8d307-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="8d307-151">Следует использовать этот отчет для планирования конфигураций брандмауэра, DNS LB и HLB.</span><span class="sxs-lookup"><span data-stu-id="8d307-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="8d307-152">Сводный отчет — отображает общая Сводка параметров, которые необходимы для настройки сети пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8d307-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="8d307-153">Отчет о сертификаты - отображает имя субъекта и альтернативные имена субъектов, которые необходимы для сертификаты, необходимые для получения пограничных серверов, использующих.</span><span class="sxs-lookup"><span data-stu-id="8d307-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="8d307-154">Отчет о — отображает исходный и конечный порты и IP-адреса для интерфейсов внешнего и внутреннего брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="8d307-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="8d307-155">Отчет о DNS - отображает полное доменное имя (FQDN) и требуется виртуальный IP-адрес/IP-адреса для каждой записи DNS создать.</span><span class="sxs-lookup"><span data-stu-id="8d307-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="8d307-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="8d307-156">Microsoft Visio</span></span>

<span data-ttu-id="8d307-p110">Экспорт проекта в Microsoft Visio приводит к созданию схемы для использования в целях документирования настроенной топологии и инфраструктуры. Импортированную схему диаграммы можно редактировать и переупорядочивать для удовлетворения ваших требований в отношении документирования. Стандартная схема Visio будет включать в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="8d307-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="8d307-160">Если данный проект является достаточно велико, чтобы сделать обязательным наличие более трех серверов переднего плана, дополнительные страницы будут созданы для пула переднего плана, серверы переднего плана, компьютер, где запущен SQL Server, IP-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="8d307-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="8d307-161">Глобальные топология — схема настроенного Скайп для сайтов Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8d307-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="8d307-162">Вкладка имя веб - отображает топология конфигурации сайта с пограничного сервера, брандмауэр, общего пользования телефона сети (общего пользования PSTN) с помощью шлюзов и развертывания внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="8d307-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="8d307-163">Внутреннего развертывания состоит из настроенных серверов и пулов, включая переднего плана пулов, директоров серверов на основе SQL Server, доменных служб Active Directory, Exchange единой системы обмена сообщениями (единой системы обмена СООБЩЕНИЯМИ) сервера, сервера почтовых ящиков Exchange, серверы Office Web Apps, Серверов-посредников и серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="8d307-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="8d307-164">Пограничный сетевой график - схема о конфигурации пограничного сервера с помощью связанных IP-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="8d307-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="8d307-165">DNS load balancing and hardware load balancers are also included.</span><span class="sxs-lookup"><span data-stu-id="8d307-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="8d307-166">Кроме того директора и сервера переднего плана или интерфейсный пул отображаются связанные Фунтов DNS или аппаратного балансировщика Нагрузки и IP-адрес (средство планирования поддерживает IPv4 и IPv6-адреса) и полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="8d307-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d307-167">См. также</span><span class="sxs-lookup"><span data-stu-id="8d307-167">See also</span></span>
<span data-ttu-id="8d307-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="8d307-168"></span></span>

[<span data-ttu-id="8d307-169">Installing the Planning Tool</span><span class="sxs-lookup"><span data-stu-id="8d307-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
