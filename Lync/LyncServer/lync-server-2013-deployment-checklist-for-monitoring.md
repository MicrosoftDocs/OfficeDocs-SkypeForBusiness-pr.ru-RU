---
title: 'Lync Server 2013: контрольный список развертывания для мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e455cb06c6890bb8925bc35a8d5f4c6775288f8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="d4efc-102">Контрольный список развертывания для мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4efc-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4efc-103">_**Последнее изменение темы:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="d4efc-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="d4efc-104">Хотя мониторинг уже установлен и активирован на каждом сервере переднего плана, существует несколько действий, которые необходимо предпринять, прежде чем вы сможете собрать данные мониторинга для Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4efc-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d4efc-105">Эти действия приведены в следующем контрольном списке.</span><span class="sxs-lookup"><span data-stu-id="d4efc-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4efc-106">Этап</span><span class="sxs-lookup"><span data-stu-id="d4efc-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="d4efc-107">Шаги</span><span class="sxs-lookup"><span data-stu-id="d4efc-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="d4efc-108">Членство в роли и группе</span><span class="sxs-lookup"><span data-stu-id="d4efc-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="d4efc-109">Документация</span><span class="sxs-lookup"><span data-stu-id="d4efc-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4efc-110"><strong>Установка необходимого оборудования и программного обеспечения</strong></span><span class="sxs-lookup"><span data-stu-id="d4efc-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="d4efc-111">Установка поддерживаемой версии Microsoft SQL Server на компьютере, который будет работать в качестве внутреннего хранилища данных для мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d4efc-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="d4efc-112">Пользователь домена, который также является членом группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="d4efc-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="d4efc-113"><a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в руководстве по поддержке</span><span class="sxs-lookup"><span data-stu-id="d4efc-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="d4efc-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в руководстве по поддержке</span><span class="sxs-lookup"><span data-stu-id="d4efc-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4efc-115"><strong>Создание приемлемой внутренней топологии для поддержки мониторинга</strong></span><span class="sxs-lookup"><span data-stu-id="d4efc-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="d4efc-116">Используйте построитель топологий Lync Server 2013 для добавления в топологию баз данных мониторинга и публикации обновленной топологии.</span><span class="sxs-lookup"><span data-stu-id="d4efc-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="d4efc-117">Чтобы определить топологию, пользователь, который является членом локальной группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="d4efc-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="d4efc-118">Чтобы опубликовать топологию, пользователь, который является членом группы администраторов домена и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d4efc-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="d4efc-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Связывание хранилища мониторинга с пулом переднего плана в Lync Server 2013</a> в руководстве по развертыванию</span><span class="sxs-lookup"><span data-stu-id="d4efc-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4efc-120"><strong>Включение подходящих параметров мониторинга</strong></span><span class="sxs-lookup"><span data-stu-id="d4efc-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="d4efc-121">Включите мониторинг регистрации вызовов (CDR) и качества связи (QoE) на глобальном уровне и уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="d4efc-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="d4efc-122">Пользователь, который является членом группы RTCUniversalServerAdmins или которому была назначена роль RBAC, предоставляющая доступ к командлетам CsCdrConfiguration и CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d4efc-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="d4efc-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Настройка записи сведений о вызовах и параметров качества взаимодействия в Lync Server 2013</a> в руководстве по эксплуатации</span><span class="sxs-lookup"><span data-stu-id="d4efc-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

