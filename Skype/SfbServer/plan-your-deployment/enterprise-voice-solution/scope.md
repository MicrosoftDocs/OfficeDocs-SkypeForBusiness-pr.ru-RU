---
title: Определение области развертывания E9-1-1 в Скайп для Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Решения, необходимые для планирования развертывания E9-1-1 в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 014ef9a07679341a7d5eada4ecbad382a9576b61
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206482"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="d2708-103">Определение области развертывания E9-1-1 в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="d2708-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="d2708-104">Решения, необходимые для планирования развертывания E9-1-1 в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="d2708-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="d2708-105">Перед настройкой Скайп для бизнеса для E9-1-1 необходимо спланировать развертывание E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d2708-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="d2708-106">Ниже приведены некоторые из тех вопросов, которые требуется рассмотреть.</span><span class="sxs-lookup"><span data-stu-id="d2708-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="d2708-107">**Что такое политика и правовые обязательства по отношению к E9-1-1 вашей организации?**</span><span class="sxs-lookup"><span data-stu-id="d2708-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="d2708-108">Правовые требования E9-1-1 для УАТС (которые в терминах E9-1-1 называются многоканальными телефонными системами (MLTS)) в каждом штате свои.</span><span class="sxs-lookup"><span data-stu-id="d2708-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="d2708-109">Следует ознакомиться с юридическим команде увидеть обязательства, которые могут относиться к развертыванию Скайп для бизнеса в соответствующих странах.</span><span class="sxs-lookup"><span data-stu-id="d2708-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="d2708-110">**Какие области на предприятии должны подпадать под действие E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="d2708-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="d2708-p103">Вы можете реализовать E9-1-1 для всего предприятия или только для отдельных областей. Например, вы можете предъявлять различные требования E9-1-1 для офисов в разных штатах или можете захотеть исключить объекты за пределами США.</span><span class="sxs-lookup"><span data-stu-id="d2708-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="d2708-113">**Как вы будете осуществлять развертывание E9-1-1 на сайтах филиалов?**</span><span class="sxs-lookup"><span data-stu-id="d2708-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="d2708-114">При развертывании E9-1-1 на сайте филиала важно понимать концепцию устойчивости голосовых решений.</span><span class="sxs-lookup"><span data-stu-id="d2708-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="d2708-115">Если централизованного магистралей SIP-E-9-1-1 и возникает ГЛОБАЛЬНОЙ сети, клиенты, вход в может отсутствовать для получения расположение из службы сведения о расположении или для подключения к поставщику услуг экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="d2708-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="d2708-116">Скайп для бизнеса предоставляет несколько стратегий для обработки устойчивости голосовой связи в филиалах, в том числе: необходимости устойчивое данных сетей, развертывание магистраль SIP в каждой ветки или внедряет экстренных вызовов на локальный шлюз во время простоев.</span><span class="sxs-lookup"><span data-stu-id="d2708-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="d2708-117">Более подробно см. в разделе [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span><span class="sxs-lookup"><span data-stu-id="d2708-117">For details, see [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>

 <span data-ttu-id="d2708-118">**Предоставлять ли доступ к E9-1-1 людям, работающим за пределами сети?**</span><span class="sxs-lookup"><span data-stu-id="d2708-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="d2708-119">Расположение автоматического приобретения доступен только для клиентов, расположенных внутри сети организации, поэтому вашей организации необходимо определить, поддерживает ли он вызовов E9-1-1 из Скайп для пользователей во время выключить локальный.</span><span class="sxs-lookup"><span data-stu-id="d2708-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="d2708-120">Например, разрешите ли Вы выполнять экстренные звонки пользователям, если они работают дома или на объекте клиента?</span><span class="sxs-lookup"><span data-stu-id="d2708-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="d2708-121">Если клиент находится за пределами корпоративной сети, его можно настроить на запрос расположения у пользователя.</span><span class="sxs-lookup"><span data-stu-id="d2708-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="d2708-122">Однако, поскольку такие указанные пользователями расположения нельзя предварительно проверить по Master Street Address Guide (MSAG), диспетчеру поставщика услуг экстренных служб потребуется получить устное подтверждение правильности расположения у звонящего перед перенаправлением звонка в службу общественной безопасности (PSAP).</span><span class="sxs-lookup"><span data-stu-id="d2708-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="d2708-123">Скайп пользователей пользователей, которые подключаются к сети организации с помощью виртуальной частной сети могут отвечать внутреннего IP-адресе, но так как эти адреса не может использоваться для идентификации фактический адрес пользователя, необходимо исключить подсети VPN из службы сведения о расположении.</span><span class="sxs-lookup"><span data-stu-id="d2708-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="d2708-124">**Хотите ли вы предоставлять маршрутизацию экстренных звонков на сайты за пределами США?**</span><span class="sxs-lookup"><span data-stu-id="d2708-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="d2708-p106">Вам может потребоваться предоставлять маршрутизацию экстренных звонков в те области Вашей компании, которые не обслуживаются поставщиком услуг экстренных служб (например, объекты в других странах). Для этого создайте новый сайт и затем назначьте политики голосовой связи сайтам, которые ссылаются на использование ТСОП для перенаправления звонка через локальный шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="d2708-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>


