---
title: Требования IIS для пулов переднего плана и серверов Standard Edition
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
ms.openlocfilehash: c00ffe97b77f20107fc3351a678c71e28bbc6675
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="4eaf1-102">Требования IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4eaf1-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4eaf1-103">_**Тема последнего изменения:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="4eaf1-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="4eaf1-104">Для серверов Standard Edition и серверов, а также режиссеров и директоров, программа Lync Server 2013 создает виртуальные каталоги в службах IIS для следующих целей:</span><span class="sxs-lookup"><span data-stu-id="4eaf1-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="4eaf1-105">Предоставление пользователям возможности загружать файлы из службы адресной книги</span><span class="sxs-lookup"><span data-stu-id="4eaf1-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="4eaf1-106">Предоставление клиентам разрешения на получение обновлений</span><span class="sxs-lookup"><span data-stu-id="4eaf1-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="4eaf1-107">Включение конференций</span><span class="sxs-lookup"><span data-stu-id="4eaf1-107">To enable conferencing</span></span>

  - <span data-ttu-id="4eaf1-108">Предоставление пользователям возможности загружать содержимое собрания</span><span class="sxs-lookup"><span data-stu-id="4eaf1-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="4eaf1-109">Предоставление пользователям разрешения на развертывание групп рассылки</span><span class="sxs-lookup"><span data-stu-id="4eaf1-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="4eaf1-110">Включение телефонной конференции</span><span class="sxs-lookup"><span data-stu-id="4eaf1-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="4eaf1-111">Включение функций группы ответа</span><span class="sxs-lookup"><span data-stu-id="4eaf1-111">To enable response group features</span></span>

<span data-ttu-id="4eaf1-112">Кроме того, накопительный пакет обновления для Lync Server 2010: Ноябрь 2011 создает виртуальные каталоги в службах IIS для следующих целей:</span><span class="sxs-lookup"><span data-stu-id="4eaf1-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="4eaf1-113">На серверах переднего плана или стандартных серверах выпуска для поддержки мобильных функций, таких как обмен мгновенными сообщениями и присутствие, на мобильных устройствах</span><span class="sxs-lookup"><span data-stu-id="4eaf1-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="4eaf1-114">На серверах переднего плана или стандартных серверах и режиссерах, позволяющих мобильным устройствам автоматически определять мобильные ресурсы</span><span class="sxs-lookup"><span data-stu-id="4eaf1-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="4eaf1-115">При развертывании мобильных устройств рекомендуется использовать IIS 7,5.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="4eaf1-116">Установщик службы Lync Server Mobility Service устанавливает некоторые флаги ASP.NET для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="4eaf1-117">Службы IIS 7,5 установлены по умолчанию в Windows Server 2008 R2, и установщик службы Mobility Service автоматически изменяет параметры ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="4eaf1-118">Если вы используете IIS 7,0 в Windows Server 2008, вам потребуется вручную изменить эти параметры.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="4eaf1-119">Lync Server требует установки следующих модулей IIS:</span><span class="sxs-lookup"><span data-stu-id="4eaf1-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="4eaf1-120">Если в вашей организации требуется найти IIS и все веб-службы на диске, отличном от системного, вы можете изменить путь к папке установки для файлов Lync Server в диалоговом окне Настройка.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="4eaf1-121">Если вы установили файлы установки по этому пути, включая Окскоре. msi, остальные файлы сервера Lync будут развернуты и на этом диске.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="4eaf1-122">Сведения о том, как переместить ИНЕТПУБ, развернутый диспетчером Windows Server Manager при установке IIS <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>, можно найти в разделе.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="4eaf1-123">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="4eaf1-123">Static Content</span></span>

  - <span data-ttu-id="4eaf1-124">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4eaf1-124">Default Document</span></span>

  - <span data-ttu-id="4eaf1-125">Ошибки HTTP</span><span class="sxs-lookup"><span data-stu-id="4eaf1-125">HTTP Errors</span></span>

  - <span data-ttu-id="4eaf1-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="4eaf1-126">ASP.NET</span></span>

  - <span data-ttu-id="4eaf1-127">Расширяемость .NET</span><span class="sxs-lookup"><span data-stu-id="4eaf1-127">.NET Extensibility</span></span>

  - <span data-ttu-id="4eaf1-128">Расширения ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="4eaf1-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="4eaf1-129">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="4eaf1-129">ISAPI Filters</span></span>

  - <span data-ttu-id="4eaf1-130">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="4eaf1-130">HTTP Logging</span></span>

  - <span data-ttu-id="4eaf1-131">Средства ведения журналов</span><span class="sxs-lookup"><span data-stu-id="4eaf1-131">Logging Tools</span></span>

  - <span data-ttu-id="4eaf1-132">Трассировка</span><span class="sxs-lookup"><span data-stu-id="4eaf1-132">Tracing</span></span>

  - <span data-ttu-id="4eaf1-133">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="4eaf1-133">Windows Authentication</span></span>

  - <span data-ttu-id="4eaf1-134">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="4eaf1-134">Request Filtering</span></span>

  - <span data-ttu-id="4eaf1-135">Сжатие статического содержимого</span><span class="sxs-lookup"><span data-stu-id="4eaf1-135">Static Content Compression</span></span>

  - <span data-ttu-id="4eaf1-136">Сжатие динамического содержимого</span><span class="sxs-lookup"><span data-stu-id="4eaf1-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="4eaf1-137">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="4eaf1-137">IIS Management Console</span></span>

  - <span data-ttu-id="4eaf1-138">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="4eaf1-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="4eaf1-139">Анонимная проверка подлинности (устанавливается по умолчанию при установке IIS)</span><span class="sxs-lookup"><span data-stu-id="4eaf1-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="4eaf1-140">Проверка подлинности с сопоставлением сертификатов клиентов</span><span class="sxs-lookup"><span data-stu-id="4eaf1-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="4eaf1-141">В таблице ниже перечислены URI для виртуальных каталогов внутреннего доступа и ресурсов файловой системы, на которые они ссылаются.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="4eaf1-142">Виртуальные каталоги для внутреннего доступа</span><span class="sxs-lookup"><span data-stu-id="4eaf1-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4eaf1-143">Функция</span><span class="sxs-lookup"><span data-stu-id="4eaf1-143">Feature</span></span></th>
