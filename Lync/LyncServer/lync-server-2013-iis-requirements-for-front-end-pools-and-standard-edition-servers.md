---
title: Требования к службам IIS для пулов переднего плана и серверов Standard Edition
description: Требования к службам IIS для пулов переднего плана и серверов Standard Edition.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f56452c7e47352333ac3ac5a51d649b0828a0ff9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573345"
---
# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="15585-103">Требования к службам IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15585-103">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15585-104">_**Последнее изменение темы:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="15585-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="15585-105">Для серверов Standard Edition и серверов переднего плана, а также директоров, программа установки Lync Server 2013 создает виртуальные каталоги в службах IIS в следующих целях:</span><span class="sxs-lookup"><span data-stu-id="15585-105">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="15585-106">Предоставление удаленным пользователям возможности загружать файлы из службы адресной книги</span><span class="sxs-lookup"><span data-stu-id="15585-106">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="15585-107">Предоставление клиентам возможности получать обновления</span><span class="sxs-lookup"><span data-stu-id="15585-107">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="15585-108">Предоставление возможности использовать конференц-связь</span><span class="sxs-lookup"><span data-stu-id="15585-108">To enable conferencing</span></span>

  - <span data-ttu-id="15585-109">Предоставление пользователям возможности загружать содержимое собраний</span><span class="sxs-lookup"><span data-stu-id="15585-109">To enable users to download meeting content</span></span>

  - <span data-ttu-id="15585-110">Предоставление пользователям возможности расширять группы рассылки</span><span class="sxs-lookup"><span data-stu-id="15585-110">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="15585-111">Предоставление возможности использовать конференц-связь по телефону</span><span class="sxs-lookup"><span data-stu-id="15585-111">To enable phone conferencing</span></span>

  - <span data-ttu-id="15585-112">Включение возможностей групп ответа</span><span class="sxs-lookup"><span data-stu-id="15585-112">To enable response group features</span></span>

