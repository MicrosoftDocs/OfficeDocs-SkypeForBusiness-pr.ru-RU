---
title: 'Lync Server 2013: средства администрирования Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a34561e9880870b53cd8f7aaad2fe13cfe33c8d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a><span data-ttu-id="ce7ea-102">Средства администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7ea-102">Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce7ea-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ce7ea-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ce7ea-104">В этой статье описаны средства администрирования для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-104">This topic describes the administrative tools for Lync Server 2013.</span></span>

<span data-ttu-id="ce7ea-105">Средства администрирования устанавливаются по умолчанию на каждом сервере Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-105">The administrative tools are installed by default on each Lync Server server.</span></span> <span data-ttu-id="ce7ea-106">Кроме того, вы можете установить средства администрирования на других компьютерах, таких как специальные консоли администрирования.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="ce7ea-107">Инструкции по установке средств администрирования можно найти в разделе [Установка средств администрирования Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ce7ea-107">For procedures to install the administrative tools, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span> <span data-ttu-id="ce7ea-108">Инструкции по открытию инструментов для выполнения задач управления можно найти в статье [Открытие средства администрирования Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ce7ea-108">For procedures to open the tools to perform management tasks, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

<span data-ttu-id="ce7ea-109">Убедитесь, что вы просматриваете требования инфраструктуры, операционной системы, программного обеспечения и прав администратора, прежде чем устанавливать или использовать средства администрирования Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-109">Ensure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server administrative tools.</span></span> <span data-ttu-id="ce7ea-110">Сведения о требованиях к инфраструктуре описаны [в разделе Требования к инфраструктуре средств администрирования в Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce7ea-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="ce7ea-111">Сведения о требованиях к операционной системе и программному обеспечению для установки средств администрирования Lync Server можно найти [в разделе Поддержка серверов и инструментальных средств операционной системы в Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Дополнительные требования к программному обеспечению для Lync Server 2013](lync-server-2013-additional-software-requirements.md), а также [дополнительные серверные службы и требования в Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce7ea-111">For details about operating system and software requirements to install the Lync Server administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="ce7ea-112">Права и разрешения пользователей, необходимые для установки и использования этих средств, описаны в разделе [права и разрешения администратора, необходимые для настройки и администрирования Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="ce7ea-112">The user rights and permissions required to install and use the tools are described in [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<span data-ttu-id="ce7ea-113">Средства администрирования состоят из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-113">The administrative tools consist of the following:</span></span>

  - <span data-ttu-id="ce7ea-114">**Мастер развертывания Lync Server**   используется для развертывания Lync Server и установки всех средств администрирования.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-114">**Lync Server Deployment Wizard**   Use to deploy Lync Server and to install all administrative tools.</span></span>

  - <span data-ttu-id="ce7ea-115">**С помощью построителя**   топологии Lync Server можно определять компоненты в развертывании.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-115">**Lync Server Topology Builder**   Use to define components in your deployment.</span></span>

  - <span data-ttu-id="ce7ea-116">**Панель управления Lync Server**   — используется для постоянного управления развертыванием с помощью веб-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-116">**Lync Server Control Panel**   Use for ongoing management of your deployment by using a web-based interface.</span></span>

  - <span data-ttu-id="ce7ea-117">**Командная консоль Lync Server Management Shell**   используется для постоянного управления развертыванием с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-117">**Lync Server Management Shell**   Use for ongoing management of your deployment by using the command line.</span></span>

  - <span data-ttu-id="ce7ea-118">**Средство ведения журнала в Lync Server**   — используется для устранения проблем с развертыванием.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-118">**Lync Server Logging tool**   Use to troubleshoot problems in your deployment.</span></span>

  - <span data-ttu-id="ce7ea-119">**Служба централизованного ведения журналов**   собирает журналы и отслеживайте файлы с одного компьютера, из пула, сайта или глобального шаблона.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-119">**Centralized Logging Service**   Collect logs and trace files from one computer, pool, site or global.</span></span> <span data-ttu-id="ce7ea-120">Выберите и определите сценарии, которые содержат поставщики, флаги и уровни трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-120">Select and define scenarios that contain providers, flags and trace levels.</span></span> <span data-ttu-id="ce7ea-121">Ведение журнала собираются, объединяются и отображаются с помощью таких средств, как текстовые средства или Снупер. exe.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-121">Logging is collected, aggregated and displayed with tools such as any text-based tool or Snooper.exe.</span></span>

<span data-ttu-id="ce7ea-122">Вы можете управлять развертыванием в основном с помощью построителя топологии и панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-122">You can manage your deployment by primarily using Topology Builder and Lync Server Control Panel.</span></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="ce7ea-123">Мастер развертывания</span><span class="sxs-lookup"><span data-stu-id="ce7ea-123">Deployment Wizard</span></span>

<span data-ttu-id="ce7ea-124">Чтобы установить все средства администрирования на компьютере, на котором еще не установлен Lync Server, необходимо использовать мастер развертывания Lync Server, который входит в состав установочного носителя.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-124">You must use the Lync Server Deployment Wizard included on the installation media to install all administrative tools onto a computer on which you have not already installed Lync Server.</span></span> <span data-ttu-id="ce7ea-125">В процессе установки средства администрирования мастер развертывания Lync Server устанавливается локально вместе с другими инструментами, чтобы позже можно было устанавливать файлы для дополнительных компонентов или удалять файлы для компонентов, которые не нужны на странице компьютерных.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-125">During the administrative tools installation process, the Lync Server Deployment Wizard is installed locally along with the other tools so that you can later use it to install files for additional components or remove files for components that you do not want on the computer.</span></span>

<span data-ttu-id="ce7ea-126">Сведения о том, как запустить мастер развертывания Lync Server впервые из установочного носителя Lync Server, можно найти в разделе [Установка средств администрирования Lync server 2013](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ce7ea-126">For details about how to run the Lync Server Deployment Wizard for the first time from the Lync Server installation media, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

</div>

<div>

## <a name="topology-builder"></a><span data-ttu-id="ce7ea-127">топологий</span><span class="sxs-lookup"><span data-stu-id="ce7ea-127">Topology Builder</span></span>

<span data-ttu-id="ce7ea-128">Дополнительные сведения о задачах развертывания, которые можно выполнить с помощью построителя топологии, приведены в документации по развертыванию для каждой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-128">For details about deployment tasks that you can you perform by using Topology Builder, see the Deployment documentation for each server role.</span></span>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="ce7ea-129">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="ce7ea-129">Lync Server Control Panel</span></span>

<span data-ttu-id="ce7ea-130">Вы можете использовать панель управления Lync Server 2013 для выполнения большинства задач администрирования, необходимых для управления и обслуживания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-130">You can use Lync Server 2013 Control Panel to perform most of the administrative tasks required to manage and maintain Lync Server 2013.</span></span> <span data-ttu-id="ce7ea-131">Панель управления Lync Server — это графический пользовательский интерфейс, позволяющий управлять конфигурацией серверов с Lync Server в дополнение к пользователям, клиентам и устройствам в Организации.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-131">Lync Server Control Panel provides you with a graphical user interface (GUI) to manage the configuration of the servers running Lync Server, in addition to the users, clients, and devices in your organization.</span></span> <span data-ttu-id="ce7ea-132">Командная консоль Lync Server Management Shell использует панель управления Lync Server в качестве основного механизма для настройки сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-132">Lync Server Management Shell uses Lync Server Control Panel as the underlying mechanism to perform Lync Server configuration.</span></span>

<span data-ttu-id="ce7ea-133">Панель управления Lync Server автоматически устанавливается на каждый сервер переднего плана Lync Server или стандартный выпуск Standard Server.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-133">Lync Server Control Panel is automatically installed on every Lync Server Front End Server or Standard Edition server.</span></span> <span data-ttu-id="ce7ea-134">В этом выпуске администрирование пограничных серверов выполняется удаленно.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-134">In this release, you administer Edge Servers remotely.</span></span> <span data-ttu-id="ce7ea-135">Вы также можете установить панель управления Lync Server на другом компьютере, например на консоли управления, с которой вы хотите централизованно управлять Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-135">You can also install Lync Server Control Panel on another computer, such as a management console from which you want to centrally manage Lync Server.</span></span> <span data-ttu-id="ce7ea-136">Подробности можно найти в разделе [Установка средств администрирования Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ce7ea-136">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="ce7ea-137">Чтобы настроить параметры с помощью панели управления Lync Server, необходимо войти в систему с помощью учетной записи, назначенной роли Ксадминистратор.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-137">To configure settings using Lync Server Control Panel, you must be logged in using an account that is assigned to the CsAdministrator role.</span></span> <span data-ttu-id="ce7ea-138">Подробные сведения о стандартных ролях администратора, доступных в Lync Server 2013, можно найти <A href="lync-server-2013-planning-for-role-based-access-control.md">в разделе Планирование управления доступом на основе ролей в Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-138">For details about the predefined administrative roles available in Lync Server 2013, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="ce7ea-139">Чтобы настроить параметры с помощью панели управления Lync Server, необходимо также использовать компьютер с минимальным разрешением экрана 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-139">To configure settings using Lync Server Control Panel, you must also use a computer with a minimum screen resolution of 1024 x 768.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a><span data-ttu-id="ce7ea-140">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="ce7ea-140">Lync Server Management Shell</span></span>

<span data-ttu-id="ce7ea-141">В Lync Server Командная консоль Lync Server Management Shell предоставляет новый способ администрирования и управления.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-141">In Lync Server, the Lync Server Management Shell provides a new method for administration and management.</span></span> <span data-ttu-id="ce7ea-142">Командная консоль Lync Server Management Shell — это мощный интерфейс управления, созданный в интерфейсе командной строки Windows PowerShell, включающий полный набор командлетов, специфических для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-142">Lync Server Management Shell is a powerful management interface, built on the Windows PowerShell command-line interface, that includes a comprehensive set of cmdlets that are specific to Lync Server.</span></span> <span data-ttu-id="ce7ea-143">В среде Lync Server Management Shell вы получаете обширный набор элементов управления конфигурацией и автоматизацией.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-143">With Lync Server Management Shell, you gain a rich set of configuration and automation controls.</span></span> <span data-ttu-id="ce7ea-144">Построитель топологии и панель управления Lync Server — реализуют подмножества этих командлетов, чтобы поддерживать управление сервером Lync.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-144">Topology Builder and Lync Server Control Panel both implement subsets of these cmdlets to support management of Lync Server.</span></span> <span data-ttu-id="ce7ea-145">Командная консоль Lync Server включает командлеты для всех задач администрирования Lync Server, и вы можете использовать командлеты отдельно для управления развертыванием.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-145">The Lync Server Management Shell includes cmdlets for all Lync Server administration tasks, and you can use the cmdlets individually to manage your deployment.</span></span> <span data-ttu-id="ce7ea-146">Дополнительные сведения можно найти в документации по [среде управления Lync Server 2013](lync-server-2013-lync-server-management-shell.md) или Справка по командной строке для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-146">For details, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation or the command-line help for each cmdlet.</span></span>

</div>

<div>

## <a name="logging-tool"></a><span data-ttu-id="ce7ea-147">Средство ведения журнала</span><span class="sxs-lookup"><span data-stu-id="ce7ea-147">Logging Tool</span></span>

<span data-ttu-id="ce7ea-148">Средство ведения журнала в Lync Server упрощает устранение неполадок, записывая ведение журнала и трассировку данных продукта во время работы продукта.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-148">The Lync Server Logging Tool facilitates troubleshooting by capturing logging and tracing information from the product while the product is running.</span></span> <span data-ttu-id="ce7ea-149">Это средство можно использовать для запуска сеансов отладки на любой роли сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-149">You can use the tool to run debug sessions on any Lync Server server role.</span></span> <span data-ttu-id="ce7ea-150">Подробные сведения о средстве ведения журнала можно найти в документации по средству ведения журнала Lync Server 2010 в [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)библиотеке TechNet по адресу.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-150">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ce7ea-151">Централизованная служба ведения журнала рекомендуется для всех сборов в журнал в средстве ведения журнала Lync Server во всех случаях.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-151">The Centralized Logging Service is recommended for all logging collection over the Lync Server Logging Tool in all circumstances.</span></span> <span data-ttu-id="ce7ea-152">Средство ведения журнала в Lync Server по-прежнему будет работать, но оно не будет обрабатываться в основном неэффективно, если Служба централизованного ведения журналов уже запущена.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-152">The Lync Server Logging Tool will still work, but it will interfere or be rendered mostly ineffective if the Centralized Logging Service is already running.</span></span> <span data-ttu-id="ce7ea-153">Следует использовать только централизованную службу ведения журналов или средство ведения журнала в Lync Server, но не оба одновременно.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-153">You should use only the Centralized Logging Service or the Lync Server Logging Tool, but never both concurrently.</span></span> <span data-ttu-id="ce7ea-154">Дополнительные сведения о централизованной службе ведения журналов и о том, зачем ее следует использовать в монопольном режиме, можно найти <A href="lync-server-2013-using-the-centralized-logging-service.md">в разделе Использование централизованной службы ведения журналов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ce7ea-154">For more information on the Centralized Logging Service and why you should use it exclusively, see <A href="lync-server-2013-using-the-centralized-logging-service.md">Using the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ce7ea-155">Содержание</span><span class="sxs-lookup"><span data-stu-id="ce7ea-155">In This Section</span></span>

  - [<span data-ttu-id="ce7ea-156">Требования к инфраструктуре средств администрирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7ea-156">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [<span data-ttu-id="ce7ea-157">Поддержка сервера и средств в операционной системе в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7ea-157">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="ce7ea-158">Программные требования для средств администрирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7ea-158">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)

  - [<span data-ttu-id="ce7ea-159">Административные права и разрешения, необходимые для установки и администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7ea-159">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [<span data-ttu-id="ce7ea-160">Требования к публикации топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7ea-160">Requirements to publish a topology in Lync Server 2013</span></span>](lync-server-2013-requirements-to-publish-a-topology.md)

  - [<span data-ttu-id="ce7ea-161">Установка средств администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7ea-161">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

  - [<span data-ttu-id="ce7ea-162">Открытие меню администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7ea-162">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)

  - [<span data-ttu-id="ce7ea-163">Устранение неполадок с панелью управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7ea-163">Troubleshooting Lync Server 2013 Control Panel</span></span>](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [<span data-ttu-id="ce7ea-164">Использование централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7ea-164">Using the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce7ea-165">См. также</span><span class="sxs-lookup"><span data-stu-id="ce7ea-165">See Also</span></span>


[<span data-ttu-id="ce7ea-166">командная консоль Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7ea-166">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

