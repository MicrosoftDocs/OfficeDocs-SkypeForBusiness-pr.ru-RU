---
title: Компоненты подключения PSTN в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Узнайте о том, как звонить по протоколу SIP, а также шлюзы PSTN для корпоративной голосовой связи в Skype для бизнеса Server.
ms.openlocfilehash: 443f5425beeed5b032968837ac56ce3a26468cdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802539"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="0d893-103">Компоненты подключения PSTN в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0d893-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="0d893-104">Узнайте о том, как звонить по протоколу SIP, а также шлюзы PSTN для корпоративной голосовой связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0d893-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="0d893-105">Решение VoIP корпоративного уровня должно предусматривать входящие и исходящие вызовы на телефонную сеть общего пользования (ТСОП) без какого-либо снижения качества обслуживания (QoS).</span><span class="sxs-lookup"><span data-stu-id="0d893-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="0d893-106">Кроме того, при совершении и приеме вызовов пользователи не должны знать об этой базовой технологии.</span><span class="sxs-lookup"><span data-stu-id="0d893-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="0d893-107">С точки зрения пользователя, Звонок между корпоративной инфраструктурой голосовой связи и PSTN должен казаться всего, как один сеанс SIP.</span><span class="sxs-lookup"><span data-stu-id="0d893-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="0d893-108">Для ТСОП-соединений вы можете развернуть либо магистраль SIP, либо шлюз ТСОП (вместе с УАТС, также известной как прямой канал SIP, или без УАТС).</span><span class="sxs-lookup"><span data-stu-id="0d893-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="0d893-109">Транкинг SIP</span><span class="sxs-lookup"><span data-stu-id="0d893-109">SIP Trunking</span></span>

<span data-ttu-id="0d893-110">В качестве альтернативы шлюзам PSTN вы можете подключить корпоративную голосовую связь к сети PSTN с помощью магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="0d893-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="0d893-111">Организация магистральной сети SIP позволяет реализовать следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="0d893-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="0d893-112">Пользователь предприятия за корпоративным брандмауэром или вне его может выполнять местный или дальний (междугородный или международный) вызов, заданный номером, совместимым с форматом E.164, который заканчивается на ТСОП как служба соответствующего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="0d893-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="0d893-113">Любой абонент ТСОП может связываться с пользователем предприятия за пределами корпоративного брандмауэра или вне его, набирая номер прямого входящего набора, связанный с этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="0d893-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="0d893-114">Для использования такого решения по развертыванию необходим поставщик услуг транкинга SIP.</span><span class="sxs-lookup"><span data-stu-id="0d893-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="0d893-115">Шлюзы ТСОП</span><span class="sxs-lookup"><span data-stu-id="0d893-115">PSTN gateways</span></span>

<span data-ttu-id="0d893-116">Шлюзы PSTN – это сторонние устройства, которые преобразуют сигналы и носители между корпоративной инфраструктурой голосовой связи и PSTN или УАТС.</span><span class="sxs-lookup"><span data-stu-id="0d893-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="0d893-117">Шлюзы PSTN работают с сервером-посредником, чтобы представлять вызов по сети PSTN или УАТС в клиенте голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0d893-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="0d893-118">Сервер, на котором выводятся сведения о клиентах, также предоставляет шлюзу PSTN Услуги для маршрутизации в КТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="0d893-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="0d893-119">Список партнеров, работающих с корпорацией Майкрософт, для предоставления устройств, которые работают с приложением Skype для бизнеса Server, можно найти [на веб-сайте Microsoft Unified Communications Partner](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="0d893-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="0d893-120">Станции УАТС</span><span class="sxs-lookup"><span data-stu-id="0d893-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="0d893-121">Если у вас есть существующая инфраструктура голосовой связи, использующая АТС, вы можете использовать АТС с корпоративной телефонной связью.</span><span class="sxs-lookup"><span data-stu-id="0d893-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="0d893-122">Поддерживаются следующие сценарии интеграции с корпоративной голосовой АТС.</span><span class="sxs-lookup"><span data-stu-id="0d893-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="0d893-123">IP-УАТС, поддерживающая обход мультимедиа, для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="0d893-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="0d893-124">IP-УАТС, которой требуется изолированный шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="0d893-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="0d893-125">УАТС с временным мультиплексированием с изолированным шлюзом ТСОП.</span><span class="sxs-lookup"><span data-stu-id="0d893-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0d893-126">Функция обхода сервера-посредника взаимодействует не со всеми шлюзами ТСОП, IP-PBX и пограничным контроллером SBC.</span><span class="sxs-lookup"><span data-stu-id="0d893-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="0d893-127">Корпорация Майкрософт протестировала набор шлюзов ТСОП и контроллеров SBC с сертифицированными партнерами и провела некоторые тесты для Cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="0d893-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="0d893-128">Обход мультимедиа поддерживается только в том случае, если у вас есть продукты и версии, указанные в [едином приложении для взаимодействия с открытым взаимодействием — Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span><span class="sxs-lookup"><span data-stu-id="0d893-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="0d893-129">Подробные сведения о партнерах, предлагающих решения для предприятий, можно найти на [веб-сайте Microsoft Unified Communications Partner](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="0d893-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="0d893-130">Сведения о партнерах, предлагающих корпоративные аппаратные решения для предприятий, включая шлюзы PSTN, можно найти на [веб-сайте Microsoft Unified Communications Partner](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="0d893-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