<span data-ttu-id="15585-113">Кроме того, накопительный пакет обновления для Lync Server 2010: Ноябрь 2011 создает виртуальные каталоги в службах IIS в следующих целях:</span><span class="sxs-lookup"><span data-stu-id="15585-113">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="15585-114">На серверах переднего плана или серверах Standard Edition для поддержки функций мобильности, таких как обмен мгновенными сообщениями и присутствие, на мобильных устройствах</span><span class="sxs-lookup"><span data-stu-id="15585-114">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="15585-115">На серверах переднего плана или серверах Standard Edition и директорах, чтобы позволить мобильным устройствам автоматически обнаруживать мобильные ресурсы</span><span class="sxs-lookup"><span data-stu-id="15585-115">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="15585-116">Если вы развертываете мобильность, мы рекомендуем использовать службы IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="15585-116">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="15585-117">Программа установки службы Mobility Service Lync Server устанавливает некоторые флаги ASP.NET для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="15585-117">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="15585-118">Службы IIS 7.5 по умолчанию установлены в Windows Server 2008 R2, и установщик службы мобильности Mobility Service автоматически изменяет параметры ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="15585-118">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="15585-119">Если вы используете службы IIS 7.0 в Windows Server 2008, вам необходимо изменить эти параметры вручную.</span><span class="sxs-lookup"><span data-stu-id="15585-119">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="15585-120">Lync Server требует установки следующих модулей IIS:</span><span class="sxs-lookup"><span data-stu-id="15585-120">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="15585-121">Если в Организации требуется, чтобы службы IIS и все веб-службы настроились на диске, отличном от системного диска, можно изменить путь к расположению установки для файлов Lync Server в диалоговом окне программы установки.</span><span class="sxs-lookup"><span data-stu-id="15585-121">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="15585-122">Если вы устанавливаете файлы установки по указанному пути, в том числе OCSCore.msi, остальные файлы Lync Server будут развернуты и на этом диске.</span><span class="sxs-lookup"><span data-stu-id="15585-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="15585-123">Сведения о том, как переместить INETPUB, развернутый диспетчером Windows Server при установке IIS, можно узнать в разделе <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="15585-123">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="15585-124">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="15585-124">Static Content</span></span>

  - <span data-ttu-id="15585-125">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="15585-125">Default Document</span></span>

  - <span data-ttu-id="15585-126">ошибки HTTP;</span><span class="sxs-lookup"><span data-stu-id="15585-126">HTTP Errors</span></span>

  - <span data-ttu-id="15585-127">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="15585-127">ASP.NET</span></span>

  - <span data-ttu-id="15585-128">расширяемость .NET;</span><span class="sxs-lookup"><span data-stu-id="15585-128">.NET Extensibility</span></span>

  - <span data-ttu-id="15585-129">расширения ISAPI;</span><span class="sxs-lookup"><span data-stu-id="15585-129">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="15585-130">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="15585-130">ISAPI Filters</span></span>

  - <span data-ttu-id="15585-131">ведение журнала HTTP;</span><span class="sxs-lookup"><span data-stu-id="15585-131">HTTP Logging</span></span>

  - <span data-ttu-id="15585-132">средства ведения журнала;</span><span class="sxs-lookup"><span data-stu-id="15585-132">Logging Tools</span></span>

  - <span data-ttu-id="15585-133">Образца</span><span class="sxs-lookup"><span data-stu-id="15585-133">Tracing</span></span>

  - <span data-ttu-id="15585-134">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="15585-134">Windows Authentication</span></span>

  - <span data-ttu-id="15585-135">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="15585-135">Request Filtering</span></span>

  - <span data-ttu-id="15585-136">Сжатие статического содержимого</span><span class="sxs-lookup"><span data-stu-id="15585-136">Static Content Compression</span></span>

  - <span data-ttu-id="15585-137">Сжатие динамического содержимого</span><span class="sxs-lookup"><span data-stu-id="15585-137">Dynamic Content Compression</span></span>

  - <span data-ttu-id="15585-138">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="15585-138">IIS Management Console</span></span>

  - <span data-ttu-id="15585-139">Сценарии и средства управления IIS</span><span class="sxs-lookup"><span data-stu-id="15585-139">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="15585-140">Анонимная проверка подлинности (устанавливается по умолчанию при установке служб IIS)</span><span class="sxs-lookup"><span data-stu-id="15585-140">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="15585-141">Проверка подлинности с сопоставлением сертификата клиента</span><span class="sxs-lookup"><span data-stu-id="15585-141">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="15585-142">В следующей таблице приведены коды URI для виртуальных каталогов внутреннего доступа и ресурсы файловой системы, на которые они ссылаются.</span><span class="sxs-lookup"><span data-stu-id="15585-142">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="15585-143">Виртуальные каталоги для внутреннего доступа</span><span class="sxs-lookup"><span data-stu-id="15585-143">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15585-144">Компонент</span><span class="sxs-lookup"><span data-stu-id="15585-144">Feature</span></span></th>
