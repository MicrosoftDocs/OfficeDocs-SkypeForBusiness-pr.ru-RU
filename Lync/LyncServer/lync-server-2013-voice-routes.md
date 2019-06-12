---
title: 'Lync Server 2013: маршруты голосовых вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e46b4074d41d2ac79dfe63bc99411a7aba72a88c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="a4c27-102">Маршруты голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4c27-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4c27-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a4c27-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a4c27-104">Маршруты звонков определяют, как Lync Server обрабатывает исходящие звонки, размещенные пользователями корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a4c27-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="a4c27-105">Когда пользователь набирает номер, сервер переднего плана нормализует строку набора номера на формат E. 164 (при необходимости) и пытается сопоставить ее с URI SIP.</span><span class="sxs-lookup"><span data-stu-id="a4c27-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="a4c27-106">Если серверу не удается найти соответствие, он применяет к исходящему звонку логику маршрутизации на основании номера.</span><span class="sxs-lookup"><span data-stu-id="a4c27-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="a4c27-107">Завершающий шаг в определении этой логики состоит в создании отдельного именованного маршрута звонка для каждого набора конечных номеров телефона, указанных в абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="a4c27-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="a4c27-108">Перед определением маршрутов исходящих звонков необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a4c27-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="a4c27-109">Развернуть как минимум одну магистральную линию связи.</span><span class="sxs-lookup"><span data-stu-id="a4c27-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="a4c27-110">При необходимости создать абонентские группы для сайтов, отдельных пользователей или контактных объектов.</span><span class="sxs-lookup"><span data-stu-id="a4c27-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="a4c27-111">Создать режимы работы с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a4c27-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="a4c27-p102">Кроме того, для включения маршрутизации исходящих звонков необходимо создать и назначить как минимум одну политику голосовых служб. Это можно выполнить как перед определением маршрутов исходящих звонков, так и после.</span><span class="sxs-lookup"><span data-stu-id="a4c27-p102">Additionally, to enable outbound call routing, you must create and assign one or more voice policies. You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="a4c27-114">Для каждого маршрута необходимо указать следующее.</span><span class="sxs-lookup"><span data-stu-id="a4c27-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="a4c27-115">Имя, позволяющее легко идентифицировать соответствующий маршрут.</span><span class="sxs-lookup"><span data-stu-id="a4c27-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="a4c27-116">Описание, если для описания маршрута одного имени недостаточно (необязательно).</span><span class="sxs-lookup"><span data-stu-id="a4c27-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="a4c27-117">Регулярное выражение для шаблона поиска соответствия, которое идентифицирует конечные номера телефонов, к которым применяется маршрут, а также исключения, к которым шаблон поиска соответствия не применяется</span><span class="sxs-lookup"><span data-stu-id="a4c27-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="a4c27-118">Одна или более магистральных линий связи, которые необходимо назначить маршруту.</span><span class="sxs-lookup"><span data-stu-id="a4c27-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="a4c27-119">Режимы работы с ТСОП, требуемые пользователям для обеспечения соответствия номеров телефонов регулярному выражению для конечных номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="a4c27-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="a4c27-120">Вы можете указать маршруты звонков на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4c27-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="a4c27-121">Эти маршруты звонков заполняют таблицу маршрутизации сервера, которую Lync Server использует для маршрутизации звонков, предназначенных для КТСОП.</span><span class="sxs-lookup"><span data-stu-id="a4c27-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="a4c27-122">Поддержка магистрали M:N</span><span class="sxs-lookup"><span data-stu-id="a4c27-122">M:N Trunk Support</span></span>

<span data-ttu-id="a4c27-123">Lync Server предоставляет гибкие возможности маршрутизации звонков в КТСОП.</span><span class="sxs-lookup"><span data-stu-id="a4c27-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="a4c27-124">Маршрут голосовых вызовов указывает набор магистральных линий связи, используемых для связи с ТСОП, которая может использоваться для конкретного голосового звонка.</span><span class="sxs-lookup"><span data-stu-id="a4c27-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="a4c27-125">Магистраль связывает сервер-посредник и номер порта с шлюзом PSTN и номером прослушивающего порта.</span><span class="sxs-lookup"><span data-stu-id="a4c27-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="a4c27-126">Это логическая связь позволяет сервер-посреднику быть связан с несколькими шлюзами и может иметь несколько подключений к одному шлюзу.</span><span class="sxs-lookup"><span data-stu-id="a4c27-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="a4c27-127">При определении маршрута звонков вы указываете магистральные тарифы, связанные с этим маршрутом, но не указываете, какие серверы обновлений связаны с этим маршрутом.</span><span class="sxs-lookup"><span data-stu-id="a4c27-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="a4c27-128">Для создания магистральных каналов путем определения связей между серверами-посредниками и шлюзами PSTN, IP-АТС и контроллерами границ сеансов (SBCs) используйте построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="a4c27-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="a4c27-129">Маршрутизация по принципу наименьшей стоимости</span><span class="sxs-lookup"><span data-stu-id="a4c27-129">Least-Cost Routing</span></span>