<th><span data-ttu-id="4eaf1-144">Универсальный код ресурса (URI) виртуального каталога</span><span class="sxs-lookup"><span data-stu-id="4eaf1-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="4eaf1-145">Ссылка на</span><span class="sxs-lookup"><span data-stu-id="4eaf1-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eaf1-146">адресной книги</span><span class="sxs-lookup"><span data-stu-id="4eaf1-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-147">Внутренняя&lt;доменная&gt;HTTPS:///АБС/Инт/Хандлер</span><span class="sxs-lookup"><span data-stu-id="4eaf1-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-148">Расположение файлов для скачивания внутренних пользователей на сервер адресной книги.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eaf1-149">Служба автообнаружения</span><span class="sxs-lookup"><span data-stu-id="4eaf1-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-150">Внутренняя&lt;доменная&gt;HTTPS:///аутодисковер</span><span class="sxs-lookup"><span data-stu-id="4eaf1-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-151">Расположение службы автообнаружения Lync Server, в которой находятся ресурсы для мобильных устройств, которые можно найти для внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eaf1-152">Обновления клиента</span><span class="sxs-lookup"><span data-stu-id="4eaf1-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-153">Внутренняя&lt;доменная&gt;http:///аутаупдате/Инт</span><span class="sxs-lookup"><span data-stu-id="4eaf1-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-154">Расположение файлов обновлений для внутренних клиентских компьютеров.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eaf1-155">CONF</span><span class="sxs-lookup"><span data-stu-id="4eaf1-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-156">Внутренняя&lt;доменная&gt;http:///конф/Инт</span><span class="sxs-lookup"><span data-stu-id="4eaf1-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-157">Расположение ресурсов конференций для внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eaf1-158">Обновления устройства</span><span class="sxs-lookup"><span data-stu-id="4eaf1-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-159">http://&lt;внутреннее доменное имя&gt;/DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="4eaf1-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-160">Расположение файлов обновления устройства единой системы обмена сообщениями (UC) для внутренних устройств UC.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eaf1-161">Зала</span><span class="sxs-lookup"><span data-stu-id="4eaf1-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-162">Внутренняя&lt;доменная&gt;http:///ЕТК/плаце/Нулл</span><span class="sxs-lookup"><span data-stu-id="4eaf1-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-163">Расположение содержимого собраний для внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eaf1-164">Служба Mobility Service</span><span class="sxs-lookup"><span data-stu-id="4eaf1-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-165">Внутренняя&lt;доменная&gt;HTTPS:///МККС</span><span class="sxs-lookup"><span data-stu-id="4eaf1-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-166">Расположение ресурсов службы Mobility Service для внутренних пользователей мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eaf1-167">Служба веб-запросов расширения групп и адресной книги</span><span class="sxs-lookup"><span data-stu-id="4eaf1-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-168">Внутренняя&lt;доменная&gt;http:///граупекспансион/Инт/сервице.асмкс</span><span class="sxs-lookup"><span data-stu-id="4eaf1-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-169">Расположение веб-службы, обеспечивающей расширение группы для внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="4eaf1-170">Кроме того, расположение службы веб-запросов адресной книги, предоставляющей глобальные сведения о списке адресов внутренним клиентам Lync Mobile Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eaf1-171">Телефонные конференции</span><span class="sxs-lookup"><span data-stu-id="4eaf1-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-172">Внутренняя&lt;доменная&gt;http:///фонеконференЦинг/Инт</span><span class="sxs-lookup"><span data-stu-id="4eaf1-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-173">Расположение данных телефонной конференции для внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eaf1-174">Обновления устройства</span><span class="sxs-lookup"><span data-stu-id="4eaf1-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-175">Внутренняя&lt;доменная&gt;http:///рекуессандлер</span><span class="sxs-lookup"><span data-stu-id="4eaf1-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-176">Расположение обработчика запросов веб-службы обновления устройства, который позволяет внутренним устройствам UC отправлять журналы и проверять наличие обновлений.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eaf1-177">"Группа ответа"</span><span class="sxs-lookup"><span data-stu-id="4eaf1-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-178">Внутренняя&lt;доменная&gt;http:///ргсконфиг</span><span class="sxs-lookup"><span data-stu-id="4eaf1-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="4eaf1-179">Внутренняя&lt;доменная&gt;http:///ргсклиентс</span><span class="sxs-lookup"><span data-stu-id="4eaf1-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="4eaf1-180">Расположение средства настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="4eaf1-181">Для пулов переднего плана в консолидированной конфигурации необходимо развернуть IIS, прежде чем можно будет добавить серверы в пул.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="разрешения" alt="security" /><span data-ttu-id="4eaf1-183">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="4eaf1-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4eaf1-184">Для назначения сертификата, используемого сервером веб-компонентов IIS, необходимо использовать оснастку администрирования IIS.</span><span class="sxs-lookup"><span data-stu-id="4eaf1-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