<th><span data-ttu-id="15585-145">Код URI виртуального каталога</span><span class="sxs-lookup"><span data-stu-id="15585-145">Virtual directory URI</span></span></th>
<th><span data-ttu-id="15585-146">Ссылается на</span><span class="sxs-lookup"><span data-stu-id="15585-146">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15585-147">Сервер адресной книги</span><span class="sxs-lookup"><span data-stu-id="15585-147">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="15585-148">&lt;внутреннее полное доменное имя HTTPS:// &gt; /АБС/Инт/Хандлер</span><span class="sxs-lookup"><span data-stu-id="15585-148">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="15585-149">Расположение файлов загрузки сервера адресной книги для внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="15585-149">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15585-150">Служба автообнаружения</span><span class="sxs-lookup"><span data-stu-id="15585-150">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="15585-151">&lt;внутреннее полное доменное имя HTTPS:// &gt; /аутодисковер</span><span class="sxs-lookup"><span data-stu-id="15585-151">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="15585-152">Расположение службы автообнаружения Lync Server, в которой размещается ресурсы мобильной связи для внутренних пользователей мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="15585-152">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15585-153">Обновления клиента</span><span class="sxs-lookup"><span data-stu-id="15585-153">Client updates</span></span></p></td>
<td><p><span data-ttu-id="15585-154">&lt;внутреннее полное доменное имя http:// &gt; /аутаупдате/Инт</span><span class="sxs-lookup"><span data-stu-id="15585-154">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="15585-155">Расположение файлов обновлений для внутренних клиентов, использующих компьютеры.</span><span class="sxs-lookup"><span data-stu-id="15585-155">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15585-156">Дает</span><span class="sxs-lookup"><span data-stu-id="15585-156">Conf</span></span></p></td>
<td><p><span data-ttu-id="15585-157">&lt;внутреннее полное доменное имя http:// &gt; /конф/Инт</span><span class="sxs-lookup"><span data-stu-id="15585-157">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="15585-158">Расположение ресурсов конференц-связи для внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="15585-158">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15585-159">Обновления устройств</span><span class="sxs-lookup"><span data-stu-id="15585-159">Device updates</span></span></p></td>
<td><p><span data-ttu-id="15585-160">&lt;внутреннее полное доменное имя http:// &gt; /DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="15585-160">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="15585-161">Расположение файлов обновлений для внутренних устройств объединенных коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="15585-161">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15585-162">Назначить</span><span class="sxs-lookup"><span data-stu-id="15585-162">Meeting</span></span></p></td>
<td><p><span data-ttu-id="15585-163">&lt;внутреннее полное доменное имя http:// &gt; /ЕТК/плаце/Нулл</span><span class="sxs-lookup"><span data-stu-id="15585-163">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="15585-164">Location of meeting content for internal users.</span><span class="sxs-lookup"><span data-stu-id="15585-164">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15585-165">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="15585-165">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="15585-166">&lt;внутреннее полное доменное имя HTTPS:// &gt; /МККС</span><span class="sxs-lookup"><span data-stu-id="15585-166">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="15585-167">Расположение службы мобильности Mobility Service для внутренних пользователей мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="15585-167">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15585-168">Служба углубления в группы и веб-запросов адресной книги</span><span class="sxs-lookup"><span data-stu-id="15585-168">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="15585-169">&lt;внутреннее полное доменное имя http:// &gt; /граупекспансион/Инт/сервице.асмкс</span><span class="sxs-lookup"><span data-stu-id="15585-169">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="15585-170">Расположение веб-службы, предоставляющей функции углубления в группы для внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="15585-170">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="15585-171">Кроме того, размещена служба веб-запросов адресной книги, которая предоставляет глобальные сведения о списках адресов внутренним мобильным клиентам Lync для Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="15585-171">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15585-172">Телефонная конференц-связь</span><span class="sxs-lookup"><span data-stu-id="15585-172">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="15585-173">&lt;внутреннее полное доменное имя http:// &gt; /фонеконференЦинг/Инт</span><span class="sxs-lookup"><span data-stu-id="15585-173">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="15585-174">Расположение данных телефонной конференц-связи для внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="15585-174">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15585-175">Обновления устройств</span><span class="sxs-lookup"><span data-stu-id="15585-175">Device updates</span></span></p></td>
<td><p><span data-ttu-id="15585-176">&lt;внутреннее полное доменное имя http:// &gt; /рекуессандлер</span><span class="sxs-lookup"><span data-stu-id="15585-176">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="15585-177">Расположение обработчика запросов веб-службы обновления устройств, который позволяет внутренним устройствам объединенных коммуникаций отправлять журналы и проверять наличие обновлений.</span><span class="sxs-lookup"><span data-stu-id="15585-177">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15585-178">Приложение группы ответа</span><span class="sxs-lookup"><span data-stu-id="15585-178">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="15585-179">&lt;внутреннее полное доменное имя http:// &gt; /ргсконфиг</span><span class="sxs-lookup"><span data-stu-id="15585-179">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="15585-180">&lt;внутреннее полное доменное имя http:// &gt; /ргсклиентс</span><span class="sxs-lookup"><span data-stu-id="15585-180">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="15585-181">Location of Response Group Configuration Tool.</span><span class="sxs-lookup"><span data-stu-id="15585-181">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="15585-182">Для интерфейсных пулов в консолидированной конфигурации необходимо развернуть службы IIS, прежде чем добавлять серверы в пул.</span><span class="sxs-lookup"><span data-stu-id="15585-182">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="защиты" alt="security" /><span data-ttu-id="15585-184">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="15585-184">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="15585-185">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span><span class="sxs-lookup"><span data-stu-id="15585-185">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

