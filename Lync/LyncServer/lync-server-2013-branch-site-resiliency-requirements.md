---
title: 'Lync Server 2013: требования к устойчивости для сайтов филиала'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff969638f8c46abdd0ebcc8d11821a6a31b3c76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="a3cf6-102">Требования к устойчивости для сайтов филиала для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3cf6-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3cf6-103">_**Тема последнего изменения:** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="a3cf6-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="a3cf6-104">В этом разделе приведены инструкции по подготовке пользователей к использованию устойчивости сайта филиала и обеспечения связи для голосовой почты, а также приведены требования к оборудованию и программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="a3cf6-105">Подготовка пользователей филиала для устойчивости сайта филиала</span><span class="sxs-lookup"><span data-stu-id="a3cf6-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="a3cf6-106">Подготовьте пользователей для обеспечения устойчивости сайтов, указав их пул регистратора в качестве работающего устройства филиала (СБА) или отказоустойчивого сервера филиалов.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="a3cf6-107">Назначения регистратора для пользователей филиала</span><span class="sxs-lookup"><span data-stu-id="a3cf6-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="a3cf6-108">Независимо от используемого решения для обеспечения устойчивости сайта филиала вам потребуется задать основной регистратор для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="a3cf6-109">Пользователи сайтов филиалов должны всегда регистрироваться в регистраторе на сайте филиала, независимо от того, находится ли этот регистратор в работающем устройстве филиала, в работающем сервере филиале или на отдельном сервере Lync Server 2013 Standard или Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="a3cf6-110">Чтобы клиент мог обнаружить пул регистратора, требуется DNS-запись SRV.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="a3cf6-111">Если бесперебойно работающее устройство филиала становится недоступным, в этом случае клиенты сайтов филиалов смогут автоматически найти регистратор архивации.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="a3cf6-112">Если на сайте филиала нет DNS-сервера, существует два альтернативных способа настройки обнаружения работающего устройства филиала или сервера с бесперебойной подразделением.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="a3cf6-113">Настройте параметр DHCP 120 на DHCP-сервере, чтобы он указывал на полное доменное имя (FQDN) работающего устройства филиала или его бесперебойный сервер.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="a3cf6-114">Настройте работающее устройство филиала или бесперебойный сервер филиала, чтобы ответить на запросы DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="a3cf6-115">Маршрутизация голосовых вызовов для пользователей филиала</span><span class="sxs-lookup"><span data-stu-id="a3cf6-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="a3cf6-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="a3cf6-117">Эта политика должна включать основной маршрут, использующий бесперебойно работающее устройство филиалов или шлюз сервера филиалов, а также один или несколько маршрутов резервного копирования, использующих магистраль с коммутируемым шлюзом телефонной сети на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="a3cf6-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="a3cf6-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="a3cf6-120">This is an important consideration for failover scenarios.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="a3cf6-121">Например, если вам нужно переименовать бесперебойно работающее устройство филиала или перенастроить бесперебойно работающее устройство филиала для подключения к пулу регистратора архивации на центральном сайте, необходимо переместить пользователей филиалов на центральный сайт в течение длительного времени.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="a3cf6-122">(Дополнительные сведения о переименовании и перенастройке бесперебойно работающего устройства ветвления можно найти в статье [Приложение B: Управление работающем устройством ветвления в Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) в документации по развертыванию.) Если пользователи не имеют политик VoIP на уровне пользователя или абонентов на уровне пользователей, то при перемещении пользователей на другой сайт политики VoIP на уровне сайта и абонентские планы на уровне сайта применяются по умолчанию, а не в VoIP на уровне сайта филиала политики и абонентские группы;</span><span class="sxs-lookup"><span data-stu-id="a3cf6-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="a3cf6-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="a3cf6-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a3cf6-125">При создании резервного маршрута для филиала мы рекомендуем добавить в пользовательскую политику филиала два режима работы с ТСОП и назначить каждому режиму отдельные маршруты.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="a3cf6-126">Первый (или основной) маршрут перенаправляет звонки на шлюз, связанный с устройством с бесперебойной подразделением (СБА) или с сервером подразделения; второй (или резервный) маршрут перенаправляет звонки на шлюз на центральном веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="a3cf6-127">Перед использованием второго режима работы с ТСОП устройство для обеспечения связи в филиалах или сервер филиала попытаются использовать все маршруты, назначенные первому режиму работы с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="a3cf6-128">Чтобы гарантировать, что входящие звонки на пользователей филиалов будут доступны этим пользователям, когда шлюз филиала или компонент Windows неработающего сайта управляющего устройства филиала недоступны (например, если устройство может находиться в сети или в работающей ветви). Шлюз был остановлен для обслуживания), создайте маршрут для перемещения при сбое на шлюзе (или с помощью прямого набора номера), чтобы перенаправить входящие вызовы в пул регистратора резервного копирования на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="a3cf6-129">From there, the calls will be routed over the WAN link to branch users.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="a3cf6-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="a3cf6-131">Подробнее о создании маршрута перемещения при сбое можно узнать [в разделе Настройка перенаправления перемещения при сбое в Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span><span class="sxs-lookup"><span data-stu-id="a3cf6-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="a3cf6-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="a3cf6-133">Если у вас есть два бесперебойно обслуживаемых устройства филиалов на сайте филиала, вы можете создать абонентскую группу на уровне сайта для обоих уровней, если только для них не требуется отдельный план обслуживания.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3cf6-134">Для учета ресурсов центрального сайта, потребляемых пользователями сайта филиала, которые используют центральный сайт для получения сведений о присутствии, конференц-связи или отработки отказа, мы рекомендуем учитывать каждого пользователя сайта филиала как пользователя, зарегистрированного на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="a3cf6-135">В настоящее время не существует ограничений на количество пользователей сайтов филиалов, включая пользователей, зарегистрированных с помощью работающего устройства филиалов.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="a3cf6-136">Кроме того, мы рекомендуем создать абонентскую группу и политику голосовой связи на уровне пользователя и затем назначить их пользователям сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="a3cf6-137">Дополнительные сведения можно найти [в разделе Создание абонентской группы в Lync server 2013](lync-server-2013-create-a-dial-plan.md) и [Создание политики маршрутизации VoIP для пользователей филиалов в документации по развертыванию в Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) .</span><span class="sxs-lookup"><span data-stu-id="a3cf6-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="a3cf6-138">Маршрутизация добавочных номеров</span><span class="sxs-lookup"><span data-stu-id="a3cf6-138">Routing Extension Numbers</span></span>

