---
title: 'Lync Server 2013: требования к устойчивости для сайта филиала'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61ca1db13f99b13dd2a6ed148f13ab6a132ad77b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="f5ff1-102">Требования к устойчивости сайтов филиалов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5ff1-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5ff1-103">_**Последнее изменение темы:** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="f5ff1-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="f5ff1-104">В этом разделе приведены инструкции по подготовке пользователей к использованию устойчивости сайта филиала и обеспечения связи для голосовой почты, а также приведены требования к оборудованию и программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="f5ff1-105">Подготовка пользователей филиала для устойчивости сайта филиала</span><span class="sxs-lookup"><span data-stu-id="f5ff1-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="f5ff1-106">Подготовьте пользователей к устойчивости сайта филиала, задав пул регистратора в качестве устройства для обеспечения связи в филиалах (SBA) или сервера для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="f5ff1-107">Назначения Регистратора для пользователей филиала</span><span class="sxs-lookup"><span data-stu-id="f5ff1-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="f5ff1-108">Независимо от выбранного решения по обеспечению устойчивости сайта филиала, необходимо назначить основной регистратор для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="f5ff1-109">Пользователи сайта филиала должны всегда регистрироваться в регистраторе на сайте филиала независимо от того, находится ли этот регистратор в устройстве для обеспечения связи в филиалах, сервере для обеспечения связи в филиалах или на отдельном сервере Lync Server 2013 Standard или Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="f5ff1-110">Чтобы клиент мог обнаружить пул Регистратора, требуется DNS-запись SRV.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="f5ff1-111">Если устройство для обеспечения связи в филиалах становится недоступным, то это способ, с помощью которого клиенты сайта филиала будут автоматически обнаруживать регистратор резервных копий.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="f5ff1-112">Если на сайте филиала не установлен DNS-сервер, существует два альтернативных способа настройки обнаружения устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="f5ff1-113">Настройте DHCP-параметр 120 на DHCP-сервере сайта филиала, чтобы указать полное доменное имя (FQDN) устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="f5ff1-114">Настройка устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах для ответа на запросы DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="f5ff1-115">Маршрутизация голосовых вызовов для пользователей филиала</span><span class="sxs-lookup"><span data-stu-id="f5ff1-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="f5ff1-116">Мы рекомендуем создать отдельную политику VoIP на уровне пользователя для пользователей на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="f5ff1-117">Эта политика должна включать основной маршрут, использующий устройство для обеспечения связи в филиалах или шлюз сервера филиала, а также один или несколько маршрутов резервного копирования, использующих магистраль с шлюзом телефонной сети общего пользования на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="f5ff1-118">Если основной маршрут недоступен, вместо него используется резервный маршрут, который использует один или несколько центральных шлюзов сайта.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="f5ff1-119">Таким образом, независимо от того, где зарегистрирован пользователь — для регистратора сайта филиала или пула регистратора резервного копирования на центральном сайте, политика VoIP пользователя действует всегда.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="f5ff1-120">Это важный фактор для сценариев отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="f5ff1-121">Например, если необходимо переименовать устройство для обеспечения связи в филиалах или перенастроить устройство для обеспечения связи в филиалах для подключения к резервному пулу резервного копирования на центральном сайте, необходимо переместить пользователей сайта филиала на центральный сайт в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="f5ff1-122">(Дополнительные сведения о переименовании или перенастройке устройства для обеспечения связи в филиалах приведены в [разделе приложение б. Управление устройством для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) в документации по развертыванию.) Если пользователи не имеют политик VoIP на уровне пользователей или абонентских группы на уровне пользователей, то при перемещении пользователей на другой сайт политики VoIP на уровне сайта и абонентские группы на уровне сайта для центрального сайта применяются по умолчанию вместо политик VoIP на уровне сайта филиала и абонентских планов.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="f5ff1-123">В этом сценарии, если только политики VoIP на уровне сайта и абонентские группы на уровне сайта, используемые пулом регистратора резервного копирования, также могут применяться к пользователям сайта филиала, их вызовы завершатся с ошибками.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="f5ff1-124">Например, если пользователи из сайта филиала, расположенного в Японии, перемещаются на центральный сайт в Редмонде, то абонентская группы с правилами нормализации, которые в начале + 1425 на все 7-значные вызовы, скорее всего, не будут правильно переводить вызовы для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f5ff1-125">При создании резервного маршрута для филиала мы рекомендуем добавить в пользовательскую политику филиала два режима работы с ТСОП и назначить каждому режиму отдельные маршруты.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="f5ff1-126">Первый (или основной) маршрут выдает прямые вызовы шлюзу, связанному с устройством для обеспечения связи в филиалах (SBA) или сервером филиала; второй, или резервный, маршрут выдает прямые вызовы шлюза на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="f5ff1-127">Перед использованием второго режима работы с ТСОП устройство для обеспечения связи в филиалах или сервер филиала попытаются использовать все маршруты, назначенные первому режиму работы с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="f5ff1-128">Чтобы обеспечить доступность входящих вызовов для пользователей сайта филиала, когда шлюз филиала или компонент Windows в сайте устройства для обеспечения связи в филиале недоступны (например, если устройство для обеспечения связи или ветвь могут быть подключены к филиалу) Шлюз отключен для обслуживания). Создайте маршрут отработки отказа на шлюзе (или с помощью поставщика прямого звонка) для перенаправления входящих вызовов в пул резервного регистратора на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="f5ff1-129">Звонки будут перенаправляться пользователям филиала через глобальную сеть.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="f5ff1-130">Убедитесь в том, что маршрут преобразует номера в соответствии с форматами номеров телефона, используемыми шлюзом ТСОП или другим узлом магистрали.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="f5ff1-131">Дополнительные сведения о создании маршрута отработки отказа приведены [в статье Настройка маршрута отработки отказа в Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span><span class="sxs-lookup"><span data-stu-id="f5ff1-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="f5ff1-132">Кроме того, для применения правил нормализации к входящим звонкам создайте абонентские группы на уровне службы для магистрали, связанной со шлюзом на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="f5ff1-133">Если на сайте филиала имеется два устройства для обеспечения связи в филиалах, можно создать абонентскую схему на уровне сайта, если не требуется отдельный план обслуживания для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5ff1-134">Для учета ресурсов центрального сайта, потребляемых пользователями сайта филиала, которые используют центральный сайт для получения сведений о присутствии, конференц-связи или отработки отказа, мы рекомендуем учитывать каждого пользователя сайта филиала как пользователя, зарегистрированного на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="f5ff1-135">В настоящее время количество пользователей сайта филиала не ограничено, включая пользователей, зарегистрированных с помощью устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="f5ff1-136">Кроме того, мы рекомендуем создать абонентскую группу и политику голосовой связи на уровне пользователя и затем назначить их пользователям сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="f5ff1-137">Для получения дополнительных сведений см раздел [Создание абонентской группы в Lync server 2013](lync-server-2013-create-a-dial-plan.md) и [Создание политики маршрутизации VoIP для пользователей филиалов в документации по развертыванию в Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) .</span><span class="sxs-lookup"><span data-stu-id="f5ff1-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="f5ff1-138">Маршрутизация добавочных номеров</span><span class="sxs-lookup"><span data-stu-id="f5ff1-138">Routing Extension Numbers</span></span>

<span data-ttu-id="f5ff1-139">При подготовке абонентских группы и политик голосовой связи для пользователей сайта филиала необходимо включить правила нормализации и правила преобразования, которые совпадают со строками и форматом чисел, используемыми в атрибуте msRTCSIP-Line (или URI строки), чтобы Lync 2013 Calls Enabled между филиалами Пользователи сайтов и центральных сайтов будут маршрутизироваться правильно, в частности, при необходимости перенаправления вызовов по протоколу PSTN, так как канал WAN недоступен.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="f5ff1-140">В отличие от обычных номеров для номеров с добавочными номерами существуют особые требования.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="f5ff1-p108">Правила нормализации и преобразования, которые соответствуют Line URI, содержащим добавочный номер (отдельный номер или в дополнении к полному номеру телефона E.164), имеют дополнительные требования. В этом разделе описываются примеры маршрутизации звонков для Line URI с добавочными номерами.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-p108">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements. This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="f5ff1-p109">Если в вашей организации не настроен прямой набор внутренних номеров для отдельных пользователей и в качестве URI линии для всех пользователей указан *только* добавочный номер, внутренние пользователи могут звонить друг другу, используя только добавочный номер. Однако вам потребуется настроить правила нормализации, которые можно применить при звонках пользователя сайта филиала пользователю центрального сайта и которые соответствуют добавочным номерам.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-p109">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number. However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="f5ff1-p110">Если канал глобальной сети между сайтом филиала и центральным сайтом доступен, то для звонков пользователей сайта филиала пользователям центрального сайта не требуется правило нормализации для преобразования номеров, поскольку звонки не маршрутизируются через ТСОП. Пример:</span><span class="sxs-lookup"><span data-stu-id="f5ff1-p110">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN. For example:</span></span>


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
<th><span data-ttu-id="f5ff1-147">Имя правила</span><span class="sxs-lookup"><span data-stu-id="f5ff1-147">Rule name</span></span></th>
<th><span data-ttu-id="f5ff1-148">Описание</span><span class="sxs-lookup"><span data-stu-id="f5ff1-148">Description</span></span></th>
<th><span data-ttu-id="f5ff1-149">Шаблон номера</span><span class="sxs-lookup"><span data-stu-id="f5ff1-149">Number pattern</span></span></th>
<th><span data-ttu-id="f5ff1-150">Translation</span><span class="sxs-lookup"><span data-stu-id="f5ff1-150">Translation</span></span></th>
<th><span data-ttu-id="f5ff1-151">Пример</span><span class="sxs-lookup"><span data-stu-id="f5ff1-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5ff1-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="f5ff1-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-153">Не преобразует номера, состоящие из 5 знаков</span><span class="sxs-lookup"><span data-stu-id="f5ff1-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-154">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="f5ff1-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-155">$1</span><span class="sxs-lookup"><span data-stu-id="f5ff1-155">$1</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-156">10001 не преобразуется</span><span class="sxs-lookup"><span data-stu-id="f5ff1-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f5ff1-p111">Вам также необходимо адаптировать добавочные номера для случаев, когда канал глобальной сети между сайтом филиала и центральным сайтом недоступен, а звонок из сайта филиала необходимо перенаправить через ТСОП. Если при отключении глобальной сети пользователь сайта филиала вызывает пользователя центрального сайта с помощью его добавочного номера, то потребуется правило преобразования исходящих звонков, добавляющее полный номер телефона пользователя центрального сайта. Если URI линии пользователя содержит полный номер телефона организации и уникальный добавочный номер пользователя, а не полный номер, являющийся уникальным для пользователя, то вам потребуется правило преобразования исходящих звонков, которое добавляет полный номер телефона организации. Пример:</span><span class="sxs-lookup"><span data-stu-id="f5ff1-p111">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN. During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number. If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5ff1-161">Описание</span><span class="sxs-lookup"><span data-stu-id="f5ff1-161">Description</span></span></th>
<th><span data-ttu-id="f5ff1-162">Шаблон</span><span class="sxs-lookup"><span data-stu-id="f5ff1-162">Matching pattern</span></span></th>
<th><span data-ttu-id="f5ff1-163">Translation</span><span class="sxs-lookup"><span data-stu-id="f5ff1-163">Translation</span></span></th>
<th><span data-ttu-id="f5ff1-164">Пример</span><span class="sxs-lookup"><span data-stu-id="f5ff1-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5ff1-165">Преобразует номера, состоящие из 5 знаков, в номер телефона пользователя и добавочный номер пользователя</span><span class="sxs-lookup"><span data-stu-id="f5ff1-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-166">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="f5ff1-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-167">+ 14255550123; EXT = $1</span><span class="sxs-lookup"><span data-stu-id="f5ff1-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-168">10001 преобразуется в +14255550123;доб.=10001</span><span class="sxs-lookup"><span data-stu-id="f5ff1-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ff1-169">Преобразует номера, состоящие из 5 знаков, в номер телефона организации и добавочный номер пользователя</span><span class="sxs-lookup"><span data-stu-id="f5ff1-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-170">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="f5ff1-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-171">+ 14255550100; EXT = $1</span><span class="sxs-lookup"><span data-stu-id="f5ff1-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-172">10001 преобразуется в +14255550100;доб.=10001</span><span class="sxs-lookup"><span data-stu-id="f5ff1-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f5ff1-p112">В этом сценарии, если узел магистрали, который обрабатывает изменение маршрута в ТСОП, не поддерживает добавочные номера, то правило преобразования исходящих звонков также должно удалять добавочные номера. Пример:</span><span class="sxs-lookup"><span data-stu-id="f5ff1-p112">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5ff1-175">Описание</span><span class="sxs-lookup"><span data-stu-id="f5ff1-175">Description</span></span></th>
<th><span data-ttu-id="f5ff1-176">Шаблон</span><span class="sxs-lookup"><span data-stu-id="f5ff1-176">Matching pattern</span></span></th>
<th><span data-ttu-id="f5ff1-177">Translation</span><span class="sxs-lookup"><span data-stu-id="f5ff1-177">Translation</span></span></th>
<th><span data-ttu-id="f5ff1-178">Пример</span><span class="sxs-lookup"><span data-stu-id="f5ff1-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5ff1-179">Удаляет добавочный номер из номеров телефонов, содержащих добавочные номера</span><span class="sxs-lookup"><span data-stu-id="f5ff1-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-180">^\+(\d *); ext = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="f5ff1-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-181">+ $1</span><span class="sxs-lookup"><span data-stu-id="f5ff1-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="f5ff1-182">+14255550123;доб.=10001 преобразуется в +14255550123</span><span class="sxs-lookup"><span data-stu-id="f5ff1-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f5ff1-p113">Если в организации не настроены номера прямого набора внутренних номеров для отдельных пользователей и Line URI для пользователя содержит номер телефона организации и уникальный добавочный номер пользователя, то независимо от того, доступен ли канал глобальной сети, вам потребуется указать в качестве номера телефона организации Line URI с номером, которые доступен узлу магистрали или шлюзу ТСОП на сайте филиала. Кроме того, для номера телефона организации Line URI необходимо добавить собственный уникальный добавочный номер для маршрутизации звонков на этот номер.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-p113">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site. You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="f5ff1-185">Дополнительные сведения о звонках между пользователями центрального сайта и сайта филиала в случае, если канал глобальной сети между сайтами недоступен, см. в подразделе "Подготовка к обеспечению связи для голосовой почты" этого раздела.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="f5ff1-186">Подробные сведения о абонентских планах и правилах нормализации, в том числе о других примерах правил, приведены в статье Руководство [и правила нормализации в Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) в документации по планированию и [настройке абонентских группы в Lync Server 2013](lync-server-2013-configuring-dial-plans.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="f5ff1-187">Подробные сведения о правилах исходящих преобразований приведены в статье [правила преобразования в Lync server 2013](lync-server-2013-translation-rules.md) в документации по планированию и [определению правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="f5ff1-188">Подготовка к обеспечению связи для голосовой почты</span><span class="sxs-lookup"><span data-stu-id="f5ff1-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="f5ff1-189">Единая система обмена сообщениями Exchange обычно устанавливается только на центральном сайте, а не на сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="f5ff1-190">Даже если канал глобальной сети между сайтом филиала и центральным сайтом недоступен, у вызывающего абонента должна быть возможность отправки сообщения голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="f5ff1-191">В результате Настройка URI линии для телефонного номера автосекретаря единой системы обмена сообщениями Exchange, предоставляющего голосовую почту для пользователей сайта филиала, требует дополнительных рекомендаций в дополнение к политике голосовой связи, абонентской группе и правилам нормализации, применяемым к этой голосовой почте. значение.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="f5ff1-192">Устройства для обеспечения связи в филиалах (устройства) и серверы для обеспечения связи в филиалах обеспечивают бесперебойную почту для пользователей филиалов во время сбоя глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="f5ff1-193">В частности, если вы используете устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах, а Глобальная сеть становится недоступной, сервер SBA или для обеспечения связи в филиалах перенаправляет неотвеченные вызовы через PSTN для обмена единой системой обмена сообщениями на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="f5ff1-194">При использовании сервера SBA или для обеспечения связи в филиалах пользователи могут также извлекать сообщения голосовой почты через PSTN во время сбоя глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="f5ff1-195">Наконец, во время отключения глобальной сети устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах помещает в очередь уведомления о пропущенных вызовах, а затем отправляет их на сервер единой системы обмена сообщениями Exchange при восстановлении глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="f5ff1-196">Чтобы обеспечить устойчивость перенаправления голосовой почты, убедитесь, что вы добавляете запись для полного доменного имени пула центрального сайта и запись полного доменного имени пограничного сервера в файл hosts на сервере для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="f5ff1-197">В противном случае при отсутствии DNS-сервера на сайте филиала разрешение DNS-имен не будет работать.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="f5ff1-198">При настройке обеспечения связи для голосовой почты для пользователей сайта филиала необходимо учитывать следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="f5ff1-199">Администратор Microsoft Exchange должен настроить автосекретарь единой системы обмена сообщениями Exchange, чтобы принимать только сообщения.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="f5ff1-200">Эта конфигурация отключает все остальные функциональные возможности, например передачу пользователю, передачу оператору, и позволяет автосекретарю только принимать сообщения.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="f5ff1-201">В качестве альтернативного варианта администратор Exchange может использовать общий автосекретарь или настроенный секретарь для маршрутизации звонков оператору.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="f5ff1-202">Администратор Lync Server должен получить номер телефона AA и использовать этот номер в качестве номера **автосекретаря единой системы обмена сообщениями Exchange** в параметрах маршрутизации голосовой почты для устройства для обеспечения связи в филиалах или сервера филиала.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="f5ff1-203">Администратор Lync Server должен получить номер телефона для абонентского доступа к единой системе обмена сообщениями Exchange и использовать этот номер в качестве номера **доступа абонента** в параметрах маршрутизации голосовой почты для устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="f5ff1-204">Администратор Lync Server должен настроить единую систему обмена сообщениями Exchange таким образом, чтобы только одна абонентская группа была связана со всеми пользователями филиала, которым требуется доступ к голосовой почте во время отключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="f5ff1-205">Если доступ к глобальной сети отсутствует, то звонки пользователям сайта филиала могут перенаправляться в ящик голосовой почты единой системы обмена сообщениями Exchange, однако только в том случае, если в политике голосовой связи, применяемой к звонку, определен номер голосовой почты, который является уникальным и не содержит добавочного номера.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="f5ff1-206">Требования к оборудованию и программному обеспечению для устойчивости сайта филиала</span><span class="sxs-lookup"><span data-stu-id="f5ff1-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="f5ff1-207">Требования к оборудованию и программному обеспечению зависят от решения, используемого для обеспечения устойчивости.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="f5ff1-208">Требования к устройствам для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="f5ff1-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="f5ff1-209">Необходимое оборудование и программное обеспечение встроены в устройство для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="f5ff1-210">Однако мы также рекомендуем, чтобы каждый сайт филиала развернут DHCP-сервер для получения IP-адресов клиентов; в противном случае, по истечении срока аренды DHCP клиенты не будут иметь IP-подключения.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="f5ff1-211">Если корпоративный DNS-сервер размещается только на центральных сайтах, пользователи сайта филиала не смогут подключаться к ним во время сбоя глобальной сети, поэтому обнаружение Lync Server, использующее DNS SRV (запись ресурса службы (SRV)), завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="f5ff1-212">Для маршрутизации в условиях отсутствия доступа к глобальной сети требуется кэшировать DNS-записи на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="f5ff1-213">Если маршрутизатор филиала поддерживает кэширование DNS, включите его.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="f5ff1-214">В противном случае вы можете развернуть DNS-сервер в филиале.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="f5ff1-215">Это может быть отдельный сервер или версия устройства для обеспечения связи в филиалах, поддерживающая возможности DNS.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="f5ff1-216">Для получения дополнительных сведений обратитесь к поставщику устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5ff1-217">Контроллер домена на сайте филиала не требуется.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="f5ff1-218">Устройство для обеспечения связи в филиалах выполняет проверку подлинности клиентов с помощью специального сертификата, который отправляет клиент в ответ на запрос сертификата клиента при входе.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="f5ff1-219">Клиенты Lync могут обнаруживать сервер Lync с помощью параметра DHCP 120 (параметр регистратора SIP).</span><span class="sxs-lookup"><span data-stu-id="f5ff1-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="f5ff1-220">Этот запрос можно настроить следующими способами:</span><span class="sxs-lookup"><span data-stu-id="f5ff1-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="f5ff1-221">Настройте DHCP-сервер на сайте филиала для ответа на DHCP-запросы 120, которые возвращают полное доменное имя регистратора на устройстве для обеспечения связи в филиале или сервере для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="f5ff1-222">Включите DHCP-сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="f5ff1-223">Когда этот параметр включен, регистратор сервера Lync Server отвечает на запросы параметров DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="f5ff1-224">Обратите внимание, что Регистратор не отвечает на все DHCP-запросы, кроме "DHCP Options 120".</span><span class="sxs-lookup"><span data-stu-id="f5ff1-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="f5ff1-225">Кроме того, для крупных сайтов филиалов, имеющих несколько подсетей, нужно включить агенты DHCP-ретрансляции для переадресации запросов "DHCP Option 120" на DHCP-сервер (конфигурация 1) или Регистратор (конфигурация 2).</span><span class="sxs-lookup"><span data-stu-id="f5ff1-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="f5ff1-226">Наконец, пользователи сайта филиала должны быть настроены для корпоративной голосовой связи и подготовлены с помощью соответствующей конечной точки единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="f5ff1-227">Требования к серверам для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="f5ff1-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="f5ff1-228">Требования к серверам для обеспечения связи в филиалах совпадают с требованиями для сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="f5ff1-229">Дополнительные сведения: [аппаратные платформы сервера для Lync Server 2013](lync-server-2013-server-hardware-platforms.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="f5ff1-230">Требования для полномасштабного развертывания Lync Server на сайте филиала</span><span class="sxs-lookup"><span data-stu-id="f5ff1-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="f5ff1-231">Дополнительные сведения приведены в статье [Определение требований к инфраструктуре для Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="f5ff1-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

