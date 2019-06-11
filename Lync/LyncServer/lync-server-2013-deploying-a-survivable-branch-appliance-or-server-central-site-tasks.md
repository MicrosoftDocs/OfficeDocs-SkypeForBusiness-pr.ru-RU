---
title: Развертывание устройства или сервера для обеспечения связи в филиалах — задачи центрального сайта
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b31e191dc2726c7e7962b0daa4ee5655245117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="d87f5-102">Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013 — задачи центрального сайта</span><span class="sxs-lookup"><span data-stu-id="d87f5-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d87f5-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d87f5-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d87f5-104">Выполните задачи, описанные в этом разделе, на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="d87f5-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="d87f5-105">Если вы развертываете бесперебойный сервер филиала, пропустите первую задачу.</span><span class="sxs-lookup"><span data-stu-id="d87f5-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d87f5-106">Перед выполнением задач, описанных в этом разделе, должны быть выполнены следующие условия:</span><span class="sxs-lookup"><span data-stu-id="d87f5-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d87f5-107">Сервер Lync Server должен быть настроен на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="d87f5-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="d87f5-108">Специалист по установке на сайте филиала должен быть добавлен в группу РткуниверсалсбатечниЦианс.</span><span class="sxs-lookup"><span data-stu-id="d87f5-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="d87f5-109">Кроме того, мы рекомендуем вам выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d87f5-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="d87f5-110">Разверните DHCP-сервер на каждом сайте филиала, чтобы разрешить клиентам получать IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="d87f5-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="d87f5-111">Кроме того, вы можете использовать DHCP-сервер на каждом сайте филиала, используя командлеты командной консоли Lync Server Management <STRONG>Set-ксрегистрарконфигуратион – енабледхкпсервер $true </STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d87f5-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="d87f5-112">Подробные сведения можно найти в разделе Требования к оборудованию и программному обеспечению <A href="lync-server-2013-branch-site-resiliency-requirements.md">для обеспечения устойчивости сайтов для Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="d87f5-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d87f5-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="d87f5-113">In This Section</span></span>

  - [<span data-ttu-id="d87f5-114">Добавление устройства для обеспечения связи в филиалах к Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d87f5-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="d87f5-115">Добавление сайтов филиалов в топологию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d87f5-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="d87f5-116">Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d87f5-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

