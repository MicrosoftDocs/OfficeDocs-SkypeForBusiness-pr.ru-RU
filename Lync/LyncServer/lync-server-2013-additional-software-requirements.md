---
title: 'Lync Server 2013: дополнительные требования к программному обеспечению'
description: 'Lync Server 2013: дополнительные требования к программному обеспечению.'
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
ms.openlocfilehash: fbc36f23a2246c9d653e47954064182c756f0dff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553045"
---
# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="c2d51-103">Дополнительные требования к программному обеспечению для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2d51-103">Additional software requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2d51-104">_**Последнее изменение темы:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="c2d51-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="c2d51-105">В дополнение к требованиям к оборудованию и операционной системе для серверных платформ, Lync Server 2013 требует установки дополнительного программного обеспечения на развертываемых серверах.</span><span class="sxs-lookup"><span data-stu-id="c2d51-105">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2d51-106">Дополнительные сведения о требованиях к платформе для серверов, на которых работает Lync Server, можно найти в статье <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools support в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c2d51-106">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="c2d51-107">Для получения дополнительных сведений о требованиях к системе для клиентских компьютеров и устройств ознакомьтесь со статьей <A href="lync-server-2013-planning-for-clients-and-devices.md">планирование для клиентов и устройств в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="c2d51-107">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="c2d51-108">Дополнительные сведения о требованиях к программному обеспечению для средств администрирования приведены <A href="lync-server-2013-administrative-tools-software-requirements.md">в статье требования к программному обеспечению для средств администрирования в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c2d51-108">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="c2d51-109">Дополнительное программное обеспечение, необходимое для всех внутренних ролей сервера</span><span class="sxs-lookup"><span data-stu-id="c2d51-109">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="c2d51-110">В этом разделе перечислены программное обеспечение, необходимое для всех внутренних серверных ролей, которые являются ролями сервера Lync Server, кроме пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="c2d51-110">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="c2d51-111">Требования к пограничным серверам и пограничным пулам перечислены далее в этом разделе под заголовком **дополнительное программное обеспечение для пограничных серверов**.</span><span class="sxs-lookup"><span data-stu-id="c2d51-111">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="c2d51-112">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="c2d51-112">Windows PowerShell 3.0</span></span>

<span data-ttu-id="c2d51-113">На каждом сервере, на котором работает Lync Server 2013, должна быть установлена правильная версия Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c2d51-113">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="c2d51-114">Дополнительные сведения см. в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="c2d51-114">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="c2d51-115">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c2d51-115">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="c2d51-116">Lync Server требует Microsoft .NET Framework 4,5 для всех внутренних ролей сервера и на любом компьютере, на котором будут выполняться средства администрирования Lync Server или Microsoft Lync Server 2013, средство планирования.</span><span class="sxs-lookup"><span data-stu-id="c2d51-116">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="c2d51-117">Для Lync Server 2013 необходимо вручную установить 64 – разрядную версию Microsoft .NET Framework 4,5 на сервере перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2d51-117">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="c2d51-118">Чтобы установить его вручную, скачайте Microsoft .NET 4,5 Framework из центра загрузки Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="c2d51-118">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="c2d51-119">Установка Microsoft .NET Framework 4.5 на серверах под управлением Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c2d51-119">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="c2d51-120">При установке Microsoft .NET Framework 4,5 на серверах, на которых будут работать Lync Server 2013 и Windows Server 2012, необходимо выполнить одно из дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="c2d51-120">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="c2d51-121">После установки пакета .NET Framework 4.5 используйте диспетчер сервера для установки службы HTTP-активации.</span><span class="sxs-lookup"><span data-stu-id="c2d51-121">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="c2d51-122">**Установка службы HTTP-активации .NET 4.5 в ОС Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="c2d51-122">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="c2d51-123">В меню **Пуск** последовательно выберите пункты **Программы**, **Администрирование**, **Диспетчер сервера**.</span><span class="sxs-lookup"><span data-stu-id="c2d51-123">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="c2d51-124">В диспетчере сервера в области **Сводка компонентов** выберите **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="c2d51-124">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="c2d51-125">Разверните **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="c2d51-125">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="c2d51-p106">Выберите пункт **WCF-активация**, если он еще не выбран. Затем выберите **HTTP-активация**.</span><span class="sxs-lookup"><span data-stu-id="c2d51-p106">Select **WCF Activation** if it isn’t already selected. Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="c2d51-128">Нажмите кнопку **Далее** и следуйте инструкциям для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="c2d51-128">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="c2d51-129">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="c2d51-129">Windows Identity Foundation</span></span>

