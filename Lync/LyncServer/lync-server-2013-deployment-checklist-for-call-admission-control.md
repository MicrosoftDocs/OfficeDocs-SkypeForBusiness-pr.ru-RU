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
ms.openlocfilehash: 0bf88529734530e70c4d0536d5337395ff0742d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="3278e-102">Контрольный список развертывания для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3278e-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3278e-103">_**Тема последнего изменения:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="3278e-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="3278e-104">Чтобы эффективно спланировать управление допуском звонков (CAC), необходимо принять во все указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3278e-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="3278e-105">Необходимые условия для развертывания CAC.</span><span class="sxs-lookup"><span data-stu-id="3278e-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="3278e-106">Информация, необходимая для решений CAC и конфигурации, которые необходимо выполнить перед развертыванием.</span><span class="sxs-lookup"><span data-stu-id="3278e-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="3278e-107">Предварительные требования к развертыванию для управления допуском звонков</span><span class="sxs-lookup"><span data-stu-id="3278e-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="3278e-108">Прежде чем развертывать управление допуском звонков, необходимо предварительно развернуть внутренние серверы Lync Server 2013, в том числе либо интерфейсный пул, либо сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3278e-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="3278e-109">Требования к сведениям для управления допуском звонков</span><span class="sxs-lookup"><span data-stu-id="3278e-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="3278e-110">В таблице ниже приведены сведения, необходимые для развертывания управления допуском звонков.</span><span class="sxs-lookup"><span data-stu-id="3278e-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="3278e-111">Требования к сведениям для развертывания управления допуском звонков</span><span class="sxs-lookup"><span data-stu-id="3278e-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3278e-112">Информация</span><span class="sxs-lookup"><span data-stu-id="3278e-112">Information</span></span></th>
<th><span data-ttu-id="3278e-113">Сводка данных, необходимых</span><span class="sxs-lookup"><span data-stu-id="3278e-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="3278e-114">Документация</span><span class="sxs-lookup"><span data-stu-id="3278e-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3278e-115">Возможности Lync Server, необходимые для Организации</span><span class="sxs-lookup"><span data-stu-id="3278e-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3278e-116">Возможности, которые должны поддерживаться вашей организацией</span><span class="sxs-lookup"><span data-stu-id="3278e-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="3278e-117">Возможности, которые должны быть включены для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="3278e-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3278e-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Определение своих требований для контроля допуска звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3278e-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3278e-119">Топологии и компоненты, которые нужно развернуть</span><span class="sxs-lookup"><span data-stu-id="3278e-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3278e-120">Компоненты, связанные с CAC, автоматически устанавливаются в составе Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3278e-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3278e-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Определение своих требований для контроля допуска звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3278e-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3278e-122">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="3278e-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3278e-123">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="3278e-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="3278e-124">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="3278e-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="3278e-125">Требования к выровнению</span><span class="sxs-lookup"><span data-stu-id="3278e-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3278e-126"><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3278e-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3278e-127">Требования к инфраструктуре</span><span class="sxs-lookup"><span data-stu-id="3278e-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3278e-128">Для CAC не требуются особые требования к инфраструктуре</span><span class="sxs-lookup"><span data-stu-id="3278e-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3278e-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Требования к инфраструктуре для контроля допуска звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3278e-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3278e-130">Требования к сетевому интерфейсу</span><span class="sxs-lookup"><span data-stu-id="3278e-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3278e-131">Сведения о внутреннем и внешнем интерфейсе</span><span class="sxs-lookup"><span data-stu-id="3278e-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="3278e-132">Сведения о маршрутизации (в том числе сведения в блоге <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>на странице Microsoft Lync Server Teams в канале ответа клиента)</span><span class="sxs-lookup"><span data-stu-id="3278e-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3278e-133"><a href="lync-server-2013-deploying-external-user-access.md">Развертывание доступа внешних пользователей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3278e-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3278e-134">Стратегия развертывания</span><span class="sxs-lookup"><span data-stu-id="3278e-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3278e-135">Последовательность развертывания</span><span class="sxs-lookup"><span data-stu-id="3278e-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="3278e-136">Рабочая группа или домен</span><span class="sxs-lookup"><span data-stu-id="3278e-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="3278e-137">Безопасность</span><span class="sxs-lookup"><span data-stu-id="3278e-137">Security</span></span></p></li>
<li><p><span data-ttu-id="3278e-138">Мониторинг и аудит</span><span class="sxs-lookup"><span data-stu-id="3278e-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="3278e-139">Рекомендации по оборудованию</span><span class="sxs-lookup"><span data-stu-id="3278e-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3278e-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Рекомендации по контролю допуска звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3278e-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3278e-141">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="3278e-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3278e-142">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="3278e-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="3278e-143">Требования к информации</span><span class="sxs-lookup"><span data-stu-id="3278e-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="3278e-144">Процесс и процедуры</span><span class="sxs-lookup"><span data-stu-id="3278e-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3278e-145"><a href="lync-server-2013-configure-call-admission-control.md">Настройка управления допуском звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3278e-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