<span data-ttu-id="a3cf6-139">Для подготовки абонентской группы и политик голосовой связи для пользователей филиалов Включите правила нормализации и правила трансляции, которые соответствуют строкам и числовой формату, используемому в атрибуте msRTCSIP-Line (или универсального кода ресурса), чтобы Lync 2013 вызывал связь между ветвями. Пользователи сайта и пользователи центрального сайта будут правильно перенаправляться, особенно при переадресации звонков по протоколу КТСОП, так как ссылка WAN недоступна.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="a3cf6-140">В отличие от обычных номеров, для номеров с добавочными номерами существуют особые требования.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="a3cf6-p108">Правила нормализации и преобразования, которые соответствуют Line URI, содержащим добавочный номер (отдельный номер или в дополнении к полному номеру телефона E.164), имеют дополнительные требования. В этом разделе описываются примеры маршрутизации звонков для Line URI с добавочными номерами.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-p108">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements. This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="a3cf6-p109">Если в вашей организации не настроен прямой набор внутренних номеров для отдельных пользователей и в качестве URI линии для всех пользователей указан *только* добавочный номер, внутренние пользователи могут звонить друг другу, используя только добавочный номер. Однако вам потребуется настроить правила нормализации, которые можно применить при звонках пользователя сайта филиала пользователю центрального сайта и которые соответствуют добавочным номерам.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-p109">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number. However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="a3cf6-p110">Если канал глобальной сети между сайтом филиала и центральным сайтом доступен, то для звонков пользователей сайта филиала пользователям центрального сайта не требуется правило нормализации для преобразования номеров, поскольку звонки не маршрутизируются через ТСОП. Пример:</span><span class="sxs-lookup"><span data-stu-id="a3cf6-p110">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN. For example:</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3cf6-147">Имя правила</span><span class="sxs-lookup"><span data-stu-id="a3cf6-147">Rule name</span></span></th>
<th><span data-ttu-id="a3cf6-148">Описание</span><span class="sxs-lookup"><span data-stu-id="a3cf6-148">Description</span></span></th>
<th><span data-ttu-id="a3cf6-149">Шаблон номера</span><span class="sxs-lookup"><span data-stu-id="a3cf6-149">Number pattern</span></span></th>
<th><span data-ttu-id="a3cf6-150">Преобразование</span><span class="sxs-lookup"><span data-stu-id="a3cf6-150">Translation</span></span></th>
<th><span data-ttu-id="a3cf6-151">Пример</span><span class="sxs-lookup"><span data-stu-id="a3cf6-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3cf6-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="a3cf6-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-153">Не преобразует номера, состоящие из 5 знаков</span><span class="sxs-lookup"><span data-stu-id="a3cf6-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-154">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="a3cf6-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-155">$1</span><span class="sxs-lookup"><span data-stu-id="a3cf6-155">$1</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-156">10001 не преобразуется</span><span class="sxs-lookup"><span data-stu-id="a3cf6-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a3cf6-p111">Вам также необходимо адаптировать добавочные номера для случаев, когда канал глобальной сети между сайтом филиала и центральным сайтом недоступен, а звонок из сайта филиала необходимо перенаправить через ТСОП. Если при отключении глобальной сети пользователь сайта филиала вызывает пользователя центрального сайта с помощью его добавочного номера, то потребуется правило преобразования исходящих звонков, добавляющее полный номер телефона пользователя центрального сайта. Если URI линии пользователя содержит полный номер телефона организации и уникальный добавочный номер пользователя, а не полный номер, являющийся уникальным для пользователя, то вам потребуется правило преобразования исходящих звонков, которое добавляет полный номер телефона организации. Пример:</span><span class="sxs-lookup"><span data-stu-id="a3cf6-p111">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN. During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number. If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3cf6-161">Описание</span><span class="sxs-lookup"><span data-stu-id="a3cf6-161">Description</span></span></th>
<th><span data-ttu-id="a3cf6-162">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a3cf6-162">Matching pattern</span></span></th>
<th><span data-ttu-id="a3cf6-163">Преобразование</span><span class="sxs-lookup"><span data-stu-id="a3cf6-163">Translation</span></span></th>
<th><span data-ttu-id="a3cf6-164">Пример</span><span class="sxs-lookup"><span data-stu-id="a3cf6-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3cf6-165">Преобразует номера, состоящие из 5 знаков, в номер телефона пользователя и добавочный номер пользователя</span><span class="sxs-lookup"><span data-stu-id="a3cf6-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-166">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="a3cf6-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-167">+14255550123;ext=$1</span><span class="sxs-lookup"><span data-stu-id="a3cf6-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-168">10001 преобразуется в +14255550123;доб.=10001</span><span class="sxs-lookup"><span data-stu-id="a3cf6-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3cf6-169">Преобразует номера, состоящие из 5 знаков, в номер телефона организации и добавочный номер пользователя</span><span class="sxs-lookup"><span data-stu-id="a3cf6-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-170">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="a3cf6-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-171">+14255550100;ext=$1</span><span class="sxs-lookup"><span data-stu-id="a3cf6-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-172">10001 преобразуется в +14255550100;доб.=10001</span><span class="sxs-lookup"><span data-stu-id="a3cf6-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a3cf6-p112">В этом сценарии, если узел магистрали, который обрабатывает изменение маршрута в ТСОП, не поддерживает добавочные номера, то правило преобразования исходящих звонков также должно удалять добавочные номера. Пример:</span><span class="sxs-lookup"><span data-stu-id="a3cf6-p112">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3cf6-175">Описание</span><span class="sxs-lookup"><span data-stu-id="a3cf6-175">Description</span></span></th>
<th><span data-ttu-id="a3cf6-176">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a3cf6-176">Matching pattern</span></span></th>
<th><span data-ttu-id="a3cf6-177">Преобразование</span><span class="sxs-lookup"><span data-stu-id="a3cf6-177">Translation</span></span></th>
<th><span data-ttu-id="a3cf6-178">Пример</span><span class="sxs-lookup"><span data-stu-id="a3cf6-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3cf6-179">Удаляет добавочный номер из номеров телефонов, содержащих добавочные номера</span><span class="sxs-lookup"><span data-stu-id="a3cf6-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-180">^\+(\d *); ВДЛ = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="a3cf6-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-181">+$1</span><span class="sxs-lookup"><span data-stu-id="a3cf6-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="a3cf6-182">+14255550123;доб.=10001 преобразуется в +14255550123</span><span class="sxs-lookup"><span data-stu-id="a3cf6-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a3cf6-p113">Если в организации не настроены номера прямого набора внутренних номеров для отдельных пользователей и Line URI для пользователя содержит номер телефона организации и уникальный добавочный номер пользователя, то независимо от того, доступен ли канал глобальной сети, вам потребуется указать в качестве номера телефона организации Line URI с номером, которые доступен узлу магистрали или шлюзу ТСОП на сайте филиала. Кроме того, для номера телефона организации Line URI необходимо добавить собственный уникальный добавочный номер для маршрутизации звонков на этот номер.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-p113">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site. You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="a3cf6-185">Дополнительные сведения о звонках между пользователями центрального сайта и пользователями сайтов филиалов при недоступности ссылки на глобальную сеть между сайтами можно найти в разделе Подготовка к бесперебойной работе с голосовой почтой ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="a3cf6-186">Подробные сведения о абонентских планах и правилах нормализации, включая другие примеры правил, приведены [в разделе планы и правила нормализации в Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) в документации по планированию и [настройке абонентской группы в Lync Server 2013](lync-server-2013-configuring-dial-plans.md) в развертывании содержатся.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="a3cf6-187">Дополнительные сведения о правилах исходящих переводов можно найти в разделе [правила перевода в Lync server 2013](lync-server-2013-translation-rules.md) в документации по планированию и [Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="a3cf6-188">Подготовка к обеспечению связи для голосовой почты</span><span class="sxs-lookup"><span data-stu-id="a3cf6-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="a3cf6-189">Единая система обмена сообщениями Exchange обычно устанавливается только на центральный сайт, а не на сайты филиалов.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="a3cf6-190">Даже если канал глобальной сети между сайтом филиала и центральным сайтом недоступен, у вызывающего абонента должна быть возможность отправки сообщения голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="a3cf6-191">В результате Настройка универсального кода ресурса (URI) для номера телефона автосекретаря UM для Exchange, предоставляющего голосовую почту для пользователей сайтов филиалов, требует особых моментов, помимо политики голосовой почты, абонентской группы и правил нормализации, применимых к этой голосовой почте. Счетчик.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="a3cf6-192">Бесперебойно работающих устройства филиалов (Сбас) и бесперебойные серверы филиалов обеспечивают бесперебойную почту для пользователей филиалов во время отключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="a3cf6-193">В частности, если вы используете работающее устройство филиала или его бесперебойный сервер, а Глобальная сеть становится недоступной, СБА или бесперебойно работающего сервера филиалов перенаправляет неотвеченные звонки по протоколу КТСОП для обмена UM на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="a3cf6-194">С помощью СБА или работающего сервера подразделения пользователи могут также получать сообщения голосовой почты через PSTN во время отключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="a3cf6-195">Наконец, в случае сбоя в глобальной сети, устройство может быть бесперебойно или может быть доставлено с помощью уведомлений о пропущенных звонках и затем отправлять их на сервер Exchange UM после восстановления глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="a3cf6-196">Чтобы обеспечить устойчивость перенаправления голосовой почты, убедитесь в том, что вы добавляете запись для полного доменного имени пула центрального сайта и запись для полного доменного имени сервера Edge в файл hosts на сервере, который работает в бесперебойном подразделении.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="a3cf6-197">В противном случае при отсутствии DNS-сервера на сайте филиала разрешение DNS-имен не будет работать.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="a3cf6-198">При настройке обеспечения связи для голосовой почты для пользователей сайта филиала необходимо учитывать следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="a3cf6-199">Администратор Microsoft Exchange должен настроить автосекретарь единой системы обмена сообщениями Exchange (AA) для приема только сообщений.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="a3cf6-200">Эта конфигурация отключает все остальные функциональные возможности, например передачу пользователю или передачу оператору, и позволяет автосекретарю только принимать сообщения.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="a3cf6-201">В качестве альтернативного варианта администратор Exchange может использовать общий автосекретарь или настроенный секретарь для маршрутизации звонков оператору.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="a3cf6-202">Администратор сервера Lync Server должен взять номер телефона AA и использовать этот номер телефона в качестве номера **автосекретаря UM** в параметрах перенаправления голосовой почты для работающего устройства филиала или сервера подразделения.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="a3cf6-203">Администратор сервера Lync Server должен получить номер телефона Access для абонента UM и использовать его в качестве номера **абонентского доступа** в параметрах перенаправления голосовой почты для бесперебойно работающего устройства филиала или для бесперебойной подсети сервера.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="a3cf6-204">Администратор Lync Server должен настроить Exchange UM таким образом, чтобы только одна абонентская группа была связана со всеми пользователями филиалов, которым нужен доступ к голосовой почте во время отключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="a3cf6-205">Если доступ к глобальной сети отсутствует, то звонки пользователям сайта филиала могут перенаправляться в ящик голосовой почты единой системы обмена сообщениями Exchange, однако только в том случае, если в политике голосовой связи, применяемой к звонку, определен номер голосовой почты, который является уникальным и не содержит добавочного номера.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="a3cf6-206">Требования к оборудованию и программному обеспечению для устойчивости сайта филиала</span><span class="sxs-lookup"><span data-stu-id="a3cf6-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="a3cf6-207">Требования к оборудованию и программному обеспечению зависят от решения, используемого для обеспечения устойчивости.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="a3cf6-208">Требования к устройствам для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="a3cf6-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="a3cf6-209">Необходимое оборудование и программное обеспечение встроено в бесперебойно работающее устройство филиалов.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="a3cf6-210">Тем не менее, мы также рекомендуем, чтобы каждый сайт ветви разработал сервер DHCP для получения IP-адресов клиентов; в противном случае, по истечении срока аренды DHCP клиенты не будут иметь IP-подключения.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="a3cf6-211">Если корпоративные DNS-серверы находятся только на центральных сайтах, пользователи сайтов филиалов не смогут подключаться к ним во время отключения глобальной сети, поэтому при обнаружении Lync Server, в котором используется запись ресурса DNS SRV (SRV), произойдет сбой.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="a3cf6-212">Для маршрутизации в условиях отсутствия доступа к глобальной сети требуется кэшировать DNS-записи на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="a3cf6-213">Если маршрутизатор филиала поддерживает кэширование DNS, включите его.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="a3cf6-214">В противном случае вы можете развернуть DNS-сервер в филиале.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="a3cf6-215">Это может быть изолированный сервер или версия работающего устройства филиала, поддерживающая возможности DNS.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="a3cf6-216">Для получения дополнительных сведений обратитесь к поставщику устройства, который является бесперебойно.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3cf6-217">Контроллер домена на сайте филиала не требуется.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="a3cf6-218">Бесперебойно работающее устройство филиала проверяет подлинность клиентов с помощью специального сертификата, который отправляет клиент в ответ на запрос сертификата клиента при входе.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="a3cf6-219">Клиенты Lync могут найти сервер Lync с помощью параметра DHCP 120 (параметр регистратора SIP).</span><span class="sxs-lookup"><span data-stu-id="a3cf6-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="a3cf6-220">Этот запрос можно настроить следующими способами:</span><span class="sxs-lookup"><span data-stu-id="a3cf6-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="a3cf6-221">Настройте DHCP-сервер на сайте филиала, чтобы ответить на запросы DHCP 120, возвращающие полное доменное имя регистратора на устройстве с бесперебойной ветви или на сервере, который находится в сети с бесперебойной подразделением.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="a3cf6-222">Включите протокол DHCP сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="a3cf6-223">Если этот параметр включен, служба регистратора Lync Server отвечает на запросы параметров DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="a3cf6-224">Обратите внимание, что регистратор не отвечает на все DHCP-запросы, кроме "DHCP Options 120".</span><span class="sxs-lookup"><span data-stu-id="a3cf6-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="a3cf6-225">Кроме того, для крупных сайтов филиалов, имеющих несколько подсетей, нужно включить агенты DHCP-ретрансляции для переадресации запросов "DHCP Option 120" на DHCP-сервер (конфигурация 1) или регистратор (конфигурация 2).</span><span class="sxs-lookup"><span data-stu-id="a3cf6-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="a3cf6-226">Наконец, пользователи сайтов филиалов необходимо настроить для корпоративного голосовой связи и подготовки с помощью соответствующей конечной точки единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="a3cf6-227">Требования к серверам для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="a3cf6-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="a3cf6-228">Требования к оставшимся серверам филиалов совпадают с требованиями для серверного переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="a3cf6-229">Дополнительные сведения можно найти в разделе [аппаратные платформы сервера для Lync Server 2013](lync-server-2013-server-hardware-platforms.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="a3cf6-230">Требования к развертыванию многомасштабного сайта Lync Server</span><span class="sxs-lookup"><span data-stu-id="a3cf6-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="a3cf6-231">Подробности можно найти в разделе [Определение требований инфраструктуры для Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="a3cf6-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

