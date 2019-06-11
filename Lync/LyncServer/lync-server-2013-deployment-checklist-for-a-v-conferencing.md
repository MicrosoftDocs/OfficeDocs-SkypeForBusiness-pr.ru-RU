---
title: Контрольный список развертывания Lync Server 2013 для конференц-связи с телефонным видео
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d787cbc1e2bbefcc2cb125e64ab7143ddbd6cf2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="bf8e4-102">Контрольный список развертывания для конференций/V в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf8e4-102">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf8e4-103">_**Тема последнего изменения:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="bf8e4-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="bf8e4-104">Как и при развертывании других компонентов Lync Server 2013, при развертывании конференции с помощью Topology Builder требуется создать и опубликовать топологию, в которой используются Конференции.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-104">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="bf8e4-105">Последовательность развертывания</span><span class="sxs-lookup"><span data-stu-id="bf8e4-105">Deployment Sequence</span></span>

<span data-ttu-id="bf8e4-106">Вы можете разворачивать конференции одновременно с развертыванием начальной топологии или после развертывания по крайней мере одного пула переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="bf8e4-107">Процесс развертывания конференций</span><span class="sxs-lookup"><span data-stu-id="bf8e4-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="bf8e4-108">В таблице ниже представлен обзор шагов, необходимых для развертывания конференций в существующей топологии.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf8e4-109">Этап</span><span class="sxs-lookup"><span data-stu-id="bf8e4-109">Phase</span></span></th>
<th><span data-ttu-id="bf8e4-110">Шаги</span><span class="sxs-lookup"><span data-stu-id="bf8e4-110">Steps</span></span></th>
<th><span data-ttu-id="bf8e4-111">Роли и членство в группах</span><span class="sxs-lookup"><span data-stu-id="bf8e4-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="bf8e4-112">Документация</span><span class="sxs-lookup"><span data-stu-id="bf8e4-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf8e4-113"><strong>Установка необходимого оборудования и программного обеспечения</strong></span><span class="sxs-lookup"><span data-stu-id="bf8e4-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="bf8e4-114">Конференции выполняются на серверах переднего плана и серверах стандартных выпусков.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-114">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="bf8e4-115">Для нее не существует дополнительных требований к оборудованию или программному обеспечению помимо требований для установки этих серверов.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bf8e4-116">Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки общего просмотра и отрисовки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="bf8e4-117">Подробнее об установке и настройке сервера Office Web Apps можно узнать в разделе <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Настройка интеграции с Office Web Apps Server и Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-117">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="bf8e4-118">Пользователь домена, являющийся членом локальной группы "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="bf8e4-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="bf8e4-119"><a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="bf8e4-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="bf8e4-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="bf8e4-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="bf8e4-121"><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="bf8e4-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Технические требования для архивации в Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8e4-123"><strong>Создание соответствующей внутренней топологии для поддержки конференц-связи</strong></span><span class="sxs-lookup"><span data-stu-id="bf8e4-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="bf8e4-124">Запустите построитель топологии, чтобы добавить в топологию Конференц-связь, а затем опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="bf8e4-125">Для определения топологии требуется учетная запись члена локальной группы "Пользователи".</span><span class="sxs-lookup"><span data-stu-id="bf8e4-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="bf8e4-126">Чтобы опубликовать топологию, учетную запись, которая является членом группы "Администраторы домена" и Рткуниверсалсерверадминс, и у нее есть разрешения полного доступа (чтение/запись и изменение) в общей папке, которая будет использоваться для хранения файлов Lync Server 2013 (чтобы Topology Builder мог Настройка обязательных DACL</span><span class="sxs-lookup"><span data-stu-id="bf8e4-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="bf8e4-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Определите и настройте топологию в построителе топологии для Lync Server 2013</a> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8e4-128"><strong>Настройка политик конференц-связи и поддержки</strong></span><span class="sxs-lookup"><span data-stu-id="bf8e4-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="bf8e4-129">Настройте параметры конференц-связи с помощью панели управления Lync Server 2013 или командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="bf8e4-130">Группа Рткуниверсалсерверадминс (только для Windows PowerShell) или назначение пользователей для роли [] или Ксадминистратор</span><span class="sxs-lookup"><span data-stu-id="bf8e4-130">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="bf8e4-131"><a href="lync-server-2013-conferencing-policies.md">Политики конференций в Lync Server 2013</a> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="bf8e4-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bf8e4-132">См. также</span><span class="sxs-lookup"><span data-stu-id="bf8e4-132">See Also</span></span>


[<span data-ttu-id="bf8e4-133">Обзор конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf8e4-133">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="bf8e4-134">Определение требований для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf8e4-134">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

