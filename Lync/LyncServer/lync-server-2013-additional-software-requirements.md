---
title: 'Lync Server 2013: дополнительные требования к программному обеспечению'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc650b4c427640398af1748e86c7bca9d76c703d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="b8c4e-102">Дополнительные требования к программному обеспечению для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8c4e-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8c4e-103">_**Тема последнего изменения:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="b8c4e-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="b8c4e-104">В дополнение к требованиям к оборудованию и операционной системе для серверных платформ Lync Server 2013 требует установки дополнительного программного обеспечения на серверах, которые вы развертываете.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8c4e-105">Сведения о требованиях к платформе для серверов Lync Server можно найти в разделе <A href="lync-server-2013-server-hardware-platforms.md">аппаратные платформы сервера для Lync server 2013</A> и <A href="lync-server-2013-server-and-tools-operating-system-support.md">серверных и инструментальных средств, поддерживаемых операционной системой в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="b8c4e-106">Дополнительные сведения о требованиях к системе для клиентских компьютеров и устройств можно найти <A href="lync-server-2013-planning-for-clients-and-devices.md">в разделе Планирование клиентов и устройств в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="b8c4e-107">Сведения о требованиях к программному обеспечению для администрирования описаны <A href="lync-server-2013-administrative-tools-software-requirements.md">в разделе Требования к программному обеспечению для администраторов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="b8c4e-108">Дополнительное программное обеспечение, необходимое для всех внутренних серверных ролей</span><span class="sxs-lookup"><span data-stu-id="b8c4e-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="b8c4e-109">В этом разделе перечислены программы, необходимые для всех внутренних ролей сервера, которые являются всеми ролями сервера Lync Server, кроме пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="b8c4e-110">Требования к пограничным серверам и пулам Edge перечислены ниже в разделе **дополнительное программное обеспечение для пограничного сервера**.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="b8c4e-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="b8c4e-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="b8c4e-112">На каждом сервере, на котором работает Lync Server 2013, должны быть установлены правильные выпуски Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="b8c4e-113">Подробные сведения можно найти в разделе [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="b8c4e-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="b8c4e-114">Платформа Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="b8c4e-115">Lync Server требует Microsoft .NET Framework 4,5 для всех внутренних серверных ролей и на любом компьютере, на котором выполняются средства администрирования сервера Lync Server или Microsoft Lync Server 2013; средство планирования.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="b8c4e-116">Для Lync Server 2013 необходимо вручную установить 64-разрядную версию Microsoft .NET Framework 4,5 на сервере перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="b8c4e-117">Чтобы установить ее вручную, скачайте Microsoft .NET 4,5 Framework из центра загрузки Майкрософт по адресу[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="b8c4e-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="b8c4e-118">Установка Microsoft .NET Framework 4,5 на серверах под управлением Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b8c4e-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="b8c4e-119">При установке Microsoft .NET Framework 4,5 на сервер, на котором работают Lync Server 2013 и Windows Server 2012, необходимо выполнить одно из дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="b8c4e-120">После установки .NET Framework 4,5 Используйте Диспетчер серверов для установки активации HTTP.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="b8c4e-121">**Установка активации .NET 4,5 HTTP в Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="b8c4e-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="b8c4e-122">В меню **Пуск** выберите пункт **программы**, а затем — **Администрирование**, а затем — **Диспетчер серверов**.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="b8c4e-123">В диспетчере серверов в разделе **Сводка по компонентам**выберите **Добавить функции**.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="b8c4e-124">Разверните **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="b8c4e-125">Выберите **Активация WCF** , если она еще не выбрана.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="b8c4e-126">Затем выберите **Активация HTTP**.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="b8c4e-127">Нажмите кнопку **Далее** и следуйте инструкциям, чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="b8c4e-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="b8c4e-128">Windows Identity Foundation</span></span>

<span data-ttu-id="b8c4e-129">Для поддержки сценариев проверки подлинности сервера и **сервера в Lync** Server 2013 необходимо установить Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="b8c4e-130">Для Windows Server 2008 R2 и Windows Server 2012 требуется выполнить различные процедуры для установки Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="b8c4e-131">Выберите серверную операционную систему из следующего списка:</span><span class="sxs-lookup"><span data-stu-id="b8c4e-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="b8c4e-132">Windows Server 2008 R2 для Windows Server 2008 R2 — убедитесь, что она уже установлена на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="b8c4e-133">Для этого выберите элемент **Установка и удаление программ**, **Просмотрите установленные обновления**и найдите в разделе **Windows** **удостоверение для Windows (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="b8c4e-134">Подробнее об установке Windows Identity Foundation можно узнать [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)в статье.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="b8c4e-135">Windows Server 2012 для Windows Server 2012 вы используете **Диспетчер серверов** для установки Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="b8c4e-136">В **мастере добавления ролей и компонентов**в диспетчере серверов выберите **компоненты**.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="b8c4e-137">В списке выберите **Windows Identity Foundation 3,5** .</span><span class="sxs-lookup"><span data-stu-id="b8c4e-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="b8c4e-138">Нажмите кнопку **Далее**, а затем — **установить**.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="b8c4e-139">Дополнительное программное обеспечение для всех серверов переднего плана и стандартных серверов выпусков</span><span class="sxs-lookup"><span data-stu-id="b8c4e-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="b8c4e-140">На всех серверах переднего плана и стандартных серверах выпусков также должны выполняться службы IIS с определенными модулями.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="b8c4e-141">Кроме того, все серверы переднего плана и серверы стандартных выпусков, для которых развернута Конференц-связь, приложение для присоединения к приостановке, объявление и группа ответа, должны запускать среду выполнения формата Windows Media</span><span class="sxs-lookup"><span data-stu-id="b8c4e-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="b8c4e-142">Службы IIS</span><span class="sxs-lookup"><span data-stu-id="b8c4e-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="b8c4e-143">Для серверов переднего плана и стандартных серверов выпусков должны выполняться службы IIS со следующими модулями:</span><span class="sxs-lookup"><span data-stu-id="b8c4e-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="b8c4e-144">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="b8c4e-144">Static Content</span></span>

  - <span data-ttu-id="b8c4e-145">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b8c4e-145">Default Document</span></span>

  - <span data-ttu-id="b8c4e-146">Ошибки HTTP</span><span class="sxs-lookup"><span data-stu-id="b8c4e-146">HTTP Errors</span></span>

  - <span data-ttu-id="b8c4e-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b8c4e-147">ASP.NET</span></span>

  - <span data-ttu-id="b8c4e-148">Расширяемость .NET</span><span class="sxs-lookup"><span data-stu-id="b8c4e-148">.NET Extensibility</span></span>

  - <span data-ttu-id="b8c4e-149">Расширения ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="b8c4e-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="b8c4e-150">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="b8c4e-150">ISAPI Filters</span></span>

  - <span data-ttu-id="b8c4e-151">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="b8c4e-151">HTTP Logging</span></span>

  - <span data-ttu-id="b8c4e-152">Средства ведения журналов</span><span class="sxs-lookup"><span data-stu-id="b8c4e-152">Logging Tools</span></span>

  - <span data-ttu-id="b8c4e-153">Трассировка</span><span class="sxs-lookup"><span data-stu-id="b8c4e-153">Tracing</span></span>

  - <span data-ttu-id="b8c4e-154">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="b8c4e-154">Windows Authentication</span></span>

  - <span data-ttu-id="b8c4e-155">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="b8c4e-155">Request Filtering</span></span>

  - <span data-ttu-id="b8c4e-156">Сжатие статического содержимого</span><span class="sxs-lookup"><span data-stu-id="b8c4e-156">Static Content Compression</span></span>

  - <span data-ttu-id="b8c4e-157">Сжатие динамического содержимого</span><span class="sxs-lookup"><span data-stu-id="b8c4e-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="b8c4e-158">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="b8c4e-158">IIS Management Console</span></span>

  - <span data-ttu-id="b8c4e-159">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="b8c4e-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="b8c4e-160">Анонимная проверка подлинности (устанавливается по умолчанию при установке IIS).</span><span class="sxs-lookup"><span data-stu-id="b8c4e-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="b8c4e-161">Проверка подлинности с сопоставлением сертификатов клиентов</span><span class="sxs-lookup"><span data-stu-id="b8c4e-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="b8c4e-162">Среда выполнения формата Windows Media и возможности рабочего стола Windows</span><span class="sxs-lookup"><span data-stu-id="b8c4e-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="b8c4e-163">**Возможности рабочего стола Windows** Все серверы переднего плана и стандартные серверы выпусков, на которых будет развернута конференция, должны иметь установленную среду выполнения формата Windows Media (за исключением Windows Server 2012, установленной в составе рабочего стола Windows.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="b8c4e-164">Для Windows Server 2012 требуется Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="b8c4e-165">Для работы с файлами Windows Media Audio (WMA), которые воспринимаются приложениями для приема, объявления и ответа, воспроизводится для объявлений и музыкальных файлов, которые требуются в среде выполнения формата Windows Media.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="b8c4e-166">Перед установкой Lync Server 2013 рекомендуется установить возможности рабочего стола Windows.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="b8c4e-167">Если Lync Server 2013 не находит это программное обеспечение на сервере, вам будет предложено установить его, а затем необходимо перезапустить сервер, чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="b8c4e-168">Дополнительное программное обеспечение для серверов переднего плана и серверов Standard Edition, работающих под управлением Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b8c4e-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="b8c4e-169">Для серверов с внешними интерфейсами требуется .NET 3,5, который не установлен по умолчанию в Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="b8c4e-170">Чтобы установить его, вставьте установочный носитель Windows Server 2012 в дисковод D и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b8c4e-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="b8c4e-171">Подробные сведения об установке .NET 3,5 на серверах под управлением Windows Server 2012 можно найти в разделе "вопросы по <https://go.microsoft.com/fwlink/p/?linkid=275032>развертыванию Microsoft .net Framework 3,5".</span><span class="sxs-lookup"><span data-stu-id="b8c4e-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="b8c4e-172">Дополнительное программное обеспечение для режиссеров</span><span class="sxs-lookup"><span data-stu-id="b8c4e-172">Additional Software for Directors</span></span>

<span data-ttu-id="b8c4e-173">Режиссеры должны запускать службы IIS со следующими модулями:</span><span class="sxs-lookup"><span data-stu-id="b8c4e-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="b8c4e-174">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="b8c4e-174">Static Content</span></span>

  - <span data-ttu-id="b8c4e-175">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b8c4e-175">Default Document</span></span>

  - <span data-ttu-id="b8c4e-176">Ошибки HTTP</span><span class="sxs-lookup"><span data-stu-id="b8c4e-176">HTTP Errors</span></span>

  - <span data-ttu-id="b8c4e-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b8c4e-177">ASP.NET</span></span>

  - <span data-ttu-id="b8c4e-178">Расширяемость .NET</span><span class="sxs-lookup"><span data-stu-id="b8c4e-178">.NET Extensibility</span></span>

  - <span data-ttu-id="b8c4e-179">Расширения ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="b8c4e-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="b8c4e-180">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="b8c4e-180">ISAPI Filters</span></span>

  - <span data-ttu-id="b8c4e-181">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="b8c4e-181">HTTP Logging</span></span>

  - <span data-ttu-id="b8c4e-182">Средства ведения журналов</span><span class="sxs-lookup"><span data-stu-id="b8c4e-182">Logging Tools</span></span>

  - <span data-ttu-id="b8c4e-183">Трассировка</span><span class="sxs-lookup"><span data-stu-id="b8c4e-183">Tracing</span></span>

  - <span data-ttu-id="b8c4e-184">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="b8c4e-184">Windows Authentication</span></span>

  - <span data-ttu-id="b8c4e-185">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="b8c4e-185">Request Filtering</span></span>

  - <span data-ttu-id="b8c4e-186">Сжатие статического содержимого</span><span class="sxs-lookup"><span data-stu-id="b8c4e-186">Static Content Compression</span></span>

  - <span data-ttu-id="b8c4e-187">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="b8c4e-187">IIS Management Console</span></span>

  - <span data-ttu-id="b8c4e-188">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="b8c4e-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="b8c4e-189">Анонимная проверка подлинности (устанавливается по умолчанию при установке IIS).</span><span class="sxs-lookup"><span data-stu-id="b8c4e-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="b8c4e-190">Проверка подлинности с сопоставлением сертификатов клиентов</span><span class="sxs-lookup"><span data-stu-id="b8c4e-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="b8c4e-191">Дополнительное программное обеспечение для серверов клиентского чата с постоянным подключением</span><span class="sxs-lookup"><span data-stu-id="b8c4e-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="b8c4e-192">На серверах, использующих сохраняемый чат, должны быть запущены очередь сообщений (также называемая MSMQ), которая является компонентом Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="b8c4e-193">Чтобы узнать, как включить MSMQ, [нажмите здесь.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="b8c4e-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="b8c4e-194">Дополнительное программное обеспечение для пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="b8c4e-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="b8c4e-195">Для пограничных серверов требуется следующее программное обеспечение:</span><span class="sxs-lookup"><span data-stu-id="b8c4e-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="b8c4e-196">На каждом сервере, на котором работает Lync Server 2013, должны быть установлены правильные выпуски Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="b8c4e-197">Подробные сведения можно найти в разделе [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="b8c4e-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="b8c4e-198">Для Lync Server требуется Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="b8c4e-199">Для Lync Server 2013, установленного в Windows Server 2008 R2, перед установкой Lync Server 2013 необходимо вручную установить версию 64-bit Microsoft .NET Framework 4,5 на сервере.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="b8c4e-200">Чтобы установить ее вручную, скачайте Microsoft .NET 4,5 Framework из центра загрузки Майкрософт по адресу[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="b8c4e-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="b8c4e-201">Для поддержки сценариев проверки подлинности сервера и **сервера в Lync** Server 2013 необходимо установить Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="b8c4e-202">Для Windows Server 2008 R2 и Windows Server 2012 требуется выполнить различные процедуры для установки Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="b8c4e-203">Выберите серверную операционную систему из следующего списка:</span><span class="sxs-lookup"><span data-stu-id="b8c4e-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="b8c4e-204">Windows Server 2008 R2 для Windows Server 2008 R2 — убедитесь, что она уже установлена на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="b8c4e-205">Для этого выберите элемент **Установка и удаление программ**, **Просмотрите установленные обновления**и найдите в разделе **Windows** **удостоверение для Windows (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="b8c4e-206">Подробнее об установке Windows Identity Foundation можно узнать [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)в статье.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="b8c4e-207">Windows Server 2012 для Windows Server 2012 вы используете **Диспетчер серверов** для установки Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="b8c4e-208">В **мастере добавления ролей и компонентов**в диспетчере серверов выберите **компоненты**.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="b8c4e-209">В списке выберите **Windows Identity Foundation 3,5** .</span><span class="sxs-lookup"><span data-stu-id="b8c4e-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="b8c4e-210">Нажмите кнопку **Далее**, а затем — **установить**.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="b8c4e-211">Не устанавливайте провайдеры многоуровневых соединителей на серверах мультимедиа</span><span class="sxs-lookup"><span data-stu-id="b8c4e-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="b8c4e-212">Не устанавливайте клиентское программное обеспечение сервера Microsoft Internet Security and Acceleration (ISA) или любое другое программное обеспечение, которое можно получить с любого другого поставщика многоуровневой службы (LSP), на любом сервере переднего плана или отдельном сервере.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="b8c4e-213">Установка этого программного обеспечения может привести к ухудшению производительности мультимедийного трафика.</span><span class="sxs-lookup"><span data-stu-id="b8c4e-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b8c4e-214">См. также</span><span class="sxs-lookup"><span data-stu-id="b8c4e-214">See Also</span></span>


[<span data-ttu-id="b8c4e-215">Программные требования для средств администрирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8c4e-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

