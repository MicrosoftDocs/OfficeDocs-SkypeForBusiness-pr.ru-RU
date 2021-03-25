---
title: Компоненты подключения к PSTN в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Узнайте о магистральных шлюзах SIP и PSTN для Корпоративная голосовая связь в Skype для бизнеса Server.
ms.openlocfilehash: 402aa365556ef52d135c3ee6c0a2e36e9bd2e780
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114625"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="4c7cb-103">Компоненты подключения к PSTN в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4c7cb-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="4c7cb-104">Узнайте о магистральных шлюзах SIP и PSTN для Корпоративная голосовая связь в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="4c7cb-p101">Решение VoIP корпоративного уровня должно обеспечивать вызовы в телефонную сеть общего пользования (ТСОП) и обратно без ухудшения качества обслуживания (QoS). Кроме того, пользователи не должны беспокоиться о выбранной технологии, когда размещают или получают вызовы. С точки зрения пользователя, вызовы между инфраструктурой корпоративной голосовой связи и ТСОП должны выглядеть в точности, как любой другой сеанс SIP.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-p101">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS). In addition, users should not be aware of the underlying technology when they place and receive calls. From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="4c7cb-108">Для подключений ТСОП можно развернуть либо распределение каналов SIP, либо шлюз ТСОП (с УАТС, также называемой прямой связью SIP, или без УАТС).</span><span class="sxs-lookup"><span data-stu-id="4c7cb-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="4c7cb-109">Распределение каналов SIP</span><span class="sxs-lookup"><span data-stu-id="4c7cb-109">SIP Trunking</span></span>

<span data-ttu-id="4c7cb-p102">Помимо использования шлюзов ТСОП, решение корпоративной голосовой связи можно подключать к ТСОП путем распределения каналов SIP. Распределение каналов SIP позволяет следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-p102">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking. SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="4c7cb-112">Пользователь предприятия за корпоративным брандмауэром или вне его может выполнять местный или дальний (междугородный или международный) вызов, заданный номером, совместимым с форматом E.164, который заканчивается в ТСОП как служба соответствующего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="4c7cb-113">Любой абонент ТСОП может связываться с пользователем предприятия за пределами корпоративного брандмауэра или вне его, набирая номер прямого входящего набора, связанный с этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="4c7cb-114">Для использования такого решения по развертыванию необходим поставщик услуг распределения каналов SIP.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="4c7cb-115">Шлюзы ТСОП</span><span class="sxs-lookup"><span data-stu-id="4c7cb-115">PSTN gateways</span></span>

<span data-ttu-id="4c7cb-116">Шлюзы ТСОП — это устройства сторонних производителей, которые передают сигналы и мультимедиа между инфраструктурой корпоративной голосовой связи и ТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="4c7cb-117">Шлюзы ТСОП работают с сервером-посредником, чтобы представить вызов ТСОП или УАТС клиенту корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="4c7cb-118">Сервер-посредник также представляет вызовы клиентов корпоративной голосовой связи в шлюз ТСОП для маршрутизации в ТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="4c7cb-119">Список партнеров, которые работают с Корпорацией Майкрософт по предоставлению устройств, которые работают с Skype для бизнеса Server, см. на сайте [Microsoft Unified Communications Partners.](https://go.microsoft.com/fwlink/p/?linkId=202836)</span><span class="sxs-lookup"><span data-stu-id="4c7cb-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="4c7cb-120">Станции УАТС</span><span class="sxs-lookup"><span data-stu-id="4c7cb-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="4c7cb-121">Если у вас есть существующая голосовая инфраструктура, использующая частный обмен филиалами (PBX), вы можете использовать PBX с помощью Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="4c7cb-122">Поддерживаются следующие сценарии интеграции корпоративной голосовой связи с УАТС:</span><span class="sxs-lookup"><span data-stu-id="4c7cb-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="4c7cb-123">IP-УАТС, поддерживающий обход сервера-посредника, с сервером-посредником;</span><span class="sxs-lookup"><span data-stu-id="4c7cb-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="4c7cb-124">IP-УАТС, которому требуется изолированный шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="4c7cb-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="4c7cb-125">УАТС с временным мультиплексированием с изолированным шлюзом ТСОП.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4c7cb-126">Обход сервера-посредника не будет взаимодействовать с каждым шлюзом ТСОП, IP-УАТС и SBC.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="4c7cb-127">Корпорация Майкрософт протестировала ряд шлюзов ТСОП и SBC с сертифицированными партнерами и выполнила некоторые тесты с IP-УАТС компании Cisco.</span><span class="sxs-lookup"><span data-stu-id="4c7cb-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="4c7cb-128">Обход мультимедиа поддерживается только продуктами и версиями, перечисленными в программе open [interoperability Unified Communications - Lync Server.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)</span><span class="sxs-lookup"><span data-stu-id="4c7cb-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).</span></span> 
  
<span data-ttu-id="4c7cb-129">Сведения о партнерах, Корпоративная голосовая связь решениях, см. на сайте [Microsoft Unified Communications Partners.](https://go.microsoft.com/fwlink/p/?linkId=202836)</span><span class="sxs-lookup"><span data-stu-id="4c7cb-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="4c7cb-130">Подробные сведения о партнерах, Корпоративная голосовая связь аппаратных решениях, включая шлюзы PSTN, см. на сайте [Microsoft Unified Communications Partners.](https://go.microsoft.com/fwlink/p/?linkId=202836)</span><span class="sxs-lookup"><span data-stu-id="4c7cb-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
