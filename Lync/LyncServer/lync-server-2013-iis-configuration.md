---
title: 'Lync Server 2013: Конфигурация IIS'
description: 'Lync Server 2013: Конфигурация IIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901aca7bf5ff8824b54e93754569a6ef5defc10e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554875"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="a7e14-103">Конфигурация IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7e14-103">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7e14-104">_**Последнее изменение темы:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="a7e14-104">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="a7e14-105">Для успешного выполнения этой процедуры вам необходимо выполнить вход на сервер как минимум с учетной записью локального администратора и пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="a7e14-105">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="a7e14-106">Перед настройкой и установкой сервера переднего плана для Lync Server 2013, Standard Edition или первого сервера переднего плана в пуле устанавливается и настраивается роль сервера и веб-службы для служб IIS.</span><span class="sxs-lookup"><span data-stu-id="a7e14-106">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="a7e14-107">Если в Организации требуется, чтобы службы IIS и все веб-службы настроились на диске, отличном от системного диска, можно изменить путь к папке установки для файлов Lync Server 2013 в диалоговом окне программы установки при первоначальной установке средств администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7e14-107">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="a7e14-108">Средства администрирования устанавливаются перед установкой служб IIS.</span><span class="sxs-lookup"><span data-stu-id="a7e14-108">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="a7e14-109">Если вы устанавливаете файлы установки по указанному пути, в том числе OCSCore.msi, остальные файлы Lync Server 2013 будут развернуты на этом диске.</span><span class="sxs-lookup"><span data-stu-id="a7e14-109">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="a7e14-110">Сведения о дтаилс можно найти в <A href="lync-server-2013-install-lync-server-administrative-tools.md">статье Установка средств администрирования Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a7e14-110">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="a7e14-111">Сведения о том, как переместить INETPUB, развернутый диспетчером Windows Server при установке IIS, можно узнать в разделе <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="a7e14-111">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="a7e14-112">В следующей таблице перечислены требуемые службы роли IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="a7e14-112">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="a7e14-113">Службы ролей IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="a7e14-113">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7e14-114">Название роли</span><span class="sxs-lookup"><span data-stu-id="a7e14-114">Role Heading</span></span></th>
<th><span data-ttu-id="a7e14-115">Служба роли</span><span class="sxs-lookup"><span data-stu-id="a7e14-115">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-116">Общие установленные функции HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-116">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="a7e14-117">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="a7e14-117">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-118">Общие установленные функции HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-118">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="a7e14-119">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a7e14-119">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-120">Общие установленные функции HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-120">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="a7e14-121">Ошибки HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-121">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-122">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="a7e14-122">Application development</span></span></p></td>
<td><p><span data-ttu-id="a7e14-123">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a7e14-123">ASP.NET</span></span></p>
<p><span data-ttu-id="a7e14-124">Для Windows Server 2012 также требуется ASP. NET 4.5.</span><span class="sxs-lookup"><span data-stu-id="a7e14-124">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-125">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="a7e14-125">Application development</span></span></p></td>
<td><p><span data-ttu-id="a7e14-126">Расширяемость .NET</span><span class="sxs-lookup"><span data-stu-id="a7e14-126">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-127">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="a7e14-127">Application development</span></span></p></td>
<td><p><span data-ttu-id="a7e14-128">Расширения Internet Server API (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="a7e14-128">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-129">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="a7e14-129">Application development</span></span></p></td>
<td><p><span data-ttu-id="a7e14-130">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="a7e14-130">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-131">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="a7e14-131">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a7e14-132">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-132">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-133">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="a7e14-133">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a7e14-134">Средства ведения журналов</span><span class="sxs-lookup"><span data-stu-id="a7e14-134">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-135">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="a7e14-135">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a7e14-136">Образца</span><span class="sxs-lookup"><span data-stu-id="a7e14-136">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-137">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a7e14-137">Security</span></span></p></td>
<td><p><span data-ttu-id="a7e14-138">Анонимная проверка подлинности (установлена и включена по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a7e14-138">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-139">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a7e14-139">Security</span></span></p></td>
<td><p><span data-ttu-id="a7e14-140">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="a7e14-140">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-141">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a7e14-141">Security</span></span></p></td>
<td><p><span data-ttu-id="a7e14-142">Проверка подлинности с сопоставлением сертификатов клиентов</span><span class="sxs-lookup"><span data-stu-id="a7e14-142">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-143">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a7e14-143">Security</span></span></p></td>
<td><p><span data-ttu-id="a7e14-144">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="a7e14-144">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-145">Производительность</span><span class="sxs-lookup"><span data-stu-id="a7e14-145">Performance</span></span></p></td>
<td><p><span data-ttu-id="a7e14-146">Сжатие статического содержимого</span><span class="sxs-lookup"><span data-stu-id="a7e14-146">Static content compression</span></span></p>
<p><span data-ttu-id="a7e14-147">Сжатие динамического содержимого</span><span class="sxs-lookup"><span data-stu-id="a7e14-147">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-148">Средства управления</span><span class="sxs-lookup"><span data-stu-id="a7e14-148">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="a7e14-149">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="a7e14-149">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-150">Средства управления</span><span class="sxs-lookup"><span data-stu-id="a7e14-150">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="a7e14-151">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="a7e14-151">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a7e14-152">В операционной системе Windows Server 2008 R2 с пакетом обновления 1 (SP1) для Windows Server R2 можно использовать Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="a7e14-152">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="a7e14-153">Сначала нужно импортировать модуль ServerManager, а затем установить роль и службы роли IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="a7e14-153">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="a7e14-154">Анонимная проверка подлинности устанавливается по умолчанию при установке роли сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="a7e14-154">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="a7e14-155">Вы можете управлять анонимной проверкой подлинности после установки служб IIS.</span><span class="sxs-lookup"><span data-stu-id="a7e14-155">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="a7e14-156">Дополнительные сведения см. в разделе "Включение анонимной проверки подлинности (IIS 7)" <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .</span><span class="sxs-lookup"><span data-stu-id="a7e14-156">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="a7e14-157">В следующей таблице указаны обязательные службы ролей IIS 8,0 и IIS 8,5 для Windows Server 2012 и Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="a7e14-157">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="a7e14-158">Для Windows Server 2012 и Windows Server 2012 R2 командлет Add-WindowsFeature был заменен командлетом Install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="a7e14-158">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="a7e14-159">Дополнительные сведения см. в разделе <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install $ WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="a7e14-159">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="a7e14-160">Службы ролей IIS 8,0 и IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="a7e14-160">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7e14-161">Название роли</span><span class="sxs-lookup"><span data-stu-id="a7e14-161">Role Heading</span></span></th>
<th><span data-ttu-id="a7e14-162">Служба роли</span><span class="sxs-lookup"><span data-stu-id="a7e14-162">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-163">Веб-сервер (IIS)</span><span class="sxs-lookup"><span data-stu-id="a7e14-163">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="a7e14-164">Веб-сервер</span><span class="sxs-lookup"><span data-stu-id="a7e14-164">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-165">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-165">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="a7e14-166">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a7e14-166">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-167">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-167">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="a7e14-168">Просмотр каталогов</span><span class="sxs-lookup"><span data-stu-id="a7e14-168">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-169">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-169">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="a7e14-170">ошибки HTTP;</span><span class="sxs-lookup"><span data-stu-id="a7e14-170">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-171">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-171">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="a7e14-172">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="a7e14-172">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-173">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-173">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="a7e14-174">Перенаправление HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-174">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-175">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="a7e14-175">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a7e14-176">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-176">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-177">Проверка работоспособности и диагностика</span><span class="sxs-lookup"><span data-stu-id="a7e14-177">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a7e14-178">Средства ведения журнала</span><span class="sxs-lookup"><span data-stu-id="a7e14-178">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-179">Проверка работоспособности и диагностика</span><span class="sxs-lookup"><span data-stu-id="a7e14-179">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a7e14-180">Монитор запросов</span><span class="sxs-lookup"><span data-stu-id="a7e14-180">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-181">Проверка работоспособности и диагностика</span><span class="sxs-lookup"><span data-stu-id="a7e14-181">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a7e14-182">Образца</span><span class="sxs-lookup"><span data-stu-id="a7e14-182">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-183">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a7e14-183">Security</span></span></p></td>
<td><p><span data-ttu-id="a7e14-184">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="a7e14-184">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-185">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a7e14-185">Security</span></span></p></td>
<td><p><span data-ttu-id="a7e14-186">Обычная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="a7e14-186">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-187">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a7e14-187">Security</span></span></p></td>
<td><p><span data-ttu-id="a7e14-188">проверка подлинности с сопоставлением сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="a7e14-188">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-189">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a7e14-189">Security</span></span></p></td>
<td><p><span data-ttu-id="a7e14-190">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="a7e14-190">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-191">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="a7e14-191">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a7e14-192">Расширяемость .NET 3,5</span><span class="sxs-lookup"><span data-stu-id="a7e14-192">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-193">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="a7e14-193">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a7e14-194">Расширяемость .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="a7e14-194">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-195">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="a7e14-195">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a7e14-196">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="a7e14-196">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-197">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="a7e14-197">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a7e14-198">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="a7e14-198">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-199">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="a7e14-199">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a7e14-200">Расширения ISAPI</span><span class="sxs-lookup"><span data-stu-id="a7e14-200">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-201">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="a7e14-201">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a7e14-202">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="a7e14-202">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-203">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="a7e14-203">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a7e14-204">Компоненты на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="a7e14-204">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-205">Средства управления</span><span class="sxs-lookup"><span data-stu-id="a7e14-205">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="a7e14-206">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="a7e14-206">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-207">Средства управления</span><span class="sxs-lookup"><span data-stu-id="a7e14-207">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="a7e14-208">Совместимость метабазы IIS 6</span><span class="sxs-lookup"><span data-stu-id="a7e14-208">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-209">Средства управления</span><span class="sxs-lookup"><span data-stu-id="a7e14-209">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="a7e14-210">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="a7e14-210">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-211">Функции .NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="a7e14-211">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="a7e14-212">.NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="a7e14-212">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-213">Функции .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="a7e14-213">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="a7e14-214">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="a7e14-214">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-215">Функции .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="a7e14-215">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="a7e14-216">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="a7e14-216">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-217">Функции .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="a7e14-217">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="a7e14-218">Активация по протоколу HTTP</span><span class="sxs-lookup"><span data-stu-id="a7e14-218">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-219">Функции .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="a7e14-219">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="a7e14-220">Общий доступ к портам TCP</span><span class="sxs-lookup"><span data-stu-id="a7e14-220">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-221">Фоновая интеллектуальная служба передачи</span><span class="sxs-lookup"><span data-stu-id="a7e14-221">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="a7e14-222">Серверные расширения IIS</span><span class="sxs-lookup"><span data-stu-id="a7e14-222">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-223">Службы рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="a7e14-223">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="a7e14-224">Службы рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="a7e14-224">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="a7e14-225">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="a7e14-226">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="a7e14-226">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-227">Пользовательские интерфейсы и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="a7e14-227">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="a7e14-228">Графические средства управления и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="a7e14-228">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-229">Пользовательские интерфейсы и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="a7e14-229">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="a7e14-230">Возможности рабочего стола</span><span class="sxs-lookup"><span data-stu-id="a7e14-230">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-231">Пользовательские интерфейсы и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="a7e14-231">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="a7e14-232">Графическая консоль сервера</span><span class="sxs-lookup"><span data-stu-id="a7e14-232">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="a7e14-233">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="a7e14-234">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="a7e14-234">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e14-235">Служба активации процессов Windows</span><span class="sxs-lookup"><span data-stu-id="a7e14-235">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="a7e14-236">Модель процесса</span><span class="sxs-lookup"><span data-stu-id="a7e14-236">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e14-237">Служба активации процессов Windows</span><span class="sxs-lookup"><span data-stu-id="a7e14-237">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="a7e14-238">API конфигурации</span><span class="sxs-lookup"><span data-stu-id="a7e14-238">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a7e14-239">В Windows Server 2012 и Windows Server 2012 R2 для установки требований к службам IIS можно использовать Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="a7e14-239">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="a7e14-240">С помощью модуля ServerManager в Windows PowerShell 3,0 введите:</span><span class="sxs-lookup"><span data-stu-id="a7e14-240">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="a7e14-241">Новый элемент с Windows Server 2012 — это параметр – source, определяющий, где можно найти исходный носитель Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="a7e14-241">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="a7e14-242">Носитель можно определить как DVD-дисковод (например, Д:\саурцес\сксс) или в сетевую папку, в которую были скопированы файлы мультимедиа (например, \\ fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="a7e14-242">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7e14-243">См. также</span><span class="sxs-lookup"><span data-stu-id="a7e14-243">See Also</span></span>


[<span data-ttu-id="a7e14-244">Требования к службам IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7e14-244">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

