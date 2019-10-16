---
title: Настройка динамического вызова экстренной помощи
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: Настройка динамического вызова экстренной помощи
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516934"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a><span data-ttu-id="d3ae3-103">Планирование и Настройка динамического вызова экстренной помощи в планах звонков</span><span class="sxs-lookup"><span data-stu-id="d3ae3-103">Plan and configure dynamic emergency calling for Calling Plans</span></span>
<span data-ttu-id="d3ae3-104">Динамическое обращение в службу экстренной помощи в планах звонков в Microsoft обеспечивает возможность настройки и маршрутизации экстренных вызовов в зависимости от текущего расположения клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-104">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span>  <span data-ttu-id="d3ae3-105">Возможность автоматической маршрутизации к соответствующей точке ответа на общедоступную безопасность (ПСАП) или уведомлению сотрудников службы безопасности в зависимости от страны использования пользователя Teams.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-105">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

> [!Note] 
> <span data-ttu-id="d3ae3-106">Динамический вызов экстренной помощи в настоящее время доступен только в Соединенных Штатах.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-106">Dynamic emergency calling is currently available only in the United States.</span></span> <span data-ttu-id="d3ae3-107">Тем не менее, уведомление на рабочем месте поддерживается через границы стран.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-107">Security desk notification, however, is supported across country boundaries.</span></span>

<span data-ttu-id="d3ae3-108">**В США**вы можете настроить динамическую маршрутизацию для экстренных вызовов, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-108">**Within the United States**, you can configure dynamic emergency call routing as follows:</span></span>
  
- <span data-ttu-id="d3ae3-109">Если клиент Teams находится на динамическом месте, определенном клиентом, это автоматически перенаправляется в ПСАП, который обслуживает географическое расположение.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-109">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span>  

- <span data-ttu-id="d3ae3-110">Если клиент Teams не находится в динамическом расположении, определяемом клиентом, для определения местоположения вызывающего абонента перед передачей звонка в ПСАП, который обслуживает географическое положение, вызов экстренной помощи от этого клиента помещается в центр звонков.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-110">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

<span data-ttu-id="d3ae3-111">Вы можете настроить уведомление на службу безопасности следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d3ae3-111">You can configure security desk notification as follows:</span></span>

- <span data-ttu-id="d3ae3-112">Если клиент Teams находится на сайте сети, определенном клиентом, для него будут уведомлены участники групп безопасности, настроенные для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-112">If a Teams client is located at a tenant-defined network site, the security group members configured for that site will be notified.</span></span>

- <span data-ttu-id="d3ae3-113">Если клиент Teams не находится на сайте сети, определенном клиентом, пользователи будут уведомлены о группе безопасности, настроенной для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-113">If a Teams client is not located at a tenant-defined network site, the security group members configured for the user will be notified.</span></span>

<span data-ttu-id="d3ae3-114">**За пределами США**звонки с помощью экстренной помощи перенаправляются на ПСАП, который сопоставлен с номером телефона, назначенным пользователю.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-114">**Outside of the United States**, emergency calls are routed to the PSAP that is mapped to the phone number assigned to the user.</span></span>  <span data-ttu-id="d3ae3-115">В некоторых странах, таких как Великобритания и Канада, перед передачей вызывающего абонента в соответствующее ПСАП экран выдается звонок, а другие пользователи прямо в ПСАП независимо от того, где находится пользователь в данный момент.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-115">Some countries, such as the Great Britain and Canada, screen the calls nationally before transferring the caller to the appropriate PSAP, while others route directly to the PSAP regardless of where the user is currently located.</span></span> 

<span data-ttu-id="d3ae3-116">Обратите внимание, что вы можете настроить динамическое уведомление службы безопасности для всех пользователей плана звонков.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-116">Note that you can configure dynamic security desk notification for all Calling Plan users.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="d3ae3-117">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="d3ae3-117">Supported clients</span></span>

<span data-ttu-id="d3ae3-118">В настоящее время поддерживаются следующие клиенты.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-118">The following clients are currently supported.</span></span>  <span data-ttu-id="d3ae3-119">Регулярно проверяйте, есть ли в этом списке обновленные сведения.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-119">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="d3ae3-120">Настольный клиент Teams для Windows</span><span class="sxs-lookup"><span data-stu-id="d3ae3-120">Teams desktop client for Windows</span></span>
- <span data-ttu-id="d3ae3-121">Настольный клиент Teams для Mac</span><span class="sxs-lookup"><span data-stu-id="d3ae3-121">Teams desktop client for Mac</span></span>

