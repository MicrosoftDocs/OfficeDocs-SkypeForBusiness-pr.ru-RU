---
title: 'Lync Server 2013: конфигурация IIS'
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
ms.openlocfilehash: 0cb8fe023d872ff19e29beb329488304048895b2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="f2911-102">Конфигурация IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2911-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2911-103">_**Тема последнего изменения:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="f2911-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="f2911-104">Для успешного выполнения этой процедуры необходимо войти на сервер с минимальным уровнем прав локального администратора и пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="f2911-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="f2911-105">Перед настройкой и установкой сервера переднего плана для Lync Server 2013, Standard Edition или первого сервера переднего плана в пуле вы устанавливаете и настраиваете роль сервера и веб-службы для служб IIS.</span><span class="sxs-lookup"><span data-stu-id="f2911-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="f2911-106">Если в вашей организации требуется найти IIS и все веб-службы на диске, отличном от системного, вы можете изменить путь к папке установки для файлов Lync Server 2013 в диалоговом окне настройки при первоначальной установке Lync Server 2013 Средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="f2911-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="f2911-107">Перед установкой IIS необходимо установить средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="f2911-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="f2911-108">Если вы установили файлы установки по этому пути, включая Окскоре. msi, остальные файлы Lync Server 2013 будут развернуты и на этом диске.</span><span class="sxs-lookup"><span data-stu-id="f2911-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="f2911-109">Дтаилс можно найти в разделе <A href="lync-server-2013-install-lync-server-administrative-tools.md">Установка средств администрирования Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f2911-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="f2911-110">Сведения о том, как переместить ИНЕТПУБ, развернутый диспетчером Windows Server Manager при установке IIS <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>, можно найти в разделе.</span><span class="sxs-lookup"><span data-stu-id="f2911-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="f2911-111">В приведенной ниже таблице указаны необходимые службы ролей IIS 7,5.</span><span class="sxs-lookup"><span data-stu-id="f2911-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="f2911-112">Службы ролей IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="f2911-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2911-113">Заголовок роли</span><span class="sxs-lookup"><span data-stu-id="f2911-113">Role Heading</span></span></th>
<th><span data-ttu-id="f2911-114">Служба ролей</span><span class="sxs-lookup"><span data-stu-id="f2911-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2911-115">Стандартные компоненты HTTP установлены</span><span class="sxs-lookup"><span data-stu-id="f2911-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="f2911-116">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="f2911-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-117">Стандартные компоненты HTTP установлены</span><span class="sxs-lookup"><span data-stu-id="f2911-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="f2911-118">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f2911-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-119">Стандартные компоненты HTTP установлены</span><span class="sxs-lookup"><span data-stu-id="f2911-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="f2911-120">Ошибки HTTP</span><span class="sxs-lookup"><span data-stu-id="f2911-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-121">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="f2911-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="f2911-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2911-122">ASP.NET</span></span></p>
<p><span data-ttu-id="f2911-123">Для Windows Server 2012 также требуется ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="f2911-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-124">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="f2911-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="f2911-125">Расширяемость .NET</span><span class="sxs-lookup"><span data-stu-id="f2911-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-126">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="f2911-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="f2911-127">Расширения ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="f2911-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-128">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="f2911-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="f2911-129">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="f2911-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-130">Исправность и диагностика</span><span class="sxs-lookup"><span data-stu-id="f2911-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f2911-131">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="f2911-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-132">Исправность и диагностика</span><span class="sxs-lookup"><span data-stu-id="f2911-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f2911-133">Средства ведения журнала</span><span class="sxs-lookup"><span data-stu-id="f2911-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-134">Исправность и диагностика</span><span class="sxs-lookup"><span data-stu-id="f2911-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f2911-135">Трассировка</span><span class="sxs-lookup"><span data-stu-id="f2911-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-136">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f2911-136">Security</span></span></p></td>
<td><p><span data-ttu-id="f2911-137">Анонимная проверка подлинности (установлен и включен по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f2911-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-138">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f2911-138">Security</span></span></p></td>
<td><p><span data-ttu-id="f2911-139">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="f2911-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-140">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f2911-140">Security</span></span></p></td>
<td><p><span data-ttu-id="f2911-141">Проверка подлинности сопоставления сертификатов клиентов</span><span class="sxs-lookup"><span data-stu-id="f2911-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-142">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f2911-142">Security</span></span></p></td>
<td><p><span data-ttu-id="f2911-143">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="f2911-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-144">Производительность</span><span class="sxs-lookup"><span data-stu-id="f2911-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="f2911-145">Сжатие статического содержимого</span><span class="sxs-lookup"><span data-stu-id="f2911-145">Static content compression</span></span></p>
<p><span data-ttu-id="f2911-146">Сжатие динамического содержимого</span><span class="sxs-lookup"><span data-stu-id="f2911-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-147">Средства управления</span><span class="sxs-lookup"><span data-stu-id="f2911-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f2911-148">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="f2911-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-149">Средства управления</span><span class="sxs-lookup"><span data-stu-id="f2911-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f2911-150">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="f2911-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2911-151">В операционной системе Windows Server 2008 R2 с пакетом обновления 1 (SP1) можно использовать Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="f2911-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="f2911-152">Сначала нужно импортировать модуль ServerManager, а затем установить роль сервера IIS 7,5 и службы ролей.</span><span class="sxs-lookup"><span data-stu-id="f2911-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="f2911-153">Анонимная проверка подлинности устанавливается по умолчанию с ролью сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="f2911-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="f2911-154">Вы можете управлять анонимной проверкой подлинности после установки IIS.</span><span class="sxs-lookup"><span data-stu-id="f2911-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="f2911-155">Дополнительные сведения можно найти в <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>разделе "включить анонимную проверку подлинности (IIS 7)".</span><span class="sxs-lookup"><span data-stu-id="f2911-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="f2911-156">В таблице ниже указаны обязательные службы ролей IIS 8,0 и IIS 8,5 для Windows Server 2012 и Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="f2911-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="f2911-157">Для Windows Server 2012 и Windows Server 2012 R2 командлет Add-WindowsFeature был заменен командлетом Install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="f2911-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="f2911-158">Подробности можно найти в разделе <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="f2911-158">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="f2911-159">Службы ролей IIS 8,0 и IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="f2911-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2911-160">Заголовок роли</span><span class="sxs-lookup"><span data-stu-id="f2911-160">Role Heading</span></span></th>
<th><span data-ttu-id="f2911-161">Служба ролей</span><span class="sxs-lookup"><span data-stu-id="f2911-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2911-162">Веб-сервер (IIS)</span><span class="sxs-lookup"><span data-stu-id="f2911-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="f2911-163">Веб-сервер</span><span class="sxs-lookup"><span data-stu-id="f2911-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-164">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="f2911-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f2911-165">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f2911-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-166">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="f2911-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f2911-167">Просмотр каталога</span><span class="sxs-lookup"><span data-stu-id="f2911-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-168">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="f2911-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f2911-169">Ошибки HTTP</span><span class="sxs-lookup"><span data-stu-id="f2911-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-170">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="f2911-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f2911-171">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="f2911-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-172">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="f2911-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f2911-173">Перенаправление HTTP</span><span class="sxs-lookup"><span data-stu-id="f2911-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-174">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="f2911-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f2911-175">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="f2911-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-176">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="f2911-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f2911-177">Средства ведения журналов</span><span class="sxs-lookup"><span data-stu-id="f2911-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-178">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="f2911-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f2911-179">Монитор запросов</span><span class="sxs-lookup"><span data-stu-id="f2911-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-180">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="f2911-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f2911-181">Трассировка</span><span class="sxs-lookup"><span data-stu-id="f2911-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-182">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f2911-182">Security</span></span></p></td>
<td><p><span data-ttu-id="f2911-183">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="f2911-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-184">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f2911-184">Security</span></span></p></td>
<td><p><span data-ttu-id="f2911-185">Обычная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f2911-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-186">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f2911-186">Security</span></span></p></td>
<td><p><span data-ttu-id="f2911-187">Проверка подлинности с сопоставлением сертификатов клиентов</span><span class="sxs-lookup"><span data-stu-id="f2911-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-188">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f2911-188">Security</span></span></p></td>
<td><p><span data-ttu-id="f2911-189">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="f2911-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-190">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="f2911-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f2911-191">Расширяемость .NET 3,5</span><span class="sxs-lookup"><span data-stu-id="f2911-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-192">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="f2911-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f2911-193">Расширяемость .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="f2911-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-194">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="f2911-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f2911-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="f2911-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-196">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="f2911-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f2911-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="f2911-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-198">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="f2911-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f2911-199">Расширения ISAPI</span><span class="sxs-lookup"><span data-stu-id="f2911-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-200">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="f2911-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f2911-201">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="f2911-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-202">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="f2911-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f2911-203">Включения на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="f2911-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-204">Средства управления</span><span class="sxs-lookup"><span data-stu-id="f2911-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f2911-205">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="f2911-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-206">Средства управления</span><span class="sxs-lookup"><span data-stu-id="f2911-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f2911-207">Совместимость метабазы IIS 6</span><span class="sxs-lookup"><span data-stu-id="f2911-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-208">Средства управления</span><span class="sxs-lookup"><span data-stu-id="f2911-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f2911-209">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="f2911-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-210">Возможности .NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f2911-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f2911-211">.NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f2911-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-212">Возможности .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f2911-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f2911-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="f2911-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-214">Возможности .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f2911-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f2911-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="f2911-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-216">Возможности .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f2911-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f2911-217">Активация HTTP</span><span class="sxs-lookup"><span data-stu-id="f2911-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-218">Возможности .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f2911-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f2911-219">Общий доступ к портам TCP</span><span class="sxs-lookup"><span data-stu-id="f2911-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-220">Фоновая интеллектуальная служба передачи</span><span class="sxs-lookup"><span data-stu-id="f2911-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="f2911-221">Серверные расширения IIS</span><span class="sxs-lookup"><span data-stu-id="f2911-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-222">Службы рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="f2911-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="f2911-223">Службы рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="f2911-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="f2911-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="f2911-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="f2911-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-226">Пользовательские интерфейсы и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="f2911-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="f2911-227">Графические средства управления и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="f2911-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-228">Пользовательские интерфейсы и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="f2911-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="f2911-229">Работа с рабочим столом</span><span class="sxs-lookup"><span data-stu-id="f2911-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-230">Пользовательские интерфейсы и инфраструктура</span><span class="sxs-lookup"><span data-stu-id="f2911-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="f2911-231">Графическая консоль сервера</span><span class="sxs-lookup"><span data-stu-id="f2911-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-232">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="f2911-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="f2911-233">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="f2911-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2911-234">Служба активации процессов Windows</span><span class="sxs-lookup"><span data-stu-id="f2911-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="f2911-235">Модель процесса</span><span class="sxs-lookup"><span data-stu-id="f2911-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2911-236">Служба активации процессов Windows</span><span class="sxs-lookup"><span data-stu-id="f2911-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="f2911-237">API конфигурации</span><span class="sxs-lookup"><span data-stu-id="f2911-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2911-238">В Windows Server 2012 и Windows Server 2012 R2 для установки требований к службам IIS можно использовать Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="f2911-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="f2911-239">С помощью модуля ServerManager в Windows PowerShell 3,0 введите:</span><span class="sxs-lookup"><span data-stu-id="f2911-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="f2911-240">Новая возможность в Windows Server 2012 — это параметр – source, который определяет, где можно найти исходный носитель Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="f2911-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="f2911-241">Этот носитель можно задать в качестве DVD-дисковода (например, Д:\саурцес\сксс) или сетевого общего доступа, в который были скопированы файлы мультимедиа (например, \\fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="f2911-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2911-242">См. также</span><span class="sxs-lookup"><span data-stu-id="f2911-242">See Also</span></span>


[<span data-ttu-id="f2911-243">Требования IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2911-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

