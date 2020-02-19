---
title: 'Lync Server 2013: командлеты пограничного сервера'
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
ms.openlocfilehash: 60081dc4d56c65e3cbef29a9231f855578d07054
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edge-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="eab68-102">Командлеты пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eab68-102">Edge Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eab68-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="eab68-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="eab68-104">Пограничные серверы предоставляют способ расширения возможностей Microsoft Lync Server 2013 для пользователей, которые не вошли во внутреннюю сеть.</span><span class="sxs-lookup"><span data-stu-id="eab68-104">Edge Servers provide a way for you to extend the capabilities of Microsoft Lync Server 2013 to people who are not logged on to your internal network.</span></span> <span data-ttu-id="eab68-105">Например, если у вас есть удаленные пользователи с проверкой подлинности с проверкой подлинности, которые входят в Lync Server 2013 через Интернет, а не через внутреннюю сеть, вам потребуется настроить пограничный сервер, на котором работает пограничная служба доступа Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eab68-105">For example, if you have remote users -- authenticated users who log on to Lync Server 2013 over the Internet rather than through the internal network -- you will need to set up an Edge Server that runs the Lync Server Access Edge service.</span></span> <span data-ttu-id="eab68-106">Кроме того, пограничные серверы необходимы, если вы хотите установить Федерацию с другой организацией или вы хотите предоставить пользователям право на взаимодействие с пользователями, у которых есть учетные записи с общедоступными службами обмена мгновенными\!сообщениями, такими как Yahoo, AOL или MSN.</span><span class="sxs-lookup"><span data-stu-id="eab68-106">Additionally, Edge Servers are required if you want to establish federation with another organization or if you want to give your users the right to communicate with people who have accounts with a public instant messaging service such as Yahoo\!, AOL, or MSN.</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="eab68-107">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="eab68-107">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="eab68-108">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="eab68-108">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="eab68-109">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="eab68-109">Messenger until the service shut down date.</span></span> <span data-ttu-id="eab68-110">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="eab68-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="eab68-111">объявлено.</span><span class="sxs-lookup"><span data-stu-id="eab68-111">has been announced.</span></span> <span data-ttu-id="eab68-112">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="eab68-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="eab68-113">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="eab68-113">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="eab68-114">Messenger.</span><span class="sxs-lookup"><span data-stu-id="eab68-114">Messenger.</span></span> <span data-ttu-id="eab68-115">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="eab68-115">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="eab68-116">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="eab68-116">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="eab68-117">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="eab68-117">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="eab68-118">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="eab68-118">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a><span data-ttu-id="eab68-119">Командлеты пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="eab68-119">Edge Server Cmdlets</span></span>

<span data-ttu-id="eab68-120">Ниже приведен список командлетов, которые относятся непосредственно к управлению пограничными серверами:</span><span class="sxs-lookup"><span data-stu-id="eab68-120">The following is a list of cmdlets that relate directly to managing Edge Servers:</span></span>

<span data-ttu-id="eab68-121">**Пограничный сервер**</span><span class="sxs-lookup"><span data-stu-id="eab68-121">**Edge Server**</span></span>

  - <span></span>  
    <span data-ttu-id="eab68-122">[Get — CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eab68-122">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eab68-123">[Set — CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eab68-123">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eab68-124">[Get — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eab68-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eab68-125">[New — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eab68-125">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eab68-126">[Remove — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eab68-126">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eab68-127">[Set — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eab68-127">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eab68-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eab68-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eab68-129">[Set — Кседжесервер](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eab68-129">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eab68-130">См. также</span><span class="sxs-lookup"><span data-stu-id="eab68-130">See Also</span></span>


[<span data-ttu-id="eab68-131">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="eab68-131">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

