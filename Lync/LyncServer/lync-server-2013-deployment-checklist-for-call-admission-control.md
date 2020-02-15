---
title: 'Lync Server 2013: контрольный список развертывания для контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d68f13c636b24729db989f25da7055333968cbbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="e3731-102">Контрольный список развертывания для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3731-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3731-103">_**Последнее изменение темы:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="e3731-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="e3731-104">Для эффективного планирования контроля допуска звонков необходимо учитывать следующие аспекты:</span><span class="sxs-lookup"><span data-stu-id="e3731-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="e3731-105">необходимые компоненты для развертывания контроля допуска звонков (CAC);</span><span class="sxs-lookup"><span data-stu-id="e3731-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="e3731-106">сведения, необходимые для развертывания CAC, и конфигурационные решения, которые необходимо принять, до развертывания.</span><span class="sxs-lookup"><span data-stu-id="e3731-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="e3731-107">Необходимые компоненты для развертывания контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="e3731-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="e3731-108">Перед развертыванием контроля допуска звонков необходимо предварительно развернуть внутренние серверы Lync Server 2013, в том числе интерфейсный пул или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e3731-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="e3731-109">Информационные требования для контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="e3731-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="e3731-110">В следующей таблице представлена сводная информация о развертывании CAC.</span><span class="sxs-lookup"><span data-stu-id="e3731-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="e3731-111">Информационные требования для развертывания контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="e3731-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3731-112">Информация</span><span class="sxs-lookup"><span data-stu-id="e3731-112">Information</span></span></th>
<th><span data-ttu-id="e3731-113">Сводка по необходимым сведениям</span><span class="sxs-lookup"><span data-stu-id="e3731-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="e3731-114">Документация</span><span class="sxs-lookup"><span data-stu-id="e3731-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3731-115">Возможности Lync Server, необходимые для Организации</span><span class="sxs-lookup"><span data-stu-id="e3731-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3731-116">Возможности, которые должны поддерживаться вашей организацией</span><span class="sxs-lookup"><span data-stu-id="e3731-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="e3731-117">Возможности, которые должны быть доступны отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="e3731-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e3731-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Определение требований для контроля допуска звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3731-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3731-119">Топологии и компоненты для развертывания</span><span class="sxs-lookup"><span data-stu-id="e3731-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3731-120">Компоненты, связанные с CAC, устанавливаются автоматически в составе Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3731-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e3731-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Определение требований для контроля допуска звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3731-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3731-122">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="e3731-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3731-123">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="e3731-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="e3731-124">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="e3731-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="e3731-125">Требования к выровненному размещению</span><span class="sxs-lookup"><span data-stu-id="e3731-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e3731-126"><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3731-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3731-127">Требования к инфраструктуре</span><span class="sxs-lookup"><span data-stu-id="e3731-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3731-128">Для CAC не применяются особые требования к инфраструктуре</span><span class="sxs-lookup"><span data-stu-id="e3731-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e3731-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Требования к инфраструктуре для контроля допуска звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3731-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3731-130">Требования к сетевому интерфейсу</span><span class="sxs-lookup"><span data-stu-id="e3731-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3731-131">Сведения о внутреннем и внешнем интерфейсе</span><span class="sxs-lookup"><span data-stu-id="e3731-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="e3731-132">Сведения о маршрутизации (в том числе сведения о блоге <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, на который входит канал ответа группы Microsoft Lync Server).</span><span class="sxs-lookup"><span data-stu-id="e3731-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e3731-133"><a href="lync-server-2013-deploying-external-user-access.md">Развертывание доступа внешних пользователей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3731-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3731-134">Стратегия развертывания</span><span class="sxs-lookup"><span data-stu-id="e3731-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3731-135">Последовательность развертывания</span><span class="sxs-lookup"><span data-stu-id="e3731-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="e3731-136">Рабочая группа или домен</span><span class="sxs-lookup"><span data-stu-id="e3731-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="e3731-137">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e3731-137">Security</span></span></p></li>
<li><p><span data-ttu-id="e3731-138">Мониторинг и аудит</span><span class="sxs-lookup"><span data-stu-id="e3731-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="e3731-139">Вопросы, связанные с оборудованием</span><span class="sxs-lookup"><span data-stu-id="e3731-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e3731-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Рекомендации по контролю допуска звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3731-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3731-141">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="e3731-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3731-142">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="e3731-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="e3731-143">Информационные требования</span><span class="sxs-lookup"><span data-stu-id="e3731-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="e3731-144">Процесс и процедуры</span><span class="sxs-lookup"><span data-stu-id="e3731-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e3731-145"><a href="lync-server-2013-configure-call-admission-control.md">Настройка контроля допуска звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3731-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

