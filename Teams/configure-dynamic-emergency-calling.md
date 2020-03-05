---
title: Настройка динамических экстренных вызовов
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
f1.keywords:
- NOCSH
description: Настройка динамических экстренных вызовов
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b22c6cec20e42ac33b15c53a49477b36a35fbe9
ms.sourcegitcommit: 5fbb57c5f0692afcb8e65516c63b96814f51ca65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417594"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="46662-103">Планирование и настройка динамических экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="46662-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="46662-104">Динамическое обращение для экстренных вызовов в планах вызовов Microsoft и прямую маршрутизацию телефонной системы обеспечивает возможность настраивать и перенаправлять экстренные вызовы и уведомлять сотрудников системы безопасности в соответствии с текущим расположением клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="46662-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="46662-105">В соответствии с топологией сети, определяемой администратором клиента, клиент Teams предоставляет сведения о сетевом подключении в запросе к службе сведений о расположении (LIS).</span><span class="sxs-lookup"><span data-stu-id="46662-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span>  <span data-ttu-id="46662-106">Если найдено соответствие, LIS возвращает расположение для клиента.</span><span class="sxs-lookup"><span data-stu-id="46662-106">If there is a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="46662-107">Данные о расположении передаются обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="46662-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="46662-108">Клиент Teams включает данные о местоположении в ходе вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="46662-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="46662-109">Эти данные затем используются поставщиком услуг экстренной помощи, чтобы определить соответствующую точку ответа на общедоступную безопасность (ПСАП) и перенаправить вызов на этот ПСАП, что позволяет диспетчеру ПСАП получить расположение вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="46662-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="46662-110">Для динамической службы экстренной помощи должны произойти следующие события:</span><span class="sxs-lookup"><span data-stu-id="46662-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="46662-111">Сетевой администратор настроил сетевые параметры и местонахождение LIS для создания карты расположения сети и экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="46662-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="46662-112">Для прямой маршрутизации требуется дополнительная настройка маршрутизации для экстренных вызовов и, возможно, для подключения партнеров.</span><span class="sxs-lookup"><span data-stu-id="46662-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="46662-113">Администратор должен настроить подключение к поставщику службы экстренной маршрутизации (ЕРС) (США) **или** настроить контроллер границ сеанса (SBC) для приложения с идентификационным номером для экстренной помощи (Елин).</span><span class="sxs-lookup"><span data-stu-id="46662-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="46662-114">При запуске, периодически и при изменении сетевого соединения клиент Teams отправляет запрос на расположение, содержащий сведения о сетевом подключении, в параметры сети и LIS.</span><span class="sxs-lookup"><span data-stu-id="46662-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="46662-115">Если веб-сайт соответствует сетевым параметрам — в клиенте Teams будут возвращаться политики вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="46662-115">If there is a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="46662-116">(Дополнительные сведения о политиках см. в разделе [Настройка политик экстренного](#configure-emergency-policies)реагирования).</span><span class="sxs-lookup"><span data-stu-id="46662-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="46662-117">Если обнаружено совпадение LIS — место в экстренном случае, в которое подключен клиент Teams, будет возвращено клиенту Teams из сетевого элемента.</span><span class="sxs-lookup"><span data-stu-id="46662-117">If there is an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span>

3. <span data-ttu-id="46662-118">Когда клиент Teams осуществляет вызов экстренной помощи, расположение для экстренного реагирования передается в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="46662-118">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="46662-119">Для прямой маршрутизации администратор должен настроить SBC для отправки экстренных вызовов поставщику ЕРС или настроить приложение SBC Елин.</span><span class="sxs-lookup"><span data-stu-id="46662-119">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="46662-120">Эта статья содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="46662-120">This article contains the following sections.</span></span>

- [<span data-ttu-id="46662-121">Настройка адресов для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="46662-121">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="46662-122">Настройка параметров сети</span><span class="sxs-lookup"><span data-stu-id="46662-122">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="46662-123">Настройка службы сведений о расположении</span><span class="sxs-lookup"><span data-stu-id="46662-123">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="46662-124">Настройка политик экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="46662-124">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="46662-125">Включение пользователей и сайтов</span><span class="sxs-lookup"><span data-stu-id="46662-125">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="46662-126">Проверка вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="46662-126">Test emergency calling</span></span>](#test-emergency-calling)


<span data-ttu-id="46662-127">Возможность автоматической маршрутизации для соответствующей точки ответа на общедоступную безопасность (ПСАП) зависит от страны использования пользователя Teams.</span><span class="sxs-lookup"><span data-stu-id="46662-127">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span> 

<span data-ttu-id="46662-128">Дополнительные сведения об экстренных звонках, в том числе сведения об экстренных адресах и маршрутах экстренных вызовов, информация для стран, а также сведения о параметрах сети и топологии сети — описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="46662-128">For more information about emergency calling--including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology--see the following:</span></span>

- [<span data-ttu-id="46662-129">Управление вызовом экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="46662-129">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="46662-130">Управление параметрами сети для функций голосовой связи в облаке</span><span class="sxs-lookup"><span data-stu-id="46662-130">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="46662-131">Управление топологией сети для функций голосовой связи в облаке</span><span class="sxs-lookup"><span data-stu-id="46662-131">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)


## <a name="supported-clients"></a><span data-ttu-id="46662-132">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="46662-132">Supported clients</span></span>

<span data-ttu-id="46662-133">В настоящее время поддерживаются следующие клиенты.</span><span class="sxs-lookup"><span data-stu-id="46662-133">The following clients are currently supported.</span></span>  <span data-ttu-id="46662-134">Регулярно проверяйте, есть ли в этом списке обновленные сведения.</span><span class="sxs-lookup"><span data-stu-id="46662-134">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="46662-135">Настольный клиент Teams для Microsoft Windows</span><span class="sxs-lookup"><span data-stu-id="46662-135">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="46662-136">Настольный клиент Teams для Apple macOS</span><span class="sxs-lookup"><span data-stu-id="46662-136">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="46662-137">Клиент Teams Mobile для клиента Apple iOS версии 1.0.92.2019121004 и App Store версии 1.0.92 и выше</span><span class="sxs-lookup"><span data-stu-id="46662-137">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="46662-138">Клиент Teams Mobile для Android Client и Google Play Store версии 1416/1.0.0.2019121201 и выше</span><span class="sxs-lookup"><span data-stu-id="46662-138">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="46662-139">Teams Phone 1449/1.0.94.2019110802 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="46662-139">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="46662-140">Назначение адресов для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="46662-140">Assign emergency addresses</span></span>

<span data-ttu-id="46662-141">Вы можете назначать адреса для экстренного реагирования обоим тарифам плана звонков и сетевым идентификаторам, которые необходимы для динамического получения местоположения.</span><span class="sxs-lookup"><span data-stu-id="46662-141">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="46662-142">(Поддерживаются подсети и ТД AP; ожидание поддержки коммутатора/порта Ethernet.)</span><span class="sxs-lookup"><span data-stu-id="46662-142">(Subnet and WiFi AP are supported; support for Ethernet switch/port is pending).</span></span>

<span data-ttu-id="46662-143">Чтобы обеспечить автоматическую маршрутизацию экстренных вызовов в США, необходимо убедиться в том, что местоположения для экстренного реагирования, назначенные сетевым идентификаторам, включают в себя соответствующие географических коды.</span><span class="sxs-lookup"><span data-stu-id="46662-143">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="46662-144">(Адреса для экстренного реагирования без географических кодов нельзя назначить сетевым идентификаторам, которые необходимы для динамических местоположений.)</span><span class="sxs-lookup"><span data-stu-id="46662-144">(Emergency addresses without geo codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="46662-145">Карты Azure используются для служб, основанных на расположении.</span><span class="sxs-lookup"><span data-stu-id="46662-145">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="46662-146">Когда вы вводите адрес для экстренного реагирования с помощью центра администрирования Microsoft Teams, Teams проверяет карты Azure для этого адреса.</span><span class="sxs-lookup"><span data-stu-id="46662-146">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="46662-147">Если совпадение найдено, коды Geo включаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="46662-147">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="46662-148">Если совпадение не найдено, вы сможете вручную создать адрес для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="46662-148">If a match is not found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="46662-149">Для этого можно использовать функцию перетаскивания PIN-кода.</span><span class="sxs-lookup"><span data-stu-id="46662-149">You can use the PIN drop feature to do this.</span></span>   

<span data-ttu-id="46662-150">Это означает, что если расположение для экстренного реагирования, созданное для назначения пользователям плана звонков, предназначено для динамического местоположения, необходимо повторно создать тот же адрес для включения в него географических кодов.</span><span class="sxs-lookup"><span data-stu-id="46662-150">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="46662-151">Для различения двух местоположений следует добавить другое описание.</span><span class="sxs-lookup"><span data-stu-id="46662-151">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="46662-152">Новое расположение для экстренного реагирования может назначаться пользователям, у которых есть прежнее расположение.</span><span class="sxs-lookup"><span data-stu-id="46662-152">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="46662-153">При полной миграции прежнее расположение может быть удалено.</span><span class="sxs-lookup"><span data-stu-id="46662-153">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="46662-154">Дополнительные сведения о настройке адресов для экстренного реагирования можно найти в разделе [Добавление расположения для экстренных случаев для Организации](add-change-remove-emergency-location-organization.md) и [Назначение места для экстренного реагирования для пользователя](assign-change-emergency-location-user.md).</span><span class="sxs-lookup"><span data-stu-id="46662-154">For more information about configuring emergency addresses, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for your user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="46662-155">Настройка параметров сети</span><span class="sxs-lookup"><span data-stu-id="46662-155">Configure network settings</span></span>

<span data-ttu-id="46662-156">Параметры сети используются для определения расположения клиента Teams и динамического получения политик вызова экстренной помощи и расположения для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="46662-156">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="46662-157">Вы можете настроить параметры сети в зависимости от того, как ваша организация предхочет вызвать экстренную функцию.</span><span class="sxs-lookup"><span data-stu-id="46662-157">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="46662-158">Сетевые параметры включают сайты, содержащие набор подсетей — они используются исключительно для назначения динамической политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="46662-158">Network settings include sites that include a collection of subnets--these are used exclusively for dynamic policy assignment to users.</span></span>  <span data-ttu-id="46662-159">Например, политика Теамсемерженцикаллинг и Теамсемерженцикаллраутинг могут быть назначены "сайту Redmond", чтобы любой пользователь, который перемещается из дома или другого местоположения Майкрософт, настроил номера экстренной службы, маршрутизацию и службу безопасности. конкретно для Редмонде.</span><span class="sxs-lookup"><span data-stu-id="46662-159">For example, a TeamsEmergencyCalling Policy and TeamsEmergencyCallRouting Policy might be assigned to the “Redmond site” so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="46662-160">Подсеть также может быть определена в LIS и может быть связана с местом для экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="46662-160">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  

<span data-ttu-id="46662-161">Учитывайте следующие определения:</span><span class="sxs-lookup"><span data-stu-id="46662-161">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="46662-162">Доверенный IP-адрес: содержит коллекцию внешних адресов Интернета в корпоративной сети и используется для определения того, входит ли конечная точка пользователя в корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="46662-162">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="46662-163">Попытка получить динамическую политику или расположение будет выполнена только в том случае, если внешний IP-адрес пользователя соответствует IP в доверенном IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="46662-163">An attempt to obtain a dynamic policy or location will only be made if the user’s external IP matches an IP in the Trusted IP address.</span></span> <span data-ttu-id="46662-164">Соответствие можно получить по IP-адресам IPv4 или IPv6 и зависит от формата пакета IP, отправляемого в параметры сети.</span><span class="sxs-lookup"><span data-stu-id="46662-164">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="46662-165">(Если у общедоступного IP-адреса есть и IPv4, и IPv6, вам нужно добавить как доверенные IP-адреса.)</span><span class="sxs-lookup"><span data-stu-id="46662-165">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="46662-166">Область сети содержит коллекцию сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="46662-166">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="46662-167">Сетевой сайт — это расположение, в котором Организация имеет физическую стоимость, например Office, набор зданий или кампус.</span><span class="sxs-lookup"><span data-stu-id="46662-167">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="46662-168">Эти сайты определяются как набор IP-подсетей.</span><span class="sxs-lookup"><span data-stu-id="46662-168">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="46662-169">Сетевая подсеть должна быть связана с определенным сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="46662-169">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="46662-170">Расположение клиента определяется на основе сетевой подсети и связанного сайта сети.</span><span class="sxs-lookup"><span data-stu-id="46662-170">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="46662-171">Дополнительные сведения можно найти в разделе [Параметры сети для функций голосовой связи в облаке](cloud-voice-network-settings.md) и [управлять топологией сети для функций голосовой связи в облаке](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="46662-171">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md) and [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="46662-172">Обратите внимание, что для некоторых изменений сетевых параметров (например, нового адреса, идентификатора сети и т. д.) может потребоваться некоторое время (в течение нескольких часов) для распространения и обеспечения доступности для клиентов Teams.</span><span class="sxs-lookup"><span data-stu-id="46662-172">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="46662-173">**Для пользователей плана звонков:**</span><span class="sxs-lookup"><span data-stu-id="46662-173">**For Calling Plan users:**</span></span>

- <span data-ttu-id="46662-174">Если требуется динамическая настройка уведомления службы безопасности, необходимо настроить оба доверенных IP-адреса и сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="46662-174">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="46662-175">Если требуются только динамические расположения, необходимо настроить только доверенные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="46662-175">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="46662-176">Если ни один из них не требуется, Настройка параметров сети не требуется.</span><span class="sxs-lookup"><span data-stu-id="46662-176">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="46662-177">**Для прямого направления пользователей выполните указанные ниже действия.**</span><span class="sxs-lookup"><span data-stu-id="46662-177">**For Direct Routing users:**</span></span>

- <span data-ttu-id="46662-178">Если требуется динамическое включение вызова экстренной или динамической конфигурации уведомления службы безопасности, необходимо настроить оба доверенных IP-адреса и сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="46662-178">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="46662-179">Если требуются только динамические расположения, необходимо настроить только доверенные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="46662-179">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span>

- <span data-ttu-id="46662-180">Если ни один из них не требуется, Настройка параметров сети не требуется.</span><span class="sxs-lookup"><span data-stu-id="46662-180">If neither are required, then configuration of network settings is not required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="46662-181">Настройка службы сведений о расположении</span><span class="sxs-lookup"><span data-stu-id="46662-181">Configure Location Information Service</span></span>

<span data-ttu-id="46662-182">Клиент Teams получает адреса для экстренного реагирования из местоположений, связанных с разными сетевыми идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="46662-182">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="46662-183">Поддерживаются как подсети, так и точки доступа к беспроводной сети (Вапс).</span><span class="sxs-lookup"><span data-stu-id="46662-183">Both subnets and Wireless Access Points (WAPs) are supported.</span></span> <span data-ttu-id="46662-184">(Ожидается поддержка коммутатора или порта Ethernet.)</span><span class="sxs-lookup"><span data-stu-id="46662-184">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="46662-185">Чтобы клиент получил расположение, необходимо заполнить службу сведений о расположении (LIS) с сетевыми идентификаторами и адресами экстренной помощи, используя следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="46662-185">For a client to obtain a location, you must populate the Location Information Service (LIS) with network identifiers and emergency locations by using the following cmdlets:</span></span>  


- <span data-ttu-id="46662-186">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -ксонлинелиспорт</span><span class="sxs-lookup"><span data-stu-id="46662-186">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="46662-187">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -ксонлинелиссвитч</span><span class="sxs-lookup"><span data-stu-id="46662-187">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="46662-188">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -ксонлинелиссубнет</span><span class="sxs-lookup"><span data-stu-id="46662-188">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="46662-189">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps
) -ксонлинелисвирелессакцесспоинт</span><span class="sxs-lookup"><span data-stu-id="46662-189">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps
) -CsOnlineLisWirelessAccessPoint</span></span> 


>[!Important] 
><span data-ttu-id="46662-190">Если подсети используются как часть сетевых сайтов, они должны быть переопределены в службе сведений о расположении для отображения динамических расположений.</span><span class="sxs-lookup"><span data-stu-id="46662-190">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


## <a name="configure-emergency-policies"></a><span data-ttu-id="46662-191">Настройка политик экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="46662-191">Configure emergency policies</span></span>

<span data-ttu-id="46662-192">Для настройки вызова экстренной помощи можно использовать следующие политики:</span><span class="sxs-lookup"><span data-stu-id="46662-192">You use the following policies to configure emergency calling:</span></span>

- <span data-ttu-id="46662-193">**Теамсемерженцикаллраутингполици** — относится только к прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="46662-193">**TeamsEmergencyCallRoutingPolicy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="46662-194">Этот параметр позволяет настроить номера для экстренного реагирования, маску для каждого номера, а также маршрут PSTN на номер.</span><span class="sxs-lookup"><span data-stu-id="46662-194">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="46662-195">Вы можете назначить эту политику пользователям, сетевым сайтам или обоим.</span><span class="sxs-lookup"><span data-stu-id="46662-195">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="46662-196">(Планы звонков. клиенты Teams автоматически включаются для вызова экстренной помощи с номерами экстренного реагирования на основе места использования Office 365.)  Вы управляете этой политикой с помощью командлетов New-, Set-и Grant-Кстеамсемерженцикаллраутинг.</span><span class="sxs-lookup"><span data-stu-id="46662-196">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Office 365 usage location.)  You manage this policy by using the New-, Set-, and Grant-CsTeamsEmergencyCallRouting cmdlets.</span></span> 

- <span data-ttu-id="46662-197">**Теамсемерженцикаллингполици** — относится к плану звонков и прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="46662-197">**TeamsEmergencyCallingPolicy** - Applies to Calling Plan and Direct Routing.</span></span> <span data-ttu-id="46662-198">Этот параметр политики позволяет настроить уведомления службы безопасности при проведении экстренного звонка.</span><span class="sxs-lookup"><span data-stu-id="46662-198">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="46662-199">Вы можете настроить пользователей, которые должны уведомлять и как они уведомлены.</span><span class="sxs-lookup"><span data-stu-id="46662-199">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="46662-200">Например, чтобы автоматически уведомлять службу безопасности своей организации и послушать ее на экстренных звонках.</span><span class="sxs-lookup"><span data-stu-id="46662-200">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="46662-201">Эта политика может быть назначена пользователям либо сетевым сайтам или обоим.</span><span class="sxs-lookup"><span data-stu-id="46662-201">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="46662-202">Вы управляете этой политикой с помощью командлетов New-, Set-и Grant-Кстеамсемерженцикаллингполици.</span><span class="sxs-lookup"><span data-stu-id="46662-202">You manage this policy by using the New-, Set- and Grant-CsTeamsEmergencyCallingPolicy  cmdlets.</span></span> 

<span data-ttu-id="46662-203">Дополнительные сведения можно найти [в разделе Управление политиками вызова экстренной помощи в Teams](manage-emergency-calling-policies.md) и [Управление политиками маршрутизации вызовов экстренной помощи в прямом маршруте](manage-emergency-call-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="46662-203">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md) and [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>


## <a name="enable-users-and-sites"></a><span data-ttu-id="46662-204">Включение пользователей и сайтов</span><span class="sxs-lookup"><span data-stu-id="46662-204">Enable users and sites</span></span>

<span data-ttu-id="46662-205">Вы можете назначать политики **теамсемерженцикаллинг** и **теамсемерженцикаллраутинг** для пользователей и сайтов.</span><span class="sxs-lookup"><span data-stu-id="46662-205">You can assign **TeamsEmergencyCalling** and **TeamsEmergencyCallROuting** policies to users and to sites.</span></span>  

<span data-ttu-id="46662-206">Политика Теамсемерженцикаллраутинг применяется только для прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="46662-206">The TeamsEmergencyCallRouting policy applies to Direct Routing only.</span></span> <span data-ttu-id="46662-207">(Несмотря на то, что эту политику можно назначить пользователю абонентского плана, политика не будет оказывать никакого воздействия.)</span><span class="sxs-lookup"><span data-stu-id="46662-207">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="46662-208">Например, чтобы включить определенного пользователя в уведомление на службу безопасности, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46662-208">For example, to enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="46662-209">Чтобы назначить политику "Contoso срочного вызова 1" для сайта 1, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46662-209">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="46662-210">Чтобы включить для вызова экстренной помощи определенного пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46662-210">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="46662-211">Чтобы назначить политику "Маршрутизация экстренных вызовов в Нью-Йорке" для сайта 1, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46662-211">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="46662-212">Если вы назначили для сайта сети и пользователя политику вызова экстренной помощи, а если этот пользователь находится на сайте сети, политика, назначенная сетевому сайту, переопределяет политику, назначенную пользователю.</span><span class="sxs-lookup"><span data-stu-id="46662-212">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


## <a name="test-emergency-calling"></a><span data-ttu-id="46662-213">Проверка вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="46662-213">Test emergency calling</span></span>

<span data-ttu-id="46662-214">Некоторые поставщики услуг для экстренной маршрутизации (Ерспс) в США предлагают Bot-каналы для проверки звонков.</span><span class="sxs-lookup"><span data-stu-id="46662-214">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="46662-215">В **плане звонков пользователи в США** могут использовать предварительно определенный тестовый 933 номер для экстренного реагирования, чтобы проверить конфигурацию для вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="46662-215">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="46662-216">Этот номер перенаправляется на Bot, который затем отправляет номер телефона вызывающего абонента (идентификатор строки вызова), адрес для экстренного реагирования или место, а также будет ли этот звонок автоматически перенаправлен на ПСАП или на экране.</span><span class="sxs-lookup"><span data-stu-id="46662-216">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="46662-217">**Прямые маршруты клиентов в США** должны координироваться в соответствии с их ерсп для тестовых служб.</span><span class="sxs-lookup"><span data-stu-id="46662-217">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="46662-218">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="46662-218">Related topics</span></span>

- [<span data-ttu-id="46662-219">Управление вызовом экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="46662-219">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="46662-220">Управление политиками экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="46662-220">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="46662-221">Управление политиками маршрутизации для экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="46662-221">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="46662-222">Добавление, изменение и удаление расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="46662-222">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="46662-223">Назначение или изменение местоположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="46662-223">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="46662-224">Параметры сети для функций голосовой связи в облаке</span><span class="sxs-lookup"><span data-stu-id="46662-224">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="46662-225">Управление топологией сети для функций голосовой связи в облаке</span><span class="sxs-lookup"><span data-stu-id="46662-225">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)
