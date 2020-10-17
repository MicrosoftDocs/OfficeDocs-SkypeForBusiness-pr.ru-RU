---
title: 'Lync Server 2013: глобальные параметры обхода сервера мультимедиа'
description: 'Lync Server 2013: глобальные параметры обхода сервера мультимедиа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e69a776c13171d74666a202108fa4b5c72e224d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554555"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="a8daa-103">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8daa-103">Global media bypass options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8daa-104">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="a8daa-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8daa-105">В этом разделе предполагается, что вы уже настроили обход сервера-посредника для всех магистральных линий на одноранговом узле (шлюз телефонной сети общего пользования (PSTN), IP-УАТС или пограничный контроллер сеансов (SBC) в поставщике услуг Интернет-телефонии) для определенного сайта или службы, для которых требуется, чтобы носители обходили сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="a8daa-105">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="a8daa-106">Кроме включения обхода сервера мультимедиа для отдельных магистральных подключений, связанных с одноранговым узлом, необходимо также включить обход сервера мультимедиа глобально.</span><span class="sxs-lookup"><span data-stu-id="a8daa-106">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="a8daa-107">Глобальные параметры обхода сервера-посредника могут указать, что обход сервера-посредника всегда выполняется для вызовов PSTN, или этот обход сервера-посредника используется с помощью сопоставления подсетей с сетевыми сайтами и областями сети, аналогично тому, как это делается с помощью контроля допуска звонков, еще одной дополнительной функции голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a8daa-107">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="a8daa-108">Если включен режим обхода сервера-посредника и контроль допуска звонков, то при определении того, следует ли использовать обход сервера-посредника, автоматически используется область сети, сетевой сайт и сведения о подсети, указанные для контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="a8daa-108">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="a8daa-109">Это означает, что вы не можете указать, что обход сервера-посредника всегда выполняется для звонков в PSTN при включенном контроле допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="a8daa-109">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="a8daa-110">В этом разделе описывается, как использовать панель управления Lync Server и Командная консоль Lync Server совместно для настройки глобальных параметров обхода сервера мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="a8daa-110">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8daa-111">При использовании этих действий для настройки обхода сервера-посредника предполагается, что у вас есть хорошее соединение между клиентами и одноранговым сервером-посредником (например, шлюз PSTN, IP-УАТС или SBC в поставщике распределения каналов SIP).</span><span class="sxs-lookup"><span data-stu-id="a8daa-111">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="a8daa-112">Если для ссылки существуют ограничения пропускной способности, обход сервера не может быть применен к вызову.</span><span class="sxs-lookup"><span data-stu-id="a8daa-112">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="a8daa-113">Обход сервера-посредника не будет взаимодействовать с каждым шлюзом ТСОП, IP-УАТС и SBC.</span><span class="sxs-lookup"><span data-stu-id="a8daa-113">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="a8daa-114">Корпорация Майкрософт протестировала ряд шлюзов ТСОП и SBC с сертифицированными партнерами и выполнила некоторые тесты с IP-УАТС компании Cisco.</span><span class="sxs-lookup"><span data-stu-id="a8daa-114">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="a8daa-115">Обход сервера-посредника поддерживается только для продуктов и версий, перечисленных в общедоступной программе для взаимодействия с единой системой обмена сообщениями — Lync Server по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="a8daa-115">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="a8daa-116">Дальнейшие действия: выберите глобальные параметры обхода сервера мультимедиа</span><span class="sxs-lookup"><span data-stu-id="a8daa-116">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="a8daa-117">После включения обхода сервера-посредника для любых подключений магистрали к одноранговому узлу для определенных сайтов или служб используйте следующий контент:</span><span class="sxs-lookup"><span data-stu-id="a8daa-117">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="a8daa-118">Разрешить обход сервера-посредника всегда, как описано в разделе [Настройка обхода сервера-посредника в Lync Server 2013, чтобы всегда обходить сервер-посредник](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="a8daa-118">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="a8daa-119">Или настройте обход сервера-посредника, чтобы использовать сведения о сайте и регионе, как описано в разделе [Configure обход сервера-посредника в глобальных параметрах Lync Server 2013, чтобы использовать сведения о сайтах и регионах](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span><span class="sxs-lookup"><span data-stu-id="a8daa-119">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a8daa-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a8daa-120">See Also</span></span>


[<span data-ttu-id="a8daa-121">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8daa-121">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="a8daa-122">Связывание подсети с сетевым сайтом в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8daa-122">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="a8daa-123">Настройка обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8daa-123">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="a8daa-124">Обход сервера-посредника и сервер-посредник в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8daa-124">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

