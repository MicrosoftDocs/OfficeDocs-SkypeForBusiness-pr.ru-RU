---
title: 'Lync Server 2013: Конфигурация IIS'
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
ms.openlocfilehash: 65d9d4f61fabdca7a3f9cb4808efe952ec7ce3b2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="0fa7a-102">Конфигурация IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fa7a-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fa7a-103">_**Последнее изменение темы:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="0fa7a-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="0fa7a-104">Для успешного выполнения этой процедуры вам необходимо выполнить вход на сервер как минимум с учетной записью локального администратора и пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="0fa7a-105">Перед настройкой и установкой сервера переднего плана для Lync Server 2013, Standard Edition или первого сервера переднего плана в пуле устанавливается и настраивается роль сервера и веб-службы для служб IIS.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="0fa7a-106">Если в Организации требуется, чтобы службы IIS и все веб-службы настроились на диске, отличном от системного диска, можно изменить путь к папке установки для файлов Lync Server 2013 в диалоговом окне программы установки при первоначальной установке Lync Server 2013 Средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="0fa7a-107">Средства администрирования устанавливаются перед установкой служб IIS.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="0fa7a-108">Если вы устанавливаете файлы установки по этому пути, включая OCSCore. msi, остальные файлы Lync Server 2013 будут развернуты на этом диске.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="0fa7a-109">Сведения о дтаилс можно найти в <A href="lync-server-2013-install-lync-server-administrative-tools.md">статье Установка средств администрирования Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="0fa7a-110">Сведения о том, как переместить INETPUB, развернутый диспетчером Windows Server при установке IIS, <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>можно узнать в разделе.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="0fa7a-111">В следующей таблице перечислены требуемые службы роли IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="0fa7a-112">Службы ролей IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="0fa7a-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0fa7a-113">Название роли</span><span class="sxs-lookup"><span data-stu-id="0fa7a-113">Role Heading</span></span></th>
<th><span data-ttu-id="0fa7a-114">Служба роли</span><span class="sxs-lookup"><span data-stu-id="0fa7a-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-115">Общие установленные функции HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-116">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="0fa7a-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-117">Общие установленные функции HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-118">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0fa7a-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-119">Общие установленные функции HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-120">Ошибки HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-121">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="0fa7a-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0fa7a-122">ASP.NET</span></span></p>
<p><span data-ttu-id="0fa7a-123">Для Windows Server 2012 также требуется ASP. NET 4.5.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-124">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="0fa7a-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-125">Расширяемость .NET</span><span class="sxs-lookup"><span data-stu-id="0fa7a-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-126">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="0fa7a-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-127">Расширения Internet Server API (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="0fa7a-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-128">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="0fa7a-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-129">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="0fa7a-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-130">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="0fa7a-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-131">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-132">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="0fa7a-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-133">Средства ведения журналов</span><span class="sxs-lookup"><span data-stu-id="0fa7a-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-134">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="0fa7a-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-135">Образца</span><span class="sxs-lookup"><span data-stu-id="0fa7a-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-136">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0fa7a-136">Security</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-137">Анонимная проверка подлинности (установлена и включена по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0fa7a-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-138">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0fa7a-138">Security</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-139">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="0fa7a-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-140">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0fa7a-140">Security</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-141">Проверка подлинности с сопоставлением сертификатов клиентов</span><span class="sxs-lookup"><span data-stu-id="0fa7a-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-142">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0fa7a-142">Security</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-143">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="0fa7a-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-144">Производительность</span><span class="sxs-lookup"><span data-stu-id="0fa7a-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-145">Сжатие статического содержимого</span><span class="sxs-lookup"><span data-stu-id="0fa7a-145">Static content compression</span></span></p>
<p><span data-ttu-id="0fa7a-146">Сжатие динамического содержимого</span><span class="sxs-lookup"><span data-stu-id="0fa7a-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-147">Средства управления</span><span class="sxs-lookup"><span data-stu-id="0fa7a-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-148">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="0fa7a-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-149">Средства управления</span><span class="sxs-lookup"><span data-stu-id="0fa7a-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-150">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="0fa7a-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0fa7a-151">В операционной системе Windows Server 2008 R2 с пакетом обновления 1 (SP1) для Windows Server R2 можно использовать Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="0fa7a-152">Сначала нужно импортировать модуль ServerManager, а затем установить роль и службы роли IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="0fa7a-153">Анонимная проверка подлинности устанавливается по умолчанию при установке роли сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="0fa7a-154">Вы можете управлять анонимной проверкой подлинности после установки служб IIS.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="0fa7a-155">Дополнительные сведения см. в <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>разделе "Включение анонимной проверки подлинности (IIS 7)".</span><span class="sxs-lookup"><span data-stu-id="0fa7a-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="0fa7a-156">В следующей таблице указаны обязательные службы ролей IIS 8,0 и IIS 8,5 для Windows Server 2012 и Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="0fa7a-157">Для Windows Server 2012 и Windows Server 2012 R2 командлет Add $ WindowsFeature заменен командлетом Install/WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="0fa7a-158">Дополнительные сведения см. в разделе <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install $ WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-158">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="0fa7a-159">Службы ролей IIS 8,0 и IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="0fa7a-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0fa7a-160">Название роли</span><span class="sxs-lookup"><span data-stu-id="0fa7a-160">Role Heading</span></span></th>
<th><span data-ttu-id="0fa7a-161">Служба роли</span><span class="sxs-lookup"><span data-stu-id="0fa7a-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-162">Веб-сервер (IIS)</span><span class="sxs-lookup"><span data-stu-id="0fa7a-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-163">Веб-сервер</span><span class="sxs-lookup"><span data-stu-id="0fa7a-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-164">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-165">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0fa7a-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-166">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-167">Просмотр каталогов</span><span class="sxs-lookup"><span data-stu-id="0fa7a-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-168">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-169">ошибки HTTP;</span><span class="sxs-lookup"><span data-stu-id="0fa7a-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-170">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-171">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="0fa7a-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-172">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-173">Перенаправление HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-174">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="0fa7a-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-175">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-176">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="0fa7a-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-177">Средства ведения журнала</span><span class="sxs-lookup"><span data-stu-id="0fa7a-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-178">Проверка работоспособности и диагностика</span><span class="sxs-lookup"><span data-stu-id="0fa7a-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-179">Монитор запросов</span><span class="sxs-lookup"><span data-stu-id="0fa7a-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-180">Проверка работоспособности и диагностика</span><span class="sxs-lookup"><span data-stu-id="0fa7a-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-181">Образца</span><span class="sxs-lookup"><span data-stu-id="0fa7a-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-182">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0fa7a-182">Security</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-183">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="0fa7a-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-184">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0fa7a-184">Security</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-185">Обычная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="0fa7a-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-186">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0fa7a-186">Security</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-187">проверка подлинности с сопоставлением сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-188">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0fa7a-188">Security</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-189">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="0fa7a-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-190">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="0fa7a-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-191">Расширяемость .NET 3,5</span><span class="sxs-lookup"><span data-stu-id="0fa7a-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-192">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="0fa7a-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-193">Расширяемость .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="0fa7a-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-194">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="0fa7a-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="0fa7a-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-196">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="0fa7a-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="0fa7a-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-198">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="0fa7a-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-199">Расширения ISAPI</span><span class="sxs-lookup"><span data-stu-id="0fa7a-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-200">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="0fa7a-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-201">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="0fa7a-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-202">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="0fa7a-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-203">Компоненты на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="0fa7a-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-204">Средства управления</span><span class="sxs-lookup"><span data-stu-id="0fa7a-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-205">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="0fa7a-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-206">Средства управления</span><span class="sxs-lookup"><span data-stu-id="0fa7a-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-207">Совместимость метабазы IIS 6</span><span class="sxs-lookup"><span data-stu-id="0fa7a-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-208">Средства управления</span><span class="sxs-lookup"><span data-stu-id="0fa7a-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-209">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="0fa7a-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-210">Функции .NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="0fa7a-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-211">.NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="0fa7a-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-212">Функции .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="0fa7a-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="0fa7a-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-214">Функции .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="0fa7a-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="0fa7a-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-216">Функции .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="0fa7a-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-217">Активация по протоколу HTTP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-218">Функции .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="0fa7a-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-219">Общий доступ к портам TCP</span><span class="sxs-lookup"><span data-stu-id="0fa7a-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-220">Фоновая интеллектуальная служба передачи</span><span class="sxs-lookup"><span data-stu-id="0fa7a-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-221">Серверные расширения IIS</span><span class="sxs-lookup"><span data-stu-id="0fa7a-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-222">Службы рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="0fa7a-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-223">Службы рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="0fa7a-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="0fa7a-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="0fa7a-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-226">Пользовательские интерфейсы и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="0fa7a-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-227">Графические средства управления и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="0fa7a-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-228">Пользовательские интерфейсы и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="0fa7a-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-229">Возможности рабочего стола</span><span class="sxs-lookup"><span data-stu-id="0fa7a-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-230">Пользовательские интерфейсы и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="0fa7a-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-231">Графическая консоль сервера</span><span class="sxs-lookup"><span data-stu-id="0fa7a-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-232">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="0fa7a-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="0fa7a-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fa7a-234">Служба активации процессов Windows</span><span class="sxs-lookup"><span data-stu-id="0fa7a-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-235">Модель процесса</span><span class="sxs-lookup"><span data-stu-id="0fa7a-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fa7a-236">Служба активации процессов Windows</span><span class="sxs-lookup"><span data-stu-id="0fa7a-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="0fa7a-237">API конфигурации</span><span class="sxs-lookup"><span data-stu-id="0fa7a-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0fa7a-238">В Windows Server 2012 и Windows Server 2012 R2 для установки требований к службам IIS можно использовать Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="0fa7a-239">С помощью модуля ServerManager в Windows PowerShell 3,0 введите:</span><span class="sxs-lookup"><span data-stu-id="0fa7a-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="0fa7a-240">Новый элемент с Windows Server 2012 — это параметр – source, определяющий, где можно найти исходный носитель Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="0fa7a-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="0fa7a-241">Носитель можно определить как DVD-дисковод (например, Д:\саурцес\сксс) или в сетевую папку, в которую были скопированы файлы мультимедиа (например, \\fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="0fa7a-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0fa7a-242">См. также</span><span class="sxs-lookup"><span data-stu-id="0fa7a-242">See Also</span></span>


[<span data-ttu-id="0fa7a-243">Требования к службам IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fa7a-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

