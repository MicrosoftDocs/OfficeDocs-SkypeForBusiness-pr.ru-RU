---
title: 'Lync Server 2013: определение области развертывания E9-1-1'
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
ms.openlocfilehash: 96f5ac1fb747a3e64be6cc84c44b390de8ce821c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="27532-102">Определение области развертывания E9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27532-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27532-103">_**Тема последнего изменения:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="27532-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="27532-104">Перед настройкой Microsoft Lync Server 2013 для E9-1-1, вам нужно спланировать E9 развертывание 1-1.</span><span class="sxs-lookup"><span data-stu-id="27532-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="27532-105">Ниже приведены некоторые из тех вопросов, которые требуется рассмотреть.</span><span class="sxs-lookup"><span data-stu-id="27532-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="27532-106">**В чем заключаются политика и правовые обязательства вашей организации в отношении E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="27532-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="27532-107">Правовые требования E9-1-1 для УАТС (которые в терминах E9-1-1 называются многоканальными телефонными системами (MLTS)) в каждом штате свои.</span><span class="sxs-lookup"><span data-stu-id="27532-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="27532-108">Чтобы понять обязательства, которые могут быть применимы к развертыванию Lync Server в ваших географических регионах, вы должны обратиться в компанию с юридическими специалистами.</span><span class="sxs-lookup"><span data-stu-id="27532-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="27532-109">**Какие области на предприятии должны подпадать под действие E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="27532-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="27532-p103">Вы можете реализовать E9-1-1 для всего предприятия или только для отдельных областей. Например, вы можете предъявлять различные требования E9-1-1 для офисов в разных штатах или можете захотеть исключить объекты за пределами США.</span><span class="sxs-lookup"><span data-stu-id="27532-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="27532-112">**Как вы будете осуществлять развертывание E9-1-1 на сайтах филиалов?**</span><span class="sxs-lookup"><span data-stu-id="27532-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="27532-113">При развертывании E9-1-1 на сайте филиала важно понимать концепцию устойчивости голосовых решений.</span><span class="sxs-lookup"><span data-stu-id="27532-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="27532-114">Если у вас есть централизованные магистральные магистрали E-9-1-1 и отключена Глобальная сеть, то при входе в систему клиенты, которым не удается получить доступ к сведениям о расположении или к поставщику служб экстренной помощи, могут быть не доступны.</span><span class="sxs-lookup"><span data-stu-id="27532-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="27532-115">Lync Server предоставляет несколько стратегий для обработки устойчивости голоса в филиалах, в том числе для обеспечения устойчивых сетей обработки данных, развертывания магистрали SIP на каждой ветви или отправки экстренных вызовов на локальный шлюз во время бездействия.</span><span class="sxs-lookup"><span data-stu-id="27532-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="27532-116">Подробности можно найти [в разделе Планирование обеспечения устойчивости голосовой связи на сайте в Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="27532-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="27532-117">**Предоставлять ли доступ к E9-1-1 людям, работающим за пределами сети?**</span><span class="sxs-lookup"><span data-stu-id="27532-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="27532-118">Автоматическое получение сведений о расположении доступно только для клиентов, расположенных в сети организации, поэтому организациям нужно решить, будет ли она поддерживать вызовы E9 1-1 из клиентов Lync, не применяя локальные.</span><span class="sxs-lookup"><span data-stu-id="27532-118">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises.</span></span> <span data-ttu-id="27532-119">Например, разрешите ли Вы выполнять экстренные звонки пользователям, если они работают дома или на объекте клиента?</span><span class="sxs-lookup"><span data-stu-id="27532-119">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="27532-120">Если клиент находится за пределами корпоративной сети, его можно настроить на запрос расположения у пользователя.</span><span class="sxs-lookup"><span data-stu-id="27532-120">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="27532-121">Однако, поскольку такие указанные пользователями расположения нельзя предварительно проверить по Master Street Address Guide (MSAG), диспетчеру поставщика услуг экстренных служб потребуется получить устное подтверждение правильности расположения у звонящего перед перенаправлением звонка в службу общественной безопасности (PSAP).</span><span class="sxs-lookup"><span data-stu-id="27532-121">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="27532-122">Клиенты Lync для пользователей, которые подключаются к сети Организации с помощью VPN, могут получить сведения о внутреннем IP-адресе, но так как эти адреса нельзя использовать для определения фактического местоположения пользователя, важно, чтобы подсети VPN были исключены из Служба сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="27532-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="27532-123">**Хотите ли вы предоставлять маршрутизацию экстренных звонков на сайты за пределами США?**</span><span class="sxs-lookup"><span data-stu-id="27532-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="27532-p106">Вам может потребоваться предоставлять маршрутизацию экстренных звонков в те области Вашей компании, которые не обслуживаются поставщиком услуг экстренных служб (например, объекты в других странах). Для этого создайте новый сайт и затем назначьте политики голосовой связи сайтам, которые ссылаются на использование ТСОП для перенаправления звонка через локальный шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="27532-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

