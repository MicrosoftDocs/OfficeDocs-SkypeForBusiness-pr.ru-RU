---
title: Контрольный список развертывания Lync Server 2013 для аудио-и видеоконференций
description: Контрольный список развертывания Lync Server 2013 для аудио-и видеоконференций.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9a4584172ed4c01eb163ea51aa4f62c2ce75185
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557775"
---
# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="78bcd-103">Контрольный список развертывания для аудио-и видеоконференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78bcd-103">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78bcd-104">_**Последнее изменение темы:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="78bcd-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="78bcd-105">Как и в случае развертывания других компонентов Lync Server 2013, для развертывания аудио-и видеоконференций требуется использовать построитель топологий для создания и публикации топологии, в которой выполняется организация конференций.</span><span class="sxs-lookup"><span data-stu-id="78bcd-105">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="78bcd-106">Порядок развертывания</span><span class="sxs-lookup"><span data-stu-id="78bcd-106">Deployment Sequence</span></span>

<span data-ttu-id="78bcd-107">Конференц-связь можно развертывать одновременно с первоначальной топологией или после развертывания по крайней мере одного пула переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="78bcd-107">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="78bcd-108">Процесс развертывания конференц-связи</span><span class="sxs-lookup"><span data-stu-id="78bcd-108">Conferencing Deployment Process</span></span>

<span data-ttu-id="78bcd-109">В следующей таблице представлен обзор действий, необходимых для развертывания конференц-связи в существующей топологии.</span><span class="sxs-lookup"><span data-stu-id="78bcd-109">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78bcd-110">Этап</span><span class="sxs-lookup"><span data-stu-id="78bcd-110">Phase</span></span></th>
<th><span data-ttu-id="78bcd-111">Действия</span><span class="sxs-lookup"><span data-stu-id="78bcd-111">Steps</span></span></th>
<th><span data-ttu-id="78bcd-112">Роли и членство в группах</span><span class="sxs-lookup"><span data-stu-id="78bcd-112">Roles and group memberships</span></span></th>
<th><span data-ttu-id="78bcd-113">Документация</span><span class="sxs-lookup"><span data-stu-id="78bcd-113">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78bcd-114"><strong>Установка обязательного оборудования и программного обеспечения.</strong></span><span class="sxs-lookup"><span data-stu-id="78bcd-114"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="78bcd-115">Конференц-связь работает на серверах переднего плана и серверах Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="78bcd-115">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="78bcd-116">Для нее не существуют дополнительные требования к оборудованию или программному обеспечению помимо требований для установки этих серверов.</span><span class="sxs-lookup"><span data-stu-id="78bcd-116">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="78bcd-117">Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки совместного использования и отрисовки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="78bcd-117">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="78bcd-118">Дополнительные сведения об установке и настройке сервера Office Web Apps приведены в статье <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Настройка интеграции с сервером Office Web Apps и Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="78bcd-118">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="78bcd-119">Доменный пользователь, входящий в локальную группу "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="78bcd-119">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="78bcd-120"><a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="78bcd-120"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="78bcd-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="78bcd-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="78bcd-122"><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="78bcd-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="78bcd-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Технические требования для архивации в Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="78bcd-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78bcd-124"><strong>Создание соответствующей внутренней топологии для поддержки конференц-связи</strong></span><span class="sxs-lookup"><span data-stu-id="78bcd-124"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="78bcd-125">Запустите построитель топологий, чтобы добавить Конференц-связь в топологию, а затем опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="78bcd-125">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="78bcd-126">Чтобы определить топологию, требуется учетная запись, входящая в локальную группу "Пользователи"</span><span class="sxs-lookup"><span data-stu-id="78bcd-126">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="78bcd-127">Чтобы опубликовать топологию, учетная запись, которая является членом группы администраторов домена и группы RTCUniversalServerAdmins, обладает разрешениями на полный доступ (чтение/запись/изменение) для общего файлового ресурса, который будет использоваться для хранилища файлов Lync Server 2013 (чтобы построитель топологии мог настроить требуемые списки DACL)</span><span class="sxs-lookup"><span data-stu-id="78bcd-127">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="78bcd-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Определение и Настройка топологии в построителе топологий для Lync Server 2013</a> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="78bcd-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78bcd-129"><strong>Настройка политик конференц-связи и поддержки</strong></span><span class="sxs-lookup"><span data-stu-id="78bcd-129"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="78bcd-130">Настройте параметры конференц-связи с помощью панели управления Lync Server 2013 или консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78bcd-130">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="78bcd-131">Группа RTCUniversalServerAdmins (только для Windows PowerShell) или назначение пользователей для роли [] или CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="78bcd-131">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="78bcd-132"><a href="lync-server-2013-conferencing-policies.md">Политики конференц-связи в Lync Server 2013</a> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="78bcd-132"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="78bcd-133">См. также</span><span class="sxs-lookup"><span data-stu-id="78bcd-133">See Also</span></span>


[<span data-ttu-id="78bcd-134">Обзор конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78bcd-134">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="78bcd-135">Определение требований для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78bcd-135">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

