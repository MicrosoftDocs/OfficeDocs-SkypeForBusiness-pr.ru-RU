---
title: 'Lync Server 2013: командлеты пограничного сервера'
description: 'Lync Server 2013: командлеты пограничного сервера.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server cmdlets
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415635(v=OCS.15)
ms:contentKeyID: 48183534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b73172331ddcde76672cccda682669f71dd7262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551675"
---
# <a name="edge-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="9d0e9-103">Командлеты пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d0e9-103">Edge Server cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d0e9-104">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="9d0e9-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="9d0e9-105">Пограничные серверы предоставляют способ расширения возможностей Microsoft Lync Server 2013 для пользователей, которые не вошли во внутреннюю сеть.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-105">Edge Servers provide a way for you to extend the capabilities of Microsoft Lync Server 2013 to people who are not logged on to your internal network.</span></span> <span data-ttu-id="9d0e9-106">Например, если у вас есть удаленные пользователи с проверкой подлинности с проверкой подлинности, которые входят в Lync Server 2013 через Интернет, а не через внутреннюю сеть, вам потребуется настроить пограничный сервер, на котором работает пограничная служба доступа Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-106">For example, if you have remote users -- authenticated users who log on to Lync Server 2013 over the Internet rather than through the internal network -- you will need to set up an Edge Server that runs the Lync Server Access Edge service.</span></span> <span data-ttu-id="9d0e9-107">Кроме того, пограничные серверы необходимы, если вы хотите установить Федерацию с другой организацией или вы хотите предоставить пользователям право на взаимодействие с пользователями, у которых есть учетные записи с общедоступными службами обмена мгновенными сообщениями, такими как Yahoo \! , AOL или MSN.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-107">Additionally, Edge Servers are required if you want to establish federation with another organization or if you want to give your users the right to communicate with people who have accounts with a public instant messaging service such as Yahoo\!, AOL, or MSN.</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="9d0e9-108">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-108">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="9d0e9-109">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9d0e9-109">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="9d0e9-110">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-110">Messenger until the service shut down date.</span></span> <span data-ttu-id="9d0e9-111">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9d0e9-111">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="9d0e9-112">объявлено.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-112">has been announced.</span></span> <span data-ttu-id="9d0e9-113">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-113">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="9d0e9-114">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9d0e9-114">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="9d0e9-115">Messenger.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-115">Messenger.</span></span> <span data-ttu-id="9d0e9-116">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-116">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="9d0e9-117">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-117">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="9d0e9-118">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-118">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="9d0e9-119">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="9d0e9-119">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a><span data-ttu-id="9d0e9-120">Командлеты пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="9d0e9-120">Edge Server Cmdlets</span></span>

<span data-ttu-id="9d0e9-121">Ниже приведен список командлетов, которые относятся непосредственно к управлению пограничными серверами:</span><span class="sxs-lookup"><span data-stu-id="9d0e9-121">The following is a list of cmdlets that relate directly to managing Edge Servers:</span></span>

<span data-ttu-id="9d0e9-122">**Пограничный сервер**</span><span class="sxs-lookup"><span data-stu-id="9d0e9-122">**Edge Server**</span></span>

  - <span></span>  
    <span data-ttu-id="9d0e9-123">[Get — CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9d0e9-123">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9d0e9-124">[Set — CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9d0e9-124">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="9d0e9-125">[Get — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9d0e9-125">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9d0e9-126">[New — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9d0e9-126">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9d0e9-127">[Remove — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9d0e9-127">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9d0e9-128">[Set — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9d0e9-128">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="9d0e9-129">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9d0e9-129">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="9d0e9-130">[Set — Кседжесервер](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9d0e9-130">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9d0e9-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9d0e9-131">See Also</span></span>


[<span data-ttu-id="9d0e9-132">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d0e9-132">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