## <a name="configure-dynamic-emergency-calling"></a><span data-ttu-id="d3ae3-122">Настройка динамического вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="d3ae3-122">Configure dynamic emergency calling</span></span>

<span data-ttu-id="d3ae3-123">Чтобы настроить динамическую функцию вызова экстренной помощи, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-123">To configure dynamic emergency calling, you need to perform the following tasks:</span></span>

- [<span data-ttu-id="d3ae3-124">Настройка адресов для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="d3ae3-124">Configure emergency addresses</span></span>](#configure-emergency-addresses)
- [<span data-ttu-id="d3ae3-125">Настройка параметров сети</span><span class="sxs-lookup"><span data-stu-id="d3ae3-125">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="d3ae3-126">Настройка службы сведений о расположении</span><span class="sxs-lookup"><span data-stu-id="d3ae3-126">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="d3ae3-127">Настройка политик экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="d3ae3-127">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="d3ae3-128">Включение пользователей и сайтов</span><span class="sxs-lookup"><span data-stu-id="d3ae3-128">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="d3ae3-129">Проверка вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="d3ae3-129">Test emergency calling</span></span>](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a><span data-ttu-id="d3ae3-130">Настройка адресов для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="d3ae3-130">Configure emergency addresses</span></span>

<span data-ttu-id="d3ae3-131">Для поддержки автоматической маршрутизации в США необходимо полностью настроить административный адрес, который является частью местоположений для экстренных случаев, которые назначены сетевым идентификаторам, и включить в него соответствующие географических коды.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-131">To support automated routing within the United States, you must fully configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="d3ae3-132">(Адреса для экстренного реагирования без географических кодов нельзя назначить сетевым идентификаторам, которые необходимы для динамических местоположений.)</span><span class="sxs-lookup"><span data-stu-id="d3ae3-132">(Emergency addresses without geo-codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

- <span data-ttu-id="d3ae3-133">Если вы ввели адрес для экстренного реагирования через центр администрирования Microsoft Teams, коды Geo автоматически включаются, если найдено соответствие.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-133">If you enter an emergency address via the Microsoft Teams admin center, the geo codes are automatically included if a match is found.</span></span>

- <span data-ttu-id="d3ae3-134">Если совпадение не найдено автоматически, вы сможете вручную создать адрес для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-134">If a match is not automatically found, you will have the opportunity to manually create an emergency address.</span></span>  

<span data-ttu-id="d3ae3-135">Это означает, что если для вызова экстренной помощи настроен адрес для экстренного реагирования, необходимо повторно создать тот же адрес для включения в него географических кодов.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-135">This means that if an existing emergency address is configured for emergency calling, the same address needs to be re-created to include the geo codes.</span></span>  <span data-ttu-id="d3ae3-136">Для различения двух адресов следует добавить другое описание.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-136">To distinguish between the two addresses, you should include a different description.</span></span> <span data-ttu-id="d3ae3-137">Новый адрес для экстренного реагирования может назначаться пользователям, у которых есть старый адрес.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-137">The new emergency address can be assigned to the users who have the old address.</span></span> <span data-ttu-id="d3ae3-138">При полной миграции старый адрес может быть удален.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-138">When fully migrated, the old address can be deleted.</span></span> 

<span data-ttu-id="d3ae3-139">Дополнительные сведения о настройке адресов для экстренного реагирования можно найти в статье [что такое места для экстренного реагирования, места и маршрутизация звонков](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="d3ae3-139">For more information about configuring emergency addresses, see [What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>

### <a name="configure-network-settings"></a><span data-ttu-id="d3ae3-140">Настройка параметров сети</span><span class="sxs-lookup"><span data-stu-id="d3ae3-140">Configure network settings</span></span>

<span data-ttu-id="d3ae3-141">Вам необходимо настроить параметры сети, чтобы динамически получать место для экстренного реагирования, используемое для маршрутизации экстренных вызовов, и (необязательно) для предоставления динамической конфигурации уведомлений на рабочем месте.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-141">You need to configure network settings to dynamically obtain an emergency location used for routing emergency calls and, optionally, to provide dynamic configuration of security desk notifications.</span></span> <span data-ttu-id="d3ae3-142">При вызове функции для экстренной помощи будет определяться, какие сетевые параметры необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-142">The emergency calling experience desired will dictate which network settings need to be configured.</span></span> 

<span data-ttu-id="d3ae3-143">Учитывайте следующие определения:</span><span class="sxs-lookup"><span data-stu-id="d3ae3-143">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="d3ae3-144">Доверенный IP-адрес: содержит коллекцию внешних адресов Интернета в корпоративной сети и используется для определения того, входит ли конечная точка пользователя в корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-144">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="d3ae3-145">Динамические расположения будут включены только в том случае, если внешний IP-адрес пользователя соответствует IP-адресу в доверенной семействе IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-145">Dynamic locations will only be enabled if the user’s external IP matches an IP in the Trusted IP collection.</span></span>  <span data-ttu-id="d3ae3-146">Соответствие можно получить по IP-адресам IPv4 или IPv6 и зависит от формата пакета IP, отправляемого в параметры сети.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-146">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>

- <span data-ttu-id="d3ae3-147">Область сети содержит коллекцию сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-147">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="d3ae3-148">Сетевой сайт — это расположение, в котором Организация имеет физическую стоимость, например Office, набор зданий или кампус.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-148">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="d3ae3-149">Эти сайты определяются как набор IP-подсетей.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-149">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="d3ae3-150">Сетевая подсеть должна быть связана с определенным сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-150">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="d3ae3-151">Расположение клиента определяется на основе сетевой подсети и связанного сайта сети.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-151">A client's location is determined based on the network subnet and the associated network site.</span></span>  


<span data-ttu-id="d3ae3-152">Для пользователей плана звонков:</span><span class="sxs-lookup"><span data-stu-id="d3ae3-152">For Calling Plan users:</span></span>

- <span data-ttu-id="d3ae3-153">Если требуется динамическая настройка уведомления службы безопасности, необходимо настроить оба доверенных IP-адреса и сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-153">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="d3ae3-154">Если требуются только динамические расположения, необходимо настроить только доверенные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-154">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="d3ae3-155">Если ни один из них не требуется, Настройка параметров сети не требуется.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-155">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="d3ae3-156">Дополнительные сведения можно найти в статье [Настройка параметров сети для маршрутизации на основе местоположения](location-based-routing-configure-network-settings.md), в которой описано, как настроить параметры сети.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-156">For more information, see [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md), which describes how to configure network settings.</span></span> <span data-ttu-id="d3ae3-157">(Сведения, приведенные в этой статье, относятся к тарифным планам и прямой маршрутизации.)</span><span class="sxs-lookup"><span data-stu-id="d3ae3-157">(The information in this article applies to both Calling Plans and Direct Routing.)</span></span>


### <a name="configure-location-information-service"></a><span data-ttu-id="d3ae3-158">Настройка службы сведений о расположении</span><span class="sxs-lookup"><span data-stu-id="d3ae3-158">Configure Location Information Service</span></span>

<span data-ttu-id="d3ae3-159">Клиент Teams получает адреса для экстренного реагирования из расположения для экстренных случаев, связанных с разными сетевыми идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-159">A Teams client obtains emergency addresses from the emergency locations associated with different network identifiers.</span></span>  <span data-ttu-id="d3ae3-160">Поддерживаются как подсети, так и точки беспроводного доступа.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-160">Subnets and Wireless Access Points are both supported.</span></span> <span data-ttu-id="d3ae3-161">(Ожидается поддержка коммутатора или порта Ethernet.)</span><span class="sxs-lookup"><span data-stu-id="d3ae3-161">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="d3ae3-162">Чтобы настроить службу сведений о расположении (LIS) с сетевыми идентификаторами и адресами экстренной помощи, выполните указанные ниже командлеты.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-162">To configure the Location Information Service (LIS) with network identifiers and emergency locations, use the following cmdlets:</span></span>

- <span data-ttu-id="d3ae3-163">Get, Set, Remove-Ксонлинелиспорт</span><span class="sxs-lookup"><span data-stu-id="d3ae3-163">Get, Set, Remove -CsOnlineLisPort</span></span>
- <span data-ttu-id="d3ae3-164">Get, Set, Remove-Ксонлинелиссвитч</span><span class="sxs-lookup"><span data-stu-id="d3ae3-164">Get, Set, Remove -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="d3ae3-165">Get, Set, Remove-Ксонлинелиссубнет</span><span class="sxs-lookup"><span data-stu-id="d3ae3-165">Get, Set, Remove -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="d3ae3-166">Get, Set, Remove-Ксонлинелисвирелессакцесспоинт</span><span class="sxs-lookup"><span data-stu-id="d3ae3-166">Get, Set, Remove -CsOnlineLisWirelessAccessPoint</span></span> 

> [!Important] 
> <span data-ttu-id="d3ae3-167">Если подсети используются как часть сетевых сайтов, они должны быть переопределены в службе сведений о расположении для отображения динамических расположений.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-167">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


### <a name="configure-emergency-policies"></a><span data-ttu-id="d3ae3-168">Настройка политик экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="d3ae3-168">Configure emergency policies</span></span>

<span data-ttu-id="d3ae3-169">Политики для экстренной помощи определяют, что происходит, когда пользователь в вашей организации совершает вызов экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-169">Emergency policies determine what happens when a user in your organization makes an emergency call.</span></span>  <span data-ttu-id="d3ae3-170">Вы можете настроить пользователей, которые должны уведомлять и как они уведомляются, когда пользователь обращается к службам экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-170">You can set who to notify and how they are notified when a user calls emergency services.</span></span> <span data-ttu-id="d3ae3-171">Например, вы можете настроить параметры политики, чтобы автоматически уведомлять службу безопасности Организации и принимать их на звонки в экстренных случаях.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-171">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>

<span data-ttu-id="d3ae3-172">Вы управляете политиками для экстренного реагирования с помощью командлетов политики New-, Set-и Grant-Кстеамсемерженцикаллинг.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-172">You manage emergency policies by using the New-, Set- and Grant-CsTeamsEmergencyCalling Policy cmdlets.</span></span>  <span data-ttu-id="d3ae3-173">Дополнительные сведения можно найти [в разделе Управление политиками вызова экстренной помощи в Teams](manage-emergency-calling-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d3ae3-173">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>


### <a name="enable-users-and-sites"></a><span data-ttu-id="d3ae3-174">Включение пользователей и сайтов</span><span class="sxs-lookup"><span data-stu-id="d3ae3-174">Enable users and sites</span></span>

<span data-ttu-id="d3ae3-175">Когда пользователи плана звонков автоматически включаются для вызова экстренной помощи, необходимо включить поддержку уведомлений для пользователей на рабочем месте, настроив политику вызовов экстренного управления, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d3ae3-175">While Calling Plan users are automatically enabled for emergency calling, you must enable users for security desk notification by configuring the emergency calling policy as shown in the following example:</span></span>


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="d3ae3-176">Вы также можете назначить политику вызова экстренной помощи сетевому сайту, как показано в следующем примере, в котором назначается политика "политика для экстренных вызовов Contoso 1" для сайта 1:</span><span class="sxs-lookup"><span data-stu-id="d3ae3-176">You can also assign the emergency calling policy to a network site as shown in the following example, which assigns a policy called "Contoso Emergency Calling Policy 1" to Site 1:</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="d3ae3-177">Если вы назначили для сайта сети и пользователя политику вызова экстренной помощи, а если этот пользователь находится на сайте сети, политика, назначенная сетевому сайту, переопределяет политику, назначенную пользователю.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-177">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


### <a name="test-emergency-calling"></a><span data-ttu-id="d3ae3-178">Проверка вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="d3ae3-178">Test emergency calling</span></span>

<span data-ttu-id="d3ae3-179">Для проверки вызова экстренной помощи в США используйте предварительно определенный тестовый номер для экстренного реагирования 933.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-179">To test emergency calling in the United States, use the predefined test emergency number 933.</span></span>  <span data-ttu-id="d3ae3-180">Этот номер перенаправляется на Bot, который затем отправляет номер телефона вызывающего абонента (идентификатор строки вызова), адрес для экстренного реагирования или место, а также указывает, будет ли этот звонок автоматически перенаправляться в ПСАП или на экране.</span><span class="sxs-lookup"><span data-stu-id="d3ae3-180">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call is automatically routed to the PSAP or screened first.</span></span>  