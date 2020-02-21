---
title: 'Lync Server 2013: связывание подсетей с сетевыми сайтами для обхода сервера-посредника'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5565be047443ebb0bf84358a592dc0b1f9314c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="d0836-102">Связывание подсетей с сетевыми сайтами для обхода сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0836-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0836-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d0836-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0836-104">В этом разделе предполагается, что параметры обхода сервера-посредника настроены, и что имеются настроенные области сети и сетевые узлы для обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="d0836-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="d0836-p101">Каждая подсеть в вашей сети должна быть связана с конкретным сетевым узлом, поскольку информация подсети используется для определения сетевого узла, в котором расположена конечная точка. Когда известны расположения обеих сторон сеанса, обход сервера-посредника может определить, куда следует отправлять мультимедиа для обработки.</span><span class="sxs-lookup"><span data-stu-id="d0836-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="d0836-108">Для обхода сервера-посредника не существуют какие-либо особые требования относительно связи подсетей с сетевыми узлами.</span><span class="sxs-lookup"><span data-stu-id="d0836-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="d0836-109">Чтобы создать связь между подсетями и сетевыми сайтами в топологии, выполните процедуры, описанные в разделе [связывание подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="d0836-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="d0836-110">Следующие действия: создание профилей политик пропускной способности</span><span class="sxs-lookup"><span data-stu-id="d0836-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="d0836-p103">После создания связи подсетей с сетевыми узлами для обхода сервера-посредника необходимо создать хотя бы один профиль политики пропускной способности, который для осуществления обхода сервера-посредника будет разделять сети на имеющие хорошие возможности подключения и на не имеющие таких возможностей. Все подсети в области сети с сетевыми узлами, в которых отсутствуют ограничения пропускной способности, имеют хорошие возможности подключения и, следовательно, могут использовать обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="d0836-p103">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass. All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="d0836-113">Процедуры настройки профилей политики пропускной способности приведены [в статье Create Profile Policy Profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d0836-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

