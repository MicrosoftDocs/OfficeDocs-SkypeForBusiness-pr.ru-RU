---
title: Контрольный список развертывания Lync Server 2013 для веб-конференций
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5f845fd57846d7f9b58351d1cb77f3f1c0142ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="bda0d-102">Контрольный список развертывания для веб-конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bda0d-102">Deployment checklist for web conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bda0d-103">_**Тема последнего изменения:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="bda0d-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="bda0d-104">Как и при развертывании других компонентов Lync Server 2013, для развертывания веб-конференций требуется использование построителя топологии для создания и публикации топологии, которая включает Конференции.</span><span class="sxs-lookup"><span data-stu-id="bda0d-104">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="bda0d-105">Последовательность развертывания</span><span class="sxs-lookup"><span data-stu-id="bda0d-105">Deployment Sequence</span></span>

<span data-ttu-id="bda0d-106">Вы можете разворачивать конференции одновременно с развертыванием начальной топологии или после развертывания по крайней мере одного пула переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bda0d-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="bda0d-107">Процесс развертывания конференций</span><span class="sxs-lookup"><span data-stu-id="bda0d-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="bda0d-108">В таблице ниже представлен обзор шагов, необходимых для развертывания конференций в существующей топологии.</span><span class="sxs-lookup"><span data-stu-id="bda0d-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bda0d-109">Этап</span><span class="sxs-lookup"><span data-stu-id="bda0d-109">Phase</span></span></th>
<th><span data-ttu-id="bda0d-110">Шаги</span><span class="sxs-lookup"><span data-stu-id="bda0d-110">Steps</span></span></th>
<th><span data-ttu-id="bda0d-111">Роли и членство в группах</span><span class="sxs-lookup"><span data-stu-id="bda0d-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="bda0d-112">Документация</span><span class="sxs-lookup"><span data-stu-id="bda0d-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bda0d-113"><strong>Установка необходимого оборудования и программного обеспечения</strong></span><span class="sxs-lookup"><span data-stu-id="bda0d-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="bda0d-114">Конференции выполняются на серверах переднего плана и серверах стандартных выпусков.</span><span class="sxs-lookup"><span data-stu-id="bda0d-114">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="bda0d-115">Для нее не существует дополнительных требований к оборудованию или программному обеспечению помимо требований для установки этих серверов.</span><span class="sxs-lookup"><span data-stu-id="bda0d-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bda0d-116">Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки общего просмотра и отрисовки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="bda0d-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="bda0d-117">Сведения о том, как установить и настроить сервер Office Web Apps, приведены в разделе <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Настройка интеграции с Office Web Apps Server и Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bda0d-117">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="bda0d-118">Пользователь домена, являющийся членом локальной группы "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="bda0d-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="bda0d-119"><a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="bda0d-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="bda0d-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="bda0d-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="bda0d-121"><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="bda0d-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="bda0d-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Технические требования для архивации в Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="bda0d-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bda0d-123"><strong>Создание соответствующей внутренней топологии для поддержки конференц-связи</strong></span><span class="sxs-lookup"><span data-stu-id="bda0d-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="bda0d-124">Запустите построитель топологии, чтобы добавить в топологию Конференц-связь, а затем опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="bda0d-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="bda0d-125">Для определения топологии требуется учетная запись члена локальной группы "Пользователи".</span><span class="sxs-lookup"><span data-stu-id="bda0d-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="bda0d-126">Чтобы опубликовать топологию, учетную запись, которая является членом группы "Администраторы домена" и Рткуниверсалсерверадминс, и у нее есть разрешения полного доступа (чтение/запись и изменение) в общей папке, которая будет использоваться для хранения файлов Lync Server 2013 (чтобы Topology Builder мог Настройка обязательных DACL</span><span class="sxs-lookup"><span data-stu-id="bda0d-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="bda0d-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Определите и настройте топологию в построителе топологии для Lync Server 2013</a> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="bda0d-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bda0d-128"><strong>Настройка политик конференц-связи и поддержки</strong></span><span class="sxs-lookup"><span data-stu-id="bda0d-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="bda0d-129">Настройте параметры конференц-связи с помощью панели управления Lync Server 2013 или командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="bda0d-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="bda0d-130">Группа Рткуниверсалсерверадминс (только для Windows PowerShell) или назначение пользователей для роли [] или Ксадминистратор</span><span class="sxs-lookup"><span data-stu-id="bda0d-130">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="bda0d-131"><a href="lync-server-2013-conferencing-policies.md">Политики конференций в Lync Server 2013</a> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="bda0d-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bda0d-132">Lync Server 2013 теперь включает параметр **максуплоадфилесиземб** , который ограничивает размер файлов, которые можно отправлять во время собрания.</span><span class="sxs-lookup"><span data-stu-id="bda0d-132">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="bda0d-133">Значение по умолчанию для этого параметра — 500 МБАЙТ.</span><span class="sxs-lookup"><span data-stu-id="bda0d-133">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="bda0d-134">Вы можете настроить **максуплоадфилесиземб** с помощью командлета **Set-ксконференЦингконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="bda0d-134">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="bda0d-135">**Максуплоадфилесиземб** не ограничивает параметр отправки файлов для Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="bda0d-135">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="bda0d-136">Для приложения Lync Web App задано значение "примерно 30MB", а управление IIS Web. config —/Датаколлабвеб/Инт\[ext\]/Хандлер/веб.Конфиг.. Чтобы настроить предельный размер для отправки файлов в Lync Web App `maxRequestLength` , `maxAllowedContentLength` Update и в файле Web. config, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="bda0d-136">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="bda0d-137">Вы должны обновить файл Web. config для каждого сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="bda0d-137">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

