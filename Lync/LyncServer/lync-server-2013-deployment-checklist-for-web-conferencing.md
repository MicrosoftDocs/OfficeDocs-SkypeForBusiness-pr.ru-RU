---
title: Lync Server 2013 контрольный список развертывания для веб-конференций
description: Lync Server 2013 контрольный список развертывания для веб-конференций.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6194cb71af268a45dc5c142c1814d8c1ef15c09e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562185"
---
# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="fbef6-103">Контрольный список развертывания для веб-конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbef6-103">Deployment checklist for web conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbef6-104">_**Последнее изменение темы:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="fbef6-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="fbef6-105">Как и в случае развертывания других компонентов Lync Server 2013, для развертывания веб-конференций необходимо использовать построитель топологий для создания и публикации топологии, в которой выполняется организация конференций.</span><span class="sxs-lookup"><span data-stu-id="fbef6-105">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="fbef6-106">Порядок развертывания</span><span class="sxs-lookup"><span data-stu-id="fbef6-106">Deployment Sequence</span></span>

<span data-ttu-id="fbef6-107">Конференц-связь можно развертывать одновременно с первоначальной топологией или после развертывания по крайней мере одного пула переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fbef6-107">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="fbef6-108">Процесс развертывания конференц-связи</span><span class="sxs-lookup"><span data-stu-id="fbef6-108">Conferencing Deployment Process</span></span>

<span data-ttu-id="fbef6-109">В следующей таблице представлен обзор действий, необходимых для развертывания конференц-связи в существующей топологии.</span><span class="sxs-lookup"><span data-stu-id="fbef6-109">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbef6-110">Этап</span><span class="sxs-lookup"><span data-stu-id="fbef6-110">Phase</span></span></th>
<th><span data-ttu-id="fbef6-111">Действия</span><span class="sxs-lookup"><span data-stu-id="fbef6-111">Steps</span></span></th>
<th><span data-ttu-id="fbef6-112">Роли и членство в группах</span><span class="sxs-lookup"><span data-stu-id="fbef6-112">Roles and group memberships</span></span></th>
<th><span data-ttu-id="fbef6-113">Документация</span><span class="sxs-lookup"><span data-stu-id="fbef6-113">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbef6-114"><strong>Установка обязательного оборудования и программного обеспечения.</strong></span><span class="sxs-lookup"><span data-stu-id="fbef6-114"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="fbef6-115">Конференц-связь работает на серверах переднего плана в интерфейсном пуле и серверах Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fbef6-115">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="fbef6-116">Для нее не существуют дополнительные требования к оборудованию или программному обеспечению помимо требований для установки этих серверов.</span><span class="sxs-lookup"><span data-stu-id="fbef6-116">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fbef6-117">Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки совместного использования и отрисовки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="fbef6-117">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="fbef6-118">Сведения об установке и настройке сервера Office Web Apps приведены в статье <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Настройка интеграции с сервером Office Web Apps и Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fbef6-118">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="fbef6-119">Доменный пользователь, входящий в локальную группу "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="fbef6-119">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="fbef6-120"><a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="fbef6-120"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="fbef6-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="fbef6-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="fbef6-122"><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="fbef6-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="fbef6-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Технические требования для архивации в Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="fbef6-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbef6-124"><strong>Создание соответствующей внутренней топологии для поддержки конференц-связи</strong></span><span class="sxs-lookup"><span data-stu-id="fbef6-124"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="fbef6-125">Запустите построитель топологий, чтобы добавить Конференц-связь в топологию, а затем опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="fbef6-125">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="fbef6-126">Чтобы определить топологию, требуется учетная запись, входящая в локальную группу "Пользователи"</span><span class="sxs-lookup"><span data-stu-id="fbef6-126">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="fbef6-127">Чтобы опубликовать топологию, учетная запись, которая является членом группы администраторов домена и группы RTCUniversalServerAdmins, обладает разрешениями на полный доступ (чтение/запись/изменение) для общего файлового ресурса, который будет использоваться для хранилища файлов Lync Server 2013 (чтобы построитель топологии мог настроить требуемые списки DACL)</span><span class="sxs-lookup"><span data-stu-id="fbef6-127">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="fbef6-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Определение и Настройка топологии в построителе топологий для Lync Server 2013</a> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="fbef6-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbef6-129"><strong>Настройка политик конференц-связи и поддержки</strong></span><span class="sxs-lookup"><span data-stu-id="fbef6-129"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="fbef6-130">Настройте параметры конференц-связи с помощью панели управления Lync Server 2013 или консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fbef6-130">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="fbef6-131">Группа RTCUniversalServerAdmins (только для Windows PowerShell) или назначение пользователей для роли [] или CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="fbef6-131">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="fbef6-132"><a href="lync-server-2013-conferencing-policies.md">Политики конференц-связи в Lync Server 2013</a> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="fbef6-132"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fbef6-133">Lync Server 2013 теперь включает параметр **максуплоадфилесиземб** , который позволяет ограничить размер файлов, которые могут быть отправлены во время собрания.</span><span class="sxs-lookup"><span data-stu-id="fbef6-133">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="fbef6-134">Его значение по умолчанию — 500 МБ.</span><span class="sxs-lookup"><span data-stu-id="fbef6-134">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="fbef6-135">Значение **MaxUploadFileSizeMb** можно изменить с помощью командлета **Set-CsConferencingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="fbef6-135">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="fbef6-136">**Максуплоадфилесиземб** не ограничивает параметр отправки файлов для Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="fbef6-136">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="fbef6-137">В качестве ограничения на загрузку размера файла для Lync Web App задано значение приблизительно 30MB и оно управляется файлом IIS web.config:/Датаколлабвеб/Инт \[ ext \] /Хандлер/web.config. Для настройки ограничения на загрузку размера файлов для Lync Web App, обновления `maxRequestLength` и `maxAllowedContentLength` в файле web.config, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="fbef6-137">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="fbef6-138">Необходимо обновить файл web.config для каждого сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="fbef6-138">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

