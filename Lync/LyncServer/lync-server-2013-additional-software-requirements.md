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
ms.openlocfilehash: 4565f91afeb703de967040edb8f6d437aedac9eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="93733-102">Дополнительные требования к программному обеспечению для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93733-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93733-103">_**Последнее изменение темы:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="93733-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="93733-104">В дополнение к требованиям к оборудованию и операционной системе для серверных платформ, Lync Server 2013 требует установки дополнительного программного обеспечения на развертываемых серверах.</span><span class="sxs-lookup"><span data-stu-id="93733-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93733-105">Дополнительные сведения о требованиях к платформе для серверов, на которых работает Lync Server, можно найти в статье <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools support в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="93733-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="93733-106">Для получения дополнительных сведений о требованиях к системе для клиентских компьютеров и устройств ознакомьтесь со статьей <A href="lync-server-2013-planning-for-clients-and-devices.md">планирование для клиентов и устройств в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="93733-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="93733-107">Дополнительные сведения о требованиях к программному обеспечению для средств администрирования приведены <A href="lync-server-2013-administrative-tools-software-requirements.md">в статье требования к программному обеспечению для средств администрирования в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="93733-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="93733-108">Дополнительное программное обеспечение, необходимое для всех внутренних ролей сервера</span><span class="sxs-lookup"><span data-stu-id="93733-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="93733-109">В этом разделе перечислены программное обеспечение, необходимое для всех внутренних серверных ролей, которые являются ролями сервера Lync Server, кроме пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="93733-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="93733-110">Требования к пограничным серверам и пограничным пулам перечислены далее в этом разделе под заголовком **дополнительное программное обеспечение для пограничных серверов**.</span><span class="sxs-lookup"><span data-stu-id="93733-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="93733-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="93733-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="93733-112">На каждом сервере, на котором работает Lync Server 2013, должна быть установлена правильная версия Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="93733-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="93733-113">Дополнительные сведения см. в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="93733-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="93733-114">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="93733-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="93733-115">Lync Server требует Microsoft .NET Framework 4,5 для всех внутренних ролей сервера и на любом компьютере, на котором будут выполняться средства администрирования Lync Server или Microsoft Lync Server 2013, средство планирования.</span><span class="sxs-lookup"><span data-stu-id="93733-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="93733-116">Для Lync Server 2013 необходимо вручную установить 64 – разрядную версию Microsoft .NET Framework 4,5 на сервере перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93733-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="93733-117">Чтобы установить его вручную, скачайте Microsoft .NET 4,5 Framework из центра загрузки Майкрософт по адресу[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="93733-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="93733-118">Установка Microsoft .NET Framework 4.5 на серверах под управлением Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="93733-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="93733-119">При установке Microsoft .NET Framework 4,5 на серверах, на которых будут работать Lync Server 2013 и Windows Server 2012, необходимо выполнить одно из дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="93733-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="93733-120">После установки пакета .NET Framework 4.5 используйте диспетчер сервера для установки службы HTTP-активации.</span><span class="sxs-lookup"><span data-stu-id="93733-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="93733-121">**Установка службы HTTP-активации .NET 4.5 в ОС Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="93733-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="93733-122">В меню **Пуск** последовательно выберите пункты **Программы**, **Администрирование**, **Диспетчер сервера**.</span><span class="sxs-lookup"><span data-stu-id="93733-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="93733-123">В диспетчере сервера в области **Сводка компонентов** выберите **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="93733-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="93733-124">Разверните **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="93733-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="93733-p106">Выберите пункт **WCF-активация**, если он еще не выбран. Затем выберите **HTTP-активация**.</span><span class="sxs-lookup"><span data-stu-id="93733-p106">Select **WCF Activation** if it isn’t already selected. Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="93733-127">Нажмите кнопку **Далее** и следуйте инструкциям для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="93733-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="93733-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="93733-128">Windows Identity Foundation</span></span>

<span data-ttu-id="93733-129">**Windows Identity Foundation** в Lync Server 2013 требует установки Windows Identity Foundation для поддержки сценариев проверки подлинности сервера и сервера.</span><span class="sxs-lookup"><span data-stu-id="93733-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="93733-130">Windows Server 2008 R2 и Windows Server 2012 требуют различных процедур установки Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="93733-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="93733-131">Выберите серверную операционную систему из следующего списка:</span><span class="sxs-lookup"><span data-stu-id="93733-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="93733-132">Windows Server 2008 R2 для Windows Server 2008 R2 убедитесь, что она уже установлена на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="93733-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="93733-133">Для этого откройте раздел **Установка и удаление программ**, **Просмотрите установленные обновления**и найдите в разделе **Windows** **Идентификация Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="93733-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="93733-134">Подробные сведения об установке Windows Identity Foundation можно найти [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)в разделе.</span><span class="sxs-lookup"><span data-stu-id="93733-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="93733-135">Windows Server 2012 для Windows Server 2012 вы используете **Диспетчер серверов** для установки Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="93733-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="93733-136">В **мастере добавления ролей и компонентов**диспетчера серверов выберите **компоненты**.</span><span class="sxs-lookup"><span data-stu-id="93733-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="93733-137">В списке выберите **Windows Identity Foundation 3,5** .</span><span class="sxs-lookup"><span data-stu-id="93733-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="93733-138">Нажмите кнопку **Далее**, а затем — **установить**.</span><span class="sxs-lookup"><span data-stu-id="93733-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="93733-139">Дополнительное программное обеспечение для всех интерфейсных серверов и серверов Standard Edition</span><span class="sxs-lookup"><span data-stu-id="93733-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="93733-140">На всех серверах переднего плана и серверах Standard Edition также должны выполняться службы IIS с определенными модулями.</span><span class="sxs-lookup"><span data-stu-id="93733-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="93733-141">Кроме того, для всех серверов переднего плана и серверов Standard Edition, на которых развернуты конференции, приложения для приостановки вызовов, объявления или группы ответа, необходимо запустить среду выполнения формата Windows Media.</span><span class="sxs-lookup"><span data-stu-id="93733-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="93733-142">IIS</span><span class="sxs-lookup"><span data-stu-id="93733-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="93733-143">Для серверов переднего плана и серверов Standard Edition должны выполняться службы IIS со следующими модулями:</span><span class="sxs-lookup"><span data-stu-id="93733-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="93733-144">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="93733-144">Static Content</span></span>

  - <span data-ttu-id="93733-145">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="93733-145">Default Document</span></span>

  - <span data-ttu-id="93733-146">ошибки HTTP;</span><span class="sxs-lookup"><span data-stu-id="93733-146">HTTP Errors</span></span>

  - <span data-ttu-id="93733-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="93733-147">ASP.NET</span></span>

  - <span data-ttu-id="93733-148">расширяемость .NET;</span><span class="sxs-lookup"><span data-stu-id="93733-148">.NET Extensibility</span></span>

  - <span data-ttu-id="93733-149">расширения ISAPI;</span><span class="sxs-lookup"><span data-stu-id="93733-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="93733-150">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="93733-150">ISAPI Filters</span></span>

  - <span data-ttu-id="93733-151">ведение журнала HTTP;</span><span class="sxs-lookup"><span data-stu-id="93733-151">HTTP Logging</span></span>

  - <span data-ttu-id="93733-152">средства ведения журнала;</span><span class="sxs-lookup"><span data-stu-id="93733-152">Logging Tools</span></span>

  - <span data-ttu-id="93733-153">Образца</span><span class="sxs-lookup"><span data-stu-id="93733-153">Tracing</span></span>

  - <span data-ttu-id="93733-154">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="93733-154">Windows Authentication</span></span>

  - <span data-ttu-id="93733-155">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="93733-155">Request Filtering</span></span>

  - <span data-ttu-id="93733-156">Сжатие статического содержимого</span><span class="sxs-lookup"><span data-stu-id="93733-156">Static Content Compression</span></span>

  - <span data-ttu-id="93733-157">Сжатие динамического содержимого</span><span class="sxs-lookup"><span data-stu-id="93733-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="93733-158">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="93733-158">IIS Management Console</span></span>

  - <span data-ttu-id="93733-159">сценарии и средства управления IIS;</span><span class="sxs-lookup"><span data-stu-id="93733-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="93733-160">анонимный доступ (устанавливается по умолчанию при установке служб IIS);</span><span class="sxs-lookup"><span data-stu-id="93733-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="93733-161">проверка подлинности с сопоставлением сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="93733-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="93733-162">Среда выполнения формата Windows Media и возможности рабочего стола Windows</span><span class="sxs-lookup"><span data-stu-id="93733-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="93733-163">**Возможности рабочего стола Windows** На всех серверах переднего плана и серверах Standard Edition, на которых будет развернута конференция, должна быть установлена среда выполнения Windows Media Format Runtime, которая, кроме Windows Server 2012, установлена в составе Windows Desktop Experience.</span><span class="sxs-lookup"><span data-stu-id="93733-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="93733-164">Для Windows Server 2012 требуется Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="93733-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="93733-165">Компонент Windows Media Format Runtime необходим для воспроизведения файлов Windows Media Audio (WMA-файлов) приложениями "Парковка вызовов", "Оповещение" и "Группа ответа" при проигрывании оповещений и музыки.</span><span class="sxs-lookup"><span data-stu-id="93733-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="93733-166">Рекомендуется установить возможности рабочего стола Windows перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93733-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="93733-167">Если Lync Server 2013 не находит это программное обеспечение на сервере, будет предложено установить его, а затем необходимо перезапустить сервер для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="93733-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="93733-168">Дополнительное программное обеспечение для серверов переднего плана и серверов Standard Edition под управлением Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="93733-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="93733-169">Для серверов переднего плана требуется .NET 3,5, который не устанавливается по умолчанию в Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="93733-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="93733-170">Чтобы установить ее, вставьте установочный носитель Windows Server 2012 в диск D и введите следующее:</span><span class="sxs-lookup"><span data-stu-id="93733-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="93733-171">Подробные сведения об установке .NET 3,5 на серверах под управлением Windows Server 2012 приведены в разделе "рекомендации по <https://go.microsoft.com/fwlink/p/?linkid=275032>развертыванию Microsoft .net Framework 3,5".</span><span class="sxs-lookup"><span data-stu-id="93733-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="93733-172">Дополнительное программное обеспечение для Директоров</span><span class="sxs-lookup"><span data-stu-id="93733-172">Additional Software for Directors</span></span>

<span data-ttu-id="93733-173">Директоры должны запускать службы IIS со следующими модулями:</span><span class="sxs-lookup"><span data-stu-id="93733-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="93733-174">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="93733-174">Static Content</span></span>

  - <span data-ttu-id="93733-175">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="93733-175">Default Document</span></span>

  - <span data-ttu-id="93733-176">ошибки HTTP;</span><span class="sxs-lookup"><span data-stu-id="93733-176">HTTP Errors</span></span>

  - <span data-ttu-id="93733-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="93733-177">ASP.NET</span></span>

  - <span data-ttu-id="93733-178">расширяемость .NET;</span><span class="sxs-lookup"><span data-stu-id="93733-178">.NET Extensibility</span></span>

  - <span data-ttu-id="93733-179">расширения ISAPI;</span><span class="sxs-lookup"><span data-stu-id="93733-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="93733-180">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="93733-180">ISAPI Filters</span></span>

  - <span data-ttu-id="93733-181">ведение журнала HTTP;</span><span class="sxs-lookup"><span data-stu-id="93733-181">HTTP Logging</span></span>

  - <span data-ttu-id="93733-182">средства ведения журнала;</span><span class="sxs-lookup"><span data-stu-id="93733-182">Logging Tools</span></span>

  - <span data-ttu-id="93733-183">Образца</span><span class="sxs-lookup"><span data-stu-id="93733-183">Tracing</span></span>

  - <span data-ttu-id="93733-184">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="93733-184">Windows Authentication</span></span>

  - <span data-ttu-id="93733-185">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="93733-185">Request Filtering</span></span>

  - <span data-ttu-id="93733-186">сжатие статического содержимого;</span><span class="sxs-lookup"><span data-stu-id="93733-186">Static Content Compression</span></span>

  - <span data-ttu-id="93733-187">консоль управления IIS;</span><span class="sxs-lookup"><span data-stu-id="93733-187">IIS Management Console</span></span>

  - <span data-ttu-id="93733-188">сценарии и средства управления IIS;</span><span class="sxs-lookup"><span data-stu-id="93733-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="93733-189">анонимный доступ (устанавливается по умолчанию при установке служб IIS);</span><span class="sxs-lookup"><span data-stu-id="93733-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="93733-190">проверка подлинности с сопоставлением сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="93733-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="93733-191">Дополнительное программное обеспечение для интерфейсных серверов сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="93733-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="93733-192">На интерфейсных серверах сохраняемого чата должен работать компонент Windows Server, MSMQ.</span><span class="sxs-lookup"><span data-stu-id="93733-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="93733-193">Для получения сведений о включении MSMQ [щелкните здесь.](https://technet.microsoft.com/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="93733-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="93733-194">Дополнительное программное обеспечение для пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="93733-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="93733-195">Для пограничных серверов требуется следующее программное обеспечение:</span><span class="sxs-lookup"><span data-stu-id="93733-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="93733-196">На каждом сервере, на котором работает Lync Server 2013, должна быть установлена правильная версия Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="93733-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="93733-197">Дополнительные сведения см. в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="93733-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="93733-198">Для Lync Server требуется Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="93733-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="93733-199">Для Lync Server 2013, установленного в Windows Server 2008 R2, перед установкой Lync Server 2013 необходимо вручную установить выпуск 64 – bit для Microsoft .NET Framework 4,5 на сервере.</span><span class="sxs-lookup"><span data-stu-id="93733-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="93733-200">Чтобы установить его вручную, скачайте Microsoft .NET 4,5 Framework из центра загрузки Майкрософт по адресу[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="93733-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="93733-201">**Windows Identity Foundation** в Lync Server 2013 требует установки Windows Identity Foundation для поддержки сценариев проверки подлинности сервера и сервера.</span><span class="sxs-lookup"><span data-stu-id="93733-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="93733-202">Windows Server 2008 R2 и Windows Server 2012 требуют различных процедур установки Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="93733-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="93733-203">Выберите серверную операционную систему из следующего списка:</span><span class="sxs-lookup"><span data-stu-id="93733-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="93733-204">Windows Server 2008 R2 для Windows Server 2008 R2 убедитесь, что она уже установлена на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="93733-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="93733-205">Для этого откройте раздел **Установка и удаление программ**, **Просмотрите установленные обновления**и найдите в разделе **Windows** **Идентификация Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="93733-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="93733-206">Подробные сведения об установке Windows Identity Foundation можно найти [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)в разделе.</span><span class="sxs-lookup"><span data-stu-id="93733-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="93733-207">Windows Server 2012 для Windows Server 2012 вы используете **Диспетчер серверов** для установки Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="93733-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="93733-208">В **мастере добавления ролей и компонентов**диспетчера серверов выберите **компоненты**.</span><span class="sxs-lookup"><span data-stu-id="93733-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="93733-209">В списке выберите **Windows Identity Foundation 3,5** .</span><span class="sxs-lookup"><span data-stu-id="93733-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="93733-210">Нажмите кнопку **Далее**, а затем — **установить**.</span><span class="sxs-lookup"><span data-stu-id="93733-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="93733-211">Не устанавливайте многоуровневые поставщики услуг на серверах-посредниках</span><span class="sxs-lookup"><span data-stu-id="93733-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="93733-212">Не устанавливайте клиентское программное обеспечение сервера Microsoft Internet Security and Acceleration (ISA) или любое другое программное обеспечение (LSP) на всех серверах переднего плана или отдельных серверах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="93733-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="93733-213">Установка этого ПО может привести к снижению скорости передачи трафика на сервере-посреднике.</span><span class="sxs-lookup"><span data-stu-id="93733-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="93733-214">См. также</span><span class="sxs-lookup"><span data-stu-id="93733-214">See Also</span></span>


[<span data-ttu-id="93733-215">Требования к программному обеспечению для средств администрирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93733-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

