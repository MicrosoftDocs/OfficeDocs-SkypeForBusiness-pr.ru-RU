---
title: 'Lync Server 2013: определение своих требований к корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8987905d2b117eb889486882b7d74ce4e52659a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="92e1a-102">Определение своих требований к корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92e1a-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92e1a-103">_**Тема последнего изменения:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="92e1a-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="92e1a-104">В этой статье приводятся общие сведения о регионах, сайтах и ссылках между сайтами в вашей топологии, а также о том, как они важны при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="92e1a-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="92e1a-105">Сведения о том, как принять эти решения, можно найти в разделе [Параметры сети для расширенных функций голосовой связи в Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="92e1a-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="92e1a-106">Сайты и регионы</span><span class="sxs-lookup"><span data-stu-id="92e1a-106">Sites and Regions</span></span>

<span data-ttu-id="92e1a-107">Сначала определите сайты в вашей топологии, в которых будут развертываться Корпоративная голосовая связь и регионы сети, к которым принадлежат эти сайты.</span><span class="sxs-lookup"><span data-stu-id="92e1a-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="92e1a-108">В частности, рассмотрите, как вы будете обеспечивать подключение к телефонной сети общего пользования (ТСОП) для каждого узла.</span><span class="sxs-lookup"><span data-stu-id="92e1a-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="92e1a-109">По соображениям управляемости и логистики определяющим фактором могут быть области, которым эти узлы принадлежат.</span><span class="sxs-lookup"><span data-stu-id="92e1a-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="92e1a-110">Решите, где будут развертываться шлюзы, где будут развертываться бесперебойные устройства филиалов (Сбас) и где можно настроить магистральные магистрали SIP (как на локальном компьютере, так и на центральном сайте) с поставщиком услуг телефонной связи через Интернет (ИТСП).</span><span class="sxs-lookup"><span data-stu-id="92e1a-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="92e1a-111">Сетевые ссылки между сайтами</span><span class="sxs-lookup"><span data-stu-id="92e1a-111">Network Links Between Sites</span></span>

<span data-ttu-id="92e1a-112">Кроме того, необходимо проанализировать использование пропускной способности, которое ожидается в сетевых связях между центральным сайтом и его сайтами филиалов.</span><span class="sxs-lookup"><span data-stu-id="92e1a-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="92e1a-113">Если вы или планируете развертывание, отказоустойчивая WAN Links между сайтами, мы рекомендуем вам развернуть шлюз на каждом сайте филиала, чтобы обеспечить локальное прекращение сеанса для пользователей на этих сайтах.</span><span class="sxs-lookup"><span data-stu-id="92e1a-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="92e1a-114">Если устойчивые каналы глобальной сети существуют, но пропускная полоса канала глобальной сети, вероятно, будет ограничена, настройте контроль допуска звонков для этого канала.</span><span class="sxs-lookup"><span data-stu-id="92e1a-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="92e1a-115">Если вы не обладаете устойчивыми ссылками на глобальную сеть, разместите на сайте филиала менее 1000 пользователей и не имеете доступ к локальным администраторам серверам Lync, поэтому мы рекомендуем развернуть бесперебойно работающее устройство филиала на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="92e1a-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="92e1a-116">Если вы размещаете пользователей 1000 и 5000 на сайте филиала, не можете использовать устойчивое подключение к глобальной сети и прошли обучение администраторам сервера Lync, мы рекомендуем развернуть бесперебойный сервер с небольшим шлюзом на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="92e1a-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="92e1a-117">Также рассмотрите возможность включения обхода сервера-посредника на ограниченных каналах, если у вас есть шлюз, поддерживающий обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="92e1a-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92e1a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="92e1a-118">See Also</span></span>


[<span data-ttu-id="92e1a-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92e1a-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

