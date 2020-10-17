---
title: 'Lync Server 2013: определение области развертывания E9 – 1 – 1'
description: 'Lync Server 2013: определение области развертывания E9 – 1 – 1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14e442718b7230dbc94aebdf6099aae9b430d5e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567541"
---
# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="1e55c-103">Определение области развертывания E9 – 1 – 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e55c-103">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e55c-104">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="1e55c-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="1e55c-105">Перед настройкой Microsoft Lync Server 2013 для E9 – 1 – 1 необходимо спланировать развертывание E9 – 1 – 1.</span><span class="sxs-lookup"><span data-stu-id="1e55c-105">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="1e55c-106">Ниже приведены некоторые из тех вопросов, которые требуется рассмотреть:</span><span class="sxs-lookup"><span data-stu-id="1e55c-106">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="1e55c-107">**В чем заключаются политика и правовые обязательства вашей организации в отношении E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="1e55c-107">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="1e55c-108">Правовые требования E9-1-1 для УАТС (которые в терминах E9-1-1 называются многоканальными телефонными системами (MLTS)) отличаются в разных штатах.</span><span class="sxs-lookup"><span data-stu-id="1e55c-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="1e55c-109">Вы должны получить сведения о обязательствах, которые могут применяться к развертыванию Lync Server в соответствующих географических регионах.</span><span class="sxs-lookup"><span data-stu-id="1e55c-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="1e55c-110">**Какие области на предприятии должны подпадать под действие E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="1e55c-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="1e55c-p103">Вы можете реализовать E9-1-1 для всего предприятия или только для отдельных областей. Например, вы можете предъявлять различные требования E9-1-1 для офисов в разных штатах или можете захотеть исключить объекты за пределами США.</span><span class="sxs-lookup"><span data-stu-id="1e55c-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="1e55c-113">**Как вы будете осуществлять развертывание E9-1-1 на сайтах филиалов?**</span><span class="sxs-lookup"><span data-stu-id="1e55c-113">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="1e55c-114">При развертывании E9-1-1 на сайте филиала важно понимать концепцию устойчивости голосовых решений.</span><span class="sxs-lookup"><span data-stu-id="1e55c-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="1e55c-115">При наличии централизованных магистральных магистральных каналов E – 9-1-1 и отключения глобальной сети клиенты, которые могут войти в систему, могут не получить сведений о расположении из службы сведений о местоположении или подключиться к поставщику услуг экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="1e55c-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="1e55c-116">Lync Server предоставляет несколько стратегий для обработки устойчивости голосовой связи в филиалах, в том числе: имеются отказоустойчивые сети данных, развертывание магистрали SIP в каждой ветви или передача экстренных вызовов на локальный шлюз во время простоя.</span><span class="sxs-lookup"><span data-stu-id="1e55c-116">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="1e55c-117">Дополнительные сведения см. [в статье Планирование устойчивости голосовой связи для сайта филиала в Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="1e55c-117">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="1e55c-118">**Предоставлять ли доступ к E9-1-1 людям, работающим за пределами сети?**</span><span class="sxs-lookup"><span data-stu-id="1e55c-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="1e55c-p105">Автоматическое получение сведений о расположении доступно только для клиентов, расположенных внутри сети организации, поэтому необходимо решить, будет ли организация поддерживать звонки E9-1-1, сделанные из нелокальных клиентов Lync. Например, разрешите ли вы выполнять экстренные звонки пользователям, если они работают дома или на объекте клиента? Если клиент находится за пределами корпоративной сети, его можно настроить на запрос расположения у пользователя. Однако поскольку такие указанные пользователями расположения нельзя предварительно проверить по Master Street Address Guide (MSAG), диспетчеру поставщика услуг экстренных служб потребуется устно подтвердить правильность расположения у звонящего перед перенаправлением звонка в службу общественной безопасности (PSAP).</span><span class="sxs-lookup"><span data-stu-id="1e55c-p105">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises. For example, will you enable users to place emergency calls if they are working from home or from a customer site? If a client is located outside the enterprise network, the client can be configured to prompt the user for a location. However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1e55c-123">Клиенты Lync для пользователей, которые подключаются к сети Организации с помощью VPN, могут получить сведения о внутреннем IP-адресе, но так как эти адреса не могут использоваться для определения фактического расположения пользователя, то важно, чтобы подсети VPN были исключены из службы сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="1e55c-123">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="1e55c-124">**Хотите ли вы предоставлять маршрутизацию экстренных звонков на сайты за пределами США.?**</span><span class="sxs-lookup"><span data-stu-id="1e55c-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="1e55c-p106">Вам может потребоваться предоставлять маршрутизацию экстренных звонков в те области вашей компании, которые не обслуживаются поставщиком услуг экстренных служб (например, объекты в других странах). Для этого создайте новый сайт и затем назначьте политики голосовой связи сайтам, которые ссылаются использование ТСОП для перенаправления звонка через локальный шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="1e55c-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

