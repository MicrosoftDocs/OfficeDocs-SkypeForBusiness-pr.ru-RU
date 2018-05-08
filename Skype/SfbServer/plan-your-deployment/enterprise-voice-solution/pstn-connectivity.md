---
title: Компоненты для подключения к ТСОП в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Ознакомьтесь с SIP-магистрали и шлюзов ТСОП для корпоративной голосовой связи в Скайп для Business Server.
ms.openlocfilehash: 4f346209b483a3d469beba233bd22ee39e45745a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="pstn-connectivity-components-in-skype-for-business-server-2015"></a><span data-ttu-id="1f525-103">Компоненты для подключения к ТСОП в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="1f525-103">PSTN connectivity components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1f525-104">Ознакомьтесь с SIP-магистрали и шлюзов ТСОП для корпоративной голосовой связи в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="1f525-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="1f525-105">Решение VoIP корпоративного уровня должно предусматривать входящие и исходящие вызовы на телефонную сеть общего пользования (ТСОП) без какого-либо снижения качества обслуживания (QoS).</span><span class="sxs-lookup"><span data-stu-id="1f525-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="1f525-106">Кроме того, при совершении и приеме вызовов пользователи не должны знать об этой базовой технологии.</span><span class="sxs-lookup"><span data-stu-id="1f525-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="1f525-107">С точки зрения пользователя инфраструктурой корпоративной голосовой связи и наоборот PSTN должны показаться любой другой сеанс SIP.</span><span class="sxs-lookup"><span data-stu-id="1f525-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="1f525-108">Для ТСОП-соединений вы можете развернуть либо магистраль SIP, либо шлюз ТСОП (вместе с УАТС, также известной как прямой канал SIP, или без УАТС).</span><span class="sxs-lookup"><span data-stu-id="1f525-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="1f525-109">Транкинг SIP</span><span class="sxs-lookup"><span data-stu-id="1f525-109">SIP Trunking</span></span>

<span data-ttu-id="1f525-110">В качестве альтернативы, используя шлюзы ТСОП решения корпоративной голосовой связи можно подключить к ТСОП с помощью распределения каналов SIP.</span><span class="sxs-lookup"><span data-stu-id="1f525-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="1f525-111">Организация магистральной сети SIP позволяет реализовать следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="1f525-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="1f525-112">Пользователь предприятия за корпоративным брандмауэром или вне его может выполнять местный или дальний (междугородный или международный) вызов, заданный номером, совместимым с форматом E.164, который заканчивается на ТСОП как служба соответствующего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="1f525-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="1f525-113">Любой абонент ТСОП может связываться с пользователем предприятия за пределами корпоративного брандмауэра или вне его, набирая номер прямого входящего набора, связанный с этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="1f525-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="1f525-114">Для использования такого решения по развертыванию необходим поставщик услуг транкинга SIP.</span><span class="sxs-lookup"><span data-stu-id="1f525-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="1f525-115">Шлюзы ТСОП</span><span class="sxs-lookup"><span data-stu-id="1f525-115">PSTN gateways</span></span>

<span data-ttu-id="1f525-116">Шлюзы ТСОП, устройствами сторонних производителей, которые преобразуют сигналы и мультимедиа между инфраструктурой корпоративной голосовой связи и ТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="1f525-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="1f525-117">Шлюзы ТСОП работать с сервера-посредника для представления ТСОП или УАТС звонок клиенту корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="1f525-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="1f525-118">Сервер-посредник также приведены вызовы от клиентов корпоративной голосовой связи ТСОП-шлюз для маршрутизации ТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="1f525-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="1f525-119">Список партнеров, работающие с корпорацией Майкрософт для обеспечения устройств, которые работают с Скайп для Business Server посетите [сайт партнеров объединенных коммуникаций корпорации Майкрософт](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="1f525-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="1f525-120">Станции УАТС</span><span class="sxs-lookup"><span data-stu-id="1f525-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="1f525-121">Если у вас есть существующая инфраструктура голосовой связи, которая использует АТС учреждения (УАТС), можно использовать эту УАТС с корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="1f525-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="1f525-122">Поддерживаемые сценарии интеграции корпоративной голосовой связи с УАТС, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1f525-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="1f525-123">IP-УАТС, поддерживающий обход сервера-посредника, с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="1f525-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="1f525-124">IP-УАТС, которой требуется изолированный шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="1f525-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="1f525-125">УАТС с временным мультиплексированием с изолированным шлюзом ТСОП.</span><span class="sxs-lookup"><span data-stu-id="1f525-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1f525-126">Функция обхода сервера-посредника взаимодействует не со всеми шлюзами ТСОП, IP-PBX и пограничным контроллером SBC.</span><span class="sxs-lookup"><span data-stu-id="1f525-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="1f525-127">Корпорация Майкрософт вместе с сертифицированными партнерами протестировала набор шлюзов ТСОП и пограничных контроллеров сеансов, а также провела с вместе с компанией Cisco тесты УАТС на базе протокола IP.</span><span class="sxs-lookup"><span data-stu-id="1f525-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="1f525-128">Обход сервера-посредника поддерживается только с помощью продуктов и версий приведенный в [Объединенных коммуникаций программы открытого взаимодействия - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span><span class="sxs-lookup"><span data-stu-id="1f525-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="1f525-129">Для получения дополнительных сведений о партнеров, которые предлагают решения для корпоративной голосовой связи посетите [веб-сайт Microsoft Unified Communications партнеров](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="1f525-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="1f525-130">Для получения дополнительных сведений о партнеров, предлагающих решений оборудования для корпоративной голосовой связи, включая шлюзы ТСОП посетите [веб-сайт Microsoft Unified Communications партнеры (en)](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="1f525-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