<span data-ttu-id="a4c27-p105">Возможность указания магистральных линий связи, используемых для маршрутизации различных номеров, позволяет определить маршруты, имеющие наименьшую стоимость, и использовать их соответствующим образом. Общее правило выбора магистральной линии связи — выбор магистральной линии связи с ближайшим шлюзом до расположения конечного номера, чтобы минимизировать затраты на международную связь. Например, если вы находитесь в Нью-Йорке и звоните абоненту в Риме, звонок будет передаваться по сети IP в магистральную линию связи со шлюзом в офисе Рима, чтобы плата взималась только за локальный звонок.</span><span class="sxs-lookup"><span data-stu-id="a4c27-p105">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly. The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges. For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="a4c27-133">Пример использования функции маршрутизации по крайней мере можно получить, выполнив указанные ниже действия. компания Fabrikam решила, чтобы пользователи Германии могли звонить на номера в США с помощью канала США.</span><span class="sxs-lookup"><span data-stu-id="a4c27-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="a4c27-134">Fabrikam также хочет настроить систему таким образом, чтобы все звонки с пользователей Lync Server из США в Германии и смежные страны и регионы на магистраль в Германии были остановлены.</span><span class="sxs-lookup"><span data-stu-id="a4c27-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="a4c27-135">Этот маршрут позволяет экономить деньги, так как звонки из Германии в Австрии, например, дешевле, чем звонки из США в Австрии.</span><span class="sxs-lookup"><span data-stu-id="a4c27-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="a4c27-136">Преобразование строк набора исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="a4c27-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="a4c27-137">Для Lync Server 2013, как и непосредственные предшественники, требуется, чтобы все строки набора номера были нормализованы в формат E. 164 для целей обратного просмотра номера (РНЛ).</span><span class="sxs-lookup"><span data-stu-id="a4c27-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="a4c27-138">Для магистральных каналов с шлюзами или частными филиалами (АТС), требующими перевод номеров в локальных форматах набора номера, Lync Server 2013 позволяет создать одно или несколько правил, которые помогут в управлении вызываемым номером (например, URI запроса) перед его маршрутизацией в стволе.</span><span class="sxs-lookup"><span data-stu-id="a4c27-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="a4c27-139">Например, можно составить правило, обеспечивающее удаление префикса +44 в начале строки набора номера с заменой префиксом 0144.</span><span class="sxs-lookup"><span data-stu-id="a4c27-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="a4c27-140">С помощью Lync Server 2013 можно создать одно или несколько правил, которые помогут вам обменять номер, прежде чем перенаправить его на магистральный звонок.</span><span class="sxs-lookup"><span data-stu-id="a4c27-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="a4c27-141">При планировании каналов, связывающих шлюзы: пары портов с серверами исправлений: пары портов, может быть полезна для групповых магистральов с одинаковым набором местных требований и, таким образом, уменьшить количество требуемых правил трансляции и время, необходимое для их написания.</span><span class="sxs-lookup"><span data-stu-id="a4c27-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="a4c27-142">Настройка идентификатора вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="a4c27-142">Configuring Caller ID</span></span>

<span data-ttu-id="a4c27-143">Lync Server предоставляет способ управления ИДЕНТИФИКАТОРом вызывающего абонента для исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="a4c27-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="a4c27-144">Например, если в Организации требуется маскировать расширения прямого набора для сотрудников и заменить их на универсальный номер компании или отдела, администратор может сделать это с помощью панели управления Lync Server, чтобы подавить идентификатор вызывающего абонента и заменить его на указанный альтернативный идентификатор вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="a4c27-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="a4c27-145">При планировании логической схемы маршрутизации следует определить пользователей, группы или сайты, к которым будет применен этот режим, или применить его ко всем сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="a4c27-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4c27-p109">Для звонков, перенаправляемых через ТСОП, вместо исходного ИД вызывающего абонента будет представлен общий ИД вызывающего абонента. Это может привести к тому, что звонки будут обходить статусы "Не беспокоить" или параметры конфиденциальности, которые могли быть заданы вызываемым.</span><span class="sxs-lookup"><span data-stu-id="a4c27-p109">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID. This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="a4c27-148">Дополнительная логика маршрутизации</span><span class="sxs-lookup"><span data-stu-id="a4c27-148">Additional Routing Logic</span></span>

<span data-ttu-id="a4c27-149">При создании маршрутов исходящих звонков необходимо учитывать следующие факторы, которые могут повлиять на логику маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a4c27-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="a4c27-150">Если вызов устанавливается через федеративную границу, доменная часть URI используется для маршрутизации звонка в сеть предприятия, которое отвечает за применение логики внешней маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a4c27-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="a4c27-151">Если часть домена в URI запроса не содержит поддерживаемый домен для организации, компонент внешней маршрутизации на сервере не будет обрабатывать соответствующий вызов.</span><span class="sxs-lookup"><span data-stu-id="a4c27-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="a4c27-152">Если пользователю не разрешена Корпоративная голосовая связь, сервер применяет другие алгоритмы маршрутизации по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="a4c27-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="a4c27-p110">Если вызов перенаправляется в шлюз, который полностью занят (все каналы магистрали заняты), этот шлюз отклоняет вызов, а логика внешней маршрутизации перенаправляет вызов на следующий маршрут с наименьшей стоимостью. Этот сценарий необходимо рассмотреть более подробно, поскольку шлюз, предназначенный для небольших заграничных офисов (например, в Цюрихе), может переносить большой объем нелокального трафика для международных звонков в Швейцарию. Если размер дополнительного трафика шлюза задан неправильно, звонки в Швейцарию могут быть перенаправлены в шлюз в Германии, что приведет к увеличению расходов на международную связь.</span><span class="sxs-lookup"><span data-stu-id="a4c27-p110">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route. Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland. If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