<span data-ttu-id="c2d51-130">**Windows Identity Foundation** в Lync Server 2013 требует установки Windows Identity Foundation для поддержки сценариев проверки подлинности сервера и сервера.</span><span class="sxs-lookup"><span data-stu-id="c2d51-130">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="c2d51-131">Windows Server 2008 R2 и Windows Server 2012 требуют различных процедур установки Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="c2d51-131">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="c2d51-132">Выберите серверную операционную систему из следующего списка:</span><span class="sxs-lookup"><span data-stu-id="c2d51-132">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="c2d51-133">Windows Server 2008 R2 для Windows Server 2008 R2 убедитесь, что она уже установлена на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="c2d51-133">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="c2d51-134">Для этого откройте раздел **Установка и удаление программ**, **Просмотрите установленные обновления**и найдите в разделе **Windows** **Идентификация Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="c2d51-134">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="c2d51-135">Подробные сведения об установке Windows Identity Foundation можно найти в разделе [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="c2d51-135">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="c2d51-136">Windows Server 2012 для Windows Server 2012 вы используете **Диспетчер серверов** для установки Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="c2d51-136">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="c2d51-137">В **мастере добавления ролей и компонентов**диспетчера серверов выберите **компоненты**.</span><span class="sxs-lookup"><span data-stu-id="c2d51-137">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="c2d51-138">В списке выберите **Windows Identity Foundation 3,5** .</span><span class="sxs-lookup"><span data-stu-id="c2d51-138">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="c2d51-139">Нажмите кнопку **Далее**, а затем — **установить**.</span><span class="sxs-lookup"><span data-stu-id="c2d51-139">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="c2d51-140">Дополнительное программное обеспечение для всех интерфейсных серверов и серверов Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c2d51-140">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="c2d51-141">На всех серверах переднего плана и серверах Standard Edition также должны выполняться службы IIS с определенными модулями.</span><span class="sxs-lookup"><span data-stu-id="c2d51-141">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="c2d51-142">Кроме того, для всех серверов переднего плана и серверов Standard Edition, на которых развернуты конференции, приложения для приостановки вызовов, объявления или группы ответа, необходимо запустить среду выполнения формата Windows Media.</span><span class="sxs-lookup"><span data-stu-id="c2d51-142">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="c2d51-143">IIS</span><span class="sxs-lookup"><span data-stu-id="c2d51-143">Internet Information Services (IIS)</span></span>

<span data-ttu-id="c2d51-144">Для серверов переднего плана и серверов Standard Edition должны выполняться службы IIS со следующими модулями:</span><span class="sxs-lookup"><span data-stu-id="c2d51-144">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="c2d51-145">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="c2d51-145">Static Content</span></span>

  - <span data-ttu-id="c2d51-146">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c2d51-146">Default Document</span></span>

  - <span data-ttu-id="c2d51-147">ошибки HTTP;</span><span class="sxs-lookup"><span data-stu-id="c2d51-147">HTTP Errors</span></span>

  - <span data-ttu-id="c2d51-148">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c2d51-148">ASP.NET</span></span>

  - <span data-ttu-id="c2d51-149">расширяемость .NET;</span><span class="sxs-lookup"><span data-stu-id="c2d51-149">.NET Extensibility</span></span>

  - <span data-ttu-id="c2d51-150">расширения ISAPI;</span><span class="sxs-lookup"><span data-stu-id="c2d51-150">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="c2d51-151">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="c2d51-151">ISAPI Filters</span></span>

  - <span data-ttu-id="c2d51-152">ведение журнала HTTP;</span><span class="sxs-lookup"><span data-stu-id="c2d51-152">HTTP Logging</span></span>

  - <span data-ttu-id="c2d51-153">средства ведения журнала;</span><span class="sxs-lookup"><span data-stu-id="c2d51-153">Logging Tools</span></span>

  - <span data-ttu-id="c2d51-154">Образца</span><span class="sxs-lookup"><span data-stu-id="c2d51-154">Tracing</span></span>

  - <span data-ttu-id="c2d51-155">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="c2d51-155">Windows Authentication</span></span>

  - <span data-ttu-id="c2d51-156">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="c2d51-156">Request Filtering</span></span>

  - <span data-ttu-id="c2d51-157">Сжатие статического содержимого</span><span class="sxs-lookup"><span data-stu-id="c2d51-157">Static Content Compression</span></span>

  - <span data-ttu-id="c2d51-158">Сжатие динамического содержимого</span><span class="sxs-lookup"><span data-stu-id="c2d51-158">Dynamic Content Compression</span></span>

  - <span data-ttu-id="c2d51-159">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="c2d51-159">IIS Management Console</span></span>

  - <span data-ttu-id="c2d51-160">сценарии и средства управления IIS;</span><span class="sxs-lookup"><span data-stu-id="c2d51-160">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="c2d51-161">анонимный доступ (устанавливается по умолчанию при установке служб IIS);</span><span class="sxs-lookup"><span data-stu-id="c2d51-161">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="c2d51-162">проверка подлинности с сопоставлением сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="c2d51-162">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="c2d51-163">Среда выполнения формата Windows Media и возможности рабочего стола Windows</span><span class="sxs-lookup"><span data-stu-id="c2d51-163">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="c2d51-164">**Возможности рабочего стола Windows** На всех серверах переднего плана и серверах Standard Edition, на которых будет развернута конференция, должна быть установлена среда выполнения Windows Media Format Runtime, которая, кроме Windows Server 2012, установлена в составе Windows Desktop Experience.</span><span class="sxs-lookup"><span data-stu-id="c2d51-164">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="c2d51-165">Для Windows Server 2012 требуется Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="c2d51-165">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="c2d51-166">Компонент Windows Media Format Runtime необходим для воспроизведения файлов Windows Media Audio (WMA-файлов) приложениями "Парковка вызовов", "Оповещение" и "Группа ответа" при проигрывании оповещений и музыки.</span><span class="sxs-lookup"><span data-stu-id="c2d51-166">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="c2d51-167">Рекомендуется установить возможности рабочего стола Windows перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2d51-167">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="c2d51-168">Если Lync Server 2013 не находит это программное обеспечение на сервере, будет предложено установить его, а затем необходимо перезапустить сервер для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="c2d51-168">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="c2d51-169">Дополнительное программное обеспечение для серверов переднего плана и серверов Standard Edition под управлением Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c2d51-169">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="c2d51-170">Для серверов переднего плана требуется .NET 3,5, который не устанавливается по умолчанию в Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="c2d51-170">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="c2d51-171">Чтобы установить ее, вставьте установочный носитель Windows Server 2012 в диск D и введите следующее:</span><span class="sxs-lookup"><span data-stu-id="c2d51-171">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="c2d51-172">Подробные сведения об установке .NET 3,5 на серверах под управлением Windows Server 2012 приведены в разделе "рекомендации по развертыванию Microsoft .NET Framework 3,5" <https://go.microsoft.com/fwlink/p/?linkid=275032> .</span><span class="sxs-lookup"><span data-stu-id="c2d51-172">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="c2d51-173">Дополнительное программное обеспечение для Директоров</span><span class="sxs-lookup"><span data-stu-id="c2d51-173">Additional Software for Directors</span></span>

<span data-ttu-id="c2d51-174">Директоры должны запускать службы IIS со следующими модулями:</span><span class="sxs-lookup"><span data-stu-id="c2d51-174">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="c2d51-175">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="c2d51-175">Static Content</span></span>

  - <span data-ttu-id="c2d51-176">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c2d51-176">Default Document</span></span>

  - <span data-ttu-id="c2d51-177">ошибки HTTP;</span><span class="sxs-lookup"><span data-stu-id="c2d51-177">HTTP Errors</span></span>

  - <span data-ttu-id="c2d51-178">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c2d51-178">ASP.NET</span></span>

  - <span data-ttu-id="c2d51-179">расширяемость .NET;</span><span class="sxs-lookup"><span data-stu-id="c2d51-179">.NET Extensibility</span></span>

  - <span data-ttu-id="c2d51-180">расширения ISAPI;</span><span class="sxs-lookup"><span data-stu-id="c2d51-180">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="c2d51-181">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="c2d51-181">ISAPI Filters</span></span>

  - <span data-ttu-id="c2d51-182">ведение журнала HTTP;</span><span class="sxs-lookup"><span data-stu-id="c2d51-182">HTTP Logging</span></span>

  - <span data-ttu-id="c2d51-183">средства ведения журнала;</span><span class="sxs-lookup"><span data-stu-id="c2d51-183">Logging Tools</span></span>

  - <span data-ttu-id="c2d51-184">Образца</span><span class="sxs-lookup"><span data-stu-id="c2d51-184">Tracing</span></span>

  - <span data-ttu-id="c2d51-185">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="c2d51-185">Windows Authentication</span></span>

  - <span data-ttu-id="c2d51-186">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="c2d51-186">Request Filtering</span></span>

  - <span data-ttu-id="c2d51-187">сжатие статического содержимого;</span><span class="sxs-lookup"><span data-stu-id="c2d51-187">Static Content Compression</span></span>

  - <span data-ttu-id="c2d51-188">консоль управления IIS;</span><span class="sxs-lookup"><span data-stu-id="c2d51-188">IIS Management Console</span></span>

  - <span data-ttu-id="c2d51-189">сценарии и средства управления IIS;</span><span class="sxs-lookup"><span data-stu-id="c2d51-189">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="c2d51-190">анонимный доступ (устанавливается по умолчанию при установке служб IIS);</span><span class="sxs-lookup"><span data-stu-id="c2d51-190">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="c2d51-191">проверка подлинности с сопоставлением сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="c2d51-191">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="c2d51-192">Дополнительное программное обеспечение для интерфейсных серверов сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="c2d51-192">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="c2d51-193">На интерфейсных серверах сохраняемого чата должен работать компонент Windows Server, MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c2d51-193">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="c2d51-194">Для получения сведений о включении MSMQ [щелкните здесь.](https://technet.microsoft.com/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="c2d51-194">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="c2d51-195">Дополнительное программное обеспечение для пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="c2d51-195">Additional Software for Edge Servers</span></span>

<span data-ttu-id="c2d51-196">Для пограничных серверов требуется следующее программное обеспечение:</span><span class="sxs-lookup"><span data-stu-id="c2d51-196">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="c2d51-197">На каждом сервере, на котором работает Lync Server 2013, должна быть установлена правильная версия Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c2d51-197">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="c2d51-198">Дополнительные сведения см. в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="c2d51-198">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="c2d51-199">Для Lync Server требуется Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="c2d51-199">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="c2d51-200">Для Lync Server 2013, установленного в Windows Server 2008 R2, перед установкой Lync Server 2013 необходимо вручную установить выпуск 64 – bit для Microsoft .NET Framework 4,5 на сервере.</span><span class="sxs-lookup"><span data-stu-id="c2d51-200">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="c2d51-201">Чтобы установить его вручную, скачайте Microsoft .NET 4,5 Framework из центра загрузки Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="c2d51-201">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="c2d51-202">**Windows Identity Foundation** в Lync Server 2013 требует установки Windows Identity Foundation для поддержки сценариев проверки подлинности сервера и сервера.</span><span class="sxs-lookup"><span data-stu-id="c2d51-202">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="c2d51-203">Windows Server 2008 R2 и Windows Server 2012 требуют различных процедур установки Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="c2d51-203">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="c2d51-204">Выберите серверную операционную систему из следующего списка:</span><span class="sxs-lookup"><span data-stu-id="c2d51-204">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="c2d51-205">Windows Server 2008 R2 для Windows Server 2008 R2 убедитесь, что она уже установлена на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="c2d51-205">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="c2d51-206">Для этого откройте раздел **Установка и удаление программ**, **Просмотрите установленные обновления**и найдите в разделе **Windows** **Идентификация Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="c2d51-206">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="c2d51-207">Подробные сведения об установке Windows Identity Foundation можно найти в разделе [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="c2d51-207">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="c2d51-208">Windows Server 2012 для Windows Server 2012 вы используете **Диспетчер серверов** для установки Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="c2d51-208">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="c2d51-209">В **мастере добавления ролей и компонентов**диспетчера серверов выберите **компоненты**.</span><span class="sxs-lookup"><span data-stu-id="c2d51-209">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="c2d51-210">В списке выберите **Windows Identity Foundation 3,5** .</span><span class="sxs-lookup"><span data-stu-id="c2d51-210">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="c2d51-211">Нажмите кнопку **Далее**, а затем — **установить**.</span><span class="sxs-lookup"><span data-stu-id="c2d51-211">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="c2d51-212">Не устанавливайте многоуровневые поставщики услуг на серверах-посредниках</span><span class="sxs-lookup"><span data-stu-id="c2d51-212">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="c2d51-213">Не устанавливайте клиентское программное обеспечение сервера Microsoft Internet Security and Acceleration (ISA) или любое другое программное обеспечение (LSP) на всех серверах переднего плана или отдельных серверах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="c2d51-213">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="c2d51-214">Установка этого ПО может привести к снижению скорости передачи трафика на сервере-посреднике.</span><span class="sxs-lookup"><span data-stu-id="c2d51-214">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2d51-215">См. также</span><span class="sxs-lookup"><span data-stu-id="c2d51-215">See Also</span></span>


[<span data-ttu-id="c2d51-216">Требования к программному обеспечению для средств администрирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2d51-216">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

