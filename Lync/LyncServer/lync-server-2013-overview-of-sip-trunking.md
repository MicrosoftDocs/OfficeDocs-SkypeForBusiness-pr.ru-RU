---
title: 'Lync Server 2013: обзор распределения каналов SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbf29b02af831f82050e9a032a35f0fa57c1eb1e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="4e177-102">Обзор распределения каналов SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e177-102">Overview of SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e177-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="4e177-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="4e177-p101">Развертывание SIP-магистралей — важный шаг на пути к упрощению телекоммуникационных систем в пределах организации и подготовке к внедрению инноваций для связи в режиме реального времени. Одним из основных преимуществ SIP-магистралей является возможность консолидации подключений организации к ТСОП на центральном сайте, в отличие от устаревших TDM-магистралей, для которых обычно требовалась отдельная магистраль от каждого сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="4e177-p101">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications. One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="4e177-106">SIP-магистрали в Lync Server</span><span class="sxs-lookup"><span data-stu-id="4e177-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="4e177-107">Возможности распределения каналов SIP Lync Server 2013 обеспечивают следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="4e177-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="4e177-108">Пользователь предприятия, как в пределах или за пределами корпоративного брандмауэра, может совершать местные или междугородные звонки, указанные E.164-совместимым номером, который завершаются в ТСОП как услуга соответствующего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="4e177-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="4e177-109">Любой абонент ТСОП может связаться с пользователем предприятия внутри или за пределами корпоративного брандмауэра, набрав номер DID, связанный с этим пользователем предприятия.</span><span class="sxs-lookup"><span data-stu-id="4e177-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="4e177-110">Экономия средств</span><span class="sxs-lookup"><span data-stu-id="4e177-110">Cost Savings</span></span>

<span data-ttu-id="4e177-111">SIP-магистрали обеспечивают существенную экономию.</span><span class="sxs-lookup"><span data-stu-id="4e177-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="4e177-112">Междугородные вызовы обычно гораздо дешевле при использовании SIP-магистралей.</span><span class="sxs-lookup"><span data-stu-id="4e177-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="4e177-113">Вы можете сократить расходы на управление и упростить развертывание.</span><span class="sxs-lookup"><span data-stu-id="4e177-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="4e177-p102">Комиссий за интерфейсы BRI и PRI можно избежать, если подключить SIP-магистраль напрямую к поставщику услуг Интернет-телефонии по значительно меньшей цене. В устаревших TDM-магистралях вызовы тарифицировались поставщиками услуг на поминутной основе. Затраты на SIP-магистрали рассчитываются в зависимости от объема использования пропускной полосы канала, которую можно покупать небольшими порциями, что более экономично. Фактические расходы зависят от модели обслуживания, предложенной вашим поставщиком.</span><span class="sxs-lookup"><span data-stu-id="4e177-p102">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost. In TDM trunking, service providers charge for calls by the minute. The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments. (The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="4e177-118">Сравнение SIP-магистралей и размещение шлюза ТСОП или IP-УАТС</span><span class="sxs-lookup"><span data-stu-id="4e177-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="4e177-p103">Поскольку SIP-­магистрали напрямую подключаются к вашему поставщику услуг, вы можете устранить шлюзы ТСОП и избежать затрат на управление ими, а также упростить процедуру управления. Использование SIP-магистрали может обеспечить значительную экономию средств за счет упрощения процессов технического обслуживания и администрирования.</span><span class="sxs-lookup"><span data-stu-id="4e177-p103">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity. Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="4e177-121">Расширенные услуги VoIP</span><span class="sxs-lookup"><span data-stu-id="4e177-121">Expanded VoIP Services</span></span>

<span data-ttu-id="4e177-122">Развертывание SIP-магистралей зачастую осуществляется ради функций голосовой, однако, поддержка голосовой связи — только первый этап.</span><span class="sxs-lookup"><span data-stu-id="4e177-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="4e177-123">С помощью магистрали SIP можно расширить возможности VoIP и включить Lync Server 2013 для предоставления более обширного набора служб.</span><span class="sxs-lookup"><span data-stu-id="4e177-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="4e177-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="4e177-124">For example:</span></span>

  - <span data-ttu-id="4e177-125">Расширенное обнаружение присутствия для устройств, на которых не установлен Lync Server 2013, обеспечивает лучшую интеграцию с мобильными телефонами, что позволяет видеть, когда пользователь наведет на мобильный телефон.</span><span class="sxs-lookup"><span data-stu-id="4e177-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="4e177-126">экстренные вызовы E9-1-1 позволяет органам, отвечающим на экстренные вызовы по номеру 911, определять местоположение вызывающего абонента по номеру телефона;</span><span class="sxs-lookup"><span data-stu-id="4e177-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e177-127">обратитесь к поставщику услуг Интернет-телефонии для получения списка поддерживаемых и доступных услуг для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4e177-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

