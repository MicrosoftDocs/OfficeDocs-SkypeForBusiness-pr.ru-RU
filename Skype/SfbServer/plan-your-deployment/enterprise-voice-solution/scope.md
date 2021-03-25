---
title: Определение области развертывания E9-1-1 в Skype для бизнеса Server
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
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Решения, необходимые для планирования развертывания E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 39397064fe525a2b1324b8ef0a0f0bb1df287653
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114575"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="5fa73-103">Определение области развертывания E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5fa73-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="5fa73-104">Решения, необходимые для планирования развертывания E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="5fa73-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="5fa73-105">Перед настройкой Skype для бизнеса для E9-1-1 необходимо спланировать развертывание E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="5fa73-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="5fa73-106">Ниже приведены некоторые из тех вопросов, которые требуется рассмотреть:</span><span class="sxs-lookup"><span data-stu-id="5fa73-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="5fa73-107">**Каковы политики и юридические обязательства вашей организации в отношении E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="5fa73-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="5fa73-108">Правовые требования E9-1-1 для УАТС (которые в терминах E9-1-1 называются многоканальными телефонными системами (MLTS)) отличаются в разных штатах.</span><span class="sxs-lookup"><span data-stu-id="5fa73-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="5fa73-109">Вы должны проконсультироваться со своей юридической командой, чтобы понять обязательства, которые могут применяться к развертыванию Skype для бизнеса в соответствующих географических регионах.</span><span class="sxs-lookup"><span data-stu-id="5fa73-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="5fa73-110">**Какие области на предприятии должны подпадать под действие E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="5fa73-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="5fa73-p103">Вы можете реализовать E9-1-1 для всего предприятия или только для отдельных областей. Например, вы можете предъявлять различные требования E9-1-1 для офисов в разных штатах или можете захотеть исключить объекты за пределами США.</span><span class="sxs-lookup"><span data-stu-id="5fa73-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="5fa73-113">**Как вы будете осуществлять развертывание E9-1-1 на сайтах филиалов?**</span><span class="sxs-lookup"><span data-stu-id="5fa73-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="5fa73-114">При развертывании E9-1-1 на сайте филиала важно понимать концепцию устойчивости голосовых решений.</span><span class="sxs-lookup"><span data-stu-id="5fa73-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="5fa73-115">Если у вас есть централизованные магистрали SIP E-9-1-1 и происходит отключение WAN, клиенты, входив в него, не смогут получить расположение от службы информации о расположении или подключиться к поставщику экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="5fa73-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="5fa73-116">Skype для бизнеса предоставляет несколько стратегий для обработки голосовой устойчивости в филиалах, в том числе: наличие устойчивых сетей данных, развертывание магистрали SIP в каждом филиале или вызов экстренной ситуации на локальный шлюз во время отключений.</span><span class="sxs-lookup"><span data-stu-id="5fa73-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="5fa73-117">Дополнительные сведения см. в разделе [Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).</span><span class="sxs-lookup"><span data-stu-id="5fa73-117">For details, see [Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).</span></span>

 <span data-ttu-id="5fa73-118">**Предоставлять ли доступ к E9-1-1 людям, работающим за пределами сети?**</span><span class="sxs-lookup"><span data-stu-id="5fa73-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="5fa73-119">Автоматическое приобретение расположения доступно только для клиентов, расположенных в сети организации, поэтому вашей организации необходимо решить, будет ли она поддерживать вызовы E9-1-1, сделанные из клиентов Skype для бизнеса, находясь вне помещения.</span><span class="sxs-lookup"><span data-stu-id="5fa73-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="5fa73-120">Например, разрешите ли вы выполнять экстренные звонки пользователям, если они работают дома или на объекте клиента?</span><span class="sxs-lookup"><span data-stu-id="5fa73-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="5fa73-121">Если клиент находится за пределами корпоративной сети, его можно настроить на запрос расположения у пользователя.</span><span class="sxs-lookup"><span data-stu-id="5fa73-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="5fa73-122">Однако поскольку такие указанные пользователями расположения нельзя предварительно проверить по Master Street Address Guide (MSAG), диспетчеру поставщика услуг экстренных служб потребуется устно подтвердить правильность расположения у звонящего перед перенаправлением звонка в службу общественной безопасности (PSAP).</span><span class="sxs-lookup"><span data-stu-id="5fa73-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="5fa73-123">Клиенты Skype для бизнеса пользователей, которые подключаются к сети вашей организации с помощью VPN, могут получить внутренние данные IP-адресов, но так как эти адреса не могут использоваться для определения фактического расположения пользователя, важно, чтобы vpn-подсети были исключены из службы информации о расположении.</span><span class="sxs-lookup"><span data-stu-id="5fa73-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="5fa73-124">**Хотите ли вы предоставлять маршрутизацию экстренных звонков на сайты за пределами США.?**</span><span class="sxs-lookup"><span data-stu-id="5fa73-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="5fa73-p106">Вам может потребоваться предоставлять маршрутизацию экстренных звонков в те области вашей компании, которые не обслуживаются поставщиком услуг экстренных служб (например, объекты в других странах). Для этого создайте новый сайт и затем назначьте политики голосовой связи сайтам, которые ссылаются использование ТСОП для перенаправления звонка через локальный шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="5fa73-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>