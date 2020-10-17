---
title: Развертывание устройства для обеспечения связи в филиалах или задач сервера-центрального сайта
description: Развертывание устройства для обеспечения связи в филиалах или задач сервера-центрального сайта.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4460ea215d6fc80ee89f1ca9bc42f08ac5d14617
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558605"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="bde33-103">Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013-Central Site Tasks</span><span class="sxs-lookup"><span data-stu-id="bde33-103">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bde33-104">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="bde33-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="bde33-105">Выполните задачи, описанные в данном разделе, на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="bde33-105">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="bde33-106">Если вы развертываете сервер для обеспечения связи в филиалах, пропустите первую задачу.</span><span class="sxs-lookup"><span data-stu-id="bde33-106">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="bde33-107">Перед выполнением данных задач следует обеспечить выполнение следующих условий:</span><span class="sxs-lookup"><span data-stu-id="bde33-107">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="bde33-108">Lync Server должен быть настроен на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="bde33-108">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="bde33-109">Следует добавить техника по установке на сайте филиала в группу RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="bde33-109">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="bde33-110">Кроме того, мы рекомендуем вам выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="bde33-110">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="bde33-111">Разверните DHCP-сервер на каждом сайте филиала, чтобы клиенты могли получать IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="bde33-111">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="bde33-112">В качестве альтернативы развертыванию DHCP-сервера на каждом сайте филиала включите службу DHCP Lync Server на устройстве для обеспечения связи в филиалах или сервере для обеспечения связи в филиалах с помощью командлета командной консоли Lync Server <STRONG>Set-CsRegistrarConfiguration – енабледхкпсервер $true</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bde33-112">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="bde33-113">Для получения дополнительных сведений обратитесь к разделу "требования к оборудованию и программному обеспечению" <A href="lync-server-2013-branch-site-resiliency-requirements.md">для обеспечения устойчивости сайта филиала для Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="bde33-113">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bde33-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="bde33-114">In This Section</span></span>

  - [<span data-ttu-id="bde33-115">Добавление устройства для обеспечения связи в филиалах в Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bde33-115">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="bde33-116">Добавление сайтов филиалов в топологию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bde33-116">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="bde33-117">Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bde33-117">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

