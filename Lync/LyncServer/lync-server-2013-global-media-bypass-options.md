---
title: 'Lync Server 2013: глобальные параметры обхода мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ebe39b6faeffd36f0dfc9e25959fe7a0b356153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="e5117-102">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5117-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5117-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="e5117-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5117-104">В этой статье предполагается, что вы уже настроили мультимедиа для всех каналов связи с узлом (коммутируемая телефонная сеть (PSTN), IP-УАТС или контроллером границ сеанса (SBC) для определенного сайта или службы. Вы хотите, чтобы мультимедиа обходило сервер по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="e5117-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="e5117-p101">Кроме включения обхода сервера-посредника для отдельных подключений магистрали, сопоставленных с кэширующим узлом, вам также следует разрешить глобальный обход сервера-посредника. Его параметры могут указывать, что попытка обхода сервера-посредника всегда предпринимается для звонков в ТСОП или что обход сервера-посредника выполняется с помощью сопоставления подсетей областям сети и сетевым узлам, что аналогично другому расширенному голосовому компоненту — контролю допуска звонков. Когда обход сервера-посредника и контроль допуска звонков включены, информация об областях сети, сетевых узлах и подсетях, указанная для контроля допуска звонков, автоматически используется при определении потребности в обходе сервера-посредника. Это означает, что вы не можете указать, что при включенном контроле допуска звонков для звонков в ТСОП всегда предпринимается попытка обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="e5117-p101">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally. Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature. When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass. This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="e5117-109">В этой статье описано, как использовать панель управления Lync Server и командную консоль управления Lync Server для настройки глобальных параметров обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e5117-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5117-110">Когда вы используете эти действия для настройки обхода сервера-посредника, предполагается, что у вас налажено хорошее взаимодействие между клиентами и кэширующим узлом сервера-посредника (например, шлюзом ТСОП, УАТС на базе протокола IP или пограничным контроллером сеансов у поставщика услуг распределения каналов SIP).</span><span class="sxs-lookup"><span data-stu-id="e5117-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="e5117-111">Если для канала связи действуют какие-либо ограничения пропускной способности, применить обход сервера-посредника к звонку нельзя.</span><span class="sxs-lookup"><span data-stu-id="e5117-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="e5117-112">Функция обхода сервера-посредника не взаимодействует с каждым шлюзом ТСОП, УАТС на базе протокола IP и пограничным контроллеров сеансов.</span><span class="sxs-lookup"><span data-stu-id="e5117-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="e5117-113">Корпорация Майкрософт протестировала набор шлюзов ТСОП и контроллеров SBC с сертифицированными партнерами и провела некоторые тесты для Cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e5117-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="e5117-114">Обход мультимедиа поддерживается только в том случае, если у вас есть продукты и версии, указанные в едином приложении <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>для взаимодействия с Open Communications — Lync Server на.</span><span class="sxs-lookup"><span data-stu-id="e5117-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="e5117-115">Дальнейшие действия: выберите глобальные параметры обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e5117-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="e5117-116">После включения функции пропуска на всех магистральных подключениях к одноранговым устройствам для определенных сайтов или служб используйте следующий контент:</span><span class="sxs-lookup"><span data-stu-id="e5117-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="e5117-117">Включить функцию обхода мультимедиа всегда, как описано в разделе [Настройка обхода мультимедиа в Lync Server 2013, чтобы всегда обходить сервер исправлений](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="e5117-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="e5117-118">Вы также можете настроить обход мультимедиа, чтобы использовать сведения о сайте и регионе, как описано в разделе [Настройка обхода мультимедиа в глобальных параметрах Lync Server 2013, чтобы использовать сведения о сайте и регионе](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span><span class="sxs-lookup"><span data-stu-id="e5117-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5117-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e5117-119">See Also</span></span>


[<span data-ttu-id="e5117-120">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5117-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="e5117-121">Связь подсети с сетевым сайтом в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5117-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="e5117-122">Настройка обхода сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5117-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="e5117-123">Сервер-посредник и обход сервера посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5117-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

